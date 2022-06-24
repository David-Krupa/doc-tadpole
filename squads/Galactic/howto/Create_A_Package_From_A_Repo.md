# How to Create a Package From a GitLab Repository 📦

- [How to Create a Package From a GitLab Repository 📦](#how-to-create-a-package-from-a-gitlab-repository-)
  - [Purpose 🧠](#purpose-)
  - [Background 🖼️](#background-️)
  - [TLDR ⏩](#tldr-)
  - [Summary](#summary)
  - [Implementation](#implementation)
    - [Create Gitlab project and repository 🆕](#create-gitlab-project-and-repository-)
    - [Scaffold the Initial Vite Project 🚀](#scaffold-the-initial-vite-project-)
      - [Structure and Configuration 🗂 🛠](#structure-and-configuration--)
    - [Build the Library 🏗️](#build-the-library-️)
    - [Publish the Build 📚](#publish-the-build-)
    - [Create a GitLab Access Token for the Library 🔐](#create-a-gitlab-access-token-for-the-library-)
    - [Create a Pipeline for the Library 🚌](#create-a-pipeline-for-the-library-)
  - [Conclusion](#conclusion)
  - [References](#references)

## Purpose 🧠

This document details the process of creating a package from a GitLab repository. Doing this makes the code from the repository available to any project with access to the repository.

This means that we can build a React component, utility library, etc. that is accessible to any BrainGu React project.

The created package is created using [vite.js](https://vitejs.dev) which builds Common JS and tree-shakable ES packages. Additionally, the the created package includes Typescript definition files though the use of [rollup.js](https://rollupjs.org/guide/en/).

## Background 🖼️

BrainGu JavaScript projects need a way to share code. Most JS projects use the Node Package Manager (npm) to pull code from the Node package repository. Creating packages directly from the code in Gitlab repositories avoids the need for using npm.

## TLDR ⏩

- First, create your project repository.
- Next, [Create GitLab Access Token for the library](#create-a-gitlab-access-token-for-the-library-🔐)
- Finally, follow the instructions in the [widow-components](https://code.il2.dso.mil/platform-one/products/widow/widow-components) README.md file. That project has automation for the remaining steps that are listed below. Go there if you just want to get started making your component. Read on if you want more details.

## Summary

This document describes the following process to make a repository available for import using `package.json`

- [How to Create a Package From a GitLab Repository 📦](#how-to-create-a-package-from-a-gitlab-repository-)
  - [Purpose 🧠](#purpose-)
  - [Background 🖼️](#background-️)
  - [TLDR ⏩](#tldr-)
  - [Summary](#summary)
  - [Implementation](#implementation)
    - [Create Gitlab project and repository 🆕](#create-gitlab-project-and-repository-)
    - [Scaffold the Initial Vite Project 🚀](#scaffold-the-initial-vite-project-)
      - [Structure and Configuration 🗂 🛠](#structure-and-configuration--)
    - [Build the Library 🏗️](#build-the-library-️)
    - [Publish the Build 📚](#publish-the-build-)
    - [Create a GitLab Access Token for the Library 🔐](#create-a-gitlab-access-token-for-the-library-)
    - [Create a Pipeline for the Library 🚌](#create-a-pipeline-for-the-library-)
  - [Conclusion](#conclusion)
  - [References](#references)

## Implementation

### Create Gitlab project and repository 🆕

Determine if your code is appropriate for an existing repository such as a common component or if it needs a new repository. If it needs a new repository contact Matt Shaver to get one created.

### Scaffold the Initial Vite Project 🚀

We will use vite.js to create the initial project files and structure. Vite includes several project templates include React and JavaScript Typescript projects. ["What is Vite.js" with Scott Tolinski](https://www.youtube.com/watch?v=ZlmFUpOT07U)

- For a React component, this should be done using vite.js to create a new React Typescript project.
  - Alternatively, you can clone the `widow-components` [repository](https://code.il2.dso.mil/platform-one/products/widow/widow-components/-/tree/master)
- For plain Typescript projects you can also use vite.js to create a "vanilla-ts" Typescript project.

After running Vite, run `npm install` to add any required dependencies. You can then run `npm run dev` to start the Vite web server and navigate to the address Vite indicates to run see the new project.

#### Structure and Configuration 🗂 🛠

- An `index.ts` file will be the root export for this library. It should export anything your want exposed to project that imports it. Additionally, each folder inside of the `src` directory should have an `index.ts` file that exports code specific to that folder.

- Add the following lines to the `scripts` section of `package.json`. These are the same lines used in the `widow-components` package.json:

```
"build": "jest && tsc --noEmit && vite build",
"build:quick": "tsc --noEmit && vite build",
"build:ci": "tsc --noEmit && vite build",
```

- Additionally, add the following to the root of your `package.json` object to expose the correct files to the project that imports this library.

```
"files": [
    "dist"
  ],
  "main": "./dist/[PROJECT NAME].umd.js",
  "module": "./dist/[PROJECT NAME].es.js",
  "exports": {
    ".": {
      "import": "./dist/[PROJECT NAME].es.js",
      "require": "./dist/[PROJECT NAME].umd.js"
    }
  },
  "types": "dist/index.d.ts",
```

- Also, copy the necessary `dependencies` and `devDependencies`, and the entire `jest` section from `package.json`
- Copy the following files from the `widow-components` repository to the root of your new project in order to complete the configuration
  - vite.config.ts
  - Vite incorporates [rollup.js](https://rollupjs.org/guide/en/) for a lot of internal tooling. This [Github issue thread](https://github.com/rollup/rollup/issues/1169) provides a good discussion of `external` vs `global` in the configuration
    - Update the the `external` section to include npm imports that should not be packaged with this library
    - Update the `globals` section
  - tsconfig.json - Remove any lines related to React unless your library uses React
  - babel.rc - Remove any code related to React unless your library uses React
  - `.eslintignore`, `eslintrc.json`, `.gitignore`, `.prettierrc`
- Run `npm install`

### Build the Library 🏗️

Run `npm build`

This will run tests and Typescript linting on the project. Exportable modules are build if the code passes both of those tests.

You can also run `npm build:quick` to bypass the tests.

### Publish the Build 📚

Push your code to the Gitlab repository for this project.

### Create a GitLab Access Token for the Library 🔐

A Gitlab "Personal Access Token" is required in order to give other projects access to this project.

Follow [these steps](https://stackoverflow.com/a/50314604/17115044) to create a deploy token for the project.

The user name and token created during this process will be part of the URL other projects will use in their package.json to import this library.

### Create a Pipeline for the Library 🚌

Submit a P1 ["New Pipeline Request"](https://jira.il2.dso.mil/servicedesk/customer/portal/73/group/110) ticket to create a "Package Pipeline" for the new library's repository.

This type of pipeline is described in the "Package Pipeline Flow" section of [this document](https://confluence.il2.dso.mil/display/P1MDOHD/HowTo+-+GitLab+-+Pipeline+Basics)

Include the statement "The command "npm run build:ci" in package.json needs to added before the "before_script" in order to build the package" in the body of the ticket. This will make the pipeline do a TypeScript check and run the Vite build tool.

Once the pipeline is created, you'll have to do the usual care an maintenance actions to keep the pipeline green.

## Testing the Package 🧪

At some point, you'll likely want to test the package in an actual applicaton. Here is one basic testing pattern:

1. Build the project using `npm run build`.  This will create a build in the `dist` folder.
2. Create a `.tgz` file of the package the files in the `dist` folder by running `npm run pack`.  This will create a`.tgz` file in the package project's root folder.
3. Copy the `.tgz` file to the target project's root folder.
4. Use the method shown in step 5 of this readme ["Using a Tarball File"](https://github.com/braingu/doc-tadpole/blob/master/squads/Galactic/howto/use-js-package-from-p1-gitlab.md#method-2---using-a-tarball-file-).  This tell's `npm install` to install this package from the `.tgz` file.
5. Run `npm install` to install the new package.

Now, any components or functions exported from the package should be available in the application.

## Conclusion

That's it. After the pipeline complete's its first successful run, you should have a package that a project can install. Next,see the document [How to Install a Package From the P1 GitLab Repository](./use-js-package-from-p1-gitlab.md) for instructions on how to use the package in a project.

## References

[Vite Library Mode documentation](https://vitejs.dev/guide/build.html#library-mode)
[Install npm module from gitlab private repository](https://stackoverflow.com/questions/22988876/install-npm-module-from-gitlab-private-repository)

```

```
