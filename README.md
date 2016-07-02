
## todos-bogotobogo_com-source

This can be a good test of your node.js install, and a good starting point for a more sophisticated MEAN stack project.

### Trying out this tutorial:

o http://www.bogotobogo.com/MEAN-Stack/MEAN-Stack-MongoDB-ExpressJS-AngularJS-NodeJS-ToDoList-App.php

And making notes of the blow-by-blow.

### Quickly Get It Running

Quick steps to get this working, so you don't have to go through the tutorial if you've already done it, e.g., on another host.

We are using ubuntu, both 14.04 and 16.04 (for now anyway).

1. Install node, npm, and express
  * For details on Ubuntu 14.04, see the tutorial
  * For details on Ubuntu 16.04, see "Installing express on Ubuntu 16.04" below
2. git clone git@github.com:tomwhartung/todos-bogotobogo_com-source.git
3. Run these commands
    ```
        mkdir todos-bogotobogo_com
        cd todos-bogotobogo_com
        express ToDo
        cp ../todos-bogotobogo_com-source/* ToDo
        cd ToDo
        npm install
        node server.js          // OR...
        DEBUG=ToDo:* npm start  // To run in debug mode
    ```
4. Install mongo-db
  * For details on Ubuntu 14.04, see:
    https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-14-04
  * For details on Ubuntu 16.04, see:
    https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-16-04
5. Load in browser:
   http://localhost:8888/

#### Installing express on Ubuntu 16.04

To install express on Ubuntu 16.04, run these commands as root:

```
// npm install express             // I do not think this is needed
npm install -g express-generator   // allows running from command line
cd /usr/bin
ln -s /usr/local/lib/node_modules/express-generator/bin/express .
which express
```

### Other ToDo Tutorials I am looking At

Have already tried this one:

o https://scotch.io/tutorials/creating-a-single-page-todo-app-with-node-and-angular

And it didn't work, probably because it wants to use database at https://modulus.io/ .

o I get this error: `MongoError: auth fails`

Also, there are some others; I will keep trying them until I figure out how to get it to work.

Using this README and repo to track what I am doing, where I am getting the code from, etc.


### Questions

1. Under the

> Recall we created our model earlier with:
> var Todo = mongoose.model
> Now, we can use Todo to GET, POST, and DELETE.

I cannot recall doing that, or see any evidence of it in the code!

Thinking they maybe got it from a different tutorial - I am seeing some parts of this that look like they were copied out of the scotch.io tutorial tried earlier.

But I am not seeing it there, either.  Carrying on with this one, for now.  There are other tutorials but we have to start somewhere, so....

*** I think this tutorial is referring to an earlier one.  See comments in server.js for more info.  ***

2. ............


### Purposes of This Exercise

I have a client that may be interested in something like this!

But also they mention this stack in the job description for the Galvanize Full Stack Instructor, and it's just about the only thing I am missing, so it shouldn't hurt to take a look-see.

### Results of scaffolding.

Note the warnings concerning:
o jade (renamed to pug),
o the version of node wanted, and
o transformers@2.1.0: Deprecated, use jstransformer
The tutorial states that we will not be using all of these files, so I am ignoring these warnings for now.

tomh@bette: /var/www/work/mark_mountjoy/github/customizations/todos-bogotobogo_com-scaffolded
 $ express ToDo

   create : ToDo
   create : ToDo/package.json
   create : ToDo/app.js
   create : ToDo/public
   create : ToDo/public/javascripts
   create : ToDo/public/images
   create : ToDo/public/stylesheets
   create : ToDo/public/stylesheets/style.css
   create : ToDo/routes
   create : ToDo/routes/index.js
   create : ToDo/views
   create : ToDo/views/layout.jade
   create : ToDo/views/index.jade

   dont forget to install dependencies:
   $ cd ToDo && npm install

tomh@bette: /var/www/work/mark_mountjoy/github/customizations/todos-bogotobogo_com-scaffolded
 $ l
total 4
drwxr-xr-x 5 tomh tomh 4096 Jul  1 11:48 ToDo
tomh@bette: /var/www/work/mark_mountjoy/github/customizations/todos-bogotobogo_com-scaffolded
 $ lf
ToDo/app.js
ToDo/package.json
ToDo/public/stylesheets/style.css
ToDo/routes/index.js
ToDo/views/index.jade
ToDo/views/layout.jade
tomh@bette: /var/www/work/mark_mountjoy/github/customizations/todos-bogotobogo_com-scaffolded
 $ cd ToDo && npm install
npm WARN deprecated jade@1.11.0: Jade has been renamed to pug, please install the latest version of pug instead of jade
npm WARN engine express@2.5.8: wanted: {"node":">= 0.4.1 < 0.7.0"} (current: {"node":"4.2.3","npm":"2.14.7"})
npm WARN deprecated transformers@2.1.0: Deprecated, use jstransformer
express@2.5.8 node_modules/express
├── mime@1.2.4
├── qs@0.4.2
├── mkdirp@0.3.0
└── connect@1.9.2 (formidable@1.0.17)

jade@1.11.0 node_modules/jade
├── character-parser@1.2.1
├── commander@2.6.0
├── void-elements@2.0.1
├── mkdirp@0.5.1 (minimist@0.0.8)
├── constantinople@3.0.2 (acorn@2.7.0)
├── jstransformer@0.0.2 (is-promise@2.1.0, promise@6.1.0)
├── with@4.0.3 (acorn@1.2.2, acorn-globals@1.0.9)
├── clean-css@3.4.18 (commander@2.8.1, source-map@0.4.4)
├── transformers@2.1.0 (promise@2.0.0, css@1.0.8, uglify-js@2.2.5)
└── uglify-js@2.6.4 (async@0.2.10, uglify-to-browserify@1.0.2, source-map@0.5.6, yargs@3.10.0)
tomh@bette: /var/www/work/mark_mountjoy/github/customizations/todos-bogotobogo_com-scaffolded/ToDo
 $ 

### Installing Mongo DB

The command in the tutorial did not work, so I am trying these:

o Preferred: http://www.liquidweb.com/kb/how-to-install-mongodb-on-ubuntu-14-04/
o Second opinion: https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-14-04

Commands run:

apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
   (both articles match)

echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | sudo tee /etc/apt/sources.list.d/mongodb.list
   (digital ocean command is slightly different)

apt-get install -y mongodb-org
   (both articles match)

















