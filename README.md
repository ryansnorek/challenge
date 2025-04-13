# Configuration Notes

## tsconfig.json
* Set the `"jsx"` flag to `"react-jsx"`, which is recommended for projects using React 17 or higher. It's more efficient by allowing TypeScript to transpile JSX into JavaScript. It also removes the need to import React into components.

* Set the `"target"` flag to `"ES2017"`. It is well supported by modern browsers and is more efficient transpiling async await syntax. However, `"ES2016"` might be a safer option if there are potential users with older browsers. 

# TODO
## Eslint
* `'@typescript-eslint/no-unused-vars': 'off'`
This is useful to allow developers to use an underscore to signal an unused varaible. 
This is common with a few design patterns. see below.

 - **MSW handlers**:
    ```javascript
    (_req, res) => res.status(200).json({ message: "Success" });
    ```

  - **Redux thunks with no args**:
    ```javascript
    (_, thunkAPI) => {
      return thunkAPI.dispatch(someAction());
    };
    ```
    
  - **Filtering values from an object**:
    ```javascript
    Object.fromEntries(
      Object.entries(obj).filter(([_, value]) => value != null)
    );
    ```

## Sonarqube linter
This helps maintain code and identify code smells like cognitive complexity and redundant code.

## Jest and React Testing Library

## Prettier