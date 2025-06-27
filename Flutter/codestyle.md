---
description: 
globs: 
alwaysApply: true
---

# Code

## Grouping and Sorting

- When generating code, group members by type, then sort alphabetically.
- When grouping members by type, use the following groups IN THIS ORDER:
  - Private Constants
  - Public Constants
  - Private Variables
  - Private Constructors
  - Public Constructors
  - Private Methods
  - Public Methods
  - Private Properties
  - Public Properties
  - Private Events
  - Public Events

## Nomenclature

- Consider variables that are not private to be "Public Properties".
- Consider variables that start with 'on' and are related to callbacks as "Events".
- Consider properties that start with 'on' and are related to callbacks as "Events".

## Regions

- Always surround code groups with a matching named region.
	- Regions should start with // #region \[GroupName\], for example: // #region \[Public Methods\]
	- Regions should end with // #endregion \[GroupName\], for example: // #endregion \[Public Methods\]
	- // #region \[GroupName\] statements should be followed by one blank line before code begins.
	- // #endregion \[GroupName\] statements should be preceded by one blank line.
- When asked to create regions, always use the group names identified in [Grouping and Sorting](mdc:#grouping-and-sorting).
- When asked to create regions, do not create empty regions for groups that don't exist.
	
## Comments

- Add documentation /// comments to all Methods, Properties and Events.
	- When adding /// comments, be sure to add them before any metadata annotations.
	- When adding /// comments, if multiple lines are needed start with a summary line and include a blank line between the summary and remaining lines.
	- When adding /// comments, explain parameters and surround parameter names with brackets. For example: "\[audio\]: The RealTime audio instance to use." and "\[name\]: The new name of the Widget."
	- When adding /// comments to properties that are read / write, only add comments to the get method.
	- When adding /// comments to something that explicitly throws an exception, document the exception at the bottom of the /// comment and surround it in brackets. For example: "Throws a \[StateError\] if the engine hasn't been started."
	- When adding /// comments, use markdown syntax when it would be beneficial but do not use it excessively.
	
## Imports

- Always sort import statements alphabetically.
- There should not be any blank lines between import statements.

# Refactoring

- When asked to apply MyCodeStyle :
	- Create code groups
	- Create regions
	- Sort regions
	- Add documentation code comments