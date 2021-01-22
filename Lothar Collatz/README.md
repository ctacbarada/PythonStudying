# Scenario
In 1937, a German mathematician named Lothar Collatz formulated an intriguing hypothesis (it still remains unproven) which can be described in the following way:

1. take any non-negative and non-zero integer number and name it **c0**;
2. if it's even, evaluate a new **c0** as **c0 ÷ 2**;
3. otherwise, if it's odd, evaluate a new **c0** as **3 × c0 + 1**;
3. if **c0 != 1**, skip to point 2.

The hypothesis says that regardless of the initial value of c0, it will always go to 1.

<br/>Of course, it's an extremely complex task to use a computer in order to prove the hypothesis for any natural number (it may even require artificial intelligence), but you can use Python to check some individual numbers. Maybe you'll even find the one which would disprove the hypothesis.

<br/>Write a program which reads one natural number and executes the above steps as long as c0 remains different from 1. We also want you to count the steps needed to achieve the goal. Your code should output all the intermediate values of c0, too.

<br/>Hint: the most important part of the problem is how to transform Collatz's idea into a while loop - this is the key to success.

<br/>
<br/>

## Test Data

---
Sample input: 15

Expected output:
<br/>46
<br/>23
<br/>70
<br/>35
<br/>106
<br/>53
<br/>160
<br/>80
<br/>40
<br/>20
<br/>10
<br/>5
<br/>16
<br/>8
<br/>4
<br/>2
<br/>1
<br/>steps = 17

---

Sample input: 16

Expected output:
<br/>8
<br/>4
<br/>2
<br/>1
<br/>steps = 4

---

Sample input: 1023

Expected output:
<br/>3070
<br/>1535
<br/>4606
<br/>2303
<br/>6910
<br/>3455
<br/>10366
<br/>5183
<br/>15550
<br/>7775
<br/>23326
<br/>11663
<br/>34990
<br/>17495
<br/>52486
<br/>26243
<br/>78730
<br/>39365
<br/>118096
<br/>59048
<br/>29524
<br/>14762
<br/>7381
<br/>22144
<br/>11072
<br/>5536
<br/>2768
<br/>1384
<br/>692
<br/>346
<br/>173
<br/>520
<br/>260
<br/>130
<br/>65
<br/>196
<br/>98
<br/>49
<br/>148
<br/>74
<br/>37
<br/>112
<br/>56
<br/>28
<br/>14
<br/>7
<br/>22
<br/>11
<br/>34
<br/>17
<br/>52
<br/>26
<br/>13
<br/>40
<br/>20
<br/>10
<br/>5
<br/>16
<br/>8
<br/>4
<br/>2
<br/>1
<br/>steps = 62

<br/>
<br/>
<br/>

## Here my solution
```
c0 = int(input('Enter a any non-negative and non-zero integer number:'))
counter = 0
while c0 != 1:
    if c0 % 2 == 0:
        c0 /= 2
        counter += 1 
        print(int(c0))
    else:
        c0 = 3 * c0 + 1
        counter += 1
        print(int(c0))
print('Steps = ', counter)