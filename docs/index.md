# Lawyer-Up School of Law
# Software Requirements Document

**Authors:** *Kenneth Devon Gaston & Gilberto Diaz*

## Table Of Contents

[TOC]

## Introduction

### Acronyms

- Subject Matter Expert (SME)
- Phoenix Wright Game (PWG)
- Lawyer-Up School of Law (LSL)
- Content Management System (CMS)
- Public Access to Court Electronic Records (PACER)

### Definitions

- TODO

[] Domain specific technical terms

[] Synonyms

[] Jargon

[x] Users (Roles)

[] Other

#### Users (Roles)

- **SME** - SME or Subject Matter Experts are attorneys, law experts, professors in law, or any matter expert in the field of law. An SME is an employee of the LSL and is responsible for creation of lessons for the PWG.
- **Player** - A player is any individual that is not a student of the LSL and is interested in playing the PWG. A player also could be an individual interested in more information about the LSL after playing the PWG. Finally, a player is an individual that is target by the marketing personnel after playing the PWG.
- **Marketing Personnel** - Marketing personnel is a group of individuals working in the marketing department and are employees of the LSL. These people are responsible for evaluating players after a player completes a lesson. They also send marketing material and electronic communication to players that have engaged with PWG.
- **PACER** - PACER is an electronic public access service of United States federal court documents. I allows users to obtain case and docket information from the United States district courts, United States courts of appeals, and United States bankruptcy courts.

### Purpose

This document lays out the software requirements of an edutainment website/game that exposes various aspect of law and document processing based on real world cases. The game is meant to be used as a marketing tool to attract potential students to the university.

### Intended Audience

All people that are interested in pursuing a law career.

### Scope

The lucrative Lawyer-Up School of Law wants to create an edutainment website that takes real-world cases to create an interactive game that engages with potential law students. People that chose to play will get a sense of real-world law cases through a series of interactive lessons and answering questions. The player might advance in the game by having correct answers and leveling up to more difficult questions. The goal of the game is to introduce an audience attracted to study law and potentially recruiting them to the Lawyer-Up School of Law.

![Scope Diagram](img/scope_diagram.png)

## System Description

The Phoenix Wright Game tries to attract people that might be interested in a Law career. The game has lessons that are focused on real-world cases that are retrieved from the Pacer system. Lessons have a series of quizzes or challenges ranked by difficulty and each quiz is composed of multiple choice questions. Lessons are ranked by difficulty as well. The player needs a score of 70% or greater to move to the next quiz. The player can move on to the next level once he finishes all quizzes in the current level.

Once a player finishes a quiz, the quiz's score and user's profile information will be available to the Marketing team for them to assess. After performing a marketing analysis on the data, the Marketing team starts sending marketing material to all the players and potentially sending personalized letters to those carefully selected.

### Use Cases

![User Case Diagram](img/use_case_diagram.jpg)

!!! note
    Are these use cases have to be changes to Rational format of I can keep them in table format?

#### Use Case 1 - SME creating a lesson

Item | Description
------------ | -------------
Event | Create a lesson
Actor | SME
Basic Steps | After evaluating a court case downloaded from the Pacer system, an SME create a lesson with its respective quizzes.
Preconditions | SME must be an employee of the University and authorize to work with the PWG.
Alternate Steps | N/A
Exceptions | ?
Business Validation/Rules | ?
Post-conditions | ?


!!! note
    I'm not sure about `Pre-conditions`, if it has to be specifically a system precondition
    or could be a business process step.

#### Use Case 2 - SME evaluating a lesson
Item | Description
------------ | -------------
Event | Evaluating a lesson
Actor | SME
Basic Steps | After a player finishes a lesson, an SME is prompt to evaluate that lesson.
Preconditions | A player must finish a lesson.
Alternate Steps | N/A
Exceptions | `Are we including exceptions in this table?`
Business Validation/Rules | `Are we including business rules in this table?`
Post-conditions | ?

!!! note
    We need to ask about `Alternate Steps`

#### Use Case 3 - Player creating an account
Item | Description
------------ | -------------
Event | Player creating an account
Actor | Player
Basic Steps | Once a player lands in the registration page, the player can fill the form with a valid email address and a secure password and click the submit button.
Preconditions | N/A
Alternate Steps | Player needs to confirm their email address by clicking the link sent to their email.
Exceptions | ?
Business Validation/Rules | ?
Post-conditions | After clicking the confirm link, player need to login into their account.

#### Use Case 4 - Player taking a quiz (Fully Dressed)

- Primary Role: Player
- Success scenario of player taking a quiz
    - Player logs in and navigates to the lesson's page.
    - Player clicks in the next available quiz to start playing.
    - Player answers all the questions and clicks the submit button.
    - Player gets the grade back.
    - Player can logout or keep playing for the next quiz available.
- Variation Scenarios:
    - Variation 1: The Lesson is Unfinished
        - Player can finish the quiz and clicks the logout button.
        - Player is warned that leaving the page will cause to lose all progress.
        - Player logs out and is redirect to the home page.
    - Variation 2: Player fails the quiz
        - Player logs in, navigates to the lesson page and starts a quiz.
        - Player answers all que questions in the quiz and clicks the submit button.
        - The grade comes back and is lower than 70%.
        - The player is prompt to review the material and re-take the quiz.
- Exceptions
    - Exception 1: Player can't login 
        - Player attempts to login three times without success.
        - Player attempts to login the fourth time and the system redirects the player to a recovery password page.
        - Player enters email address into the form and clicks the submit button.
        - Player goes to his email address and click the link sent by the system to create a new password.
        - Player enter a password twice and clicks the submit button.
        - The system validates that both passwords match and updates player's password in the database.
        - Players is redirect to the login page.

### Entity Relationship Diagram

![Entity Relationship Diagram](img/entity_relationship_diagram.jpg)

### Communication Diagram

![Communication Diagram](img/communication_diagram.jpg)
