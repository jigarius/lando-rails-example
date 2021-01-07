# Lando Rails Example

Planning to dockerize your Ruby on Rails dev environment? Here's how you can
easily set up your Rails project with Lando.

Read the full article on [Jigarius.com](https://jigarius.com/).

## Usage

Here's how you can use this repository. Please note that this is intended to
be used for local development only and not for production.

  * Follow the steps mentioned under _Existing app_ or _New app_.
    * This will ensure that you have a Rails app.
  * In `config/database.yml` to update database credentials.
    * See `lando/appserver/example.database.yml`.
  * In `config/environments/development.rb` allow requests from `*.lndo.site`.
    * Add `config.hosts << /.*\.lndo\.site/`.
  * Run `lando rake db:create` to create databases.
  * Run `lando rake db:migrate` to execute migrations.
  * Run `lando rails-server` to start the `rails server`.

Voila! Your Rails app should now be running at `rails.lndo.site`.

### Existing app

If you have an existing Rails app,

  * Copy the `.lando` file to the root of your Rails project.
  * Update your `config/database.yml` to use the correct credentials.
    * See `lando/appserver/example.database.yml`.
  * `cd` into the root directory of your project.
  * Run `lando start` (you must have Lando installed).

### New app

  * Clone/download this repository.
  * `cd` into the code directory.
  * Modify the following config as per your needs:
    * Project name in the `.lando.yml`
    * Ruby version (for advanced users).
      * in the `.lando.yml` file.
      * in the `Gemfile`.
      * in the `lando/appserver/Dockerfile`.
    * Rails version in the `Gemfile` (for advanced users).
  * Create a new Rails app `lando rails new --database=postgresql /app`.
    * You can add other flags, e.g. `--minimal`.
    * The Rails install path must be `/app`.

Run the command `lando` to see a list of available commands.
