# Program calculate year of birth!

## Summary

Create program that calculates the year of birth.

## Tasks

* define the variables `age` and `name`
* make a calculation for the year in which the person was born
* print out "OMG <person>, you are <age> years old so you were born in <year>" with the correct values

### Second Part

* prompt the user for input and re-assign the variable `age` and `name`
* figure out a way to account for if the person's birthday has already happened this year or not

### Extra

* go look into the library time
* print out the amount of hour this person has lived

## Acceptance Criteria

* program defines the variable `age` and `name`
* program prints the string "OMG <person>, you are <age> years old so you were born in <year>"

```python
import datetime

currentDate = datetime.datetime.now()

while True:
        deadline= input ('Plz enter your date of birth (dd/mm/yyyy) ')
        try:
            deadlineDate= datetime.datetime.strptime(deadline,'%d/%m/%Y')
            break
        except ValueError:
            print ("Invalid input please try again")

print(deadlineDate)
daysLeft = currentDate - deadlineDate
print(daysLeft)

years = ((daysLeft.total_seconds())/(365.242*24*3600))
yearsInt=int(years)

months=(years-yearsInt)*12
monthsInt=int(months)

days=(months-monthsInt)*(365.242/12)
daysInt=int(days)

hours = (days-daysInt)*24
hoursInt=int(hours)

minutes = (hours-hoursInt)*60
minutesInt=int(minutes)

seconds = (minutes-minutesInt)*60
secondsInt =int(seconds)

hoursLived = (yearsInt *24*3600) + hoursInt

print('You are {0:d} years, {1:d}  months, {2:d}  days, {3:d}  hours, {4:d} minutes, '
      '{5:d} seconds old.'.format(yearsInt,monthsInt,daysInt,hoursInt,minutesInt,secondsInt))
print('OMG , you are {years} years old so you were born in {date}'.format(years=yearsInt, date=deadlineDate))
print('You lived: {}h in total' .format(hoursLived))

```
### Potential Outcome
```python
Plz enter your date of birth (dd/mm/yyyy) 02.02.2000
Invalid input please try again
Plz enter your date of birth (dd/mm/yyyy) 20/02/2000
2000-02-20 00:00:00
7794 days, 16:03:09.126538
You are 21 years, 4  months, 2  days, 20  hours, 8 minutes, 54 seconds old.
OMG , you are 21 years old so you were born in 2000-02-20 00:00:00
You lived: 1814420h in total
```