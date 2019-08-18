## Validations

### confirmation
You should use this helper when you have two text fields that should receive exactly the same content. For example, you may want to confirm an email address or a password. 
```
class Person < ApplicationRecord
  validates :email, confirmation: true
  validates :email_confirmation, presence: true
end
```

In your view template you could use something like:
```
<%= text_field :person, :email %>
<%= text_field :person, :email_confirmation %>
```

This check is performed only if email_confirmation is not nil. 
To require confirmation, make sure to add a presence check for the confirmation attribute

### format
The attributes values are only letters (no numbers).
```
class Product < ApplicationRecord
  validates :legacy_code, format: { with: /\A[a-zA-Z]+\z/,
    message: "only allows letters" }
end
```

### length
Validates the length of the attribute.
```
class Person < ApplicationRecord
  validates :name, length: { minimum: 2 }
  validates :bio, length: { maximum: 500 }
  validates :password, length: { in: 6..20 }
  validates :registration_number, length: { is: 6 }
end
```
The default error messages depend on the type of length validation being performed. You can personalize these messages using the :wrong_length, :too_long, and :too_short options and %{count} as a placeholder for the number corresponding to the length constraint being used. You can still use the :message option to specify an error message.
```
class Person < ApplicationRecord
  validates :bio, length: { maximum: 1000,
    too_long: "%{count} characters is the maximum allowed" }
end
```
### presence
