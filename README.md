# The Game of Set, Reloaded | JavaScript Game of Set | Lab 5

This repo contains The Game of Set created using JS/HTML/CSS. This is re-implementation of CSE 3901: Lab 2 using JS/HTML/CSS instead of Ruby.

"Set" is a card game in which players attempt to find a group of cards that satisfy a particular criterion, called a set. Our set game has special sets of rules, which add a scoring system, hints, and lives. 

Hints highlight two cards from a set currently on the table. The player's score increases when they correctly make a set, and decreases when they incorrectly make a set. Finally, the streak tracks the number of sets that have been made in a row, and resets whenever a hint is used or a set is incorrectly guessed.

For a complete description of the base game, see: <i>https://en.wikipedia.org/wiki/Set_(card_game)</i>

## Installation Instructions
A current version of Ruby 2.6.6 is required, along with bundle. 
Run the following command to install the required gems.

```bash
bundle install
```

Run the following command to start the server:

```bash
./start_server.sh
```

The server will be running on localhost:4567.

## Playing the Game

To see the rule modifications made, see the introduction.

Use a mouse to select 3 cards as a set. Once the cards are selected, press "<i>Submit</i>" to submit a potential set. If the cards selected do not make up a set, you will lose a life AND lose a point from your score. If the cards selected do make up a set, you will gain points for your score and you will have a set streak.

If you believe there are no sets on the board, you can select "<i>Add 3</i>" to have 3 more cards dealt to the table. If there are any valid sets on the board, you will lose a life. If there are no valid sets on the board, 3 more cards will be dealt. 

If you are having a hard time finding a set, select "<i>Hint</i>" to highlight the border of 2 cards. This will deduct one life from your total lives.

Select "<i>Restart</i>" to start a new game of Set. 

# Testing the game

Since we have not learned any javascript testing framworks, the testing of this game is done manually with the help of utility functions defined in `source/javascripts/test.js`. To use this testing functionality, load the game as normal, and then run the function `activateTestingMode()` in the console of your web browser. This will make a button with the label "Select Set" appear at the top of the website. Click on this button to select a set without deducting a life. This allows for much easier manual testing of functionality, especially near the endgame.

## Architecture
The page is built from a single layout called `layout.erb` found in `source/layouts` and built into the homepage
`index.html.erb`. 

`index.html.erb` is styled with the CSS styles found under `source/stylesheets` called `site.css.scss`. We used a minimalistic style with a custom button type that uses flexbox to create a dynamic button arrangement.

`source/images` contains the image files needed to run the site. The root of that folder contains images specific to the interface such as the lives implementation and an example set. The folder `cards` contains the unique 81 cards that make up the game of set named with a key value(1-81) that is then hashed into our javascript. These cards use SVG in order to display at any resolution necessary.

Our javascript is comprised of multiple files contained in `source/javascripts`.

- `card.js`:        Contains the `card` class, which contains logic to create and keep track of cards as they are used in the game
- `life.js`:        Contains logic relating to the life functionality
- `listeners.js`:   Contains all event listeners that are registered to add dynamic logic to user actions
- `set.js`:         Contains logic for finding and removing sets
- `site.js`:        Contains the global variables used by our game, some utility functions, and initialization code to begin the game
- `test.js`:        Contains testing functions used to test the game more easily
- `view.js`:        Contains functions to update the graphical objects in the site
## Rubric

Project 5 will use the same rubric as the Project 2 (Ruby Game of Set) with the exception of the Style section, which will be as shown below.

100 points overall, broken down in the following categories

* Correctness (35 points)
* Functionality/features (30 points)
* Design (15 points)
* Documentation (10 points)
* Style (5 points)
* Testing (5 points)

### Documentation ###

1. Poor
* Readme is unhelpful
* In-code documentation is minimal with no class-level information
* Writing contains grammatical and/or spelling mistakes
* Commit messages add no useful information

2. Fair
* Readme is helpful but incomplete
* In-code documentation is sparse with few class-level comments
* Writing is disjointed or awkward
* Commit messages add little information

3. Good
* Readme is mostly complete
* In-code documentation is helpful (e.g. class-level comments)
* Writing is clear
* Commit message have useful first-line summaries

4. Excellent
* Readme is very thorough
* In-code documentation is complete (e.g. mathematical models for abstractions)
* Writing is compelling and crisp
* Commit messages are substantial and include first-line summaries

### Correctness ###

1. Poor
* Crashes or incorrect behavior

2. Fair
* Odd behavior which could cause a reasonable user to file a bug report

3. Good
* Fully correct for expected user actions
* Unexpected user actions cause surprising behavior

4. Excellent
* Fully correct and very robust, even to malicious user actions

### Functionality/Features ###

1. Poor
* Difficult to use
* Awkward interface

2. Fair
* Playable basic two-person game
* Player moves are checked and some statistics are kept

3. Good
* Enjoyable game with at least one good extra feature
* Computer provides hints or something beyond the basic card game

4. Excellent
* Particularly engaging game with several extra features
* People will want to play this game in their spare time

### Style ###

1. Poor
* Violations of common style guidelines (HTML and JS)
* Style inconsistencies within the project

2. Fair
* Loose adherence to a common style
* Code looks more procedural than declarative
* Unnecessary use of explicit iterations (for/while)

3. Good
* Broad adherence to a common style
* Style rules are implicit
* Use of standard libraries to make code concise and readable

4. Excellent
* Strict adherence to a known style
* Documented style rules
* Excellent use of standard libraries and idiomatic JS
* Elegant use of blocks


### Design ###

1. Poor
* No classes
* high concrete coupling between class implementations
* Literals used instead of constants

2. Fair
* Few classes used
* Poor interfaces with limited observability and controlability
* Some constants used but hard-coded literals are common

3. Good
* Classes used to encapsulate state and behavior
* Some concrete coupling between implementations
* Constants used extensively but a few hard-coded literals present

4. Excellent
* Beautiful classes with clean APIs
* Clear separation of abstraction and concrete representation
* Trivially generalizable along multiple dimensions

### Automated Unit Testing ###
(Graders will be lenient since JS has not been covered)

1. Poor
* Very little or no automated testing

2. Fair
* Tests run automatically but coverage is poor
* Doesn't always follow unit testing best practices

3. Good
* Test coverage is good
* Follows best practices
