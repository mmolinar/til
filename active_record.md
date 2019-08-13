## Validations

# Confirmation
`class Person < ApplicationRecord
  validates :email, confirmation: true
  validates :email_confirmation, presence: true
end`
In your view template you could use something like:
`<%= text_field :person, :email %>
<%= text_field :person, :email_confirmation %>`

This check is performed only if email_confirmation is not nil. 
To require confirmation, make sure to add a presence check for the confirmation attribute
