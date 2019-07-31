## Commands

Create a new rails app/project
`rails new name_of_project`

See all of the command line options that Rails accepts `rails new -h`

Generate a Controller
`bin/rails generate controller Controller_Name controller_action`

Rails provides a resources method which can be used to declare a standard REST resource. In config.rb add:
`resources :articles` For an Articles resource.

To create a model:
`bin/rails generate model Article` Name of model is always singular

To run the migration of the database created with the model:
`bin/rails db:migrate`
