## Summary

Gestionnaire de packets to install and update programs all at once. Brew is for iOS. Brew is the  command for brew to startup, followed by a command like "search" or "install" to do something.

Always install everything with brew so that updates are done at once and not one by one.
  
## First steps (once only ie new machine)

First thing to install is brew itself.

Then install Git with brew
`brew install git`

Install Rbenv. Rbenv is like a brew for Ruby (Gestionnaire de Ruby). Everytime we use Ruby we'll do it using Rbenv.
`brew install rbenv`

Makes it easy to install any Ruby version
`brew install ruby-build`

Install to make sure rails db:.... 'always' works.
`brew install rbenv-bundle-exec`

Install after rbenv so installing bundler is not forgotten in a step. Avoids having to install with "gem install bundler" after installing rbenv. 
`brew install rbenv-bundler`


## Main Usage

First let's search for a packet (cause we don't obvsiously know the packet name)
`brew search my_search_string` ie "sub" to look for "sublime"

Then install the packet related
`brew install my_packet`


## Advance usage

"Casks" are additional 'add-ons' like Chrome. They don't come with brew.

To install a cask
`brew install cask name_of_cask`

## Uninstalling Brew

To unistall Brew because it doesn't work for whatever reason.
`ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"`

## Aternative tools

apt-get for linux, apk for alpine
