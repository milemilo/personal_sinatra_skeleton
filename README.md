## dbc Sinatra skeleton
*with some person tweaks!*

Drop this onto your computer and have an app running in less than 5 minutes. Personal embellishments to the [dbc](http://devbootcamp.com) skeleton listed below. I can't take credit for the core environment, database, rake, or gem set up. 

------

**TO DO**

- Error handling
- Refine AJAX to toggle login/signup form
- Cross-browser CSS (currently functioning in Chrome)

------

#### Modifications

- Password fun with [bcrypt](http://bcrypt-ruby.rubyforge.org/)
- [Open Sans](http://www.google.com/fonts/specimen/Open+Sans) as base font, [Bitter](http://www.google.com/fonts/specimen/Bitter) as paragraph font
- JavaScript with AJAX for logging in and signing up users
- Fixed top nav bar
- [Sticky footer](http://ryanfait.com/sticky-footer/)
- [Sass](http://sass-lang.com/) for CSS
- [Slim](http://slim-lang.com/) syntax for (most) viewsx
- A few erb files in views/erb

* Pre-wired controller to compile Sass to CSS 
 - Sass files should be ```*.scss``` and stored in the ```/public/css``` folder
 - If you add any new files, include them in the head of ```layout.slim``` 

* Pre-wired controller for ```users``` that includes:
 - login GET/POST
 - signup GET/POST
 - logout GET
 - user profile GET


------

#### Important stuff

1. ```bundle```
2. Create necessary migrations (```rake generate:migration NAME=CreateTableNames```) and models (```rake generate:model NAME=Name```)
3. ```rake db:create && rake db:migrate```
4. ```shotgun```
5. Have a blast

------

#### Requirements

- PostgreSQL
- You like AJAX

* **Users table***. The ```/login``` and ```/signup``` GET/POST routes and views make some assumptions about your app. Namely, that you have a ```Users``` table and are using Sinatra's built-in sessions feature. The model and migration are both provided for the ```Users``` table.
 - Users login with an email and password (as opposed to username and password)
 - ```Users``` includes fields for ```first_name```, ```last_name```, ```email```, and ```password_hash```
 - ```email``` and ```password_hash``` are required
 - ```email``` must be unique
 - ```password_hash``` is passed in through ```params``` with ```password``` processed by bcrypt