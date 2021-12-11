# Object Oriented System Design

## Basics:

Object-oriented programming (OOP) is a style of programming that focuses on using objects to design and build applications. Contrary to procedure-oriented programming where programs are designed as blocks of statements to manipulate data, OOP organizes the program to combine data and functionality and wrap it inside something called an “Object”.


## OO Analysis and Design:

OO Analysis and Design is a structured method for analyzing and designing a system by applying object-oriented concepts. This design process consists of an investigation into the objects constituting the system. It starts by first identifying the objects of the system and then figuring out the interactions between various objects.

The process of OO analysis and design can be described as:
1. Identifying the objects in a system;
2. Defining relationships between objects;
3. Establishing the interface of each object; and,
4. Making a design, which can be converted to executables using OO languages.

## UML: 

UML stands for Unified Modelling Language and is used to model the Object-Oriented Analysis of a software system. UML is a way of visualizing and documenting a software system by using a collection of diagrams, which helps engineers, businesspeople, and system architects understand the behavior and structure of the system being designed.

Benefits of using UML:
1. Helps develop a quick understanding of a software system.
2. UML modelling helps in breaking a complex system into discrete pieces that can be easily understood.
3. UML’s graphical notations can be used to communicate design decisions.
4. Since UML is independent of any specific platform or language or technology, it is easier to abstract out concepts.
5. It becomes easier to hand the system over to a new team.

Structural UML diagrams
* Class diagram
* Object diagram
* Package diagram
* Component diagram
* Composite structure diagram
* Deployment diagram
* Profile diagram

Behavioral UML diagrams
* Use case diagram
* Activity diagram
* Sequence diagram
* State diagram
* Communication diagram
* Interaction overview diagram
* Timing diagram

## Use Case Diagrams:

Use case diagrams describe a set of actions (called use cases) that a system should or can perform in collaboration with one or more external users of the system (called actors). Each use case should provide some observable and valuable result to the actors.

1. Use Case Diagrams describe the high-level functional behavior of the system.
2. It answers what system does from the user point of view.
3. Use case answers ‘What will the system do?’ and at the same time tells us ‘What will the system NOT do?’.

![Alt text](Diagrams/UseCaseDiagram.png?raw=true "Use Case")

## Class Diagram:

Class diagram is the backbone of object-oriented modeling - it shows how different entities (people, things, and data) relate to each other. In other words, it shows the static structures of the system.

A class diagram describes the attributes and operations of a class and also the constraints imposed on the system. Class diagrams are widely used in the modeling of object-oriented systems because they are the only UML diagrams that can be mapped directly to object-oriented languages.

The purpose of the class diagram can be summarized as:
1. Analysis and design of the static view of an application;
2. To describe the responsibilities of a system;
3. To provide a base for component and deployment diagrams; and,
4. Forward and reverse engineering.

![Alt text](Diagrams/ClassDiagram.png?raw=true "Class Diagram")

## Sequence Diagram:

Sequence diagrams describe interactions among classes in terms of an exchange of messages over time and are used to explore the logic of complex operations, functions or procedures. In this diagram, the sequence of interactions between the objects is represented in a step-by-step manner.

Sequence diagrams show a detailed flow for a specific use case or even just part of a particular use case. They are almost self-explanatory; they show the calls between the different objects in their sequence and can explain, at a detailed level, different calls to various objects.

A sequence diagram has two dimensions: The vertical dimension shows the sequence of messages in the chronological order that they occur; the horizontal dimension shows the object instances to which the messages are sent.

![Alt text](Diagrams/SequenceDiagram.png?raw=true "Class Diagram")

## Activity Diagrams:

We use Activity Diagrams to illustrate the flow of control in a system. An activity diagram shows the flow of control for a system functionality; it emphasizes the condition of flow and the sequence in which it happens. We can also use an activity diagram to refer to the steps involved in the execution of a use case.

Activity diagrams illustrate the dynamic nature of a system by modeling the flow of control from activity to activity. An activity represents an operation on some class in the system that results in a change in the state of the system. Typically, activity diagrams are used to model workflow or business processes and internal operations.

![Alt text](Diagrams/ActivityDiagram.png?raw=true "Class Diagram")

# Object Oriented Design Case Studies

<details> <summary> Library Management System: </summary>
  
### System Requirements:

1. Library should have name, address and owner details.
2. Library will have different types of books like hard cover, paperback, magazines and journals.
3. One book can have multiple copies and each copy will have unique barcode assign to it.
4. Library can have multiple librarians for managing users and books.
5. Librarian can assign/return book to/from the user.
6. Librarian can add new books or can remove books from the application.
7. Librarian can add new users or also can deactivate existing users account from the application.
8. Librarian should be able to get information that which user has taken what book or which user has taken what all books or which book is taken by whom.
9. Library will have active users with subscription.
10. Users can take max of 5 books with each book only for 10 days
11. Users can search books based on title, publisher and author.
12. Application should send notification to librarian and user if user doesn’t return book in 10 days
13. Application should locate book to the physical rack location in the library.
14. Each user will have a member card with unique barcode assign to it.

### Class Design:

1. Library —> Name, Owner, Address
2. Address —> Address details.
3. Book —> Name, title, Author, Published date, ratings.
4. BookCopies —> Unique bar code, price, type, date of purchase, isAvailable, dateTaken, currentlyTakenBy, returnedOn.
5. Librarian —> Name, uniqueId, address, active.
6. User —> Name, Occupation, address, active, uniqueId.
7. Account —> uniqueId, type, user/LibrarianId, credentials.
8. Notifications
9. BookLending
10. Rack
11. Fine
</details>

<details> <summary> Parking Lot System: </summary>

### System Requirements:

1. Parking lot should have one entry point for 4 wheelers and one entry point for 2 wheelers.
2. Customers should be able to collect ticket at the entry gate
3. Customers will pay the parking fees at the exit gate while leaving.
4. Customers can pay with cash or UPI by scanning the qr code.
5. Application should have feature to generate ticket with vehicle number and collect the payment against that ticket.
6. Application should capture time when generating ticket and collect fees based on number of hours.
7. Application should have parking information, number of parking floors, number of parking space for 2 wheeler and 4 wheeler on each floor.
8. Application should track parking space available on each floor.
9. Application should have indicator outside parking building showing parking status for each floor.
10. Each floor should also suggest available parking space for handicapped vehicles.

### Class Design:

1. Parking —>Name, floors.
2. Floor —> totalBikesSpace, totalCarsSpace, totalHandicappedSpace, List<bikes>, List<cars>, List<handicapped>, addBike(), removeBike(), addCar(), removeCar(), addHandicapped(), removeHandicapped(), parkingSpaceAvailable(Vehicle)
3. Vehicle (interface) —> pricePerHour, licencePlate, vehicleType
4. Cars
5. Bikes
6. Handicapped
7. Ticket —> ticketNumber, entryDateTime, Vehicle, floor, getFloorAvailability(), updateParkingAvailabiltyStatus()
8. ParkingDisplayBoard
</details>
  
<details> <summary> Online Shopping System: </summary>

### System Requirements
  
1. User should be able to view product categories
2. User should be able to search product using name or category
3. User should be able to view product details
4. User should be able to add product to the cart
5. User should be able to delete product from the cart
6. User should be able checkout the cart
7. User should be able to select/add address for delivery
8. User should be able view/add review and ratings for product
9. System should send notifications to user whenever shipping status has changed

### Actors:

Guest User: Guest user can search product, view product and can explore categories
Member User: User can do all operations as of guest along with adding adding/updating product reviews and ratings, adding products to cart, checkout and purchase product.
System: System will send notifications to users.

### Class Diagram:
1. Categories —> Name, List<Products>, addProduct(), removeProduct()
2. Product —> Name, price, description, List<Images>, Ratings, Reviews, Seller, HashMap<String, String> parameters.
3. Images —> URL, altText
4. Ratings —> ratings, User
5. Reviews —> reviewMsg, User
6. Seller —> sellerName, Address, licenceNumber
7. User —> username, credentials, email, phoneNumber, List<Address>
8. Cart —> User, List<Product>
9. Order —> List<Product>, User, AddressToShip, paymentMethod.
10. OrderLog —> will track the order status, like packaged, shipped and delivered.
11. ShipmentLog —> will track the different status of shipment.
12. Address —> address Details.
13. Notifications —> sendsNotification()
</details>
  
<details> <summary> Stack Overflow Design: </summary>

### System Requirements:

1. Any non member (guest) user can view questions and answers.
2. Members should be able to open a question
3. Members should be able to add an answer to an open question
4. Members should be able to comment to an answer/question.
5. Member can upvote a question or an answer
6. Member can add bounty to a question to draw attention
7. Member can add tags to a question.
8. Member can vote to close a question
9. Moderator can close a question or can reopen any closed question

### Actors:
  
Non Members —> Will be able to view question and its answers
Members —> all non members activity, plus they can post a question, answer a question, can upvote or devote a question and answer.
Moderator —> In addition to what members can do, moderator can close an open question or reopen already closed question. 

### Class Design:

1. Question —> id, question, postedByUser, List<Answers>, List<Tags>, List<Comments>, Bounty, Image, postedOn, isClosed, closedOn
2. Answer —> id, answer, postedByUser, isUpvoted, List<Comments>, Image, postedOn, flagged
3. Comments —> id, comment, postedBy, commentedOn, flagged
4. Bounty —> points, expirtyDate
5. Image —> url, text
6. User —> id, name, email, phoneNumber, credentials
7. Tag —> tagName
8. Notifications —> sendNotification()
  
</details>
  
<details> <summary> Movie Ticket booking System: </summary>
  
### System Requirements:
  
1. It should be able to list all the cities where affiliated cinemas are located
2. Each cinema can have multiple halls and each hall can run single movie at a time
3. Each movie will have multiple shows
4. Customer should be able to search movie by there name, title, language, production house.
5. Once the customer selects the movie, the service should display all available cinemas running that show with time
6. User should be able to view available seats/arrangements of seats and should be able to select single or multiple seats.
7. User can apply coupon to get discounts
8. User should be able to proceed with ticket booking and should get reservation status.
9. System should send notifications to users for new movies or shows.

### Actors:
  
1. Admin —> can add/remove movies to a particular cinema hall.
2. FrontDesk officer —> book/cancel tickets
3. Customer —> search movies, book tickets.
4. Guest —> search movies
5. System —> Sends notifications to users.

### Class Design:
  
1. Cities —> id, name, List<CinemaHalls>
2. CinemaHalls —> id, name, location, List<Halls>
3. Halls —> id, List<Seats>, numberOfSeats, List<Shows>
4. Seats —> type, number, availableStatus, isBookingInProgress, bookingProgressStartedOn.
5. Movie —> name, production, genre, language, releaseOn, director.
6. Shows —> Movie, startTime, endTime
7. Booking —> bookedByUser, List<Seats> seatsBooked, totalAmount, Shows
8. OfferType —> id, name, Type
9. Coupons —> id, OfferType, expiryTime
10. System —> sendsNotifications()
  
</details>
  
<details> <summary> ATM: </summary>

### System Requirements:

1. Card Reader —> to read the users ATM card
2. Keybad —> to enter information into the atm machine.
3. Screen —> to display information to the user
4. Cash dispenser —> for dispensing cash
5. Deposit slot —> for users to deposit cash.
6. Printer —> for printing receipts
7. Communication/Network infrastructure —> It is assumed that ATM has communication infrastructure to communicate to the bank servers upon on any activity.

### Following operations can be performed on account

1. Balance Enquiry
2. Deposit Cash
3. Withdraw Cash
4. Change pin
5. Mini Statement

### Class Design:

1. ATM —> id, location
2. Menu —> menuName, menuId, List<Menu> subMenus.
3. CardReader —> will read the information and validate it with the bank servers
4. Printer —> printReceipts()
5. Deposit —> txnId, List<Notes>, totalAmount, UserAccount, makeDeposit()
6. CashDispenser —> txnId, List<Notes> totalAmount, UserAccount, validateTxn(), dispenseCash()
7. Notes —> denomination
8. Bank —> name, bankCode
9. UserAccount —> Bank, Card and other user details
10. Card —> user card details.
11. Transaction —> transaction details
12. Communication —> to interact with bank servers
  
</details>
  
<details> <summary> Linkedln: </summary>
  
### System Requirements:

1. User should be able to create account on linkedln and basic information to their profile.
2. User should be able to search users by there name, industry or profession.
3. User should be able to post with messages, images and videos
4. User should be able to send/accept connection request to/from other users
5. User can also follow other users
6. User can see post or activities of other users within its connection
7. User can add emotions, comment or share to other users post.
8. User can comment or add emotions to other users comments.
9. User can message or inMail to other users
10. System can provide connection suggestions to users based on there current connections, industry or type of work.
11. System can send notifications to users whenever there is any activity from user connections.

### Actors of Linkedln:
  
1. Members
2. Admin
3. System

### Class Design:
  
1. UserProfile —> userDetails, Image profilePhoto, Image coverPhoto, List<EducationDetails>, List<ExperienceDetails>, List<CertificationDetails>, UserCredentials
2. Image —> id, url, text
3. EducationDetails —> id, Institute, yearOfPassing, YearOfAdmission, degree
4. ExperienceDetails —> id, companyName, joiningDate, relievingDate, designation, industryType
5. CertificationDetails —> id, certificationName, dateGiven, expiryDate
6. UserCredentials —> username, password, token (for api’s)
7. UserConnections —> this will not be object oriented, basically this information might be stored in from of Graph (graph database).
8. Post —> message, Image, Video, postedOn, postedBy, List<Emotions>, List<Comments>, isShared, sharedFromUser
9. Video —> id, url, text
10. Emotions —> id, type, postedBy, postedOn
11. Comments —> id, commentedBy, commentedOn, List<Comments>
12. Notifications —> sendNotifications()
13. Search —> byName, byIndustry, byOccupation

</details>
  
<details> <summary> CrickInfo: </summary>

### System Requirements:

1. System should keep track of all cricket playing teams and matches.
2. For each match system should keep track of each team playing 11 team members
3. For each match system should have commentatory for each ball
4. For each match, system should have live score and score card
5. System should have track for each player playing records
6. System should track of each ODI, T20 and test series

### Class Design:

1. Team —> teamName, List<Player>, country
2. Player —> name, jerseyNumber, BatingStats, BowlingStats, MatchesPlayedStats
3. MatchesPayedStats —> totalODIMatches, totalTestMatchs, totalT20Matches
4. BatingStats —> totalRuns, highestScore, average in each format.
5. BowlingStats —> totalRunsGiven, totalWicketsTaken, totalOversBowled, average in each format.
6. Series —> seriesName, List<Teams>, startFrom, endFrom, List<Match>, typeOfSeries, countryPlayedIn, manOfTheSeries
7. Match —> matchNumber, venue, List<Player> team1, List<Player> team2, List<Commenatory>, manOfTheMatch, LiveScore, List<Innings>
8. Innings —> Team teamBatted, totalRuns, totalWickets, inningsNumber
9. LiveScore —> Batting figures, bowling figures
10. Commentatory —> comments, timePosted, overNumber, ballNumber
  
</details>
