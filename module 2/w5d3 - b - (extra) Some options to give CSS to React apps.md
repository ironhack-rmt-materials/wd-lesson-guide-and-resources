

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
    - Example: Tailwind, Bootstrap

- 4. Component libraries
    - Example: Chakra UI, Mantine, Semantic UI



## Example Global CSS
- Refresh: media queries / responsive


## (skip) Example CSS Framework


## Example Chakra UI

- Getting started:
    - https://chakra-ui.com/getting-started
    - npm i
    - render `<ChakraProvider>`


- Render Button
    - https://chakra-ui.com/docs/components/button


- Example Grid

    ```jsx

    <SimpleGrid columns={{ base: 1, md: 2, lg: 3 }} spacing={10}>
        <Box bg='teal.200'>One</Box>
        <Box bg='teal.200'>Two</Box>
        <Box bg='teal.200'>Three</Box>
    </SimpleGrid>

    ```



## Component libraries vs. plain CSS

Advantages:
- can get a very professional look and feel with a few lines of code
- can get responsive working nicely

Disadvantages:
- need to spend some time to get to know your tool
- customizing details can be.... hell



