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
If minimum is going to be set to 1, it's best to use the "presence" validation and set it to true: `presence: true`

### numericality
This helper validates that your attributes have only numeric values. By default, it will match an optional sign followed by an integral or floating point number. To specify that only integral numbers are allowed set :only_integer to true.
```
class Player < ApplicationRecord
  validates :points, numericality: true
  validates :games_played, numericality: { only_integer: true }
end
```
Besides only_integer it also accepts: `:greater_than, :greater_than_or_equal_to, :equal_to, :less_than, :less_than_or_equal_to, :other_than, :odd, :even`

### presence
Validates the attribute is not empty.
```
class Person < ApplicationRecord
  validates :name, :login, :email, presence: true
end
```
If you want to be sure that an association is present, you'll need to test whether the associated object itself is present, and not the foreign key used to map the association.
```
class LineItem < ApplicationRecord
  belongs_to :order
  validates :order, presence: true
end
```

### uniqueness
This helper validates that the attribute's value is unique right before the object gets saved. It does not create a uniqueness constraint in the database, so it may happen that two different database connections create two records with the same value for a column that you intend to be unique. To avoid that, you must create a unique index on that column in your database.
```
class Account < ApplicationRecord
  validates :email, uniqueness: true
end
```
There is a :scope option that you can use to specify one or more attributes that are used to limit the uniqueness check:
```
class Holiday < ApplicationRecord
  validates :name, uniqueness: { scope: :year,
    message: "should happen once per year" }
end
```
Uniqueness also take in `:case_sensitive` 

## Validation options
### :message
As you've already seen, the :message option lets you specify the message that will be added to the  errors collection when validation fails. When not used, default error message appears.
```
class Person < ApplicationRecord
  # Hard-coded message
  validates :name, presence: { message: "must be given please" }
 
  # Message with dynamic attribute value. %{value} will be replaced with
  # the actual value of the attribute. %{attribute} and %{model} also
  # available.
  validates :age, numericality: { message: "%{value} seems wrong" }
 
  # Proc
  validates :username,
    uniqueness: {
      # object = person object being validated
      # data = { model: "Person", attribute: "Username", value: <username> }
      message: ->(object, data) do
        "Hey #{object.name}!, #{data[:value]} is taken already! Try again #{Time.zone.tomorrow}"
      end
    }
end
```
