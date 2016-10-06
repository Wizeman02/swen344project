##Student Enrollment System##

The Anatomy of our Node Project:

Right now the root directory of our Node project should look something like this:

    app/
        bin/
        templates/
        public/
        routes/
        app.js
        index.html
    node_modules/
    coverage/
    specs/
    bower.json
    package.json
    gulpfile.js

Explained(code comments are more specific):

    swen344project/
    |  app/ - contains our actual code, Javascript/Angular code, HTML templates, any styles, and our app.js and index.html.
    |   |   bin/       - figuring this out myself...
    |   |   public/    - contains AngularJS/any kind of javascript code, any CSS/SCSS/LESS, and static content like images.
    |   |   templates  - HTML templates that our Angular directives will use.
    |   |   app.js     - entry point to our application.
    |   |   index.html - the HTML file. all other necessary HTML will get used via Angular directives and controllers.
    |   |   routes/ - exactly what you think it does, holds routing information for different parts of the app
    |   |   specs/ - contains Jasmine unit tests
    |   bower.json - contains dependencies like node_modules/, but more specific ones like Angular Material or Bootstrap would go here
    |   gulpfile.js - very important for development, see the comments in the file for what each gulp task does
    |   package.json - defines what Node packages we need. Different gulp plugins, Angular itself, and Express are included here
    |   .coverdata/ - related to code coverage results when running `gulp tests`
    |   .coverrun - related to code coverage functionality when running `gulp tests`
    |   reports/ - contains an actual HTML file that displays the code coverage results when running `gulp tests`
    |   README.md - this file
    |   run.sh - .gitignore keeps ignoring this file, and I don't yet know why... feel free to use it by running `. run.sh` from root

        
DEVELOPMENT

After cloning the project, you'll need to run `npm install` and probably `bower install` as well in order to install all packages into the project. I made the .gitignore file include this node_modules folder because when its deployed to 'production', it will get built on the server/Heroku anyways as is common practice.

To run the app, simply go to the root directory and run `gulp`. This will run the `default` task within `gulpfile.js`. This in turn runs everything that is passed to the runSequence() method. See `gulpfile.js` for details. Running 'gulp' starts by deleting the /dist/ folder, then it minifies, combines, and injects all Javascript and CSS in app/ and bower_components/ into index.html. Then it puts all the needed files into a new dist/ folder and runs the development server on that new dist/ folder. The functionality to include any HTMl templates from app/templates into the dist/ folder still doesn't exist, but we have no templates yet to worry about.

Run the server locally: `. run.sh`

After making any changes, go back to terminal and press CTRL+C to stop the server. The just re-run the above command `. run.sh' and 


TESTING

From the root directory, run `gulp tests` to run all jasmine unit tests.  This refers to everything within the 'app/spec' directory. This can be nested and split into folders for organizational reasons, it doesn't all have to be in one file. BUT -- each file does need to have xxxx.spec.js at the end, not just xxxx.js!

#Contributors
Tyler Russell
Joshua James
Max Mendleson
Austin Cowan
Fawaz Alhenaki
