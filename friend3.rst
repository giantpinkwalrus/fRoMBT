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
While Jenny is on a coffee break her friends starts editing the board.


.. code:: robotframework

    	*** Test Cases ***
	Friend2 Creates Tickets
		Open Shared Board
		Login to Shared Board    Friend2
		Open Help
		Close Help
		Create Ticket    8    8
		Open Ticket Edit    8    8
		Input Ticket Text    Friend2 suggestion
		Click Done Ticket Edit
		Log Out
	
	Close3
		Close Browser
