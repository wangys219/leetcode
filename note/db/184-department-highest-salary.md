# 部门工资最高的员工

## mysql实现

```
select d.`Name` as Department, e.`Name` as Employee, e.Salary as Salary
from department d, employee e
where d.Id = e.DepartmentId
and e.Salary >= (
select Salary
from employee
where DepartmentId = d.Id
order by Salary desc
limit 1
)
```

```
select d.Name as Department, e.Name as Employee, e.Salary 
from Employee e,Department d 
where e.DepartmentId=d.id 
and e.Salary,e.DepartmentId) in (
select max(Salary), DepartmentId
from Employee
group by DepartmentId
)
```
