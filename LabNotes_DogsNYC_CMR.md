# Notes on the Dogs of NYC homework
## Week 3 - Lede Program

### Question 1: How many dogs are registered in NYC?
---
First, I imported the url from the library

```python
urllib.urlretrieve("http://www.jonathansoma.com/lede/dogs.csv", "dogs.csv")
```

Now, I counted how many dogs there are in NYC according to the sample

```python
dogs = open("dogs.csv", "rb")
import csv
with open('dogs.csv', 'rb') as csvfile:
    dogcsv = csv.reader(csvfile, delimiter=',')
    count = 0
    for dog in dogcsv:
        count = count + 1
    print count
```

This gave me the result, 81542

### Question 2: How many dogs are registered in Brooklyn?
---
First I figured out that the boroughs were listed under *Column 9*

```python
dogs = open("dogs.csv", "rb")
import csv
with open('dogs.csv', 'rb') as csvfile:
    dogcsv = csv.reader(csvfile, delimiter=',')
    count = 0
    for dog in dogcsv:
        print dog[9]
        count = count + 1
        print count
```

Once I confirmed that's where the name of the boroughs were, I looked at the number of occurrences of "Brooklyn" in the row

```python
dogs = open("dogs.csv", "rb")
import csv
with open('dogs.csv', 'rb') as csvfile:
    dogcsv = csv.reader(csvfile, delimiter=',')
    count = 0
    for dog in dogcsv:
        if dog[9] == "Brooklyn":
                count = count + 1
    print count
```

I repeated the procedure with the rest of the boroughs. 

### Question 3: How many dogs named Max live in the Lower East Side?
---
Next I looked at how many dogs there are named Max in the lower east side. There are three zip codes in this area: 10002, 10003 and 1009. I found the zip codes using [this website](http://www.health.ny.gov/statistics/cancer/registry/appendix/neighborhoods.htm). 

```python
import csv
with open('dogs.csv', 'rb') as csvfile:
    dogscsv = csv.reader(csvfile, delimiter=',')
    rows = list(dogscsv)
    row = rows[0]
    count = 0
for row in rows:
        if row[0] == "Max" and row[10] == "10003":
            count = count + 1
        if row[0] == "Max" and row[10] == "10002":
            count = count + 1
        if row[0] == "Max" and row[10] == "10009":
            count = count + 1
print count 
```


### Question 4: How many dogs are named Max in Bed Stuy?
---
I used the same method for Bed Stuy, where the zip codes are 11205, 11206, 11216, 11221, 11233 according to [this website](http://www.city-data.com/neighborhood/Bedford-Stuyvesant-Brooklyn-NY.html)

```python
import csv
with open('dogs.csv', 'rb') as csvfile:
    dogscsv = csv.reader(csvfile, delimiter=',')
    rows = list(dogscsv)
    row = rows[0]
    count = 0
for row in rows:
        if row[0] == "Max" and row[10] == "11205":
            count = count + 1
        if row[0] == "Max" and row[10] == "11206":
            count = count + 1
        if row[0] == "Max" and row[10] == "11216":
            count = count + 1
		if row[0] == "Max" and row[10] == "11221":
            count = count + 1
		if row[0] == "Max" and row[10] == "11233":
            count = count + 1
print count 
```

---
> This is a test of blockquotes in Markdown, inspired by [this guide](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

--- 
***

	