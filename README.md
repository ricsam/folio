## StackOverflow
[https://stackoverflow.com/users/1105047/richie](https://stackoverflow.com/users/1105047/richie){:target="_blank"}

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

Bioinformatic algorithms in CoffeeScript, served either under an express server where data is [downloaded](https://github.com/ricsam/OriC-finder/blob/v2.0/modules/genome-download.coffee){:target="_blank"} from `ftp.ncbi.nlm.nih.gov`, or as a front-end only application where cached data is used (using the precursor to ["ph pages server"](https://ricsam.github.io/folio/#2015---gh-pages-server--member-platform) for single-page app logic.

- [The implemented "dnaa algorithm"](https://github.com/ricsam/OriC-finder/tree/v2.0/public/pages_/dnaa){:target="_blank"}, initialized from main.coffee
- [The implementation of the front-end application logic](https://github.com/ricsam/OriC-finder/tree/v2.0/public/server_){:target="_blank"}

### 2015 - "gh pages server" / member-platform

- [Demo](https://ricsam.github.io/member-platform/apps/register-with-autofill){:target="_blank"} (not configured to run on the github pages domain)
- [Source](https://github.com/ricsam/member-platform/tree/gh-pages){:target="_blank"}

A platform for registration of student-union cards which could be used for e.g. events. To build this service I created a ["gh pages server (github pages server)"](https://github.com/ricsam/member-platform/tree/gh-pages/amd_/js){:target="_blank"} which uses the 404.html page to route paths to content. The resources needed can be defined in a simple manner using [router.json](https://github.com/ricsam/member-platform/blob/gh-pages/router.json){:target="_blank"}. The gh pages server, which is simply a front-end only service, is designed to have the same functionality as a normal server when it comes to routing, with URL wildcards and aliases. The main content served in the platform is in the form of ["apps"](https://github.com/ricsam/member-platform/tree/gh-pages/apps_){:target="_blank"} which can have associated settings pages and permissions. 

### 2012 - Hot-Corn-Dog
[https://github.com/ricsam/Hot-Corn-Dog](https://github.com/ricsam/Hot-Corn-Dog){:target="_blank"}

This is a small GNOME Shell extension where you can pick your own "hot corners" for toggling the overview, or for running custom applications. You can also change the "hot corner" for the message tray.
Writtin in Javascript

## A MongoDB unit test I've used in a project

```javascript

(() => {

const MongoClient = require('mongodb').MongoClient;
const url = 'mongodb://localhost:27017/ExchangeData';


/* OVERALL TEST DESIGN 
  (1) Nodes are set onto UAIT
  (2) They are saved to DB using DB handler.
  (3) See if result is expected.
*/


console.clear();
console.log('DBHandler.js @saveNode(node) -> undefined');

MongoClient.connect(url, function(err, db) {

  delete require.cache[require.resolve('util/DBHandler.js')];
  const assert = require('assert');
  const DBHandler = require('util/DBHandler.js');
  const {createNodes} = require('util/test_data.js');
  const _ = require('lodash');

  const dbh = new DBHandler(db, 'test');
  dbh.collection.deleteMany({}).then(setUpDB).catch(e => {
    if (e.name === 'AssertionError') {
      console.warn('%cTest ' + e.message + ': ✘', 'font-size: 12px');
      console.log('%cExpected:', 'font-size: 15px; color: green;');
      console.log(JSON.stringify(e.expected, true, 2));
      console.log('%cActual:', 'font-size: 15px; color: red;');
      console.log(JSON.stringify(e.actual, true, 2));
    } else {
      console.warn('%cTest: ✘', 'font-size: 20px');
      console.log(e);
    }
  });


  async function setUpDB() {
    let docs;

    let nodes, nodes1, nodes2, nodes3, nodes4, nodes5;

    nodes = createNodes(10, 20, 2, 2);
    nodes2 = createNodes(10, 20, 3, 2);
    await dbh.saveNode(nodes[0]);
    docs = await dbh.collection.find({}).toArray();
    assert.equal(docs[0].cc.hasOwnProperty('2'), true);
    assert.equal(docs[0].cc['2'].length, 3);
    assert.deepEqual(docs[0].interval, [10, 15]);
    
    await dbh.saveNode(nodes2[0]);
    docs = await dbh.collection.find({}).toArray();
    assert.equal(docs[0].cc.hasOwnProperty('2'), docs[0].cc.hasOwnProperty('3'), true);
    assert.equal(docs[0].cc['3'].length, 1);
    assert.equal(docs[0].cc['3'][0].date, 12);

    await dbh.saveNode({
      state: 'ready',
      cc: {},
      trades: [],
      interval: [1, 3]
    });
    docs = await dbh.collection.find({}).toArray();
    assert.equal(docs.length, 1);
    await dbh.collection.deleteMany({});

    nodes = createNodes(10, 20, 2, 2); /* candle size: 2, number of nodes: 2*/
    nodes2 = createNodes(10, 20, 2, 2);
    nodes[0].cc['2'].splice(1, 1);
    await dbh.saveNode(nodes[0]);
    docs = await dbh.collection.find({}).toArray();
    /* missing middle candle */
    assert.equal(docs[0].cc['2'][0].date, 10);
    assert.equal(docs[0].cc['2'][1].date, 14);

    await dbh.saveNode(nodes2[0]);
    docs = await dbh.collection.find({}).toArray();
    assert.equal(docs[0].cc['2'][1].date, 12);

    /* test sorting */
    await dbh.collection.deleteMany({});
    nodes = createNodes(10, 20, 2, 2); /* candle size: 2, number of nodes: 2*/
    nodes2 = createNodes(30, 40, 2, 2);
    await dbh.saveNode(nodes2[0]);
    await dbh.saveNode(nodes[0]);
    docs = await dbh.getNodes(10, 40, 2);
    // console.log(JSON.stringify(docs.map(o => _.omit(o, 'trades', 'cc')), true, 2));
    assert.deepEqual(docs[0].interval, [10, 15]); 
    assert.deepEqual(docs[1].interval, [30, 35]);

    /* test overlapping */
    await dbh.collection.deleteMany({});
    nodes = createNodes(10, 20, 3, 1); /* candle size: 3, number of nodes: 1*/
    assert.equal(nodes[0].cc['3'][0].date, 9);
    nodes2 = createNodes(10, 40, 3, 1);
    await dbh.saveNode(nodes[0]);
    await dbh.saveNode(nodes2[0]);
    docs = await dbh.getNodes(10, 40, 3);
    assert.deepEqual(docs[0].interval, [10, 20]); 
    assert.equal(docs[0].cc['3'][0].date, 9);
    assert.deepEqual(docs[1].interval, [20, 40]);
    assert.equal(docs[1].cc['3'][0].date, 18);

    await dbh.collection.deleteMany({});
    nodes = createNodes(10, 40, 3, 1);
    nodes2 = createNodes(35, 50, 3, 1);

    await dbh.saveNode(nodes[0]);
    await dbh.saveNode(nodes2[0]);
    docs = await dbh.getNodes(10, 50, 3);
    assert.deepEqual(docs[0].interval, [10, 40]); 
    assert.equal(docs.length, 2);
    // docs = await dbh.collection.find({}).toArray();

    /* this was a hard bug to find! - test small node inserted onto large DB node */
    await dbh.collection.deleteMany({});
    nodes = createNodes(3, 27, 1, 1); /* DB large */
    nodes2 = createNodes(21, 24, 1, 1); /* node small */
    await dbh.saveNode(nodes[0]);
    await dbh.saveNode(nodes2[0]);

    docs = await dbh.getNodes(3, 27, 1);
    assert.equal(docs.length, 1);


    await dbh.collection.deleteMany({});
    nodes = createNodes(21, 24, 1, 1); /* DB small */
    nodes2 = createNodes(3, 27, 1, 1); /* node large */
    await dbh.saveNode(nodes[0]);
    await dbh.saveNode(nodes2[0]);

    docs = await dbh.getNodes(3, 27, 1);
    assert.equal(docs.length, 3);


    await dbh.collection.deleteMany({});

    nodes5 = createNodes(8, 15, 1, 1);await dbh.saveNode(nodes5[0]);
    nodes2 = createNodes(2, 4, 1, 1);await dbh.saveNode(nodes2[0]);
    nodes3 = createNodes(4, 6, 1, 1);await dbh.saveNode(nodes3[0]);
    nodes4 = createNodes(6, 8, 1, 1);await dbh.saveNode(nodes4[0]);
    nodes1 = createNodes(2, 8, 1, 1);await dbh.saveNode(nodes1[0], true);

    docs = await dbh.getNodes(2, 15, 1);
    docs = docs.map(o => _.omit(o, 'trades', 'cc'));
    
    assert.deepEqual(docs, [
      {"state": "ready", "interval": [2, 4 ] },
      {"state": "ready", "interval": [4, 6 ] },
      {"state": "ready", "interval": [6, 8 ] },
      {"state": "ready", "interval": [8, 15 ] }
    ]);

    console.log('%cTEST: ✔', 'font-size: 15px; color: green;')
    db.close();
  }

});

```