# Widow Custom React Hooks

### Purpose

Document Widow custom React hooks as they are created in order to increase visibility and application standardization, as well as decrease duplication. Developers should add to this document as new custom hooks are created.

### What is a custom React Hook?

According to the React documentation "**A custom Hook is a JavaScript function whose name starts with "use" and that may call other Hooks.**"

Since it is a function, a hook can return anything a JavaScript function can. For example, the "useDispatch" hook returns a function that is usually assigned to the variable dispatch.

Hooks can also return objects or arrays as shown in the "useSelector" and "useState" examples below:

Just like functions, hooks provide a tool for abstracting and/or separating logic. In the case of React, hooks are often used to separate complicated logic from the "view" portion of a component.

| **File name**                                                                                                                              | **Call Signature** | **Description**                                                                                                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [useFilteredAssets.tsx](https://code.il2.dso.mil/platform-one/products/widow/widow-react/-/blob/dev/src/hooks/useFilteredAssets.tsx)       |                    | Given a set of filters, roster, and start & end times, returns an array of type Asset. The Assets in this array have a "take_off_date_time" that is between the provided start time and end time. |
| [useFilteredTimelines.tsx](https://code.il2.dso.mil/platform-one/products/widow/widow-react/-/blob/dev/src/hooks/useFilteredTimelines.tsx) |                    | Given a set of filters and start & end times, returns an array of type Timeline. The timelines in this array have a "date_time" that is between the provided start time and end time.             |
