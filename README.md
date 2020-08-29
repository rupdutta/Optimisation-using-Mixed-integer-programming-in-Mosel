# Optimisation-using-Mixed-integer-programming-in-Mosel
Assignment Problem - Hungarian Method
Question - 
A company offers a security service by placing guards within the grid squares shown in the Table below. The objective is to minimise total pay costs. Their customer requires at least two guards per row and at least two guards per column. The Table below shows the maintenance pay per guard paid by the customer for each location.

[Matrix locations and mainteance pay]
1,1 - 6
1,2 - 10
1,3 - 10
1,4 - 9
2,1 - 5 
2,2 - 7 
2,3 - 5
2,4 - 10
3,1 - 3
3,2 - 7
3,3 - 6
3,4 - 9
4,1 - 9
4,2 - 4
4,3 - 7
4,4 - 8

The customer is willing to increase the amount of they pay by 10% if the firm will provide an even number of guards per row and per column. An even number is an integer which yields no remainder when divided by two. Show how your (I)LP model for could be adjusted to accommodate the amended requirements.

Soln - 
This problem can be categorized as an assignment problem, which falls under the transportation modelling technique. Although the transportation simplex method appears to be very efficient, however for assignment problems, the transportation simplex is often very inefficient. A high degree of degeneracy in an assignment problem may cause the transportation simplex to be an inefficient way of solving assignment problems. Due to the following reason, the Hungarian method is applied to solve the assignment problem by assuming that a single grid can only have one security guard. However, the problem does not explicitly state that assumption. Thus, an alternate approach is also displayed in the implementation of the problem.

Mosel Implementation - 
The software implementation of the problem statement can be shown in the form of a pseudocode to show an outline or a rough draft of the code in Mosel.
The pseudocode is as follows:
Algorithm: Integer Programming Mosel Model
Input: IP model with sixteen decision variables.
Output: Get minimized optimal solution and add 10% increased pay condition
1. Declare all decision variables, the objective function and all constraints.
2. Initialize all object coefficient values from the ‘guard.dat’ file
3. for each constraint do:
plot the boundary and feasible region.
end-do
4. If the intersection of all constraints is empty then
terminate and return the print status procedure.
5. Else
for each corner point of the feasible solution space do:
Calculate the objective function value.
end-do
end-if
6. Return the co-ordinates of the corner point that yield the optimal solution
7. Calculating each row and column stating an even condition with an If loop
8. Recalculate objective function by adding increased price and return the recalculated objective function’s solution value.

According to the algorithmic approach taken and the software implementation , one can clearly state the two approaches followed:
The Binary Integer Programming Approach which will invariably restrict all decision variables to have integer values of only zero and one.
The Total Integer Programming Approach which will invariably restrict all decision variables to have integer values only. This means that discrete values as solutions are expected.
Since this problem explicitly states to show an ILP model to accommodate the amended requirements, hence it is considered building an ILP model assuming 2 guards in a grid square.
Considering the second approach which is the Integer Programming approach, the optimal solution that I have come across is 42.
I have used the Simplex Method to solve this problem in Mosel. The observation discovers that if a constant is added to each cost in a row (or column) of a balanced assignment problem, then the optimal solution to the problem is unchanged. If I add R to each cost in the first row of the security guard problem, then
The new objective function = old objective function + R * (x(i))
As any feasible solution to this security problem must have,
x(i) >= 2 (for i = 1..4 )
new objective function + old objective function + R
Thus, the optimal solution to the Security Guard problem remains unchanged if a constant R is added to each cost in the first row. A similar argument applies to any other row or column. The Hungarian method alternatively proves the same on all occasions.


