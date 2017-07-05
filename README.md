# CakePHP, LTI, ReactJS and Material UI Skeleton App

A skeleton for creating [LTI-enabled](http://www.spvsoftwareproducts.com/php/lti_tool_provider/) 
applications with [CakePHP](http://cakephp.org) 3.x, 
combined with [React](https://facebook.github.io/react) 
and [Material-UI](http://www.material-ui.com/)

## PHP Installation

Download [Composer](http://getcomposer.org/doc/00-intro.md) or update `composer self-update`.

From the root directory of the app, if Composer is installed globally, run
```bash
composer install
```

Or, if Composer is only installed locally run `php composer.phar install`.

## Configuration

Read and edit `config/app.php` and setup the 'Datasources' and any other
configuration relevant for your application.

### Database setup

Run the SQL in DB_LTI.sql to create the necessary tables for the SQL setup. 

## LTI Setup

You will need to create a lti_consumer record in order to create the first LTI 
link to the app. Necessary fields to complete at consumer_key, name, secret, 
set enabled to 1 and protected to 0.

In src\Controller\LtiConsumerController.php, set up the redirect logic to 
redirect the user once the LTI launch has been verified and the user 
registered. This may involve looking up whether there is already an item 
associated with this LTI link, if there is sending the user to that item, and 
if there isn't, allowing them to associate an item.

Launch url will be (localhost\app)\launch (see config\routes.php)

## Javascript Installation

### Package.json

#### Either:

Update the details in package.json to match the new project

#### Or:

`npm init` then run through the questions

### Install Dependencies

#### Either:

In the webroot/js directory, run `npm install` to install dependencies.
The dependencies are listed in package.json.

#### Or:

Install react and material-ui:
`npm install --save react react-dom material-ui react-tap-event-plugin html5shiv`

Install dev dependencies:
`npm install --save-dev browserify babelify babel-preset-react gulp gulp-concat gulp-count gulp-livereload gulp-load-plugins gulp-notify gulp-sourcemaps gulp-uglify gulp-util lodash.assign vinyl-buffer vinyl-source-stream watchify`

### Gulp
To build the js bundle, run `gulp`. The gulp build steps are defined in 
gulpfile.js

gulp is set to watch the js directories for any changes and will automatically
run the build steps and reload the browser using livereload when changes are 
detected. 

### Topbar

A topbar (webroot/js/src/topbar.jsx) is included as an example of setting up a 
Material UI component to work with browserify, etc, as this differs slightly 
from the Material UI docs.

### LiveReload

1. Install the LiveReload desktop app from http://livereload.com/
2. Install the appropriate browser plugin (not IE!)
3. Enable LiveReload for your page by clicking the plugin icon

### Material UI Theme

The Material UI theme can be modified by editing webroot/js/src/theme.jsx

See http://www.material-ui.com/#/customization/themes

## Fonts

The app uses the [Roboto font](https://www.google.com/fonts/specimen/Roboto) 
and [Material icons](https://design.google.com/icons/).

## Licenses
* [CakePHP](http://cakephp.org/): [MIT](https://github.com/cakephp/cakephp/blob/master/LICENSE.txt)
* [PHP LTI Tool Provider class](http://www.spvsoftwareproducts.com/php/lti_tool_provider/): [LGPLv3](http://www.gnu.org/licenses/lgpl.html)
* [React](https://facebook.github.io/react) :[BSD](https://github.com/facebook/react/blob/master/LICENSE)
* [Material-UI](http://www.material-ui.com/) :[MIT](https://github.com/callemall/material-ui/blob/master/LICENSE)
* [react-tap-event-plugin](https://github.com/zilverline/react-tap-event-plugin) :[MIT](https://github.com/zilverline/react-tap-event-plugin/blob/master/LICENSE)
* [HTML5Shiv](https://github.com/aFarkas/html5shiv) :[MIT](https://github.com/aFarkas/html5shiv/blob/master/MIT%20and%20GPL2%20licenses.md)
* [Roboto font](https://www.google.com/fonts/specimen/Roboto) :[Apache License, version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html)
* [Material icons](https://design.google.com/icons/) :[CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)
