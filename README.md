# DanDecomp: Dandelion Decomposition

DanDecomp, short for Dandelion Decomposition, is a file organization system designed to facilitate code decomposition, maintainability, and scalability. The name is in reference to the idea of modules decomposing and "blowing away," planting, and developing their own submodules.  DanDecomp encourages breaking down larger modules into smaller, focused submodules that can evolve over time.

## Benefits and Intent

The primary benefits and intent of the DanDecomp system are:

- **Modularization**: Promote the creation of reusable and focused modules and submodules for better code organization.
- **Decomposition**: Encourage the decomposition of larger files into smaller, more manageable pieces, improving readability and maintainability.
- **Scalability**: Provide a structure that can easily grow and adapt as projects evolve, accommodating various architectural patterns and technologies.
- **Consistency**: Establish a clear and consistent naming convention, making it easier to locate and understand code within the project.

## File Structure Guidelines

1. **Organize code into pages, modules, and submodules**: Store entry points in a "pages" folder, main modules in a "modules" folder within the `src` directory, and decompose modules into reusable submodules.

2. **Use singular names for module and submodule folders**: Create folders with singular module names for each module and submodule, reflecting their purpose.

3. **Adopt fully-qualified module names for files**: Use fully-qualified module names (a file in common/button/play would be called common-button-play) for files within the submodule folders, making it easier to expand single files into folders of modules without significant renaming.

4. **Decompose files into submodules**: When decomposing files into submodules, create a new folder, move the existing file into that folder, and continue breaking it down into smaller submodules, maintaining the original file name.

5. **Omit the base module folder's name from file names**: Exclude the base module folder's name from file names, such as not naming any files "module-...".

6. **Store entry points in a "pages" folder**: Use a "pages" folder in the project root to store entry points, representing different sections of the application or website.

## Example Folder Structure
```
src/
  modules/
    common/
      button/
        play/
          common-button-play.ts
          common-button-play-styling.ts
          common-button-play-click.ts
          common-button-play-animation.ts
        record/
          common-button-record.ts
      popup-window/
        common-popup-window.ts
        common-popup-window.scss
  pages/
    home/
      home.ts
    about/
      about.ts

```


## Decomposing a Module

Here's a step-by-step example of decomposing a module using the DanDecomp system with the updated file structure:

Identify a file that has grown too large or complex and needs to be broken down into smaller, more manageable pieces. For example, let's say the common-button-play.ts file within the common folder contains a lot of code related to different aspects of the play button's functionality.

Create a new folder within the current module folder to represent the submodule. In this case, we'll create a folder named play within the button folder inside the common folder:

```
src/modules/common/button/play/
```
Move the existing file into the newly created submodule folder - (note that it is not necessary to rename this file):

```
src/modules/common/button/play/common-button-play.ts
```
Now, begin decomposing the common-button-play.ts file into smaller, focused submodules:

a. Create a new TypeScript file to handle the styling, such as common-button-play-styling.ts, within the play folder:

   ```
   src/modules/common/button/play/common-button-play-styling.ts
   ```
b. Create another TypeScript file to manage click events, such as common-button-play-click.ts, within the play folder:

   ```
   src/modules/common/button/play/common-button-play-click.ts
   ```
c. Create a TypeScript file to handle animations, such as common-button-play-animation.ts, within the play folder:

   ```
   src/modules/common/button/play/common-button-play-animation.ts
   ```
Update any import statements in your codebase to reference the new submodule files.

By following these steps, you can decompose a complex file into smaller, focused submodules that are easier to understand and maintain.


## Examples Applying DanDecomp to different languages/patterns
Although DanDecomp was originally developed for React projects, it is meant to be a general naming system for any language or project. Here are some examples of how it can look applied to different stacks, languages, and design patterns:

### Vue
```
src/
  modules/
    common/
      button/
        play/
          play-button.vue
          play-button-styles.scss
          play-button-click.js
          play-button-animation.js
        record/
          record-button.vue
      popup-window/
        popup-window.vue
        popup-window-styles.scss
  pages/
    home/
      home.vue
    about/
      about.vue
```

### React
```src/
  modules/
    common/
      button/
        play/
          play-button.tsx
          play-button-styles.scss
          play-button-click.ts
          play-button-animation.ts
        record/
          record-button.tsx
      popup-window/
        popup-window.tsx
        popup-window-styles.scss
  pages/
    home/
      home.tsx
    about/
      about.tsx
```

### Typescript
```src/
  modules/
    common/
      button/
        play/
          play-button.ts
          play-button-styling.ts
          play-button-click.ts
          play-button-animation.ts
        record/
          record-button.ts
      popup-window/
        popup-window.ts
        popup-window.scss
  pages/
    home/
      home.ts
    about/
      about.ts
```

### C
```
src/
  modules/
    common/
      button/
        play/
          play-button.c
          play-button.h
          play-button-styling.c
          play-button-styling.h
          play-button-click.c
          play-button-click.h
          play-button-animation.c
          play-button-animation.h
        record/
          record-button.c
          record-button.h
      popup-window/
        popup-window.c
        popup-window.h
        popup-window-styles.c
        popup-window-styles.h
  pages/
    home/
      home.c
      home.h
    about/
      about.c
      about.h
```
