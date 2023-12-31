Its also called the TDZ
A very good example to Understand TDZ is 

#### Illustration 1 of TDZ 
![[Screenshot 2023-12-23 at 4.43.12 PM.png|700]]

Here though `studentName` is let initialised before using it in function, but its called in the TDZ zone of the variable. Hence the error. 

Rather the code should be 
![[Screenshot 2023-12-23 at 4.44.37 PM.png|600]]

we have moved the let to the top. 