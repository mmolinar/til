## Summary

First steps when beginning a new project and/or setting up a new machine.

## New machine

Install fish. Find out how.
 
Create a public/private ssh key pair
`ssh-keygen -t rsa -b 4096 -C "label or name for the key`

If you're using macOS Sierra 10.12.2 or later, you will need to modify your "~/.ssh/config" file to automatically load keys into the ssh-agent and store passphrases in your keychain.
`Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa`
  
Add your SSH private key to the ssh-agent and store your passphrase in the keychain. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_rsa in the command with the name of your private key file.
`ssh-add -K ~/.ssh/id_rsa` ie `ssh-add -K ~/.ssh/id_rsa_github`


## New project

Install Ruby version desired
`rbenv install 2.7.1`

Use this version
`rbenv shell 2.7.1`

Install gem bundler to be able to install gems.
`gem install bundler`

Install rails and all gems needed for the project (or cloned project)
`gem install rails`

Update Gemfile.lock with:
`bundle install`

Initialize Rspec (or Minitest) for debugging
`rspec --init`

Get gem Pry for debugging and `require 'pry'` in the program needing debugging.  
`
gem pry
`

Use `binding.pry` in the line of code of your program you want to debug. exit pour sortir du Pry.

Use `gem dotenv` to keep your API keys off Github. 

Store all your keys in a .env folder and add the .env folder in your .gitignore so it won't be pushed and the keys stay private.

Then create a database and migrate said database.
`rails db:create`
`rails db:migrate`
