Define a procedure that takes three numbers as arguments and returns the sum of the squares 
of the two larger numbers.

    (define (square n) (* n n))

    (define (sum-squares x y)
            (+ (square x) (square y)))

    ( define (larger x y)
              (if (> x y) x y))

    ( define (large-two-sum-squares  a b c)
            (if (= a (larger a b))
              (sum-squares a (larger b c))
              (sum-squares b (larger a c))))

; ---------
; Test
; ---------

    ( if (= 41 ( large-two-sum-squares 3 4 5)) true false)
