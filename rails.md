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

## Rails Console
all : te ressort tous les éléments de ton model (array).

new : crée une nouvelle instance de ton model.

save : enregistre cette instance.

create : crée et enregistre une instance de model.

update(attribute: value) : met à jour l'attribute de cet objet / entrée.

last : te retourne la dernière entrée créée dans le model.

first : pareil mais pour la première.

find(x) : te retourne l'entrée BDD dont l'id vaut x (integer).

find_by(attribute: value) : te retourne le premier élément qui a value à l'attribute.

where(attribute: value) : te retourne tous les éléments (dans un array) qui ont value à l'attribute.

destroy : supprime de la BDD l'entrée en question.
