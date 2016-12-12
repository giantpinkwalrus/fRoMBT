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
	Library 		OperatingSystem

She starts to do the TODO-list:


.. code:: robotframework

	*** Test Cases ***
	Jenny Login
		Open Browser To Login Page
		Login User    jenny.porter@test.com    jennyporter


As she has logged in she creates new board as a basis for their party plan


.. code:: robotframework

	*** Test Cases ***
	Jenny Creates a Board
		Create Board
		Click Edit Board    2    2
		Input Board Name    Party TODO-list
		Change Background    5    5
		Click Done Board Edit

Now she add couple tasks to the board before sharing it to friends.


.. code:: robotframework

    	*** Test Cases ***
	Jenny Opens Board and Create Tickets
		Open Board    2    2
		Open Help
		Close Help
		Create Ticket    1    1
		Open Ticket Edit    1    1
		Input Ticket Text    Clean before party
		Click Done Ticket Edit
		Create Ticket    2    2
		Open Ticket Edit    2    2
		Input Ticket Text    Get food?
		Click Done Ticket Edit
		Create Ticket    3    3
		Open Ticket Edit    3    3
		Input Ticket Text    Get drinks?
		Click Done Ticket Edit
		Create Ticket    4    4
		Open Ticket Edit    4    4
		Input Ticket Text    Select music
		Click Done Ticket Edit
		Create Ticket    5    5
		Open Ticket Edit    5    5
		Input Ticket Text    Who to invite?
		Click Done Ticket Edit
		Create Ticket    6    6
		Open Ticket Edit    6    6
		Input Ticket Text    Clean after party
		Click Done Ticket Edit


Jenny has organized tickets. Now she shares the board to her friends.


.. code:: robotframework

    	*** Test Cases ***
	Jenny Shares Board
		Share Board From Board


Jenny sends the board url to her friends using facebook group conversation. And asks her friends to add new tasks or edit the old ones.

Jenny goes for coffee break.


.. code:: robotframework

    	*** Test Cases ***
	Jenny Goes For Coffee
		Create File 		vars.py 		Shared = "${Shared}"
		Log Out
	
	Close1
		Close Browser


While Jenny is on a coffee break her friends starts editing the board.

