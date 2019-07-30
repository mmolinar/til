## Summary
Rbenv is like Brew for Ruby, a Gestionnaire de Ruby. Rbenv has to be installed with Brew. 

Everytime we use Ruby, it should be by Rbenv.

Rbevn installs irb which is a Ruby interpreter (console) and installs some gems.

## Before starting new project

Go into the project and check the Ruby versions on local and project are the same
`rbenv versions`

## Main Usage
If Ruby version is system version, change to another one
`rbenv local 2.7...?` (or tab after rbenv local to see what the options are)

Install the same Ruby version
`rbevn install 2.7...?`

Then install bundler gem
`gem install bundler`

Initialize Rbenv
`rbenv init`

Then follow instructions. 

## Other
Rbenv help and not man to see what to do.

rm -rf .ruby-version on the Projects to go back to ruby system and have to create a new ruby version or choose a new one with each porejct




