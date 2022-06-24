# Testing Standards for Decepticon

## General TL;DR

:white_check_mark: Small Tests

:white_check_mark: Verbose Test Names Using 'should'

:white_check_mark: 'Given...When...Then...' Test Description

:white_check_mark: Test Behavior

:white_check_mark: Descriptive Assertion Messages

:x: Long Tests

:x: Test Methods

## Test Names

Give your tests verbose names that include a description using 'should' and the expected result.

Example:

```python
def test_setting_vertices_should_create_new_vertices_matrix():
```

## Test Descriptions

Always add a description for your test. Use the 'Given...When...Then...' format to help others understand the test.

Example:

```
Given a Shape instance that already contains dimensions "x" and "y"
When I set new vertices
Then the vertices matrix should contain only the new coordinates and Dimension instances "x" and "y" should be unchanged
```

## What to Test

Test behavior, not individual methods.  Try to focus on what is accessible from the public API and its expected output.  Leave room for internal/private methods to be refactored.

## Test Output/Messages

Always add descriptive messages to your assertions. Make sure the dev can debug easily from the test message.

Example:

```python
assert (
    square.dimensions_dict["x"] == dimension_x
), "square.dimension_dict['x'] should be the same Dimension instance from init"
```

## Test Organization

Use `# setup` and `# test` to separate any methods needed to set the stage from the actual test.

```python
def test_something_should_return_that_other_thing():
    # setup
    new_object = SomeClass()

    # test
    assert some_function(new_object) == "this", "some_function should return 'this' when passing a new instance of SomeClass."
```