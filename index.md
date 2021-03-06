<a class="button" href="http://mathrush.meteorapp.com/">View the Application</a>

<a class="button" href="https://github.com/hexokinase/math-rush">View on Github, check out the developer guide in the readme!</a>

## Table of Contents

* [About Math Rush](#about-math-rush)
* [Vision](#vision)
  * [Professor-Student Model](#professor-student-model)
  * [Real Time Multiplayer Games](#real-time-multiplayer-games)
  * [Leaderboards](#leaderboard)
* [Installation](#installation)
* [User Guide](#user-guide)
* [Milestone 1](#milestone-1)
* [Milestone 2](#milestone-2)
* [Community Feedback](#feedback)
* [Future Vision](#future-vision)

## About Math Rush

## Vision <a name="vision"></a>

To create a fun and exciting way for college students to practice the math subjects they are taking while connecting with other top performers.

### Professor-Student Model <a name="professor-student-model"></a>

One goal for the future is to partner with the Mathematics Department at the University of Hawaii. Professors would be able to create "courses" that would align with their course schedules. A student can sign up for a course, which gives them access to the games specific to that subject. The games-type page would update automatically for new topics according to the course schedule. Students would still have access to games about previous topics, but the showcased games would reflect the topics they are currently learning in class. The professors would create the games using templates that we provide.

### Real-Time Multiplayer Games <a name="real-time-multiplayer-games"></a>

Not every game should be a one-person experience. We want to create games that can be played simultaneously with any number of students. This would allow an entire class of students to participate in the same game at once. This would encourage friendly competition while studying new material. These games would have a built in group chat that allows students to ask for help, and interact with their classmates.

A professor could set suggested times for students to log in and play in order to maximize participation. Students could opt-in to receive an email 5-10 minutes before the suggested game time. Or when a student logs in, they will recieve a notification of an ongoing or upcoming suggested game time.

To take it even further a professor could have a moderator role, creating questions in real-time for the students to solve. A seperate professor message feed could be displayed so that his/her messages don't get lost in the regular group chat.

### Leaderboards <a name="leaderboard"></a>

The leaderboards will contain statistics from the different types of games played. From discrete mathematics to calculus 4, the leaderboard will keep track of all the different topics and rank each player based on their performances.

## Installation <a name="installation"></a>

1. [Install Meteor](https://www.meteor.com/install).

2. [Download a copy of Math Rush](https://github.com/hexokinase/math-rush).

3. cd into the app directory and install the libraries with

```
$ meteor npm install
```

and run the system with:

```
$ meteor npm run start
```

Make the sure application appears at [http://localhost:3000](http://localhost3000), and login with your UH account to start!

## User Guide <a name="user-guide"></a>

<img class="ui medium left floated image" src="../images/finished-landing-page.png">
At the landing page, click the login button and enter your UH account credentials. Upon successful login, the application should redirect you to the home page.

<img class="ui medium left floated image" src="../images/finished-home-page.png">
From the home page, you have the option to start a random game, go to the game types page, view the leaderboards, or view your profile. This can be done with either the 4 buttons on the page or the options on the navigation bar.

<img class="ui medium left floated image" src="../images/leaderboard.png">
Upon entering the profile page, it will provide information on the user such as their email address, active subjects they are learning, and subjects they already finished.

<img class="ui medium left floated image" src="../images/finished-game-type-page.png">
The game type page will allow the user to choose between several math subjects. Using the categories listed, you can either choose to play the game or view the leaderboard for that subject.

<img class="ui medium left floated image" src="../images/game-page.png">
The game page holds the game that the user can play. Once completed, the application will direct the user to the leaderboard page.

<img class="ui medium left floated image" src="../images/leaderboard.png">
Once in the leaderboard page, you can see who scored the highest in each category of the game. Once finished, feel free to navigate through the previous pages using the navigation bar on top. 

## Milestone 1 <a name="milestone-1"></a>

Milestone 1 started on November 8th, 2017, and ended on November 22th, 2017.

The goals for this milestone were to complete the mockup HTML for the Landing, Home, User-Profile, Leaderboard, and Game Types pages. Then, to link these pages together using Meteor FlowRouter.

To start, we downloaded [Bowfolios](https://github.com/bowfolios/bowfolios) and added our mockups to the pages folder. We then converted each mockup page to a template which could be used by FlowRouter. Here are some of the mockup pages:

#### Landing Page
<img class="ui medium left floated image" src="../images/landing-page.png">

#### Home Page
<img class="ui medium left floated image" src="../images/home-page.png">

#### Profile Page
<img class="ui medium left floated image" src="../images/profile-page.png">

#### Game Type Page
<img class="ui medium left floated image" src="../images/game-mode-page.png">

## Milestone 2 <a name="milestone-2"></a>

Milestone 2 started on November 23rd, 2017 and ended on December 13, 2017.

The goal for this milestone was to update the mockup pages to have better graphic design and include functionality. A navigation bar was added to all the pages to allow the user to traverse through the application. The landing page received a fresh new upgrade, and our first game was introduced to the application. Here are some of the new changes:

#### Updated Landing Page

<img class="ui medium left floated image" src="../images/new-landing-page.png">
We remodeled the landing page to a more sleek design. Our first approach to the application was to create a fun and exciting enviornment to learn and practice math. However, this application is focused on college students and teachers at the University of Hawaii, which lead to a more professional look.

#### Game Page and Navigation Bar
<img class="ui medium left floated image" src="../images/game-page.png">
We added our first math game. This game shows a few math problems and allows the user to input their answer and check if it is correct. Although this game is still primitive, we plan on expanding our concept to several, more complicated games in the future.

A navigation bar was also added to all the pages, allowing the user to move through the application as they please.

## Community Feedback <a name="feedback"></a>
Showing our website and concept to University of Hawaii at Manoa community members, we received valuable information and comments. Here are some things they had to say, all comments will be used to make the website better:

- **Pros**
    - "The Pages are aesthetically pleasing to look at and don't strain my eyes like many other websites."
    - "Definitely an interesting concept, would definitely benefit the math department, could be used as extra credit or even homework assignments."
    - "This concept could be used to gamify more than just math assignments, but could be used in other disciplines, but this is a good start."
    - "Could be used in ICS 111 and 211 to drill in fundamental concepts into new programmers heads."
    - "The game is really awesome, especially if you could translate it to other, more difficult classes, I could use it as a quick everyday brain exercise."

- **Improvements**
    - "Would be nice if you had an about me page, that talks about the background and purpose of the app, as well as the creators."
    - "The leaderboard page is nice, but seems very plain, adding pictures or statistics would definitely spice it up."
    - "The minimalistic style is pretty to look at times, but sometimes seems lackluster and underwhelming. Needs more consistency in design and color throughout pages."
    - "The buttons should all be animated like the ones on the home page, the animations make it ten times cooler."
    - "The profile page would be nicer if it was personalized for the user, and the login/logout button would be nicer on the header."


## Future Vision <a name="future-vision"></a>

Although there are tremendous strides to the completition of this application, there are still numerous functionalities that we would like to impliment. Here is our vision for Math Rush:

- **Real-time Multiplayer Math Games:** One game we had in mind is a live, multiplayer math game where multiple users will type in an answer to a math problem shown on screen. The first user to enter the correct answer would get points. The players would race to get a certain amount of points to win.
- **Teacher Profile:** As a platform for students to learn math, it would be great to get teachers involved. Allowing teachers to upload problems, subjects, and other study material to the games would create a more focused, class-based application for the students.
- **Study Connections:** We would also like to implement a way for users, students and teachers alike, to connect with each other. Whether that's via instant messaging or office hours, it would be useful for students to connect with those who are doing good in a certain material. By simply checking who is on the top of the leaderboards for a certain subject, any user can connect with them to create study sessions or tutoring oppprtunities.

In the end, we hope that this program will be a valuable asset to the math community of the University of Hawaii at Manoa. While Math Rush is still a growing application, we think that it will become an incredible learning platform in the future. Stay tuned!
