## Projects

### 2015 - OriC-finder
#### [http://ricsam.github.io/OriC-finder#select/] http://ricsam.github.io/OriC-finder
Bioinformatic algorithms in CoffeeScript, served either as a express server where data is [downloaded](https://github.com/ricsam/OriC-finder/blob/v2.0/modules/genome-download.coffee) from ftp `ftp.ncbi.nlm.nih.gov` via express back-end, or as a front-end only application where cached data is used (this isomorfic logic is handled like [this](https://github.com/ricsam/OriC-finder/blob/3088e3d168cb9454edbec257437cc32dcd844ad1/public/server_/GenBank.coffee#L84).

- [The implemented "DnaA algorithm"](https://github.com/ricsam/OriC-finder/tree/v2.0/public/pages_/dnaa), initialized from main.coffee
- [The implementation of the front-end application logic](https://github.com/ricsam/OriC-finder/tree/v2.0/public/server_)
