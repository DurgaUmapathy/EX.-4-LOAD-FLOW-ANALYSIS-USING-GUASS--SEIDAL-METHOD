# EX.-4-LOAD-FLOW-ANALYSIS-USING-GAUSS--SEIDAL-METHOD
# AIM: 
To carry out the load flow analysis of the given power system by Gauss-Seidal 
method. 

# SOFTWARE REQUIRED:
ETAP Software
 
# THEORY: 
Load flow analysis is the study conducted to determine the steady state 
condition of the given system. A large number of numerical algorithms have been developed 
and Gauss Seidal method is one of such algorithms. 
 
# PROBLEM FORMULATION: 
   
The performance equation of a power system may be written as  
[Ibus]=[Ybus][Vbus] ----------------------------(1) 
Selecting one of the buses as reference bus, we get (n-1) simultaneous equations. The bus 
loading equations can be written as: 
    
i
i i
i V
jQ P I − = ------------------------------------------ (2) 
 Where i=1, 2, 3…n. 
     
=
= n
k
k ik i i
VYV P
1
* Re------------------------------- (3) 
    
=
−= n
k
k ik i i
VYV Q
1
* Im---------------------------- (4) 
The bus voltage can be written in the form of  





 − = 
=
n
j
j ij i
n
i
VY I Y V
1
0.1--------------------------- (5) 
Where i=1, 2, 3 …n) & I is not equal to slack bus. 
Substituting i in the expression for Vi we get 





 − − = 
 =
n
i j j
o
i ij o
i
i i
n
new
i
VY V
jQ P
Y V
,1
*
0.1 
If the latest available voltage is used in the above expression, we get, 





 − − − =  
+= =
n
i j
o
j ij
n
j
n
j ij o
i
i i
ii
i
VY VY V
jQ P
Y V
1 1
*
0.1 
The above equation is required formula. This equation can be solved for bus voltages in 
iterative manner. During each iteration, we compute all the bus voltages and check for the 
convergence is carried out by comparison with voltages obtained at the end of previous 
iteration. 
 
  After the solution is obtained, the slack bus real and reactive powers, the 
reactive power generation at the other generator buses and line flows can be calculated. 
 
  This method is easier when compared with other methods, because the 
calculations are very simple. This is used for making a good initial start for Newton-Raphson 
method.


# ALGORITHM: 
```
1. Read the data such as line data, specified bus powers, specified voltages,    
      Q limits at generator buses and tolerance for convergence. 
2. Compute Y-bus matrix. 
3. Initialize all the bus voltages. 
4. Iter=1. 
5. Consider i=2 where i is the bus number. 
6. Check whether this P-V bus or P-Q bus. If it is P-Q bus, go to step 8. Otherwise   
      go to next step.  
7. Compute Qi. Check for Q- limit variation. Qgi=Qi+QLi. 
If Qgi>Qimax, then equate Qgi to Qimax there by converting it in to   P-Q bus. Qi=Qimax
Qi, then go to step 8.   
Similarly, if Qgi<Qimin, then equate Qgi to Qimin there by converting it in to   P-Q bus. 
Qi=Qimin-QLi, then go to step 8.   
 If Qgi is with in the upper and lower limits, don’t change Qgi. where 
 Qi=Qgi-QLi, then go to step 8. 
8. Calculate the new value of the bus voltage using Gauss-Seidal formula.   
 




 − − − =  
+= =
n
i j
o
j ij
n
j
n
j ij o
i
i i
ii
i
VY VY V
jQ P
Y V
1 1
*
0.1 .Adjust the voltage magnitude of   
      the bus to specified magnitude if Q limits are not violated. 
9.   If all the buses are considered, go to step 10.Otherwise increment  
      the bus number i=i+1 and go to step 6. 
10.  Check for convergence. If there is no convergence go to step 12. 
11.  Update the bus voltages using the formula 
        Vi= Vi old + α (Vinew – Vi old)        (i= 1, 2, 3 …n) 
12. Calculate the slack bus power at P-V buses, real and reactive line  
      flows, real and reactive line losses and print all the results     
      including all the complex bus voltages and all the bus angles.  
13.  Stop.
```

# CIRCUIT DIAGRAM:
# OUTPUT: 
# RESULT:
Thus the load flow analysis using gauss-seidal method is successfully done using etap software and the 
output is obtained.

