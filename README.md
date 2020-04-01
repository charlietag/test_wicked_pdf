# README

* Try rails gem
  * https://github.com/mileszs/wicked_pdf

## Things you may want to cover:

* Ruby version
  * 2.6.0

* Rails version
  * 6.0.2.1

* Gems - useful for dev
  * gem 'pry-rails', :group => :development
  * gem 'bullet', group: 'development'

* Gems - tried this time
  * gem 'wicked_pdf'
  * gem 'wkhtmltopdf-binary'

* jQuery
  * yarn add jquery
    * test_rails_delayedjob_mailer_simpleform/app/javascript/packs/application.js

      ```bash
      import "jquery/src/jquery"
      ...
      ```

* bootstrap
  * yarn add bootstrap popper.js (don't add popper v2, bootstrap default requires v1.16) , (no need to import popper.js manually, bootstrap will do it automatically)
    * app/javascript/packs/application.js
    * app/assets/stylesheets/application.css

## Rails setup

* generate Book
  * `bin/rails g scaffold Book name:string author:string`


## config - credential

* command
  * `EDITOR=vim bundle exec rails credentials:edit`

    ```
    development:
      db:
        user: user
        pass: pass

    production:
      db:
        user: user
        pass: pass
    ```


* https://github.com/charlietag/test_wicked_pdf/compare/v0.0.0...master

