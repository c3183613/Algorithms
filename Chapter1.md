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
1. Write an algorithm that find the smallest element amount a, b, and c
```
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

```
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
finiteness, corectness, generality- if any, are lacking in the following?
Explain. The input is a set of S integers and an integer m. The ouput is all
subsets of S that sum to m.
