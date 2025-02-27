# Week 1

## Statis vs Dynamic Web Apps

![alt text](image.png)

> Static web apps will display the same content to the user, wheras dynamic sites allow for personalisation for a tailor-made experience

Web apps are a **thin client** and differ heavily from other types of applications.

## Model View Controller (MVC) Software Design Pattern

- MVC outlines that data should be isolated from the presentation
    - Like all apps, data layer should be seperate from presentation layer
- A web app can have multiple presentations for the same data
    - In the case of a dynamic web apps
- The intention of MVC is to isolate the what, how and its presentation
    - Model (what)
        - Data or information for your application
        - Provides access to the systems data and business rules
        - Can contain a bit of business logic
            - Such as managing data consistency
    - Controller (how)
        - Processes/formats the information in the model
            - Prices/discounts
            - Review rating
            - Orchestrates interaction between the view and model
        - View (presentation)
            - Displays the model and allows the user to interact with the model
            - Allow interactions with user to edit model where relevant
            - An advantage of using MVC is that you can change the view without impacting the rest of the system

![alt text](image-1.png)

> As mentioned prior, the presentation is abstracted from the data layer, the controller acts as an intermediary between the two

## Web application design process

- Is completed over 4 steps
    - Requirements
        - Gather requirements for application/feature
    - User story
        - Make a user story (See below)
    - Conceptual Model
        - Use user stories to identify concepts related to our web app
            - Refine concepets to represent the classes (object type) required in application
            - Also allows us to find associations between them and their attributes and methods
    - Data model
        - Convert conceptual model to data model for the application

## Developing user stories

> I am going to omega gloss over this since I already do this at work

The gist of this is, a user story is a short description of what the user requires. Told from the first person.

they use this format:

```
Title: as a ____ I require/want/need ____ to do ____ (sometimes a reason is good here)

Description: Provide details on the functionality that is required

Acceptance criteria: what is the outcome that the user requries
```

So if we apply this to a retail staff member wanting to be able to have a new screen created that allows them to view stock of neighbouring stores. it would look as follows

```
Title: As a sales assistant, I need to view other stores stock on hand screen to provide real time information to customers

Description: Sales assistants are encountering experiences with customers asking if there is stock at another location. To complete this request, the staff member is required to call the store on the customers behalf in order to get this information and relay it to the customer. etc etc etc

Acceptance criteria:
- An independant screen on __ that allows stores to see the stock on hand of a given item across all stores in a region
- More requirements here im not doing all of this
```

The way the unit teaches user stories is also fine, which ditches the description in favour of a more detail rich title.

## Developing the Conceptual Model

The point of the conceptual model is to help identify relevant concepts related to the problem raised in the US

