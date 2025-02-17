

# Some options to give CSS to React apps

<!--

How: demo on popcorn time

Note:
- consider doing a full session where we give style to the whole app popcorn-time (ex. using Chakra)

-->


Some options to apply CSS to our React apps:

- 1. Global CSS

- 2. One CSS file per component

- 3. CSS Framework
    - Example: Bootstrap, Tailwind

- 4. Component libraries
    - Example: Chakra UI, Mantine, Semantic UI
    - Tailwind component libraries: Flowbite React, daisyUI
    <!-- @note: As of Nov. 2024, Chakra has released v3, but the documentation still appears to be somewhat immature  -->

## Example Global CSS
- Refresh: media queries / responsive


## (optional) Example CSS Framework
- Can do a quick demo with bootstrap (eg. create an index.html)


## Example Mantine

- Setup:
    - follow steps here: https://mantine.dev/guides/vite/
    <!-- 
        Note: on Vite, you may get this error "ERR_ABORTED 504 (Outdated Optimize Dep)"
        https://stackoverflow.com/a/75953479/11298742
    -->

Show example with Buttons:
    ```jsx
    <Button variant="outline" color="indigo">Edit</Button>
    <Button variant="outline" color="red">Delete</Button>
    <Button variant="filled" color="indigo">Back to projects</Button>
    ```

Demo: implement responsiveness with `SimpleGrid`

```jsx
<SimpleGrid cols={{ base: 1, md: 3}} >
    {projects.map((projectDetails) => {
        return (
            <div>
                {/* ... */}
            </div>
        )
    })}
</SimpleGrid>
```



Some interesting core elements:
- Layout
    - Grid
    - SimpleGrid
- Forms:
    - Button and its variants (eg. button with icon)
    - Input
    - Checkbox
- Combobox
    - Autocomplete
    - Multiselect
- Navigation
    - Burger
- Data Display
    - Accordion
    - Badge
    - Card
    - Timeline
- Overlays
    - Dialog
    - Menu

Other packages (requires installation): 
- Mantine Dates 
    - Calendar
    - Datepicker
- Mantine Form
- Mantine Charts


Customizing with a theme:

```jsx
const customTheme = {
  colorScheme: 'light',
  colors: {
    primary: [
      "#e1fdff", "#cff6fc", "#a5eaf4", "#76dded", "#51d3e7", "#39cce4", "#25cae3", "#0bb2ca", "#009eb5", "#008a9f"],
    secondary: [
      "#fff3e4", "#fce6d1", "#f4cca6", "#edb076", "#e7994e", "#e48934", "#e38225", "#c96f18", "#b46211", "#9d5305"],
  },
  primaryColor: 'primary',  // Sets primary as the main color
  secondaryColor: 'secondary',  // (Hypothetical) For secondary button or text usage
};


<MantineProvider theme={customTheme} withGlobalStyles withNormalizeCSS>
    <App>
</MantineProvider>

```


```jsx
    <Text color="primary" size="lg" weight={700}>Primary Color Text</Text>
    <Text color="secondary" size="lg" weight={700}>Secondary Color Text</Text>
    <Button color="primary" size="md">Primary Button</Button>
    <Button color="secondary" size="md">Secondary Button</Button>
```




## Component libraries vs. plain CSS

Advantages:
- can get a very professional look and feel with a few lines of code
- can get responsive working nicely

Disadvantages:
- need to spend some time to get to know your tool
- customizing details can be.... hell



