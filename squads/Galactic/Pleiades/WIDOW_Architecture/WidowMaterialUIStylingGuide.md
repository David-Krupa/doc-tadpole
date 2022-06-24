# Widow Material UI Styling Guide

### Purpose

Present best practices related to using Material UI styling techniques in Widow in order to achieve the following goals:

- Support coherent styling in the app
- Encapsulate styling within components to make component styling more visible
- Ease transition to the upcoming whole app Widow Material UI
- Support application theming and theme switching using [MUI theme techniques](https://material-ui.com/customization/theming/)

### Background

One of the first questions you should ask is what kind of styling you are applying and why are you doing it?

- If the answer is to recreate an already existing MUI component, then stop and use that MUI component.
- If you are styling to create a Widow-specific version of an existing MUI component, consider creating a [Common Widow Component](file:////wiki/spaces/BG/pages/1850310699/Common+Widow+Components) built using the existing MUI component.

There are several guidelines you can use that can simplify achieving the goals listed in the purpose of this document.

This [Widow MUI Styling presentation](https://docs.google.com/presentation/d/1AfJm1NDrVz5-p4nKIaqwMKX6HjGSeaoMixdcIDlXgBA/edit?usp=sharing) provides an overview of the potential issues related to integrating MUI components and styling in the app and how to avoid them

### **Summary**

- Don’t style components using CSS or SCSS files. Instead use, Material UI’s CSS in JS solutions to style components. These solutions have access to the MUI theme while maintaining access to CSS pseudo-selectors.
- When able, pull styling attributes from the MUI theme using the makeStyles hook or directly using MUI component style-specific props as shown in the Widow MUI styling presentation linked above.
- Due to performance Material UI’s CSS-in JS is preferred over using large amounts of [inline styles](https://reactjs.org/docs/faq-styling.html).
- When necessary, React [inline styling](https://reactjs.org/docs/dom-elements.html#style) can also access theme variables. This means that standard HTML components such as div or span can access MUI them variables such as colors or spacing. This is done via the useTheme hook for functional components or the withTheme Higher Order Component for class based components. Documentation [here](https://material-ui.com/styles/advanced/#accessing-the-theme-in-a-component).

### Additional Resources

- Official MUI styling documentation
  - [Accessing a MUI theme in a component](https://material-ui.com/customization/theming/#accessing-the-theme-in-a-component)
  - [makeStyles hook](https://material-ui.com/styles/api/#returns-3)
- Widow MUI styling presentation: <https://docs.google.com/presentation/d/1AfJm1NDrVz5-p4nKIaqwMKX6HjGSeaoMixdcIDlXgBA/edit?usp=sharing>
- Net Ninja’s Material UI Styling video tutorials. Net Ninja's entire MUI series is very useful and is recommended viewing. The following videos are styling specific:
  - <https://youtu.be/OK00k47RMPI>
  - <https://youtu.be/xIIJfmDnvPE>
  - <https://youtu.be/6BkqRkw0Lwc>
- Anthony Sistilli’s MUI video tutorial series.
  - <https://youtu.be/pHclLuRolzE>
