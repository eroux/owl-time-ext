# owl-time-ext-tib
Owl Time ontology extension for Luni-solar Indic calendars.

### Concepts

Here is a list of concepts that appear in Luni-solar Indic calendars:

##### Month of the year

A month of the year has two aspects:
- a name: in an ordered sequence of 12, which we define as resources
- duplicate tag: two consecutive months can have the same name, in which case the second is considered duplicate

Note: due to the [open world assumption](https://en.wikipedia.org/wiki/Open-world_assumption) of RDF, if a month of the year is not duplicate, it must be indicated explicitely.

Note: in specific calendar systems (not all), a month can be ommited and the calendar can go from month number 2 (in the sequence of 12 names) to month number 4.

Note: in most systems, a month starts at the new moon, but in some others, it starts at the new moon.

##### Day of the month

A day of the month has the following characteristics:
- a day index: a number between 1 and 30
- duplicate tag: two consecutie days can have the same index, in which case the second is considered duplicate

##### Day of the week

For the day of the week we use the individuals of the OWL-Time ontology, and provide translations.

Note that some Bhutanese calendars [are one day of the week off](http://kalacakra.org/calendar/bhut_art.htm). In that case when a day is considered to be a Monday in Bhutan, it is indicated as a Monday, even though it is a Tuesday in most other calendars.

##### jovian cycle index

Some systems have the notion of a 60 years jovian cycle, and in some of these each 60 years cycle has an index, which is a number starting at 1.

##### year in jovian cycle

The 

### Assumptions

- For one calendar system, there is only one 