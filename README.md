## Projects

### 2016 - "local-server-deployer"
Anonymous (using TOR network) web crawler in phantomjs. The developed es6 code was automatically [deployed](https://github.com/ricsam/local-server-deployer/blob/master/deployer.js) via CRUD operations to servers on the local network. The local servers executes a [configure.js](https://github.com/ricsam/local-server-deployer/blob/master/local/configure.js) which handles the prerequisites to run the application. Thereafter the phantomjs instance is started with the [web crawler code](https://github.com/ricsam/local-server-deployer/blob/master/local/scripts/crawler.js)
Compiles and deploys code to local 

### 2015 - OriC-finder
#### [http://ricsam.github.io/OriC-finder#select/] http://ricsam.github.io/OriC-finder
Bioinformatic algorithms in CoffeeScript, served either as a express server where data is [downloaded](https://github.com/ricsam/OriC-finder/blob/v2.0/modules/genome-download.coffee) from `ftp.ncbi.nlm.nih.gov`, or as just a front-end only application where cached data is used (this isomorfic logic is handled like [this](https://github.com/ricsam/OriC-finder/blob/3088e3d168cb9454edbec257437cc32dcd844ad1/public/server_/GenBank.coffee#L84).

- [The implemented "dnaa algorithm"](https://github.com/ricsam/OriC-finder/tree/v2.0/public/pages_/dnaa), initialized from main.coffee
- [The implementation of the front-end application logic](https://github.com/ricsam/OriC-finder/tree/v2.0/public/server_)
