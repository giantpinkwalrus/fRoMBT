.. default-role:: code

============
Scenario2
============

Browser: Google Chrome
Operation System: Ubuntu 14.04

Jenny Porter
Occupation: Social Network Marketing person
Age: 25

Always online and reachable on social networks. On workin hours
spend her time on social network marketing and on spare time stays connected
with friends from all over the world.

Primary Actor: Jenny Porter

Other Actors: Friend1, Friend2, Friend3, Friend4, Friend5

Roles: Common Users


.. contents:: Table of contents
   :local:
   :depth: 2


=================
Scenario 2 Tests
=================

Jenny is planning a party for the weekend with her friends. So Jenny needs to do a TODO-list for the party which she can
share with her friends and assign task for everyone what to do. Jenny is planning the party with her 5 friends.

Jenny uses Contriboard for doing the TODO-list because she has used it at work and knows how it works.

.. code:: robotframework

	*** Settings ***
	Resource 		ScenarioTests/resource.txt
	Variables 		vars.py

Jenny gets back. Jenny and her friends talk about who does what and when.


.. code:: robotframework

    	*** Test Cases ***
	Jenny Comes Back
		Open Browser To Login Page
		Login User    jenny.porter@test.com    jennyporter
		Open Board    2    2
		Open Help
		Close Help

Now that they are decided what to do. They assign the tickets to each other and edit them accordingly. They all add their name for their task and moves them
on their correct places. So they can see what has been done and what need to be done.


.. code:: robotframework

    	*** Test Cases ***
	Jenny Edit Tickets
		Open Ticket Edit    1    1
		Input Ticket Text    Clean before party: Jenny
		Click Done Ticket Edit
		Log Out
	
	Close7
		Close Browser

	Friend 1 Edit Tickets
		Open Shared Board
		Login to Shared Board    Friend1
		Open Help
		Close Help
		Open Ticket Edit    7    7
		Input Ticket Text    Friend1 suggestion: Friend 1
		Click Done Ticket Edit
		Log Out
	
	Close8
		Close Browser

	Friend 2 Edit Tickets
		Open Shared Board
		Login to Shared Board    Friend2
		Open Help
		Close Help
		Open Ticket Edit    8    8
		Input Ticket Text    Friend2 suggestion: Friend 2
		Click Done Ticket Edit
		Log Out
	
	Close9
		Close Browser

	Friend 3 Edit Tickets
		Open Shared Board
		Login to Shared Board    Friend3
		Open Help
		Close Help
		Open Ticket Edit    9    9
		Input Ticket Text    Friend3 suggestion: Friend 3
		Click Done Ticket Edit
		Log Out
	
	Close10
		Close Browser

	Friend 4 Edit Tickets
		Open Shared Board
		Login to Shared Board    Friend4
		Open Help
		Close Help
		Open Ticket Edit    10    10
		Input Ticket Text    Friend4 suggestion: Friend 4
		Click Done Ticket Edit
		Log Out
	
	Close11
		Close Browser

	Friend 5 Edit Tickets
		Open Shared Board
		Login to Shared Board    Friend5
		Open Help
		Close Help
		Open Ticket Edit    11    11
		Input Ticket Text    Friend5 suggestion: Friend 5
		Click Done Ticket Edit
		Log Out
	
	Close12
		Close Browser


TODO-list is ready. So they log out and update the list when they are done tasks or have to add something on the board.


.. code:: robotframework

    	*** Test Cases ***
	TODO-List is finished
		Open Browser To Login Page
		Login User    jenny.porter@test.com    jennyporter
		Open Board    2    2
		Open Help
		Close Help
		Close Board
		Log Out
		
	Close Final
		Close Browser
		[Teardown]

