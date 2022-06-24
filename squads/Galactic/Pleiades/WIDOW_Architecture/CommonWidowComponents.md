# Common Widow Components

### Purpose

Document common widow components as they are created in order to increase visibility and application standardization, as well as decrease duplication. Developers should add to this document as new common components are created.

### What is a common component?

A common component is one that is expected to be used in multiple places in the application. An example of a common component is the roundDeleteButton which is included in the list below.

Common components are also basic components such as a specialized button (again see roundDeleteButton). Larger composite components consisting of multiple other components would not necessarily be classified as a common component even if it was used in multiple places in the app.

How do you know if a component should be added to this list? You’ll have to use your judgement. A good candidate for this list would likely have several of the following qualities:

- Used in multiple parent components
- Is relatively small
- Is created by specifically styling and or composing one or more MUI components

| File Name and location   | Image(s)                                                                                                         | Description                                                                                                                                                                                          |     |     |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- |
| addNewElementButton.tsx  | normal state: hovered: internal button contents ordered as a row: Button set to be full height of its container: | MUI Button component that displays a plus sign and a text value passed via the "label" prop. Button size & padding, font weight, content orientation, and more can be controlled by component props. |     |     |
| eventFieldTypeSelect.tsx | closed: opened:                                                                                                  | Common component to select TimeField types.                                                                                                                                                          |     |     |
| icaoSelect.tsx           | closed: opened: inputing a custom value: acceptCustomValue prop set to false:                                    | Common component to select ICAO using a MUI autocomplete component. Includes an acceptCustomValue prop to toggle MUI autocomplete freeSolo prop on an off                                            |     |     |
| modalClose.tsx           | normal hovered                                                                                                   | common close component for Widow modals                                                                                                                                                              |     |     |
| roundDeleteButton.tsx    |                                                                                                                  | A MUI IconButton component that display a MUI Clear icon on a circular background. Includes props to control positioning relative to its nearest positioned parent component                         |     |     |
| wiidowSelect.tsx         |                                                                                                                  | A MUI Select Dropdown Component that allows a user to select an option from a drop down.                                                                                                             |     |     |
