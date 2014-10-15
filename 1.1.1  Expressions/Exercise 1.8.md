Newton's method for cube roots is based on the fact that
if y is an approximation to the cube root of x,
then a better approximation is given by the value

![](http://mitpress.mit.edu/sicp/full-text/book/ch1-Z-G-5.gif)

Use this formula to implement a cube-root procedure analogous to the square-root procedure.

    (define (square x) (* x x))

    (define (average3 x y) (/ (+ x y) 3))

    (define (improve guess x)
      (average3 (/ x (square guess)) (* guess 2)))


    (define (cube-root-iter guess x)
      (if (= guess x)
          guess
          (cube-root-iter (improve guess x) x)))

    (define (cube-root x )
      (cube-root-iter 1 x))

;; test

    (cube-root 1)
    (cube-root 2)
    (cube-root 3)
    (cube-root 8)
