Please see my notes as they pertain to the listed requirements.

Part 1 | Design
---------------

Requirements
------------

1.  A foosball game can be initiated by any registered user, and subsequently joined by other registered users.  
To minimize the number of pages and actions the app would need to make, the entire process is contained to 3 pages.  Registration and Sign in are in the upper right corner, and would be replaced with "Welcome, {Player's Name}!" once the user either registers or signs in.  

The landing page always has the Standings information since a typical user, I would expect, would go on to research this information.  This is available immediately in the first wider column.  Column two contains everything for initiating a match.

2.  There are four players for each game, two to a team.
This is illustrated in the second column.  Those clicking icons on the same side of the table would be on the same team.  While it is not currently displayed, we may need to include the copy titles "Team 1" and "Team 2" to avoid confusion when entering in the winner of a match.  I view the top duo as Team 1, and the bottom as Team 2.

3.  A win for a team is logged as a win for each individual player.
Programmatically, this passing of information would occur on the backend without the need to tell the user it is happening.

4.  There should be an indication to users not currently playing that a game is currently in progress.
This verbiage is in place as illustrated in simplifi_foosBuild_landing_activeMatch.jpg.  The title changes to "Spectate", and the descriptive copy adjusts to clarify once every slot in the match has been filled.

5.  Once the game is finished, the game results are entered.
Once every slot in a match has been filled, the "Enter Results" button appears.  We may need to have a button there that reads "Verify Entry" in case the user wants to back out of the match.  Then, after all are locked in, a "Begin Match" button becomes available.  Although, the ommision of these steps could enforce a commitment to the match for the player!  Either way would work. 

6.  At any time a user can navigate to a standings page.
The standings information would be available on all pages expect the Enter Results page thus negating the need to navigate to a specific page.

7.  Don’t worry about user registration/management.
Noted.  For the purposes of the app, I would expect the Registration process would include the ability to enter First Name, Last Name, and a profile picture.


Part 2 | Development
--------------------

Requirements
------------

1.  Read the foosball_players.json file and return a table of each player and display the following data points:  First Name, Last Name, Department, Wins, Losses, Win percentage

As agreed by email conversations with Eric, data has been converted to JavaScript (in the index.html file's head instead of linking to an external file).  I have kept the format of the JSON file, and I have also provided a commented-out block of code that would load the JSON data from the JSON file if loaded server-side, or a local web server link WAMP, MAMP, etc.  Details are in that code block based on the way Datatables handles ajax calls.

2.  Make each column sortable.
Check!

3.  Add Search field that matches on first or last name
Check!

4.  Add a filter for departments.
This option is in the code, but based on the current Search functionality, this ability already appears to be supported.  If I misunderstood, let me know.

5.  Try and identify what various users would see during the various states of the app.
As little as possible!  The only thing they should see is the standings info, and ability to join matches.  The rest would all happen on the backend.

6.  Are there any edge cases you discovered that should be considered?

a.  Multiple users joining at the same time - a refresh of data after verifying your entry would be necessary to make sure someone else didn't hop in before you.

b.  Who has permissions to begin the matches and enter results.  What happens if the user clicks Enter Results beforehand, or enters false data?
