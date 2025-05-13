

# TypeScript + React


## Create a new app with Vite (React + TypeScript)

- npm create vite@latest




## Components and props


- Syntax with an inline type annotation:

    ```ts
    function Book(props: { title: string; year: number }) {
        //...
    }
    ```


- Syntax with a type alias:

    ```ts
    type BookProps = {
        title: string;
        year: number;
    }

    function Book(props: BookProps) {
        // ...
    }
    ```


Example 1: props for a Recipe component

    ```ts
    type RecipeProps = {
        title: string;
        difficulty: 'easy' | 'medium' | 'hard';
    }

    function Recipe(props: RecipeProps) {
        return (
            <div className="card">
                <h2>{props.title}</h2>
                <p>Difficulty: {props.difficulty}</p>
            </div>
        );
    }

    export default Recipe;

    ```


    ```ts
    function App() {
        return (
            <>
                <Recipe title="Classic Avocado Toast" difficulty="easy" />
                <Recipe title="Sweet Potato Falafel" difficulty="medium" />
            </>
        );
    }
    ```



## Other topics

- useState
- useEffect + api requests
- Forms and JavaScript events
- Context API
- working with external libraries...
- ...



