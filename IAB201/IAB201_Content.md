
# Week 1

I ceebs, basic shit like what is orm, what is modelling etc. If you need to know this watch the lectures

# Week 2

This week has a focus on Data and information modelling
- Fundamentals

- Entity relationship

- ORM

- Design Procedures

## Functions of an information system

An information system comprises of 3 elements

- Memory
    -I need to know what the information systems looks like right now

- Informative
    - I need to know why the information systems looks the way it does

- Active
    - I need to be able to provide actions that can change the current system

This is all achieved through conceptual modelling.

### Conceptual modelling

Is the activity that elicits and describes the general knowledge a particular info system needs to know, also known as your conceptual schema (aka IFB105)

![alt text](9-Figure1-1.png)

If you remember these things you know what conceptual modelling is

### What is state?

A state of a domain consists of set of relevant properties, with a domain being the objects and relationships between each states.

A state of domain can consist of a set of objects, a set of relationships and a set of concepts in which they are classified.

### Required domain knowledge

There are a few functions that need to be kept in mind when modelling

- Memory
    - Memory functions maintain representations of states
        - All states need to be represented in our models

- States can vary over time
    - Therefore we must define all potential state changes.

- Representations of states must be consistent
    - We must define when a representation of state is consistent

- Ansering queries require an inference capability
    - Derivation Rules
        - specifiying how a new data type can be derived from the original data

## Concepts and entities

- A concept is an abstract/generic idea generalised from specific instances.
    - A person

An entity consists of 2 things.

- Entity types
    - A concept whose instances are individual, identifiable objects
        - To read a book
    - All entity types have a name that is
        - Unique
        - Meaningful to people who act in the domain
        - Are common nouns in the singular form

- Entity
    - An object that is an instance of an entity type
        - A book

![alt text](image.png)

Our concept (a person) who we represent with the name charlotte has tthe entity of a person

Concept flow down through to entity type and then entities

A student (Concept) requires people (entity type), which are then populated with people (entities)

### Attributes

Is a property of an entity, of interest to the domain, is used to qualify, identify ,classify, quantify or in any other way expresss the state of that entity. Attributes should be used to help differentiate entities from one another

Lets take a person a example

The combination of date of birth, name and a signature are usually more than enough to help u differentiate one person from another. Whereas hair colour, eye colour and height aren't as useful.

Another example would be a car. Rego, year of manufacture, the body type, the manufacturer are all good attributes, the top speed and the history of accidents is less so.

An entity should have no more than 8 attributes, if it requires more. You may need to re-analyse your entity

### Cardinality constraints

Is the constraint of an entity type playing a role in a relationshiop. This constraint places a limit on both the minimum and maximum number of entities that can appear in this relationship

```min >= 0, max >= min, max > 0```

To illustrate

Card(Person reads book) = (0,2)
Card(Book is read by Person) = (0,1)

Meaning that a person can read up to 2 books at any given time, while a book can only be read by either noone or one person at a time.

### Entity types and reference modes

Information systems can only use facts as stated - people can misinterpret facts (see politcal argument ever)

The description of an entity MUST specify the entity type being referred to

to illustrate.

- Lee is located in '10b'
    - The patient james is located in the ward '10b'
        - The patient with fname james is located in the ward with name '10b'

## What is information?

Information is data + semantics. With data being the items stored in our system, and the semantics being the meaning behind the data.

Only by considewring the semantics of teh Universe of Discourse (UoD) can a robust, quality information system be designed


## Where is information stored?

Database. If you dont remember IFB105 idk what to tell you pookie

## Elementary facts

A fact that can be explained in a sentence

```Stevie wonder plays keyboard.```

If we want to express that explicitly.

```Person Stevie Wonder plays instrument keyboard. - Concept person plays entity instrument.```

It is a simple statement about the domain.

## Predicates

Whilst elementary facts assert that our entities play roles within our systems, predicates can be used to specify roles. Predicates are expressed via a sentence.

### Surface structures vs deep structures

Where the arity of our predicates are greater than one, we can read them in multiple ways (binary or greater)

![alt text](image-1.png)

`Mary works in sales | Sales employs Mary`

whilst they have different surface structures, they share the same deep structure.

If our predicate was Unary, it would only have a surface structure.

## Keep this in mind

![alt text](image-2.png)

# Week 3

Is a consolidation week, no new content.

# Week 4

![alt text](image-16.png)

## Domains

At any given time, the state of a doman consistes of:

- Objects
- Relationships
- A set of concepts that we use to classify them with.

Eg: We can have our entities of person and vehicle with the relationship of drives.

## Conceptual Modelling Part 2

This lecture takes a focus on conceptual modelling langauges. Namely Entity-Relationship Modelling (ER) and Unified Modelling Language (UML)

### ER

![alt text](image-17.png)

#### ER Language variants

There are a multitude of different notation sets in use for ER. With no standard in place. We will be using the Ellis-Barker (also known as just Barker) notation, which is one of the more popular options

### Barker Notation

Barker is advantagous for us as it:

- Was designed for easy understandability
- Avoids the use of technical components that have no relevance to/may confuse a business user
- Provides limited and consistent set of sumbols
- Provides a complete, concise, clear and unambigious statement of informtion requirements.

Barker Notation is as follows

- We denote a relationship with a line, having

#### Syntax

- An entity type is rounded rectangle with the name at the top and tha attributes at the bottom.

![alt text](image-18.png)

And can use a set of markers to help differentiate the attributes

![alt text](image-19.png)

- We denote a relationship with a line, having an entity type at each end
- The line is composed of two halfs, each half referring to the role the adjacent entity type plays in the realtionship
    - A solid line indicates mandatory
    - A dotted line indicates optional
    - Cardinality is denoted by the presence of a 'Crows Foot' notation joining the line to the entity

![alt text](image-20.png)

    - There are 16 possible relationship combinations

![alt text](image-21.png)

![alt text](image-22.png)

##### Understanding solid to dotted lines

![alt text](image-23.png)

Here we can see that Hire agreements are required for vehicles. But we don't own every car, therefore not every vehicle requires one.

A hiring agreement cannot exist without a vehicle. But a vehicle can exist without a hiring agreement

##### Understanding Many to Many relationships

To make a many to many relationship more readable. We can notate it like this to help improve clarity:

![alt text](image-24.png)

#### Cardinality Cheat-Sheet

![alt text](image-25.png)

### Similarity vs Specificty

In real life we can encounter exampels of objects that share characterisitcs with others. But have a few specific differences that make them distinct from one another. For example, All dogs are mammals. but not all mammals are dogs.

### Supertypes and subtypes

Supertypes are a generic entity type related to one or more entity sub-types and contains common characteristics.

Subtypes contain all of the characteristics of the super type alongside some unique characteristics.

#### Subtype Rules

![alt text](image-26.png)

# Week 5

This is another consolidation week. 

# Week 6

# Conceptual Schema Design Procedure

- Transform familiar examples into elementary facts and apply quality checks
- Draw the fact types and apply a population check
- Check for entity types to be combined and note any arithmetic derivations
- Add uniqueness constraints and check arity (length) of fact types
- Add mandatory role constraints and check for logical derivations
- Add value, set comparison and subtyping constraints
- Add other constraints and perform final checks

## Add uniqueness constraints and check the arity of fact types

I am just going to paste the ones that I feel are important to remember
![alt text](image-34.png)

![alt text](image-35.png)

![alt text](image-36.png)

## Add mandatory role constraints and check for logical derivations

Ditto for previous section

![alt text](image-38.png)

![alt text](image-39.png)

![alt text](image-37.png)

## Add Value, set comparison and subtyping constraints

![alt text](image-40.png)

![asdf ](image-41.png)

![alt text](image-42.png)

![alt text](image-43.png)

![alt text](image-44.png)

![alt text](image-45.png)

## Add other constraints and perform final checks

Transofrm ORM to ERD

![alt text](image-47.png)

handy cheat sheet

![alt text](image-48.png)


![alt text](image-49.png)
The little bar indicates mandatory role

![alt text](image-50.png)
an employee can be allocated either a bus pass or a parking bay, not both

# SUPER SUPER IMPORTANT

![alt text](image-46.png)
# Week 7

Consolidation :)

# Week 8

# Week 9