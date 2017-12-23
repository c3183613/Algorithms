# Notes
Input       - Algorithm receives *input*  
Output      - Algorithm produces *output*  
Precision   - The steps are precisely stated  
Determinism - The immediate results of each step of execution are unique and
are determined only by the inputs and results of the preceding steps  
Finiteness  - The algorithm termintes; i.e. stops after a finite amount of
instructions  
Correctness - The output produced by the algorithm is correct  
Generality  - The algorithm applies to a set of inputs.


# Exercises  
## 1.1  
1. Write an algorithm that find the smallest element amount a, b, and c
```"c++"
int ReturnSmallest(const int num1, const int num2, const int num3)
{
    int smallest = num1;
    if(smallest > num2)
        smallest = num2;
    if(smallest > num3)
        smallest = num3;
    return smallest;
}
```
2. Write an algorithm that finest the second-smallest element amount the
distinct values a,b, and c

```"c++"
int SecondSmallest(const int num1, const int num2, const int num3)
{
    // If two of the three inputs are the same
    if(num1 == num2 || num1 == num3)
        return num1;
    else if(num2 == num3)
        return num2;
    if(num1 > num2 && num1 < num3)
        return num1;
    else if(num2 > num1 && num2 < num3)
        return num2;
    else
        return num3;
}
```

3. Write the standard method of adding two positive decimal integers, taught in
elements schools, as an algorithm.
```"c++"
int AddTwoNums(const int num1, const int num2)
{
    return num1 + num2;
}
```

4. Which properties of an algorithm - input, output, precision, determinism,
finiteness, correctness, generality- if any, are lacking in the following?
Explain. The input is a set of S integers and an integer m. The ouput is all
subsets of S that sum to m.
  1. List all subsets of S and their sums
  2. Proceed through the subsets listed in step 1 and output each whose sum is m  
If S is infinite, no termination of algorithm, which also =leads to no output.  

## 1.2
Write all algorithms in pseudo code
1. Write an algo that returns the smallest value in the array `s[1], ... , s[n]`
. Use a while loop
```"c++"
int ReturnSmallest(const int[] array, const int array_size)
{
    int array_counter = 0;
    int smallest_num = 0;
    if(array_size >= 1)
        smallest_num = array[1];
    else
        // throw input exception
    while(array_counter <= array_size)
    {
        if(smallest_num > array[array_counter])
            smallest_num = array[array_counter];
        array_counter++;
    }
    return smallest_num;
}
```

2. Do `1.` with a for loop.
```"c++"
int ReturnSmallest(const int[] array, const int array_size)
{
    int array_counter = 0;
    int smallest_num = 0;
    if(array_size >= 1)
        smallest_num = array[1];
    else
        // throw input exception
    for(array_counter = 0; array_counter <= array_size; array_counter++)
    {
        if(smallest_num > array[array_counter])
            smallest_num = array[array_counter];
    }
    return smallest_num;
}
```

3. Write an algorithm that ouputs the largest and second largest values in the
array `s[1], ..., s[n]`. Assume that n>1 and the values in the array are
distinct.
```"c++"
void Find_Largest_And_Second_Largest(const int[] array, const int array_size)
{
    // array_size > 1
    // values are distinct
    int largest_val, second_largest_val;
    largest_val = array[1];
    for(int array_counter = 2; array_counter <= array_size; array_counter++)
    {
        if(array[array_counter] > largest_val)
        {
            second_largest_val = largest_val;
            largest_val = array[counter];
        }
    }
    std::cout << "Largest: " << largest_val << std::endl;
    std::cout << "Second largest: " << second_largest_val << std::endl;
}
```

4. Do `3.` for the smallest and second smallest values.

5. Write an algorithm that outputs the smallest and largest values in the array s[1], ..., s[n]

6. Write an algorithm that return the index of the first occurence of the largest element in the array s[1], ..., s[n]

7. Write an algorithm that return the index of the last occurence of the largest element in the array s[1], ..., s[n]
