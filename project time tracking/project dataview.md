
---

Feel free to delete these, they're just examples of how the dataview plugin runs the query. If you want to move the location of your project dataview file, you will need to adjust the file paths in the code blocks below. 

```
TABLE WITHOUT ID sum(rows.time) AS "total hours"
FROM "project time tracking" OR "project time tracking/archive"
WHERE file.day >= date(today)-dur(6 days) 
FLATTEN time
GROUP BY true
```

```
TABLE WITHOUT ID dateformat(file.day, "MM/dd") AS date, sum(time) AS "total", task, time, desc FROM "project time tracking" OR "project time tracking/archive"
WHERE file.day >= date(today)-dur(6 days) AND file.day <=date(today)
SORT file.day DESC
```

---

```dataview
TABLE WITHOUT ID sum(rows.time) AS "total hours"
FROM "project time tracking" OR "project time tracking/archive"
WHERE file.day >= date(today)-dur(6 days) 
FLATTEN time
GROUP BY true
```

```dataview
TABLE WITHOUT ID dateformat(file.day, "MM/dd") AS date, sum(time) AS "total", task, time, desc FROM "project time tracking" OR "project time tracking/archive"
WHERE file.day >= date(today)-dur(6 days) AND file.day <=date(today)
SORT file.day DESC
```


