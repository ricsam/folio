## Projects

### 2017 - "killergame"
[https://killergame-42f36.firebaseapp.com/](https://killergame-42f36.firebaseapp.com/){:target="_blank"}
A game developed in Firebase. Using the firebase API to [serve notifications](https://github.com/ricsam/killergame/blob/master/functions/firebase-messaging-sw.js){:target="_blank"} and [handle login and DB](https://github.com/ricsam/killergame/blob/master/functions/app/metamorph-functions.js#L320){:target="_blank"}. The server side code in firebase is hard to test and slow to deploy, however the backend API is more or less the same as the frontend. Thus is developed the interface for the application in a isomorfic manner so I could test back-end logic in the [webbrowser](https://github.com/ricsam/killergame/blob/master/functions/app/metamorph-functions.js#L6){:target="_blank"}. The complete application logic is confined in [main.js](https://github.com/ricsam/killergame/blob/master/functions/app/main.js){:target="_blank"} and [ui-binds.js](https://github.com/ricsam/killergame/blob/master/functions/app/ui-binds.js){:target="_blank"}

### 2016 - "local-server-deployer"
Anonymous (using TOR network) web crawler in phantomjs. The developed es6 code was automatically [deployed](https://github.com/ricsam/local-server-deployer/blob/master/deployer.js){:target="_blank"} via CRUD operations to servers on the local network. The local servers executes a [js file](https://github.com/ricsam/local-server-deployer/blob/master/local/configure.js){:target="_blank"} which handles the prerequisites to run the application. Thereafter the phantomjs instance is started with the [web crawler code](https://github.com/ricsam/local-server-deployer/blob/master/local/scripts/crawler.js){:target="_blank"} which runs the underlying [API](https://github.com/ricsam/local-server-deployer/blob/master/local/scripts/keyboard-api.js){:target="_blank"} for common tasks, like moving mouse, typing and clicking links.

### 2015 - OriC-finder
[http://ricsam.github.io/OriC-finder](http://ricsam.github.io/OriC-finder#select/){:target="_blank"}
Bioinformatic algorithms in CoffeeScript, served either under an express server where data is [downloaded](https://github.com/ricsam/OriC-finder/blob/v2.0/modules/genome-download.coffee){:target="_blank"} from `ftp.ncbi.nlm.nih.gov`, or as a front-end only application where cached data is used (this isomorfic logic is handled like [this](https://github.com/ricsam/OriC-finder/blob/3088e3d168cb9454edbec257437cc32dcd844ad1/public/server_/GenBank.coffee#L84){:target="_blank"}).

- [The implemented "dnaa algorithm"](https://github.com/ricsam/OriC-finder/tree/v2.0/public/pages_/dnaa){:target="_blank"}, initialized from main.coffee
- [The implementation of the front-end application logic](https://github.com/ricsam/OriC-finder/tree/v2.0/public/server_){:target="_blank"}



### 2015 - GitHub server / member-platform

- [Demo](https://ricsam.github.io/member-platform/apps/register-with-autofill){:target="_blank"} (not configured to run on the github pages domain)
- [Source](https://github.com/ricsam/member-platform/tree/gh-pages){:target="_blank"}

A platform for registration of student-union cards which could be used for e.g. events. To build this service I created a ["github server"](https://github.com/ricsam/member-platform/tree/gh-pages/amd_/js){:target="_blank"} which uses the 404.html page to route paths to content. The resources needed can be defined in a simple manner using [router.json](https://github.com/ricsam/member-platform/blob/gh-pages/router.json){:target="_blank"}. The github server, which is simply a front-end only service, is designed to have the same functionality as a normal server when it comes to routing, with URL wildcards and aliases. The main content served in the platform is in the form of ["apps"](https://github.com/ricsam/member-platform/tree/gh-pages/apps_){:target="_blank"} which can have associated settings pages and permissions. 
[https://ricsam.github.io/member-platform/apps/register-with-autofill](https://ricsam.github.io/member-platform/apps/register-with-autofill){:target="_blank"}


### automator
[https://github.com/ricsam/automator/blob/master/scripts/GUI/Action-module.js](https://github.com/ricsam/automator/blob/master/scripts/GUI/Action-module.js){:target="_blank"} Skrivet i React.js och Electon
```javascript


```


### Hot-Corn-Dog 2012
[https://github.com/ricsam/Hot-Corn-Dog](https://github.com/ricsam/Hot-Corn-Dog){:target="_blank"}
This is a small GNOME Shell extension where you can pick your own "hot corners" for toggling the overview, or for running custom applications. You can also change the "hot corner" for the message tray.
Writtin in Javascript