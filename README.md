# Notice!

*I have since updated my deployment process. It is now named 'launch', has its [own repository](http://github.com/bengourley/launch), and is available on npm. I highly recommend that you use that.*

This repository only exists because there is a [blog post](http://blog.clock.co.uk/2011/04/11/deploying-node-js-apps/) that points to it, and it looks like some of you were hitting a 404 at this repo and getting confused (understandably). Please be aware that I won't be developing on this repository, but you can still get in touch if you want to talk about it.

# Node Deployment

Screenshot:

![Screen shot of deployment](http://f.cl.ly/items/3k3z1V3M2s272t2Q392O/Screen%20Shot%202011-08-03%20at%2023.19.13.png "Screenshot")

Disclaimer: These files and their descriptions are very specific to my project setup. They will not work on your current setup!

## Jakefile.js

This file lives in the project root. It is called by the post-receive hook and does most of the work.

## package.json

This is a file standardised by npm. This means on any development environment, you can cd the project root and run:
	
	npm install

This will install of the dependencies declared in the package.json file. The jakefile also automates this same task on the deployment environment.


## post-receive

This is the git post-receive hook. Place it in the hooks directory in the git reposity of the project.


## props.json

This is a sample json document outlining the build properties. It also lives in the site root /config


## site.Sitename-state

This is the upstart daemon config. Place it in /etc/event.d/. State should be live/dev.


## monitrc

This is the monit config. Place it in /usr/local/etc/monitrc. The all of the sites to be monitored can be placed in this monolithic file.
