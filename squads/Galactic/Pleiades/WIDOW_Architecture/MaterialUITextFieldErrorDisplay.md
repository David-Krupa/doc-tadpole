# Material UI TextField Component Input Error Display Pattern

### Purpose

To document common patterns for displaying input error information when using Material UI components.

### TextField (and others) Entry Error

This technique can be used for MUI TextField and any other component that has the boolean error and string helperText props. The following example is from the MapExport component.

In this example the string value mapIntervalErrorMessage is cast to a boolean value on ine 135 to determine if the helperText on line 136 is displayed as an error. This pattern is useful if the helperText is only used to display error information.

The mapIntervalErrorMessage is a value is set whenever the mapInterval value is changed. The mapInterval value is updated by the TextField component. In the picture below, a useEffect is used to check the value of mapInterval when it changes, determine if the value is correct, and provide an error message if appropriate.
