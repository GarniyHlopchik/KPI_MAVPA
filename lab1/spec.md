## Сутності

# Person

Спільні дані для звичайних юзерів та модераторів. Містить поля id (UUID, primary key), login, password_hash, username

# User

Звичайний користувач. Містить атрибут person_id - foreign key на Person.

# Moderator

Також містить атрибут person_id - foreign key на Person.

# Thread

Гілка, що містить повідомлення. Має атрибути id, is_active, name

# Message

Повідомлення. Атрибути: id, sender_status (registered, verified, not_verified), text, username, tripcode

## Зв'язки

