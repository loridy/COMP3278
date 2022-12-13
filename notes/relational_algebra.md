# Relational Algebra 

## Basic Operators

1. Selection $\sigma$. 
    - eg. Select all authors called "May": 
    - $\sigma_{name=May}(Author)$
2. Projection $\pi$. 
    - eg. Report **bookID** and **title** of all books
    - $\pi_{bookID, title}(Book)$
4. Union $\cup$. 
    - must have same attributes
    - eg. Find all names in CD and DVD tables
    - $\pi_{name}(CD) \cup \pi_{name}(DVD)$
6. Set Difference -. 
    - eg. Find ID of students who haven't submitted assignment
    - $\pi_{studentID}(Student) - \pi_{studentID}(Submit)$
8. Cartesian Product $\times$.
    - eg. Display the date of tutorials of the course
    - $\pi_{Course.date}(\sigma_{Course.name=xxx}(\sigma_{Course.courseID=Tutorial.courseID}(Course \times Tutorial)))$
10. Rename $\rho$.

## Additional Operators

1. Set Intersection $\cap$.
2. Natural Join $\Join$.
3. (Left Outer Join/ Right Outer Join)
4. Assignment $\leftarrow$.
5. Division $\div$.

## Extended Operators

## Algebraic properties

1. Only the final operations in a sequence of projection operations are needed
2. Conjunctive selection operations can be deconstructed into a sequence of individual selections
3. Selection operations are commutative
4. Natural join operations are associative
5. The selection operation distributes over the natural join operation under the following two conditions
    - It distributes when all the attributes in selection condition involve only the attributes of one of the expressions(say, E1) being joined
    - The selection distributes when selection condition p1 involves only the attributes of E1 and p2 involves only the attributes of E2
6. The projection operation can distribute over the natural join operation.
7. The set operations union and intersections are commutative
    - The set different operation is NOT commutative
8. The set operations union and intersections are associative
    - The set different operation is NOT associative
9. The selection operation distributes over the union, intersection and set difference operations
10. The projection operation distributes over the union operation
    - Projection does not distribute over intersection and set difference
