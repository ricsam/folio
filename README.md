## Projects

### 2017 - "killergame"
A game developed in Firebase. Using the firebase API to [serve notifications](https://github.com/ricsam/killergame/blob/master/functions/firebase-messaging-sw.js) and handle login and data. The server side code in firebase is hard to test and slow to deploy, however the backend API is more or less the same as the frontend. Thus is developed the interface for the application in a isomorfic manner so I could test back end logic in the webbrowser (https://github.com/ricsam/killergame/blob/master/functions/app/metamorph-functions.js#L6). The complete application logic is confined in [main.js](https://github.com/ricsam/killergame/blob/master/functions/app/main.js) and [ui-binds.js](https://github.com/ricsam/killergame/blob/master/functions/app/ui-binds.js)

### 2016 - "local-server-deployer"
Anonymous (using TOR network) web crawler in phantomjs. The developed es6 code was automatically [deployed](https://github.com/ricsam/local-server-deployer/blob/master/deployer.js) via CRUD operations to servers on the local network. The local servers executes a [configure.js](https://github.com/ricsam/local-server-deployer/blob/master/local/configure.js) which handles the prerequisites to run the application. Thereafter the phantomjs instance is started with the [web crawler code](https://github.com/ricsam/local-server-deployer/blob/master/local/scripts/crawler.js).

### 2015 - OriC-finder
[http://ricsam.github.io/OriC-finder#select/] http://ricsam.github.io/OriC-finder
Bioinformatic algorithms in CoffeeScript, served either as a express server where data is [downloaded](https://github.com/ricsam/OriC-finder/blob/v2.0/modules/genome-download.coffee) from `ftp.ncbi.nlm.nih.gov`, or as just a front-end only application where cached data is used (this isomorfic logic is handled like [this](https://github.com/ricsam/OriC-finder/blob/3088e3d168cb9454edbec257437cc32dcd844ad1/public/server_/GenBank.coffee#L84).

- [The implemented "dnaa algorithm"](https://github.com/ricsam/OriC-finder/tree/v2.0/public/pages_/dnaa), initialized from main.coffee
- [The implementation of the front-end application logic](https://github.com/ricsam/OriC-finder/tree/v2.0/public/server_)

