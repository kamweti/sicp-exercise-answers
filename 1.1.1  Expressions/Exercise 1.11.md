A function f is defined by the rule that f(n) = n if n<3 and f(n) = f(n - 1) + 2f(n - 2) + 3f(n - 3) if n> 3.
Write a procedure that computes f by means of a recursive process.

    ( define (f n)
      (if (< n 3)
        n
        (+
          (* n (f (- n 1)))
          (* (- n 2) (f (- n 2)))
        )
      ))

    ; test
    (f 4)
    (+ (* 4 (f 3)) (* 2 (f 2)))
    (+ (* 4 ((+ (* 3 (f 2)) (* 1 (f 1))))) (* 2 2))
    (+ (* 4 ((+ (* 3 2) (* 1 1)))) 4)
    (+ (* 4 ((+ 6 1))) 4)
    (+ (* 4 7) 4)
    (+ 28 4)
    32


Write a procedure that computes f by means of an iterative process.


    ;; a = f(n - 1)
    ;; b = f(n - 2)
    ;; c = f(n - 3)
    ;; return a + 2b + 3c 


    (define (f n)
      (if (< n 3)
          n
          (f-iter 2 1 0 n))) ;; taking n to be 3

      (define (f-iter a b c n)
        (if (< n 3)
          a
          (f-iter 
              (+ a (* 2 b) (* 3 c)) ;; new a
              a         ;; new b
              b         ;; new c
              (- n 1)
          ))
      )
