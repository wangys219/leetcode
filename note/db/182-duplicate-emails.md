#

## mysql实现

```
select Email
from (select Email,count(*) as count
from person
group by Email) as temp
where count > 1
```

```
select Email
from person
group by Email
having count(Email) > 1
```

```
select distinct p1.Email as Email
from person p1, person p2
where p1.Email = p2.Email
and p1.Id != p2.Id
```
