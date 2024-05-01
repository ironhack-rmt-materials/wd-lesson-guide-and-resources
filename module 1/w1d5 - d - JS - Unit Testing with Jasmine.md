

# JS | Unit Testing with Jasmine




## Intro

- Intro to TDD:
    - Red
    - Green
    - Refactor

- Our goal: 
    - implement a function that will receive an amount in cents (ex. 149) & return the corresponding value in decimal (ex. 1.49). 
    - following TDD




## Initial approach with console.logs


```js
    //  cents-to-decimals.js

    // Converts a value from cents to a floating point number with 2 decimals
    function centsToDecimals() {
    
    }


    // Test Specs: centsToDecimals

    // Should convert value from cents to floating point number with 2 decimals
    console.log(centsToDecimals(105) === 1.05);
    console.log(centsToDecimals(23) === 0.23);

    // Should return `undefined` when the first argument passed is a string
    // ...

    // Should return 0 when the first argument is not passed
    // ...

```



## Setup Jasmine

<!-- 

@LT:  
- very brief (can also be done in advance)
- for today's lab setup is already done

-->

- follow stepts in students portal:
    - visit: https://github.com/jasmine/jasmine/releases
    - download the latest standalone version (`jasmine-standalone-x.y.z.zip`)
    - unzip
    - copy all the content in the root of the project
    - Remove the starter code (files in `src` and `spec`)
    - Create file `src/cents-to-decimals.js`
    - Create file `spec/cents-to-decimals.spec.js`
    - Link the JavaScript files in the `SpecRunner.html`
    - Open `SpecRunner.html` with Live Server





## [RED] Write tests with Jasmine

- Intro: describe(), it(), expect()
    - diagram: https://miro.medium.com/v2/resize:fit:1400/1*UeIWTQVlLLuI3YlczTmnsg.png

- Create a suite of tests with describe()

    ```js        
    describe("function centsToDecimals", function(){

    });
    ```

- Add tests/specs with .it()

    ```js        
    describe("function centsToDecimals", function(){
        it("Should convert value from cents to floating point number with 2 decimals", function(){

        });
    });
    ```

- Add expectations (a test can contain one or multiple expectations)

    ```js        
    describe("function centsToDecimals", function(){
        it("Should convert value from cents to floating point number with 2 decimals", function(){
            expect(centsToDecimals(105)).toBe(1.05);
            expect(centsToDecimals(400)).toBe(4.00);
            expect(centsToDecimals(23)).toBe(0.23);
        });
    });
    ```

- Write tests for other possible edge cases...

    ```js        
    describe("function centsToDecimals", function(){
        
        // ...
        // ...

        it("Should return null, if invoked without any argument", function(){
            expect(centsToDecimals()).toBeNull();
        });

        it("Should return null, if invoked with an argument that is not a valid number", function(){
            expect(centsToDecimals("eleven")).toBeNull();
        });
    });
    ```


- Explain: matchers (see students portal)
    - Some examples:
        - expect(xxx).toBe()    - strict equality, compares if two values are exactly the same
        - expect(xxx).toEqual() - deep equality, can be used to compare objects and arrays
        - expect(xxx).toBeLessThan()
        - expect(xxx).toBeGreaterThan()
        - expect(xxx).toBeNull()
        - expect(xxx).not.toBe()


- (skip) xdescribe() vs. describe()




## [GREEN] Write code to pass the tests

    ```js
    function centsToDecimals(amount) {

        if(amount === undefined){
            return null;
        }

        if(typeof amount !== "number"){
            return null;
        }

        const result = amount / 100;
        return result;
    }
    ```




## [REFACTOR] Improve code quality

    ```js
    function centsToDecimals(amount) {

        if(typeof amount !== "number"){
            return null;
        }

        return amount / 100;
    }
    ```


