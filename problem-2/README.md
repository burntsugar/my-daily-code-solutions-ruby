# Problem 2

````
From https://www.dailycodingproblem.com/

Daily Coding Problem: Problem #2 [Hard]

Good morning! Here's your coding interview problem for today.

This problem was asked by Uber.

Given an array of integers, return a new array such that each element at index i of the new array is the product of all the numbers in the original array except the one at i.

For example, if our input was [1, 2, 3, 4, 5], the expected output would be [120, 60, 40, 30, 24]. If our input was [3, 2, 1], the expected output would be [2, 3, 6].

Follow-up: what if you can't use division?
````

# Assumption


# Solution

## Psuedocode

````
get array
Initialise result array
Initialise current element index to 0
Loop through each element in the array (outer)
    initialise product to 1
    Loop through each element in the array (inner)
        if the current element index (outer) is not the same as the current element index (inner)
            accumulate the multiplied product of the current element value
        end if
    end loop (inner)        
    push to result array
    increment current element index
end loop (outer)

````

## Ruby Solution
````ruby
def solve
    arr = [1, 2, 3, 4, 5]
    new_arr = []
    count = 0
    0.step(arr.length-1,1) { |i|
        product = 1
        0.step(arr.length-1,1) { |j|
            if (j != count)
                product *= arr[j]
            end
        }
        new_arr << product
        count += 1
    }
    new_arr
end
````

# Tests

Tests in /spec

# Extra

nup

# Other

I don't understand the requirement that states...

> Follow-up: what if you can't use division?