# Mean-Variance-and-Cross-Correlation

# AIM

To write a Scilab program to find the mean and variance of two random variables X and Y, and to find the correlation between two given sequences.

# APPARATUS REQUIRED:
• Computer with i3 Processor

• SCI LAB

# THEORY

Mean:

The mean of a random variable gives the average value of that variable over a given range. It shows the central tendency of the data.

Variance:

The variance shows how much the values of a variable differ from its mean value. A high variance means the values are more spread out, while a low variance means they are close to the mean.

Correlation:

Correlation measures how closely two signals or sequences are related. If two signals are similar in shape, they will have a high correlation value. Correlation is often used to compare signals or patterns.
In this program, integration is used to calculate the average and spread (mean and variance), and the built-in correlation function in Scilab is used to compare two input sequences.

# ALGORITHM

1.Start the program and clear the previous data.

2.Define a function for X to calculate its value within a given range.

3.Integrate this function between two limits to get the mean of X.

4.Do the same steps for Y to get its mean.

5.Define two more functions for X and Y to get their second order values.

6.Integrate those functions to get the mean of the square values.

7.Subtract the square of the mean from the mean of the square to get the variance.

8.Display the mean and variance values for both X and Y.

9.Ask the user to type two sequences as input.

10.Use the correlation function in Scilab to find how the two sequences are related.

11.Plot the correlation result on a graph for observation.

# PROGRAM
```
clear; clc;
function X = f(x)
    z = (5 - x).^2;
    X = x .* z;
endfunction
a = 0; b = 1;
EX = intg(a, b, f);
function Y = c(y)
    z = (5 - y).^2;
    Y = y .* z;
endfunction
EY = intg(a, b, c);
function X2 = g(x)
    z =  (5 - x).^2;
    X2 = (x.^2) .* z;
endfunction
EX2 = intg(a, b, g);
function Y2 = h(y)
    z = (5 - y).^2;
    Y2 = (y.^2) .* z;
endfunction
EY2 = intg(a, b, h);
vX2 = EX2 - (EX)^2;
vY2 = EY2 - (EY)^2;
disp(EX, "i) Mean of X =");
disp(EY, "   Mean of Y =");
disp(vX2, "ii) Variance of X =");
disp(vY2, "   Variance of Y =");
x= input("type in the reference sequence="); 
y= input("type in the second sequence="); 
n1=max(size(y))-1;
n2=max(size(x))-1;
r=corr(x,y,n1);
plot2d3('gnn',r);

```
# OUTPUT:

<img width="1388" height="773" alt="image" src="https://github.com/user-attachments/assets/a436349e-8aa1-487b-83e3-4ed02167ef84" />

<img width="743" height="598" alt="Screenshot 2025-11-04 103155" src="https://github.com/user-attachments/assets/91b77a7f-728f-4e64-bdd5-d644cb5e4be9" />
