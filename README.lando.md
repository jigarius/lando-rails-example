# Lando Rails Example

Planning to dockerize your Ruby on Rails dev environment? Here's how you can
easily set up your Rails project with Lando.

Read the full article on [Jigarius.com](https://jigarius.com/).

## Usage

Here's how you can use this repository. Please note that this is intended to
be used for local development only and not for deployment on
production servers.

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
  * Modify the following as per your needs:
    * Project name in the `.lando.yml`
    * Ruby version
      * in the `.lando.yml` file.
      * in the `Gemfile`.
    * Rails version in the `Gemfile`.
  * Run `lando start` (you must have Lando installed).
  * Create a new Rails project `lando rails new --database=postgresql /app`.
    * This example uses postgres but you can change it if you want.
    * The Rails installation must be placed at `/app`.
  * Update your `config/database.yml` to use the correct credentials.
    * You can use the same settings as `lando/appserver/example.database.yml`.
