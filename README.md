# Pewlett-Hackard-Analysis

## Project Overview

Pewlett Hackard, a very large organization has noticed a potential trend of a large chunk of employees retiring recently.  I have been tasked with analyzing a set of 6 csv files pertaining to employee background information in order to find out how many current employees will be retiring and which departments these retiring employees work in so the organization can plan accordingly. In addition, I have qualified employees who may be retiring soon for the organizations new mentorship program.

## Results
### Number of Retiring Employees by Title
- A total of 90,398 will be retiring in the near future
- The majority of employees that will be retiring soon are in Senior positions
- Only 2 managers are due to retire 

### Employees Eligible for Mentorship Program

- 1,549 employees set to retire are eligible for the mentorship program 


## Summary

1. here are 90,398 roles that will need to be filled across 7 different categories in the organization.  Most of these are senior positions, only 2 manager positions will be left to fill.

2. 1,549 employees available for the mentorship program,  there are not enough qualified employees ready for retirement in the departments to mentor the next generation of employees.  Each mentor would have to have about 58 mentees, which is much too large of a workload for any employee, especially part-time retiring employees.  By breaking down the mentorship eligible employees by department in the query below, we can see that the employees are proportionally spread to the employees that are retiring but there is still too few employees to mentor the retiring employees.  

```
SELECT COUNT(title), title
FROM mentorship_eligibility
GROUP BY title
ORDER BY COUNT(title) DESC;
```
mentorship eligibility by 1 year to employees born in 1964 there are 19,905 eligible employees which is much more manageable.  The 'WHERE' line of the query extending the eligible employees and visualize the department breakdown of the extended filter is shown below.

```
WHERE (e.birth_date BETWEEN '1964-01-01' AND '1965-12-31')
```
