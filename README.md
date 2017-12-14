** Below guide is adapted from Philip Johnson's [Bowfolios guide](https://bowfolios.github.io/)
# Installation

First things first, [install Meteor](https://www.meteor.com/install).

Next, [download a copy of Math ](https://github.com/hexokinase/math-rush/archive/master.zip), or clone it using git.

Third, extract contents and cd into the app/ directory and install libraries with:

```
$ meteor npm install
```

Fourth, run the system with:

```
$ meteor npm run start
```

The application will appear at [http://localhost:3000](http://locahost:3000). Login and try it out!

The app/ directory has this top-level structure:

```
client/
  lib/           # holds Semantic UI files.
  head.html      # the <head>
  main.js        # import all the client-side html and js files.

imports/
  api/           # Define collection processing code (client + server side)
    addsubtract/
    base/
    interest/
    profile/
  startup/       # Define code to run when system starts up (client-only, server-only)
    client/        
    server/        
  ui/
    components/  # templates that appear inside a page template.
    layouts/     # Layouts contain common elements to all pages (i.e. menubar and footer)
    pages/       # Pages are navigated to by FlowRouter routes.
    stylesheets/ # CSS customizations, if any.

node_modules/    # managed by Meteor

private/
  database/      # holds the JSON file used to initialize the database on startup.

public/          
  images/        # holds static images for landing page and predefined sample users.

server/
   main.js       # import all the server-side js files.
```

The app/ directory has this top-level structure:

```
client/
  lib/           # holds Semantic UI files.
  head.html      # the <head>
  main.js        # import all the client-side html and js files.

imports/
  api/           # Define collection processing code (client + server side)
    base/
    interest/
    profile/
  startup/       # Define code to run when system starts up (client-only, server-only)
    client/        
    server/        
  ui/
    components/  # templates that appear inside a page template.
    layouts/     # Layouts contain common elements to all pages (i.e. menubar and footer)
    pages/       # Pages are navigated to by FlowRouter routes.
    stylesheets/ # CSS customizations, if any.

node_modules/    # managed by Meteor

private/
  database/      # holds the JSON file used to initialize the database on startup.

public/          
  images/        # holds static images for landing page and predefined sample users.

server/
   main.js       # import all the server-side js files.
```

## Import conventions

This system adheres to the Meteor 1.4 guideline of putting all application code in the imports/ directory, and using client/main.js and server/main.js to import the code appropriate for the client and server in an appropriate order.

This system accomplishes client and server-side importing in a different manner than most Meteor sample applications. In this system, every imports/ subdirectory containing any Javascript or HTML files has a top-level index.js file that is responsible for importing all files in its associated directory.   

Then, client/main.js and server/main.js are responsible for importing all the directories containing code they need. For example, here is the contents of client/main.js:

```
import '/imports/startup/client';
import '/imports/ui/components/form-controls';
import '/imports/ui/components/directory';
import '/imports/ui/components/user';
import '/imports/ui/components/landing';

import '/imports/ui/layouts/landing';
import '/imports/ui/layouts/gametypes';
import '/imports/ui/layouts/profile';
import '/imports/ui/layouts/home';
import '/imports/ui/layouts/game1';
import '/imports/ui/layouts/leaderboard';

import '/imports/ui/pages/landing';
import '/imports/ui/pages/gametypes';
import '/imports/ui/pages/profile';
import '/imports/ui/pages/home';
import '/imports/ui/pages/game1';
import '/imports/ui/pages/leaderboard';

import '/imports/ui/stylesheets/style.css';
import '/imports/api/addsubtract';

```

Apart from the last line that imports style.css directly, the other lines all invoke the index.js file in the specified directory.

We use this approach to make it more simple to understand what code is loaded and in what order, and to simplify debugging when some code or templates do not appear to be loaded.  In our approach, there are only two places to look for top-level imports: the main.js files in client/ and server/, and the index.js files in import subdirectories.

Note that this two-level import structure ensures that all code and templates are loaded, but does not ensure that the symbols needed in a given file are accessible.  So, for example, a symbol bound to a collection still needs to be imported into any file that references it.

## Naming conventions

This system adopts the following naming conventions:

  * Files and directories are named in all lowercase, with words separated by hyphens. Example: accounts-config.js
  * "Global" Javascript variables (such as collections) are capitalized. Example: Profiles.
  * Other Javascript variables are camel-case. Example: collectionList.
  * Templates representing pages are capitalized, with words separated by underscores. Example: Directory_Page. The files for this template are lower case, with hyphens rather than underscore. Example: directory-page.html, directory-page.js.
  * Routes to pages are named the same as their corresponding page. Example: Directory_Page.

  ## CSS

  The application uses the [Semantic UI](http://semantic-ui.com/) CSS framework. To learn more about the Semantic UI theme integration with Meteor, see [Semantic-UI-Meteor](https://github.com/Semantic-Org/Semantic-UI-Meteor).

  The Semantic UI theme files are located in [app/client/lib/semantic-ui](https://github.com/ics-software-engineering/meteor-application-template/tree/master/app/client/lib/semantic-ui) directory. Because they are located in the client/ directory and not the imports/ directory, they do not need to be explicitly imported to be loaded. (Meteor automatically loads all files into the client that are located in the client/ directory).

  Note that the user pages contain a menu fixed to the top of the page, and thus the body element needs to have padding attached to it.  However, the landing page does not have a menu, and thus no padding should be attached to the body element on that page. To accomplish this, the [router](https://github.com/hexokinase/math-rush/blob/master/app/imports/startup/client/router.js) uses "triggers" to add an remove the appropriate classes from the body element when a page is visited and then left by the user.

  ## Routing

  For display and navigation among its four pages, the application uses [Flow Router](https://github.com/kadirahq/flow-router).

  Routing is defined in [imports/startup/client/router.js](https://github.com/ics-software-engineering/meteor-application-template/blob/master/app/imports/startup/client/router.js).

  Math Rush defines the following routes:

    * The `/` route goes to the public landing page.
    * The `/home` route goes to the main home page.
    * The `/userprofile` route goes to the profile page associated with the user page/
    * The `/gametypes` route goes to the game types page to view games.
    * The `/leaderboard` route goes to the highscores page, currently is just a mockup.
    * The `/game1` route goes a game that the user can play, functionality is currently limited.

  ## Authentication

  For authentication, the application uses the University of Hawaii CAS test server, and follows the approach shown in [meteor-example-uh-cas](http://ics-software-engineering.github.io/meteor-example-uh-cas/).

  When the application is run, the CAS configuration information must be present in a configuration file such as  [config/settings.development.json](https://github.com/ics-software-engineering/meteor-application-template/blob/master/config/settings.development.json).

  Anyone with a UH account can login and use BowFolio to create a portfolio.  A profile document is created for them if none already exists for that username.

  ## Authorization

  We are currently working to make the profile page personalized and only accessible by the user, but it is currently a default public page.

  ## Configuration

  The [config](https://github.com/hexokinase/math-rush/tree/master/config) directory is intended to hold settings files.  The repository contains one file: [config/settings.development.json](https://github.com/hexokinase/math-rush/blob/master/config/settings.development.json).

  The [.gitignore](https://github.com/hexokinase/math-rush/blob/master/.gitignore) file prevents a file named settings.production.json from being committed to the repository. So, if you are deploying the application, you can put settings in a file named settings.production.json and it will not be committed.

  Math Rush checks on startup to see if it has an empty database in [initialize-database.js](https://github.com/hexokinase/math-rush/blob/master/app/imports/startup/server/initialize-database.js), and if so, loads the file specified in the configuration file, such as [settings.development.json](https://github.com/hexokinase/math-rush/blob/master/config/settings.development.json).  For development purposes, a sample initialization for this database is in [initial-collection-data.json](https://github.com/hexokinase/math-rush/blob/master/app/private/database/initial-collection-data.json).

  ## Quality Assurance

  ### ESLint

  Math Rush includes a [.eslintrc](https://github.com/hexokinase/math-rush/blob/master/app/.eslintrc) file to define the coding style adhered to in this application. You can invoke ESLint from the command line as follows:

  ```
  meteor npm run lint
  ```

  ESLint should run without generating any errors.  

  It's significantly easier to do development with ESLint integrated directly into your IDE (such as IntelliJ).
