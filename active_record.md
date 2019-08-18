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

### presence
