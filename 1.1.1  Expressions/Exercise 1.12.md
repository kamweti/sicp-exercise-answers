The following pattern of numbers is called Pascal's triangle.

         1
        1 1
       1 2 1
      1 3 3 1
     1 4 6 4 1

The numbers at the edge of the triangle are all 1, and each number inside the triangle is
the sum of the two numbers above it.
Write a procedure that computes elements of Pascal's triangle by means of a recursive process.

                 1      ---- row 0
                1 1     ---- row 1
               1 2 1    ---- row 2
              1 3 3 1   ---- row 3
             1 4 6 4 1  ---- row 4

             | | | | |
             | | | | |

    column   0 1 2 3 4

What we already know

1. For a given nth row there can only be n column values
2. nth row column 0 is equal to 1
3. nth row column n equals to row
4. all other values outside the triangle are equal to zero

given

(3-1, 1-1) = 1
(3-1, 1)   = 2

therefore (3 1) = (3-1, 1-1) + (3-1, 1)

we can write

    (define (pascal row column)
      (if (> column row)
        0
        ( if (or (= row column) (= column 0) )
          1
          (+ (pascal (- row 1) (- column 1)) (pascal (- row 1) column) )
        )
      )
    )


; test

    (pascal 4 2)
