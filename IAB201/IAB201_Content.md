
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

## What is information?

Information is data + semantics. With data being the items stored in our system, and the semantics being the meaning behind the data.

Only by considewring the semantics of teh Universe of Discourse (UoD) can a robust, quality information system be designed


## Where is information stored?

Database. If you dont remember IFB105 idk what to tell you pookie

## Elementary facts

A fact that can be explained in a sentence

```Stevie wonder plays keyboard```

If we want to express that explicitly.

```Person Stevie Wonder plays instrument keyboard.\Concept person plays entity instrument```