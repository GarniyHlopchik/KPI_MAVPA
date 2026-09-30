Feature: Logging in
  Scenario: SCN1 - First Access
    Given the user just opened the website
    Then a list of threads and login button should appear
  Scenario: SCN2 - Registration
    Given the user is not logged in yet
    When the user presses "register" button
    And enters valid data in the form
    And submits it
    Then a message about successful registration and login should appear
    And Main Page should now contain Groups button and Create Thread button
  Scenario: SCN3 - Login
    Given the user is not logged in yet
    When the user presses "login" button
    And enters valid data in the form
    And submits it
    Then a message about successful login should appear
    And Main Page should now contain Groups button and Create Thread button
Feature: Threads
  Scenario: SCN4 - Open Thread Logged In
    Given there are threads available in the list
    Given the user is logged in
    When the user clicks on one of the threads
    Then messages from that thread should appear on the screen
    And a text input for new messages should appear
  Scenario: SCN5 - Open Thread Anonymous
    Given there are threads available in the list
    Given the user is not logged in
    When the user clicks on one of the threads
    Then messages from that thread should appear on the screen
    And a text input for new messages should appear
    And text inputs for username and tripcode should appear above message input
  Scenario: SCN6 - Send Message
    Given the user is in a thread
    Given the user is not banned
    Given there is a message in the text input
    When the user presses "send" or clicks Enter
    Then the message should be sent to current thread
  Scenario: SCN7 - Delete Message
    Given the user is logged in
    Given the user is not banned
    Given there is a delete button next to a message (it is owned)
    When the user pressed the delete button
    Then the message should disappear
  Scenario: SCN8 - Edit Message
    Given the user is logged in
    Given the user is not banned
    Given there is an edit button next to a message (it is owned)
    When the user pressed the edit button
    And enters new message in a form
    And presses enter
    Then the message should change to a new one
  Scenario: SCN9 - Edit Thread
    Given the user is logged in
    Given the user is not banned
    Given there is an edit button next to a thread (it is owned)
    When the user presses the edit button
    And reenters thread name and description in a form
    And presses Edit button
    Then the thread should change
    And a message about successful change should appear
  Scenario: SCN10 - Delete Thread
    Given the user is logged in
    Given the user is not banned
    Given there is a delete button next to a thread (it is owned)
    When the user presses the delete button
    Then the thread should disappear
    And a message about successful deletion should appear
Feature: Groups
  Scenario: SCN11 - Go To Groups
    Given the user is logged in
    Given the user is not in a thread
    When the user presses the "Groups" button
    Then a list of groups the user is a part of should appear
    And a button to create a group should appear
  Scenario: SCN12 - Create a group
    Given the user is logged in
    Given the user is not banned
    Given the user is in the Groups tab
    When the user presses the "Create Group" button
    And enters group name and members in the form
    And presses "Create Group"
    Then the group should be created
    And a message about successful creation should be displayed
  Scenario: SCN13 - Edit a group
    Given the user is logged in
    Given the user is not banned
    Given the user is in the Groups tab
    Given there is an edit button next to a group (it is owned)
    When the user presses the edit button
    And reenters group name and members in a form
    And presses Edit button
    Then the group should change
    And a message about successful change should appear
  Scenario: SCN14 - Delete a group
    Given the user is logged in
    Given the user is not banned
    Given the user is in the Groups tab
    Given there is a delete button next to a group (it is owned)
    When the user presses the delete button
    Then the group should disappear
    And the message about successful deletion should appear
  Scenario: SCN15 - Enter a group
    Given the user is logged in
    Given the user is in the Groups tab
    Given there are available groups
    When the user clicks on one of the available groups
    Then the messages from the group should appear
    And a text input field should appear
Feature: Moderation
  Scenario: SCN16 - delete a message
    Given the user is logged in
    Given the user has moderation rights
    Given the user is in a thread
    When the user presses the delete button next to a message
    Then the message should disappear
    And a message about succesful deletion should appear
  Scenario: SCN17 - ban a user
    Given the user is logged in
    Given the user has moderation rights
    When the user presses the delete button next to a username of another user
    And enters the amount of time in a from
    Then the other user should become banned
    And a message about successful ban should appear
  Scenario: SCN18 - delete a thread
    Given the user is logged in
    Given the user has moderation rights
    When the user presses the delete button next to any thread in the list
    Then the thread should disappear
    And a message about successful deletion should appear
  Scenario: SCN19 - Moderation RIghts
    Given the user is logged in
    Given the user has moderation rights
    Then a delete button should display next to any thread in the list
    And a delete button should display next to any message in any thread
    And a ban button should display next to any username of a registered user