# owl-time-ind

[Owl Time ontology](https://www.w3.org/TR/owl-time/) extension for Indic calendars.

## Scope

The scope if this proposed extension is to cover most calendars of Indic origin, with a focus on Buddhist ones for the first iteration. This includes:
- Himalayan calendar systems (Tibetan, Bhutanese, Newari, etc.)
- South-East Asian calendar systems (Cambodian, Burmese, etc.)
- because these are used very extensively, we also define properties for animal, gender and elemement of years, even though they are of Chinese origin

We limit ourselves to year cycles, years, months and days, future extensions might cover:
- Chinese calendars
- Hindu calendars
- more precise units of time (hours, minutes, etc.)
- astrological properties

## Design Philosophy

The purpose of this ontology is not only to be used in modern controlled environments, but also to record all dates present in historical documents, some of which can be incomplete, ambiguous or even erroneous (ex: February 30th 2020). We take inspiration from [GODOT](https://godot.date) for this part.

#### Use cases

The use cases focus on Digital Humanities:
- encoding a date indicated in a document (most of the time a year or a date)
- encoding one or several possible interpretations for the Gregorian equivalent of a date 

## Concepts

Here is a list of concepts that we intend to cover:

##### General perspective

Although some details inevitably differ between the usage in different calendar systems, we consider that the general concepts of:
- day
- month
- week
- year

are similar enough with those described in the OWL-Time ontology to use the related classes and properties directly, with no redefinition.

##### Month of the year

A month of the year has two aspects:
- a name: in an ordered sequence of 12, which we define as resources
- duplicate tag: two consecutive months can have the same name, in which case the second is considered duplicate

Note: due to the [open world assumption](https://en.wikipedia.org/wiki/Open-world_assumption) of RDF, if a month of the year is not duplicate, it must be indicated explicitely.

Note: in specific calendar systems (not all), a month can be ommited and the calendar can go from month number 2 (in the sequence of 12 names) to month number 4.

Note: while the 12 month names are always in the same order, the cycle can start on different months according to the calendar system.

Note: in most systems, a month starts at the new moon, but in some others it starts at the full moon.

##### Day of the month

A day of the month has the following characteristics:
- a day index: a number between 1 and 30
- duplicate tag: two consecutie days can have the same index, in which case the second is considered duplicate

##### Day of the week

For the day of the week we use the individuals of the OWL-Time ontology, and provide translations.

Note that some Bhutanese calendars [are one day of the week off](http://kalacakra.org/calendar/bhut_art.htm). In that case when a day is considered to be a Monday in Bhutan, it is indicated as a Monday, even though it is a Tuesday in most other calendars.

#### Eras

Some calendars have the concept of era. We provide an individual for each one.

#### Jovian cycle

Some systems have the notion of a 60 years cycle (ex: Tibetan rabjung) or of a jovian cycle (based on the position of Jupiter). Both cycles have the same origin and name years in a very similar fashion. We thus choose to conflate them in one concept which we name jovian cycle.

Note: in some cases jovian cycles can have leap years (see [Sewell 1896](https://archive.org/details/indiancalendarwi00seweuoft) p. 32 & seq.).

##### Jovian cycle index

In some calendar systems (ex: Tibetan), each jovian cycle is assigned an index (ex: the jovian cycle of index 1 starts in 1027 in Tibet). We represent it with a number. In order to allow references back to before the first jovian cycle, we don't put any restriction on the index (it can be negative).

##### Year name in jovian cycle

The jovian cycle is divided in 60 names, for which we provide individuals.

## Bibliography

- **Henning2007**: Henning E., *Kālacakra and the Tibetan Calendar*
- **Sewell1896**: Sewell R., *The Indian Calendar*
- **Eade1995**: Eade J.C., *The Calendrical Systems of Mainland South-East Asia*
- **Billard1962**: Billard R, *L'Astronomie Indienne*


## RDF Conventions

We follow the conventions to use English for the identifiers of property and class names. We do not follow that convention for individuals, because they don't have well accepted translations in English and have a lot of variations in spellings and scripts in their original languages. We thus use non-semantic identifiers (`:DOM09834`) in that case, à la RDA.

## TODO

- can/should xsd:gDay be used as a datatype for indicating the day of the month?

## License

The work is under the copyright of the authors listed below and is distributed under the [CC0 License](LICENSE).
