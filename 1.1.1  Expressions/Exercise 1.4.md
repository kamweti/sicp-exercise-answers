Observe that our model of evaluation allows for combinations whose operators are compound expressions. Use this observation to describe the behavior of the following procedure:

    ( define (a-plus-abs-b a b)
            (( if (> b 0) + -) a b))

procedure accepts two parameters where if the second parameter is greater than zero

we will go ahead and add the first and second parameters, else 
it will subtract the first parameter from the second
