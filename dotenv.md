Create .env folder in your app on same level as your Gemfile etc..

Install `gem 'dotenv'`

Run `$bundle install` to update Gemfile.lock

Add keys to your .env folder
```
TWITTER_API_KEY="my-twitter-api-key"
TWITTER_API_SECRET="this_is_soooo_secret"

BEST_WEBSITE_EVER="thehackingproject"
```

Add this to your `app.rb`
```
require 'dotenv'# Appelle la gem Dotenv

Dotenv.load('.env') # Ceci appelle le fichier .env (situé dans le même dossier que celui d'où tu exécute app.rb)
# et grâce à la gem Dotenv, on importe toutes les données enregistrées dans un hash ENV

# Il est ensuite très facile d'appeler les données du hash ENV, par exemple là je vais afficher le contenu de la clé TWITTER_API_SECRET
puts ENV['TWITTER_API_SECRET']

#Autre exemple 
puts ENV['BEST_WEBSITE_EVER']
```

Go into your folder where you're keeping .env and execute `$ ruby lib/app.rb`. You should be able to see the secret contents inside.

Architecture of the dotenv_test folder:
```
dotenv_test
├── lib
│   └── app.rb
├── README.md
├── Gemfile
├── .env
└── .gitignore
```
### DONT FORGET! Add .env to your .gitignore before pushing to Github otherwise your keys will be exposed
