# DRAFT: Material UI Component Testing

## Autocomplete Component

The [Material UI Autocomplete](https://material-ui.com/components/autocomplete/) component is not a standard HTML select component which means it cannot be tested like one. The component is composed of multiple HTML elements with provide multiple interaction points for testing. For example, the standard practice in Widow is for the Autocomplete to render a MUI Text Field component for use as a text input.

Other subcomponents can be seen in the Autocomplete source file [here](https://github.com/mui-org/material-ui/blob/next/packages/material-ui/src/Autocomplete/Autocomplete.js). Rendering a TextField as the Autocomplete’s input is standard

### Testing Techniques

A typical test may involve using the [userEvent](https://github.com/testing-library/user-event) library to type a value in the Autocomplete’s text input. There are several techniques for querying this text input. Several methods are shown below

- Using within to query for the text box by role
- Providing a data-testid for the AutoComplete’s TextField and accessing the input directly in the test

Once the input is accessible, additional testing can be done as demonstrated in Widow component tests such as icaoSelect.test.tsx

### Triggering onChange within autocomplete:

1.  Access the autocomplete and input as outlined above
2.  Focus on the autocomplete
3.  On the input, type with userEvent the arrow down and enter inputs to simulate selecting one of the selection options

```
const autocomplete = screen.queryByTestId('autocomplete')

const input =
within(queryByTestId('autocomplete')!).getByRole('textbox')

autocomplete.focus()

userEvent.type(input, '{arrowdown}{enter}')
```

### More Resources

- <https://stackoverflow.com/questions/60882089/how-to-test-material-ui-autocomplete-with-react-testing-library>
