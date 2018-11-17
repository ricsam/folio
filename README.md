## StackOverflow
[https://stackoverflow.com/users/1105047/richie](https://stackoverflow.com/users/1105047/richie){:target="_blank"}

## Open source

### 2017 - ipc-promises
[https://github.com/ricsam/ipc-promises](https://github.com/ricsam/ipc-promises){:target="_blank"}

A ES6 promise interface for the use of the inter-process communication in Electron.js

### 2015 - Murkel
[https://github.com/ricsam/murkel](https://github.com/ricsam/murkel){:target="_blank"}

Static website generator from markdown files

### 2012 - Hot-Corn-Dog
[https://github.com/ricsam/Hot-Corn-Dog](https://github.com/ricsam/Hot-Corn-Dog){:target="_blank"}

This is a small GNOME Shell extension where you can pick your own "hot corners" for toggling the overview, or for running custom applications. You can also change the "hot corner" for the message tray.
Written in Javascript

## Web app examples
  * NASA Media library search
    * [Repo](https://github.com/ricsam/nasa-app){:target="_blank"}
    * [Demo](https://ricsam.github.io/nasa-app/){:target="_blank"}
  * Weather app
    * [Repo](https://github.com/ricsam/weather-app){:target="_blank"}
    * [Demo](https://ricsam.github.io/weather-app/){:target="_blank"}



## Projects

### 2017 - "killergame"
[https://killergame-42f36.firebaseapp.com/](https://killergame-42f36.firebaseapp.com/){:target="_blank"}

A game developed in Firebase. Using the firebase API to [serve notifications](https://github.com/ricsam/killergame/blob/master/functions/firebase-messaging-sw.js){:target="_blank"} and [handle login and DB](https://github.com/ricsam/killergame/blob/master/functions/app/metamorph-functions.js#L320){:target="_blank"}. The server side code in firebase is hard to test and slow to deploy, however the backend API is more or less the same as the frontend. Thus I developed the API in an [isomorfic manner](https://github.com/ricsam/killergame/blob/master/functions/app/metamorph-functions.js#L6){:target="_blank"} so I could test back-end logic in the webbrowser. The complete application logic is confined by [main.js](https://github.com/ricsam/killergame/blob/master/functions/app/main.js){:target="_blank"} and [ui-binds.js](https://github.com/ricsam/killergame/blob/master/functions/app/ui-binds.js){:target="_blank"}

### 2016 - "local-server-deployer"
Anonymous (using TOR network) web crawler in phantomjs. This project enables locally developed es6 code to be deployed via [CRUD operations](https://github.com/ricsam/local-server-deployer/blob/master/deployer.js#L55){:target="_blank"} to servers on the local network. The local servers executes a [js file](https://github.com/ricsam/local-server-deployer/blob/master/local/configure.js){:target="_blank"} which handles the prerequisites to run the application (e.g. starting TOR and [Babel compiling](https://github.com/ricsam/local-server-deployer/blob/master/local/configure-api.js#L94){:target="_blank"}). Thereafter the phantomjs instance is started with the [web crawler code](https://github.com/ricsam/local-server-deployer/blob/master/local/scripts/crawler.js){:target="_blank"} which runs the underlying [API](https://github.com/ricsam/local-server-deployer/blob/master/local/scripts/keyboard-api.js){:target="_blank"} for common tasks, like moving mouse, typing and clicking links.

### 2016 - Desktop automator
[https://github.com/ricsam/automator](https://github.com/ricsam/automator){:target="_blank"}

Written in React.js and Electron. Scripts like [this](https://github.com/ricsam/automator/blob/master/scripts/autoclicker.listener.js){:target="_blank"} are provided by a GUI like [this](https://github.com/ricsam/automator/blob/master/scripts/autoclicker.renderer.js#L88){:target="_blank"}

### 2015 - OriC-finder
[http://ricsam.github.io/OriC-finder](http://ricsam.github.io/OriC-finder#select/){:target="_blank"}

Bioinformatic algorithms in CoffeeScript, served either under an express server where data is [downloaded](https://github.com/ricsam/OriC-finder/blob/v2.0/modules/genome-download.coffee){:target="_blank"} from `ftp.ncbi.nlm.nih.gov`, or as a front-end only application where cached data is used (the precursor to ["gh pages server"](https://ricsam.github.io/folio/#2015---gh-pages-server--member-platform) was used for single-page app logic).

- [The implemented parallelized "dnaa algorithm"](https://github.com/ricsam/OriC-finder/tree/v2.0/public/pages_/dnaa){:target="_blank"}, initialized from main.coffee
- [The implementation of the front-end application logic](https://github.com/ricsam/OriC-finder/tree/v2.0/public/server_){:target="_blank"}

### 2015 - "gh pages server" / member-platform

- [Demo](https://ricsam.github.io/member-platform/apps/register-with-autofill){:target="_blank"} (not configured to run on the github pages domain)
- [Source](https://github.com/ricsam/member-platform/tree/gh-pages){:target="_blank"}

A platform for registration of student-union cards with an API to develop associated apps e.g. app for member-only ticket sales. To build this I created ["gh pages server" (github pages server)](https://github.com/ricsam/member-platform/tree/gh-pages/amd_/js){:target="_blank"} which uses the 404.html page to route paths to content. The resources needed can be defined in a simple manner using [router.json](https://github.com/ricsam/member-platform/blob/gh-pages/router.json){:target="_blank"}. The gh pages server, which is simply a front-end only service, is designed to have the same functionality as a normal server when it comes to routing, with URL wildcards and aliases. The main content served in the platform is in the form of ["apps"](https://github.com/ricsam/member-platform/tree/gh-pages/apps_){:target="_blank"} which can have associated settings pages and permissions. 


