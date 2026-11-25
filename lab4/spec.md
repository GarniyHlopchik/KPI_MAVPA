## Activity diagram

# (UC8: View Thread Messages)

Gherkin-сценарії:

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

Додатково було додано третій сценарій для покриття варіанту неуспішної спроби відкриття гілки (зазначено у розбіжностях):

Scenario: SCN5b - Attempt to open Non-Existant Thread
  Given there are threads available in the list
  When the user clicks on one of the threads which no longer exists internally
  Then an error message should appear on the screen
  And the user should be redirected back to an updated threads list

Уточнення до попередніх вимог:

- користувач може запросити перегляд повідомлень у гілці лише після того, як отримав актуальний список гілок (повідомлення)
- процес відмальовування повідомлень та відмальовування елементів інтерфейсу (що включає в себе перевірку інформації про те, чи є користувач зареєстрованим) виконуються паралельно та об'єднуються перед показом результату користувачеві
- інтерфейс показує користувачеві поля юзернейму та тріпкоду за *умови*, що користувач не зареєстрований
- якщо час очікування на відповідь від бекенду перевищує 5 секунд, то фронтенд видасть користувачеві повідомлення про мережеву помилку та запропонує повернутись до списку гілок.
