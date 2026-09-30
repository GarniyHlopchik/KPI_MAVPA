WHEN the user opens the website, the system SHALL list open threads and provide a button to register/login

WHEN the user presses register/login, the system SHALL open the page for entering account data

WHEN the user enters login and password and presses "register", the system SHALL validate whether login exists in the database and whether the password is strong enough, create a new user and log them in.

WHEN the user enter login and password and presses "login", the system SHALL find a user with such password in the database and verify that the password hash matches and log the user in.

IF the user tries to register or log in, but enters invalid data, the system SHALL display a message about a failed attempt and redirect the user back to login/register page.

IF the user enter login data associated with an account of a moderator, the system SHALL provide the user moderator priveledges.

WHILE the user is logged in, the system SHALL provide a button to create a new thread and view private groups.

The system SHALL provide a button for deleting or editing any thread that a given user owns.

WHEN the user presses the "new thread" button, the system SHALL redirect them to a page where the user can enter thread name and description

WHEN the user enters thread data and presses "create", the system SHALL create a new open thread in the database.

WHEN the user clicks on a thread from the list of threads, the system SHALL open that thread and display the messages it contains.

WHILE the user is in a thread, the system SHALL display any messages that are now in it, and provide a text field to write a new message.

IF the user is not logged in while in a thread, the system SHALL provide fields for username and tripcode above the message input.

IF the user presses Enter while nothing is in the message input box, nothing will happen

WHEN the user presses Enter while there is text in the message input box, the system SHALL add the message to the thread.

The system SHALL provide a button for deleting or editing any message that a given user owns.

WHEN the user presses "private groups" button from the website's homepage, the system SHALL display every group that the user is a part of and provide a button to create a new group

WHEN the user presses a button to create a new group, the system SHALL provide a form where the user can put the name of the group, the description, and username of every user that will be a part of it.

WHEN the user enters the data in the form, the system SHALL validate it and create a new private group in the database.

IF the user enters invalid data (such as empty group name or nonexistant usernames), the system SHALL display an error message and redirect the user back to the group creation page.

WHEN the user clicks on a private group from the list, the system SHALL display the messages it contains and provide a text input for the user's message.

WHILE the user has moderator priveledges, the system SHALL provide a delete button every public thread and message it displays.

WHILE the user has moderator priveledges, the system SHALL provide a "ban" button next to every registered user's name

WHEN the user presses the "ban" button, the system SHALL provide them with a form where they can enter the amount of time to ban the user for.

WHEN the user enters the amount of time and presses Enter, the system shall give the other user a ban status in the database and fill in the "banned until" field in it.

IF the user tries to send a message while banned, the system SHALL not send it.