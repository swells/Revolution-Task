# Author

Sean M. Wells <sean.wells.sc@gmail.com>

# Environment

OSX

# Supported Browsers

Latest stable: Chrome, FireFox, Safari 

Note: It will probably work in IE 10/11 as well however I did not verify this.

# Libraries Used

- [AngularJS](https://angularjs.org)
  1. AngularJS Core 
  2. Internationalisation i18n [pascalprecht.translate](http://angular-translate.github.io/)
  3. Low level Angular Directive [ui.ace](http://angular-ui.github.io/ui-ace/) 
     for the [Ace Editor](http://ace.c9.io/). This is the editor used for 
     authoring blog posts.
  4. Markdown parser [marked](https://github.com/chjj/marked) used for 
     converting blog posts written in markdown to HTML.     

AngularJS was used because it is quick to develop in. Given my current workload 
I could only budget at most *three* days to work on the test spread out over the
week. 

Getting a basic REST based CRUD application up and going in AngularJS is easy
using their [$resource](https://docs.angularjs.org/api/ngResource/service/$resource)
service. This is a "factory which creates a resource object that lets you 
interact with RESTful server-side data sources." This was an natural fit for the
test.

-  [Twitter Bootstrap](http://getbootstrap.com/) for CSS *only*
        
Bootstrap was used as the boilerplate responsive foundation. I then styled the
site to not make it look like Bootstrap. This was done using LESS and can be
viewed in `/webapp/styles/less`. 
    
# List of Source Code

```
/webapps
   /bower_components
      - Home to all the libraries used. 
   /images
       - None
   /scripts
      /controllers
         - create.js (Controller to Create a new blog post)
         - delete.js (Controller to Delete a specific blog post)
         - edit.js (Controller to Edit a specific blog post)
         - list.js (Controller to View a list of all existing blog posts)
         - main.js (Parent Controller)
         - post.js (Controller to View a specific blog post)
      / directives
         - blog-editor.js (Custom Angular directive for the editor widget)
         - marked.js (Custom Angular directive for markdown widget)
         - resizeable.js (Custom Angular directive for resizing elements)
      /services
         - Post.js (Resource object that lets you interact with the RESTful 
                    server-side data sources.)
      /vendor
         - Home to any JavaScript assets that could not be pulled in via Bower.                    
   /styles
      /less
         - blog.less
         - buttons.less
         - content.less
         - elements.less
         - includes.less
         - layout.less
         - theme-salesforce.less
         - variables.less
      - main.css (The compiled result of the above .less files)
   /views
      /directives
         - blog-editor.html (Partial for the `blog-editor`)
      - create.html (Partial for the Controller to Create a new blog post)
      - delete.html (Partial for the Controller to Delete a specific blog post)
      - edit.html (Partial for the Controller to Edit a specific blog post)
      - list.html (Partial for the Controller to View a list of all existing blog posts)         
      - post.html (Partial for the Controller to View a specific blog post)
      
   - index.html (The base view for the single page application)
   - robots.txt (The Robot Exclusion Standard)

```
 
# Notes to augment your code comments

I scaffolded the application using [Yeoman](http://yeoman.io/) to manage bower
packages and to setup a base Gruntfile.js to manage the UI building. I felt this
was necessary to easily lint the JavaScript and test to see if everything minimized
properly as if this was a production deployment.

I developed the test outside of Java using a simple [Express.js](http://expressjs.com/) 
server that mimicked the actual supplied Java server code. This allowed for 
faster development, live page loading on file changes, ect... I then moved the 
un-minimized and unoptimised files over to Java/Jetty to verify for submition.


# Not completed in time

Internationalization i18n bundle in some other language other than en.


