# README

* Try rails gem
  * gem: `wicked_pdf`
    * gem: `wkhtmltopdf-binary`
    * OS packages for "Traditional Chinese" fonts
      * 標楷體 Only
        * `yum install -y cjkuni-ukai-fonts cjkuni-uming-fonts`
      * 更多字體 如 新細明體 (但是要自己CSS 指定-還沒找到指定的方法，因為預設會變醜)
        * `yum groupinstall "Fonts"`

  * gem: `grover`
    * gem: `dotenv-rails` ({RAILS_APP}/.env)
      * `GROVER_NO_SANDBOX="true"`
    * "Traditional Chinese" supports
      * Default : NO NEED to do anything
    * Frontend packages
      * `yarn add puppeteer
    * OS packages which Google Puppeteer requires to render pages to PDF
      * https://github.com/puppeteer/puppeteer/blob/master/docs/troubleshooting.md#chrome-headless-doesnt-launch-on-unix
        
        ```bash
        yum install -y \
        pango \
        libXcomposite \
        libXcursor \
        libXdamage \
        libXext \
        libXi \
        libXtst \
        cups-libs \
        libXScrnSaver \
        libXrandr \
        GConf2 \
        alsa-lib \
        atk \
        gtk3 \
        ipa-gothic-fonts \
        xorg-x11-fonts-100dpi \
        xorg-x11-fonts-75dpi \
        xorg-x11-utils \
        xorg-x11-fonts-cyrillic \
        xorg-x11-fonts-Type1 \
        xorg-x11-fonts-misc
        ```

        ```bash
        yum update nss -y
        ```

## Differences

* wicked_pdf
  * Easy to customize specific pdf pages
    * EX
      * {RAILS_APP}/app/assets/stylesheets/pdf.scss
      * {RAILS_APP}/app/controllers/books_controller.rb (format.pdf)
      * {RAILS_APP}/app/views/books/index.pdf.erb
      * {RAILS_APP}/app/views/layouts/pdf.pdf.erb
* grover
  * Easy to print page to pdf
    * EX
      * URI ---> URI.pdf
      * Done
  * Config files
    * config/application.rb
    * config/initializers/grover.rb
    * .env (dotenv-rails , for disabling GROVER_NO_SANDBOX)

## Things you may want to cover:

* Ruby version
  * 2.6.0

* Rails version
  * 6.0.2.2

* Gems - useful for dev
  * gem 'pry-rails', :group => :development
  * gem 'bullet', group: 'development'

* Gems - tried this time
  * gem 'wicked_pdf'
  * gem 'wkhtmltopdf-binary'
  * gem 'grover'
  * gem 'dotenv-rails'

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
      * `import "bootstrap/dist/js/bootstrap"`
    * app/assets/stylesheets/application.css
      * `*= require 'bootstrap/dist/css/bootstrap'`

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
