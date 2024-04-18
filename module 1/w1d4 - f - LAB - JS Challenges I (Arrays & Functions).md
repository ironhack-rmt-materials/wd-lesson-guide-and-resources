
# LAB - JS Challenges I (Arrays & Functions)


## Bonus: Iteration 6 | Product of Adjacent Numbers


Possible solution:

    ```js
    function greatestProduct(matrix) {

        let maxProduct = -Infinity;

        
        for(let row = 0; row<matrix.length; row++){
            for(let column = 0; column < matrix[row].length; column++){

            // product of horizontal adjacent numbers
            if (column < matrix[row].length - 3) {
                const productHorizontalNumbers = matrix[row][column] * matrix[row][column + 1] * matrix[row][column + 2] * matrix[row][column + 3];
                if (productHorizontalNumbers > maxProduct) {
                maxProduct = productHorizontalNumbers;
                }
            }

            // product of vertical adjacent numbers
            if(row < matrix.length - 3) {
                const productVerticalNumbers = matrix[row][column] * matrix[row+1][column] * matrix[row+2][column] * matrix[row+3][column]
                if (productVerticalNumbers > maxProduct) {
                maxProduct = productVerticalNumbers;
                }
            }

            }
        }

        return maxProduct;

    }

    ```


