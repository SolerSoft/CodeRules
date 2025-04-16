---
description:
globs:
alwaysApply: true
---

# General
- Use log instead of print for debugging.
- Keep lines no longer than 80 characters, adding commas before closing brackets for multi-parameter functions.

# Documentation
- Document complex logic and non-obvious code decisions.
- Follow official Flutter documentation for best practices.

# Dart

## Basic Principles

- Use English for all code and documentation.
- Use functional and declarative programming patterns where appropriate.
- Prefer composition over inheritance.
- Always declare the type of each variable and function (parameters and return value).
	- Avoid using any.
	- Create necessary types.
- Don't leave blank lines within a function.
- One export per file.

## Nomenclature

- Use PascalCase for classes.
- Use camelCase for variables, functions, and methods.
- Use underscores_case for file and directory names.
- Use UPPERCASE for environment variables.
	- Avoid magic numbers and define constants.
- Include verbs in function names.
	- If it returns a boolean, use isX, hasX, canX, etc.
	- If it doesn't return anything, use loadX, executeX, saveX, etc.
- Use complete words instead of abbreviations
	- Except for standard abbreviations like API, URL, etc.
	- Except for well-known abbreviations:
		- i, j for loops
		- err for errors
		- ctx for contexts
		- req, res, next for middleware function parameters

## Functions

- Use arrow syntax for simple functions and methods (less than 5 lines).
- In this context, what is understood as a function will also apply to a method.
- Write short functions with a single purpose. Ideally less than 20 instructions.
- Avoid nesting blocks by:
	- Early checks and returns.
	- Extraction to utility functions.
- Use higher-order functions (map, filter, reduce, etc.) to avoid function nesting.
	- Use arrow functions for simple functions (less than 3 instructions).
	- Use named functions for non-simple functions.
- Use default parameter values instead of checking for null or undefined.
- Reduce function parameters using RO-RO
	- Use an object when it is necessary to pass large numbers of parameters (more than 3).
	- Use a result class object when it is necessary to return results with multiple values.
	- Declare necessary types for input arguments and output.
- Use a single level of abstraction.

## Data

- Don't abuse primitive types and encapsulate data in composite types.
- Avoid data validations in functions and use classes with internal validation.
- Prefer immutability for data.
	- Use readonly for data that doesn't change.
	- Use as const for literals that don't change.

## Classes

- Follow SOLID principles.
- Prefer composition over inheritance.
- Declare interfaces to define contracts.
- Write small classes with a single purpose.
	- Less than 200 instructions.
	- Less than 10 public methods.
	- Less than 10 properties.

## Exceptions

- Use exceptions to handle errors you don't expect.
- If you catch an exception, it should be to:
	- Fix an expected problem.
	- Add context.
	- Otherwise, use a global handler.

## Testing

- Do not write tests unless instructed to do so.
- Follow the Arrange-Act-Assert convention for tests.
- Name test variables clearly.
	- Follow the convention: inputX, mockX, actualX, expectedX, etc.
- Write unit tests for each public function.
	- Use test doubles to simulate dependencies.
		- Except for third-party dependencies that are not expensive to execute.
- Write acceptance tests for each module.
	- Follow the Given-When-Then convention.

# Flutter

## Basic Principles

- Use const constructors for immutable widgets.
- Use clean architecture
	- see modules if you need to organize code into modules
	- see controllers if you need to organize code into controllers
	- see services if you need to organize code into services
	- see repositories if you need to organize code into repositories
	- see entities if you need to organize code into entities
- Use repository pattern for data persistence
	- see cache if you need to cache data
- Controller always takes methods as input and updates the UI state that effects the UI
- Use extensions to manage reusable code
- Use ThemeData to manage themes
- Use AppLocalizations to manage translations
- Use constants to manage constants values
- When a widget tree becomes too deep, it can lead to longer build times and increased memory usage. Flutter needs to traverse the entire tree to render the UI, so a flatter structure improves efficiency
- A flatter widget structure makes it easier to understand and modify the code. Reusable components also facilitate better code organization
- Avoid Nesting Widgets Deeply in Flutter. Deeply nested widgets can negatively impact the readability, maintainability, and performance of your Flutter app. Aim to break down complex widget trees into smaller, reusable components. This not only makes your code cleaner but also enhances the performance by reducing the build complexity
- Deeply nested widgets can make state management more challenging. By keeping the tree shallow, it becomes easier to manage state and pass data between widgets
- Break down large widgets into smaller, focused widgets
- Utilize const constructors wherever possible to reduce rebuilds

## Testing

- When requested to include tests:
	- Use the standard widget testing for flutter
	- Use integration tests for each api module.

## Performance
- Use const widgets where possible to optimize rebuilds.
- Implement ListView optimizations (e.g., ListView.builder).
- Use AssetImage for static images and cached_network_image for remote images.
- Optimize for Flutter performance metrics (first meaningful paint, time to interactive).

## UI and Styling
- Use Flutter's built-in widgets and create custom widgets.
- Implement responsive design using LayoutBuilder or MediaQuery.
- Use themes for consistent styling across the app.
- Use Theme.of(context).textTheme.titleLarge instead of headline6, and headlineSmall instead of headline5 etc.
- Create small, private widget classes instead of methods like Widget _build....
- When external data is loaded, implement RefreshIndicator for pull-to-refresh functionality.
- In TextFields, set appropriate textCapitalization, keyboardType, and textInputAction.
- Always include an errorBuilder when using Image.network.

## Error Handling and Validation
- Implement error handling in views using a SnackBar.
- Handle empty states within the displaying screen.