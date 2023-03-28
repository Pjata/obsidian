#### Tasks
##### Due Today
```tasks
not done
due today
```
##### Due This Week
```tasks
not done
due after yesterday
due before in 1 weeks
```
##### Due This Month
```tasks
not done
due after yesterday
due before in four weeks
```

##### Past Due
```tasks
not done
due before date(today)
```
##### No Due Date
```tasks
not done
no due date
```
#### Other Tasks

```dataviewjs
dv.taskList(dv.pages('-"Templates"').file.tasks
.where(t => !t.completed && !t.text.includes("@frank") &&
!t.text.includes("#task")
))
```