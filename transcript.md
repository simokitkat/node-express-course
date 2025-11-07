1:45:59
NPM Info
all right at this point we're familiar with two types of modules our own as well as the nodes built-in ones
1:46:06
but just like in any good infomercial i'll say but wait there's more
1:46:14
we also have access to the world's biggest code store and before you seriously start
1:46:20
questioning my mental state imagine this scenario you're building an app
1:46:26
and of course as any good app it needs to have a slider just for funsies
1:46:32
now at this point you generally have two options build it from the scratch yourself
1:46:38
or search on google and copy paste someone else's solution
1:46:44
well have no issues with either of these options keep in mind that someone
1:46:49
somewhere has struggled with the same issue the need for the slider
1:46:56
and there's a good chance that that person was kind enough to build it
1:47:01
and share the whole project with us so our only job
1:47:07
is to go through the docs and with the help of one command just add it to our project
1:47:14
we can do that because when we install node we automatically also install npm
1:47:21
or node package manager and npm enables us to do three things
1:47:28
reuse our own code in other projects use code written by other developers
1:47:35
and lastly share our own solutions with other developers as well
1:47:40
the npm project is hosted at npmjs.com again the site is
1:47:48
npm.js and here you can find everything starting with useful utility functions
1:47:56
to full-blown frameworks and libraries and as an example if you're familiar with react you know that react has the
1:48:04
create react app package and of course it is hosted on the npm
1:48:11
a typical node project will have more than few npm packages
1:48:16
installed as dependencies and before we install some cool packages
1:48:22
let's talk about naming npm calls the reusable code a package
1:48:28
and a package essentially is a folder that contains a javascript code now another names you'll hear
1:48:35
are modules and dependencies and honestly at this point
1:48:40
all three are used interchangeably when talking about shareable javascript code
1:48:46
so don't be surprised if during the course i call them any of these names package dependency or module at the end
1:48:53
of the day they all mean the same thing lastly let me just mention two things first
1:48:58
there is no quality control in npm registry anyone can publish anything
1:49:05
so it's up to you to sniff out the empty and useless packages and yes there are
1:49:10
quite a few of those ones out there as well a good indication of the security
1:49:16
and usefulness of package is the amount of weekly download if the number is high
1:49:23
meaning if it's popular it's a good chance that it's a battle tested and ready to go
1:49:28
and that brings me to my second point remember the slider example we discussed in the beginning of the video
1:49:35
when it comes to npm packages there's a good chance that if there is a bug
1:49:41
someone else has already fixed it and as a result it's already fixed in
1:49:46
the package or there's a working solution all right so that you did for intro let's start
1:49:54
using node package manager in our own project and as a side note if
1:49:59
you want to search for some packages just visit npmjs.com
1:50:06
and then for example if you're looking for the bootstrap you'll find the package
1:50:11
and of course you can click on any of them this will bring you to the docs as well
1:50:17
as weekly downloads and rest of the stuff once we're familiar with node package manager let's see how we can
NPM Command
1:50:24
start using it in our own project and the good news is that it's much simpler than you would expect you see
1:50:31
when we install node we also install npm and because of that we have access to
1:50:37
npm global command and you can check the npm version by running npm
1:50:43
version in your terminal just keep in mind that the version most likely won't be the same as your node version and
1:50:51
that is totally okay so you can either do that in the terminal
1:50:56
or of course in the integrated terminal and you can simply type npm and then
1:51:01
hyphen hyphen version i believe you can also check by hyphen hyphen v and there it is of course now we have the version
1:51:10
for our node package manager and then we have two flavors we can install package
1:51:16
as a local dependency and that just means that we'll only use that package
1:51:22
in this particular project that we're working on and the command for that one would be npm
1:51:29
install or i for short and then whatever is the package name so whether that is
1:51:34
bootstrap low dash express or whatever or we can install dependency as a global
1:51:41
dependency and that just means that we can use it in any project and the command for that one would be again npm
1:51:48
i or install whichever method you prefer and then hyphen g so this is going to be
1:51:55
the flag and then again the package name now when you install something globally most likely on a mac they will ask you
1:52:03
for the sudo so you'll have to provide the credentials that's why you'll run sudo
1:52:09
npm install and then hyphen g and again package name
1:52:14
as far as which one you'll use more often that definitely will be a local dependency flavor
1:52:20
because even though yes you can install packages globally with arrival of npx
1:52:27
there's actually less and less need for setting up something globally that's why
1:52:34
we'll focus on local dependencies first how to set it up in our project and then
1:52:39
in a few videos when we talk about npx i'll cover why there's less need for
1:52:46
setting up something globally now there's one more thing that we would need to set up in our project as far as
1:52:52
dependencies so i know i know you're eager to start installing the packages
1:52:58
but let's just wait a little bit and next video we'll add that extra thing that
1:53:04
we're missing right now and then we'll be in good shape and then we'll start installing every package under the sun
First Package
1:53:11
excellent we now know that we have access to the npm global command we now
1:53:16
know that in order to install the local package we will need to run npm i
1:53:22
and the package name so what are we missing well we're missing file by the
1:53:27
name of package.json and essentially you can think of it as a manifest file that stores important
1:53:35
information about our project and there are three ways how you can create package.json first is the manual
1:53:43
approach where you just create a package.json in the root and please do
1:53:48
that in the root if that's something that eventually you decide doing
1:53:53
and then of course you would need to create each property or there are two
1:53:59
ways how we can automate this and the first one is running npm init
1:54:04
and in there they'll just step by step ask you the questions and if you want to skip it you can just press enter
1:54:11
and the another way the third way is running npm init with a y flag and then
1:54:18
everything is set up as default so i'm not going to show you the manual approach it's just too time consuming
1:54:25
and we'll right away go with npm in it first i'll show you the step by step approach and then of course i'll show
1:54:32
you how everything is set up by default using the y flag so go to your terminal
1:54:37
and just type npm in it and there it is of course now they tell you that there's
1:54:43
going to be a walkthrough of creating a package.json file and the first one is
1:54:49
the package name and by default of course it is going to use the folder name now keep in mind that if you
1:54:55
eventually want to publish this package then the name has to be unique so you
1:55:01
need to make sure that nowhere in the npm you can see the package with the same
1:55:08
name and i'm just gonna go with tutorial as far as version we'll talk about versions shortly so i'll just skip this
1:55:15
one as far as description whatever again is just the default now as far as the entry point eventually will change it
1:55:22
but for now it's good enough we're going to go with one intro js and then the
1:55:27
test command as well as git repository and keywords and author and license and
1:55:32
we simply say yes and we are in good shape so now of course we have the package json file with name version
1:55:40
description as well as the main property and of course the scripts author and the
1:55:45
license now i'll remove it i'll say delete and i'll show you that of course you can skip all those
1:55:52
questions by simply typing npm in it and why and as you can guess
1:55:59
yes of course you can come here later and then just change these values that's
1:56:04
why it's definitely faster to just type npm in it and then the y flag
1:56:11
so why do we need this package.json well because if i would want to install the
1:56:17
package the local package now of course this package is going to be stored as a dependency and to show
1:56:25
you that let's just go with npm and you know what let me clear the console first so we're
1:56:30
going to go with npm i and then we're going to go with the package name lowdash and if you're not
1:56:37
familiar with lodash it's just a utility library and i'm just specifically using
1:56:43
for installation purposes there's no real reason to have low dash for our own
1:56:49
project but it's just something pretty interesting that i would want to showcase that's why we're using lodash
1:56:55
and we run it and notice how we installed the package and check it out now in the package.json we have
1:57:02
dependencies property and it's an object and inside of that object we have a
1:57:08
package by the name of lowdash now i'll show you
1:57:13
in this video or maybe in the next one why it's so important to have this package.json
1:57:19
but another thing that i would want to showcase once we can see that we have dependencies property if you go in your
1:57:27
visual studio code and if you click on refresh explorer what you'll also notice
1:57:34
is this node modules folder and in that node modules folder this is where all
1:57:40
the dependencies are stored so if you don't have that folder already
1:57:46
and pm creates it so in our case of course we didn't have any dependencies so when we install that first dependency
1:57:53
npm creates that folder and this is where you'll find the dependencies now
1:57:59
notice something interesting where for the low dash we only have one folder right so we have
1:58:05
only one dependency but when we need to keep in mind that of course there's going to be some packages
1:58:12
that have other dependencies and that's why i first installed lodash
1:58:17
just to showcase that yes once you install dependency of course it is going to be in node modules but if you'll try
1:58:24
to install a package that is bigger that uses other dependencies you'll notice
1:58:30
something pretty cool where if i clear my terminal and if i'm gonna run npm i
1:58:36
and then bootstrap again you can use any other package you'd want this is just to
1:58:41
showcase how the packages work we won't use the bootstrap in this project so
1:58:47
once i install and once i refresh check it out not only i have low dash
1:58:54
not only i have bootstrap which i installed but since bootstrap is using jquery as well as the proper js now
1:59:01
these are installed as dependencies and if you take a look at the dependencies property now of course we have the
1:59:08
bootstrap as well and again the whole point of this video is to
1:59:13
showcase why we need package.json so we need it because we need to provide information about our project and inside
1:59:22
there a very important property is the dependencies one because in there we'll
1:59:28
just store the dependencies which our project is using and then some packages
1:59:34
are actually going to use more dependencies and they will be automatically installed as well in our
1:59:41
case that was bootstrap and just to give you a taste of the package
1:59:48
why don't we just navigate to app and i'm going to do that below the comments of course you probably would
1:59:55
need to clean the file and as a side note the last module the http i saved in
2:00:00
file by the name of 12 http and back in the app.js in order to start
2:00:06
using the module in our case i guess i'm gonna go with low dash
2:00:12
first i would need to set up the variable and common convention is calling the variable like so and we'll
2:00:19
set it equal to require and now of course we have access to the low dash
2:00:25
now this is the difference between node packages like for example the http
2:00:31
or the file module or whatever and the ones that you install the external ones
2:00:38
the external ones you always have to install first if you won't install the dependency well
2:00:44
node won't be able to find it so in our case we did install the dependency the lowdash so now of course i can just
2:00:51
assign it to the variable and since lowdash is utility library why don't we
2:00:56
test out one of their methods and i'm just going to go with items and i'll create an array of arrays so items is
2:01:04
going to be an array however the items are going to be arrays itself
2:01:09
so two and three and then we're gonna go with four
2:01:14
and low dash has this method the flat and deep method that effectively will
2:01:20
just spit this back as a flat array and the way we set it up we just go with
2:01:27
const and i'll call this new items and then since we have access
2:01:32
to everything in this variable now i can simply go with underscore here dot and then flat
2:01:42
and deep so flatten deep and then we'll pass in the items and now if we console
2:01:47
log new items and if i go to my terminal and just type node app.js and by the way i
2:01:55
need to save it so let me go back i'll say node app.js and once we run check it out in a
2:02:02
console i can see of course the one two three four so lowdash has the method by
2:02:08
the name of flattendeep we have access to it because we install it as dependency and now of course i can start
2:02:15
using it now we're not gonna use bootstrap in this project because that
2:02:20
would be too time-consuming bootstrap was just used so you can see that some
2:02:26
dependencies will have more packages so once we install one dependency there's actually going to be
2:02:32
more dependencies and hopefully you have a clear understanding of how you would set up package.json how we would install
2:02:39
the package and next video i would want to showcase why having package.json is so crucial and so beneficial
2:02:48
when we are starting to share our project with other developers
Share Code
2:02:54
awesome we have package.json we installed few dependencies and now i want to cover
2:03:01
why having package.json is so crucial when we start sharing our project with
2:03:07
other developers and for this example i'm going to use github as well as few
2:03:13
basic git commands and my assumption is that since this is somewhat of a advanced course you're already familiar
2:03:20
with git and github and you have the account if you don't please stop the video create the account
2:03:26
and just use your favorite search engine to learn about the basics of setting up
2:03:32
the github repository as well as basic git commands so
2:03:37
our task is to push this up to the up and now million dollar question are we
2:03:44
just pushing everything up including the mode modules which
2:03:49
for the most projects is going to be somewhat big i believe i just checked in our case it
2:03:55
was like nine megabytes but trust me it always gets way bigger than that
2:04:01
or we would just want to send the code and you can probably already guess that
2:04:06
since i'm implying that the size is too big that we'll have to push this up to
2:04:12
the github without the node modules and we'll start by creating a dummy repo on
2:04:19
a github so let me open up a new window i'm going to go with github
2:04:24
and i'll just create a temp repo and then i'm just going to create a repo
2:04:29
and i'm looking for these three commands essentially i would want to get that url
2:04:36
the remote url so i know where to push it and then inside of the repo before we
2:04:42
set it up as github repo first i would want to go with new file and we'll
2:04:48
create a git ignored because of course what i would want is to place the node modules
2:04:54
in a git ignore file because that way they will be ignored by my source control and i won't be pushing up this
2:05:02
giant folder to the github because you'll see in a second that there is no
2:05:07
need for it so we're going to go with forward slash and then node modules and if you're not familiar with git ignored
2:05:13
it's just a file that specifies which files are going to be ignored by the source control and in
2:05:20
our case as you can see i'm placing node modules inside there then i'll clear my
2:05:25
console and i'll just initialize this as an empty git repo and then we'll add
2:05:32
everything so git add git commit we'll just say first commit
2:05:39
first commit and then i'll copy and paste those three commands in order to set up that url
2:05:46
the remote url and once i have this in place should be able to go back to my github
2:05:53
and there it is this is my repo now probably your next question is okay
2:05:59
so we pushed it up to the github but i can clearly see that in my app.js
2:06:05
well technically i'm using the load as dependency right but we didn't push up the node modules
2:06:12
folder so how the person who is going to get this repo will be able to run the
2:06:18
code in the app.js since there's no node modules and you told us previously that we can only run
2:06:25
it if the dependency is there well let's check it out i'm going to go with clone option so i'll just get the
2:06:32
url i'll navigate back here and i'll do that in messed up again it
2:06:38
doesn't really matter we're just going to go with desktop and then git clone
2:06:43
now i copy and paste the url i'll open up a new instance of my text error copy and
2:06:52
paste and this is where the magic happens if we have package json we simply need
2:06:59
to run npm install and what is going to happen
2:07:04
the npm will check for dependencies that we have in the package.json and automatically set up
2:07:13
that node modules folder so if i go here first of all i can see that there has
2:07:19
been some changes that is already good news that just means that i have my node modules and if i refresh
2:07:26
check it out so now of course i have my node modules folder and if you have been
2:07:33
using react applications you're probably already familiar with this one where again
2:07:38
when you are setting up the code you're not sharing the node modules folder and i can showcase that by taking
2:07:46
a look at my react projects and that's not what i wanted i didn't want to look at my awesome picture what i wanted is
2:07:53
react and then let's go with project and you'll see that in that repo
2:08:00
we have bunch and bunch of folders and each folder has two more folders final
2:08:06
and setup and now check it out none of them have the node models because imagine the size
2:08:12
of this sucker if i would push for every project for every folder the
2:08:18
node modules instead i have package json so when you get the repo when you clone
2:08:25
the repo or download or whatever then of course you get the package json
2:08:30
and in here these are the dependencies and you just run npm install and they are being
2:08:37
installed okay hopefully it is clear that why it is so crucial to have the package.json because we can just share
2:08:43
the code without dragging the massive node modules folder with us
2:08:49
we can simply just provide what packages our project is using
2:08:54
and then once we get the repo then we just run npm install that is the command
2:09:01
and then npm will install all the packages that are in the dependencies
Nodemon
2:09:06
awesome we're familiar with npm we're familiar with package.json
2:09:12
now let's finally install the dependency that we'll use for the remainder of the
2:09:17
course and that is no other than the node one and of course if you want to
2:09:23
get more info you can visit the npm and you can search for the package but as
2:09:28
far as the general setup is just to watch our files and then restart our app for us so that
2:09:36
way we don't have to each and every time type node and then whatever the file
2:09:42
name and we can install it as a simple dependency that is definitely an option
2:09:48
but since i also would want to cover depth dependencies we'll install that as a depth dependency and the command for
2:09:56
dev dependencies is following where we go with npm and then i or install
2:10:02
whatever and then we go with nodemon so that is the package name and then you
2:10:07
can either do hyphen d so that just signals that that is a that
2:10:12
dependency or you'll see this save and dev so again whichever method you choose
2:10:20
that is really up to you but just remember that both of them will save it as a dev dependency so let's install it
2:10:27
and then i'll talk about it why we would want to set up as a div dependency and the reason for that is because if we
2:10:34
think about it do we really need nodemon in production and the answer is no when we push it up
2:10:40
to digitalocean or heroku or whatever we'll of course use something more serious than nodemon to restart our
2:10:48
application pm2 comes to mind but while we're developing yeah that is an option
2:10:54
so in this case we'll add right away nodemon to the dev dependencies now what
2:11:00
else what kind of packages we would add to dev dependencies for example testing packages for example
2:11:07
linting for example formatting and that sort of thing again nothing stops you from jamming this in dependencies
2:11:14
but if you think about it it makes way more sense if we add this as dev dependency
2:11:20
so we use it while we are creating the app but then once it's in production
2:11:26
then we just share the dependencies that actually the app is using
2:11:31
not the ones that we used while we developed the app hopefully that is clear and once we have the package we're
2:11:38
almost there now we just need to understand how the scripts work in a package.json and at the moment
2:11:45
as you can see we have the test one we won't use that one and inside of the script object we just set up the
2:11:52
commands and as a side note we can set up the command right now even without the node mod for example i could
2:11:59
go with start and that command will be equal to npm
2:12:05
and or i'm sorry node and then for example app.js so that is my command and
2:12:11
once i save my package.json instead of running this node app.js i can simply
2:12:17
run npm and start and there it is as you can see same functionality i run app.js and i
2:12:26
get back the array as well as the hello world again we still exit the application so it's not like we're out
2:12:32
of the woods but i'm just showcasing that yes we can set up the commands and then in the command we just provide a
2:12:39
value and in this case of course it is node and app.js
2:12:44
now for some commands you can simply type npm start as you can see but for
2:12:49
some of them you'll have to provide the full value and that is going to be npm
2:12:55
run and nor to showcase that i'm going to go with dev and that one will be equal and here we're gonna go with a
2:13:02
node mod and then app.js so instead of running node
2:13:08
like we're doing in the start now i'm setting up a dev command and in order to
2:13:13
run this one i'll have to go with run and then whatever here's the command name again some of them you'll be able
2:13:19
to use the shortcut where you go with start and some of them you'll have to go the full route with npm run and then
2:13:26
whatever is the command and as a side note yes you can still run npm run start
2:13:31
and this is also going to invoke the command but in our case we have dev and in here i
2:13:38
have nodemon and then app js so let's try it out let's say first the
2:13:45
package json and you should notice something pretty cool where if i go with npm
2:13:51
run and dev now i'm spinning up the node one and it tells me that nodemon is watching
2:13:59
my application and since i know that of course we can test it out where i'm gonna go with
2:14:06
console.log and then instead of the hello world which i have after new items i'm gonna
2:14:12
go with hello people and you should see something interesting where once i
2:14:17
change the text yep nodemon restarts my app and now of course my value is
2:14:23
hello people awesome so now i don't have to type every time the node and then
2:14:30
whatever file name nodemon automatically just restarts my app and i simply set it
2:14:37
up as a script now if you want to change this around if you don't want to run npm
2:14:43
around dev you can simply say nodemon and then app.js and just remove the dev1
2:14:49
completely and a side note again if you have worked with react project you are
2:14:55
familiar with the setup because for react again we run npm start and then there's a value that spins up the whole
2:15:03
react dev server where we can see our application not bad not bad well we're
Uninstall
2:15:08
still on a roll let's cover how we can uninstall the package as well and as a
2:15:13
side note if you want to stop the nodemon just press again ctrl and c
2:15:19
and notice how we're of course stopping the nodemon and again if we want to spin
2:15:25
up we'll just go with npm start and as far as
2:15:30
uninstalling the package we have the command for that and the name is uninstall so i'll stop the nodemon and
2:15:38
in the terminal i'll type npm uninstall and then of course the package
2:15:43
name which in my case is going to be a bootstrap now this is one of the
2:15:49
approaches how we can do that and there's also a nuclear approach now why i'm calling this a nuclear approach
2:15:55
because that way we remove the whole node modules folder and don't worry
2:16:00
once you run the npm install then of course you set everything back up from the scratch as well as you would remove
2:16:06
this package like json and don't worry i will cover the package.json file a bit
2:16:13
later and the way that is going to look like well we can first clear the terminal
2:16:18
i'll install the bootstrap from the scratch again so say bootstrap here and
2:16:23
by the way probably need to add npm i and now again as you can see i have it
2:16:29
as my dependency and then like i said the nuclear approach is removing the
2:16:34
node modules yep and then removing the package log
2:16:40
and then just running npm install now of course in the package.json if i want to
2:16:46
remove the bootstrap for example in this case i can simply remove it from my dependencies so i just remove it in the
2:16:53
package.json then clear everything and then we go with npm and then install
2:16:59
and now we'll get from the scratch the node modules since we're the ones who removed it
2:17:06
and also we'll get that package hyphen lock json now i'm showing you that
2:17:12
nuclear approach because if you have used gatsby you know that cats be somewhat notorious for sometimes just
2:17:19
being a little bit annoying where you do need to remove the cache folder you do need to remove the node modules as well
2:17:27
as package lock and then once you start up everything from scratch then
2:17:32
as a magic the gatsby app starts working and check it out if we take a look at
2:17:37
the node modules now yes there's a bunch of modules that nodemon is using right
2:17:43
but there's no bootstrap and i can clearly see that because there's nothing under the letter of b so we can clearly
2:17:50
see that we removed bootstrap from our dependencies all right and now let's take a look at
Global Install
2:17:56
how we can install package globally and what would be some of the use cases and
2:18:03
first let's start with command let's jog our memory command was npm install and
2:18:08
then dash g and the package name and in mac they might ask you for permissions so you'll
2:18:15
have to start with sudo and then again same spiel npm install blah blah blah and first i want to showcase that i
2:18:23
haven't installed nodemon globally and the easiest way for me to showcase
2:18:29
that is by running nodemon and app js so
2:18:34
we'll try to install nodeman package globally why well because then i can use nodemon in any of
2:18:41
my projects at the moment i have it as a local package and of course i can spin
2:18:46
it up by running npm start but let's imagine scenario where i have i don't know 20 nodal applications and i'm
2:18:53
constantly working on node applications so to make my life easier i will install
2:18:59
node 1 globally and then i won't get this error because at the moment you can see command not found normal all right
2:19:06
so how do we do that well we can install it in our terminal or we can do it in the
2:19:13
integrated thermal it doesn't really matter when it comes to global packages you can install it from anywhere so in
2:19:19
my case i'm just going to navigate back to my terminal just so you don't think that i'm cheating and i'll zoom in and we'll simply run
2:19:27
and by the way i need to start with sudo and then npm install and hyphen g and of course we're looking
2:19:34
for nodemon so now of course i'm prompted to enter my password and once i enter my
2:19:41
password of course i'm going to install nodemon globally and now
2:19:47
in any of my projects i can simply go with command of nodemon and then
2:19:53
whatever is the file name now to show you some of the use cases if you
2:20:00
work with gatsby you know that they have the global gatsby cli tool and that was
2:20:06
one of the reasons why you installed something globally is because well you used one of the frameworks for example
2:20:13
react or gatsby in this case and then of course in order to set up the gatsby project or
2:20:19
react project you needed to install this globally now things have changed though with arrival of npx and i'll talk about
2:20:27
the npx at the end of the video but notice if you navigate to your react docs and if you look for create react
2:20:35
app which again was something that you needed to install globally
2:20:40
now they suggest this npx route where essentially you go with npx and then
2:20:46
again whatever is the command name for example for create react app that would be create react app for strappy the
2:20:54
headless cms that would be create strappy app and hopefully you get the gist where for every resource that of
2:21:01
course would be different and with that command you don't have to install that tool globally
2:21:08
for example again in our case we're installing nodemon but normally prior to npx you would install this create react
2:21:15
app globally and then you can spin up those react projects now i'm going to go back to my terminal as you can see i was
2:21:22
successful so what's going to happen if i go back to my project and if i run
2:21:28
nodemon and app.js since i have installed that package globally
2:21:33
there it is i spin up my app.js and if you don't believe me i can change it
2:21:38
back to hello world and i have no issues hello world and there it is now of
2:21:44
course i have hello world e in the console so hopefully it is clear that
2:21:49
yes we can install packages globally and yes one of the biggest use cases was
2:21:56
working with some type of front-end library but with an arrival of npx
2:22:02
things have shifted where now those libraries suggest using the npx route
2:22:08
instead as far as my personal preference since i'm recording a lot of courses and
2:22:14
since some of the global packages usually introduce some kind of bugs to the students now not for all the
2:22:21
students but there's always this one student who just has a lot of issues
2:22:26
with the global package personally i avoid them as much as possible so i always either use the mpx
2:22:33
or i just set it up as a local dependency again it's not a rule you can do whatever you would want but i'm just
2:22:40
telling you what is my preferred option as far as what is npx it stands for
2:22:46
execute and official name is the package runner it is a feature that was
2:22:52
introduced in npm 5.2 and again the main idea is following
2:22:59
where you can run that cli tool for example in this case create react app
2:23:05
without installing these globally so as long as you have npm with a version of
2:23:10
5.2 or greater instead of doing this whole spiel of setting up the cli tool
2:23:17
globally you just go with npx and then whatever here is the tool name and of course the last one is the folder name
Package-Lock.Json
2:23:25
as far as the package log json why do we need it well if we take a look
2:23:30
at our dependencies we can see that they have versions and if you remember
2:23:36
some of the dependencies have dependencies on their own and of course we need to keep in mind that those
2:23:43
dependencies have versions as well and for example the person who gets your
2:23:50
project you probably want them to have the same exact setup because keep in
2:23:55
mind as these versions change well so does some of the functionality
2:24:01
correct so for example you set up to your whole project you use some kind of dependency that uses some other package
2:24:10
and that version changes not for example for the bootstrap but for the jquery and
2:24:15
then pretty much your project is obsolete meaning it might get some bugs because the
2:24:23
version of the jquery changed so that's why you have this package.json
2:24:28
and in there you have those specific versions for all the packages
2:24:34
not only for dependencies but also for the packages that the dependency is using now as far
2:24:43
as this version we have three values and you can think of it as a contract
2:24:48
between us the people who are using the package and the person who is creating and first
2:24:55
number is a major change so when this changes that means that there are some breaking changes now the second one is a
2:25:03
minor one so that means that it is backward compatible so for example if this changes to 18
2:25:10
i shouldn't expect any breaking changes and the last one is just a patch for the
2:25:15
bug fix so that's also something to keep in mind when you decide to publish your
2:25:20
own package that of course that's why we have here this version now lastly i
2:25:26
would just want to mention that if you're interested in more info about the package.json i would suggest this
2:25:33
resource so i simply went with package.json then keep on scrolling keep on scrolling and
2:25:39
you're looking for i guess this blog post right so the name is the basics of
2:25:45
package.json and in here you literally find everything explained to the
2:25:51
smallest detail whether that is a name version and rest of the fields that you
Important Topics Intro
2:25:56
can find in a package.json beautiful we now know how to utilize npm and for
2:26:03
starters as a result for the remainder of the course instead of frantically typing
2:26:08
node.js in a terminal we'll simply spin up nodemon and it will watch for the
2:26:14
changes and restart the app for us now what before we move on to creating
2:26:19
servers with express.js there are a few important node topics i would like to cover first and those topics are
2:26:26
following event loop async patterns in node.js events emitter and streams in
2:26:32
node.js while these topics are extremely important please keep in mind that our goal is to only understand the general
2:26:39
ideas behind these concepts and i only introduce them so you have an overall understanding of how things work
2:26:46
in node.js before we build our first node.js app if you're not satisfied with my
2:26:52
explanations or simply want to do more research by yourself just type any of these terms in your favorite search
2:26:58
engine and i can guarantee you'll find plenty of useful resources within a matter of seconds
2:27:04
like blog posts youtube videos and conference talks with that said it's my strong opinion that it might be easier
2:27:11
to understand those concepts more deeply so not just a general understanding but understanding them more deeply once you
2:27:18
have one or few working node apps under your developer's belt let me also
2:27:24
mention that in order not to waste your time with time consuming setup in few upcoming videos i will run some
2:27:31
pre-built code let me be very clear though i'm only going to do that in a few videos
2:27:37
and for the remainder of the course we will type out everything together all right
Event Loop
2:27:43
and let's kick things off by discussing the event loop now event loop in node.js is one of
2:27:49
those topics where i could spend the entire course discussing it and it still
2:27:54
wouldn't be enough so let's try to avoid that and instead just understand the
2:28:00
journal concepts while there are tons of useful event loop explanations out there the one that
2:28:05
i probably like the most is this one the event loop is what allows node.js
2:28:12
to perform non-blocking i o so input and output operations despite the fact that
2:28:19
javascript is single threaded by offloading operations to the system
2:28:24
kernel whenever possible and as you can see i'm reading straight
2:28:30
from the node docs now don't beat yourself up if this
2:28:35
sounds like a lot of gibberish there's a reason why one can dedicate the entire course just for event loop it is a
2:28:43
pretty complex topic but one word i do want you to remember
2:28:48
is this offloading and you'll see why in a second also don't worry i have
2:28:53
prepared more examples as well as some slides to get my point across but just
2:28:59
in case you're not happy with my examples or you just want to explore the note
2:29:05
event loop in greater detail here are a few external resources i find
2:29:10
particularly useful when it comes to blog posts just go to your favorite search engine
2:29:16
and type node.js event loop and the one that i find really useful is
2:29:22
this one and the resource is nodejs and not.org
2:29:27
but it is dot dev and then follow the link and here they
2:29:33
cover event loop in great detail with a lot of cool
2:29:38
examples and pictures and slides and all that good stuff and when it comes to
2:29:44
videos i would suggest going to youtube and then just type event loop and the
2:29:49
first video that's going to pop up is going to be the event loop bot in browser javascript
2:29:56
and i'll talk about it in a second and the nodejs specific event loop video
2:30:02
is this one i believe it's 15 minutes long and you can see the name over here
2:30:08
so this is a very very useful video where the speaker covers a lot of useful
2:30:15
details about node.js loop in great detail and the reason why i'm suggesting
2:30:21
the first one as well well what is the language that we use in node
2:30:28
that of course is javascript right and even though there's some differences between the event loop
2:30:33
the one that we use in the browser and the one that is in the node.js
2:30:38
if you understand the concepts behind the event loop that we use in a browser
2:30:43
trust me you're already halfway there to understanding how the no js event loop
Event Loop Slides
2:30:51
works since it's such an important topic like promised i have prepared some of my
2:30:56
own resources as well we'll start with the slides and move on to the closed
2:31:01
examples in next video as a side note i made all the course slides available on course api.com again
2:31:10
their website name is coors api.com and once you click on the slides
2:31:15
link you'll see all the slides and i would want to start our discussion
2:31:21
by taking a look at what it means that javascript is synchronous and single
2:31:27
threaded and effectively it's just a fancy way of saying that just repeat
2:31:32
everything line by line so for example if i have console log with first task
2:31:38
then i have a for loop that takes some time in this case two seconds but that could be 10 seconds that could be 20 or
2:31:45
whatever and then i have another console log of next task javascript will just start reading
2:31:52
everything and it will read it line by line and if this takes a long time it
2:31:58
will only run the next test once it's done performing this time consuming one
2:32:05
so hopefully that is clear that javascript just reads everything line by line
2:32:11
and now let's take a look at our second slide and in here we can see the
2:32:16
solution if we would want to offload something to the browser so when we're building
2:32:24
browser javascript apps we have this option of offloading to the browser now of
2:32:29
course it doesn't mean that we can offload the for loop that's not going to work this effectively is still going to
2:32:36
be the blocking code but browser nicely provides the api
2:32:41
where we can offload those tasks to the browser and only when the task is done
2:32:48
then we execute the callback and probably the example we have done the most is the fetch essentially when we
2:32:55
make the network request but we can also do that for example with a set timeout
2:33:01
so i still have console.log with first task but then even though my set timeout
2:33:07
function has the second argument of zero so essentially i have set timeout function
2:33:14
i provide the callback function that's going to be executed in certain amount of time even if this is zero meaning you would
2:33:21
expect this one to run right away it only runs after the next task so once
2:33:30
javascript is done executing the immediate code only then it executes the callback so in
2:33:37
this case we have the set timeout the api that is provided from the browser
2:33:42
and we just said that we would want to execute that e in zero seconds so effectively there is no wait time
2:33:49
however javascript will first execute this code and only then will execute the
2:33:55
callback so that way we can offload those time consuming operations to the
2:34:02
browser again it doesn't mean that we can offload for loops it means that browser does provide some apis
2:34:09
where we don't have to write the blocking code now let me be very clear though when i say we cannot offload for
2:34:16
loops what i mean is that we can still write blocking code in javascript
2:34:23
but the browser does provide some nice apis where we can offload those time
2:34:30
consuming tasks and that brings us to our main friend the nodejs event loop again
2:34:39
before i go over the example let me stress something event loop is somewhat complex and this is just to give you a
2:34:47
general understanding so let's imagine this scenario i have an app and just like any cool app
2:34:54
i have subscribers or users or however you would want to call them and in this
2:34:59
case since my app is so so popular i have eight of them and what do the users do well they're
2:35:07
probably being annoying and they're requesting something from the application and as the requests are
2:35:14
coming in the event loop is responsible for avoiding this type of scenario
2:35:22
so let's imagine this i have all these users the requests are coming in but larry the little
2:35:29
decides that in his request there's going to be some kind of time consuming i don't know
2:35:36
database crawl or something like that so effectively he's requesting something and behind the scenes in my code that
2:35:42
means that i need to perform something that takes a long time so
2:35:48
in this case the event loop just registers the callback so it registers what needs to
2:35:55
be done when the task is complete because if the event loop wouldn't do
2:36:00
that then we would have this scenario where the requests are coming in
2:36:05
and because larry is requesting something that takes a long time the
2:36:10
rest of the users would have to wait and essentially it's not that the actual operation takes a long time it's just
2:36:18
the fact that we're wasting our time on waiting for that operation to be done
2:36:24
and only then we can serve the other users but what the event loop does it
2:36:31
registers the callback and only when the operation is complete it executes it now
2:36:37
keep in mind that again we're not executing this right away when we can effectively it's the same
2:36:44
scenario where we run our immediate code first and only then when we have the time we
2:36:52
execute the callback so for example in this scenario if i would have hundred console logs
2:36:57
after the next task i would run them first and only then the
2:37:02
second task would appear here regardless of what is the time set in here because
2:37:09
again we're running our immediate tasks first and only then we run the callbacks so the same thing happens here
2:37:16
where the requests are coming in let's say that the operation is complete we
2:37:21
first registered the callback operation is complete and instead of executing that callback right away
2:37:28
it effectively gets put at the end of the line and then when there is no
2:37:34
immediate code to run then we execute the callback hopefully that is clear
2:37:39
event loop is our best friend because with the help of event loop we can offload some time consuming operations
Event Loop Code Examples
2:37:47
and effectively just keep all our users happy all right and once we have looked at the event loop in theory
2:37:55
to hammer this home let's also take a look at some code examples where we can
2:38:00
see event loop in action as a side note all code examples are
2:38:06
located in the event loop example directory so if you need to take a look
2:38:11
just grab the repo and you can find it there and you should be familiar with
2:38:16
our first example since it's a async version of read file
2:38:23
method so we import read file from the fs module and then we have console.log
2:38:29
started our task first then we have read file method where we pass the path
2:38:36
we pass the encoding and then of course we have the callback and then in the callback i cancel logged
2:38:43
first result and then of course i have completed the first task and then right after the read file
2:38:50
i have starting next task and something really interesting in a console i can see that
2:38:56
we first cancel logged started the first task then i right away have
2:39:02
starting the next task and then of course once i'm done once i get back my
2:39:07
result then of course i have hello this is first text file and of course completed first task and again the
2:39:15
reason why is this happening because read file is a synchronous
2:39:20
and we already know that event loop will offload this in this case to a file system
2:39:27
so we start reading the file notice like okay run this line of code
2:39:32
then offload this one and only when i get back to the result
2:39:37
then run the callback so when the file system responds with error
2:39:43
or the data then we invoke this one all right so we offload this task and we just keep on
2:39:49
reading the code that's why we have started the first task starting the next one so right away go to the next test
2:39:56
and this one this asynchronous one well we're just offloading and then once the response comes back
2:40:03
whether it's an error whether it's a success only then we invoke the callback
2:40:08
hopefully that is clear now as far as this comment i only added this one because we need to
2:40:16
keep in mind that of course i'm just grabbing this code from the file
2:40:21
but the file is sitting in the folder so if you were to run
2:40:27
nodemon and then directly the filename which is of course going to be in the event loop the path won't match so this
2:40:34
path only matches because of course i have app.js but if you'll try to run
2:40:40
this code directly in this file that's why it's not going to match and you need to go one level up now my assumption is
2:40:48
that you're running it the same as me and you're running that with npm start
2:40:54
that's why i kept the path matching to the one in the app.js now
2:40:59
our next example so let me clear my app.js i can close the read file as well as package.json and then the next one is
2:41:07
set timeout so select here everything and copy and paste in my fgs i'll
2:41:13
restart and then i have two console logs and the third one is e in a set timeout
2:41:20
and this is pretty typical example for javascript loop as well if you have
2:41:25
taken javascript courses which again i assume you have since you're watching the note one you probably remember this
2:41:32
example where i got you here is following yeah i have the console log
2:41:37
first and i have the second and third and you think that since set timeout is
2:41:42
set to zero so since we're saying yeah call this callback function but actually wait only
2:41:49
zero seconds you'd think that the order would be first second and
2:41:54
third right well wrong because we have first third and second
2:42:00
why well because set timeout is asynchronous correct and what happens
2:42:05
with asynchronous well they get offloaded so in this case we run first
2:42:10
third and then the second because this one gets offloaded again
2:42:16
this one goes to the back of the line and only when we're done with our immediate code pretty much with
2:42:23
our synchronous code only then we invoke that callback all right now i also added
2:42:30
these comments here where i have started operating system process and then completed and exited the operating
2:42:38
system process and the reason why i'm showing you that because in next two examples we'll do something a little bit
2:42:45
different so now i would want to go to set interval and by the way it's going to be a bit
2:42:51
clearer if we run here node and then app.js so let me stop this and i'll go
2:42:57
with node and objects and you'll notice that we started the operating system
2:43:02
process and then the moment we're done with the code that's it we exit now if
2:43:08
we'll take a look at the set interval you'll notice something really interesting where if i go with node and
2:43:16
app.js notice something interesting and by the way of course i didn't copy and paste so go to the third example
2:43:22
and then just remove all this code and copy and paste so that's my third example and in here i have the set
2:43:30
interval now again yes we'll have to run few times node app.js and now check it out
2:43:36
so what i see here is i will run first so that's my console log
2:43:42
and then i have the set interval and notice how we're not exiting the process here
2:43:47
so we start the process similarly to the second example but if in the second example we actually
2:43:55
exited because we completed all our tasks in this case we're not doing that why
2:44:00
well because set interval is asynchronous now the difference between the set
2:44:06
timeout and set interval is the fact that set interval runs in those increments in this case of
2:44:12
course it is those two seconds so every two seconds the
2:44:18
event loop is just gonna invoke that callback now that's why we're not exiting
2:44:25
that's why we're still in the process and we can only exit the process if we
2:44:30
kill it so that would be control and c or there's some unexpected error
2:44:36
otherwise it will always stay alive now again keep in mind one thing where
2:44:42
notice i will run first was first why well because again this is
2:44:48
asynchronous and i know i've said this before 20 000 times but again this is probably the core building block of no
2:44:55
the fact that every time we have some asynchronous action it's just going to be offloaded
2:45:00
and then when it's time we invoke the callback and our last example is a
2:45:06
server and again i just wanted to showcase how the process stays alive
2:45:13
so i'll take all the code and copy and paste in app.js
2:45:19
now i'll stop this one so stop the process and then we'll clear the console and again
2:45:25
just to showcase how the process stays live i'm going to go with node and app.js and i'm doing that so you're not
2:45:32
confused with nodemon and then check it out so we have server listening on port
2:45:38
5000 and then every time the request comes in
2:45:44
well we invoke this callback and in our callback we're simply cancel logging request event and then we send back the
2:45:52
hello world so now if i were to go to a localhost 5000 there it is
2:45:59
i have the response of hello world and in a console i'll see this request event
2:46:05
and check it out how again this process stays alive why well because listen is asynchronous
2:46:13
and the moment we set it up now event loop is just waiting for those requests to
2:46:19
come in and then once they come in then of course we run our callback now please
2:46:26
don't confuse this callback with what we're responding our request i went so this callback is
2:46:34
just when we're setting up the server because in here we can have the success over there so in our case as you can see
2:46:40
everything went great we have server listening on port 5000 but of course there also
2:46:46
might be an error and this one of course just responds to that request event but
2:46:53
the whole point is with server.listen we just say hey event loop just keep
2:47:00
listening for those incoming requests and the moments show up then respond to them appropriately
Async Patterns - Blocking Code
2:47:07
hopefully it is clear and of course we can move on to our next topic all right and up next i want to talk about
2:47:14
asynchronous patterns in node.js so if we remember
2:47:21
when we were setting up the file system module we covered how we have two flavors we
2:47:27
have the synchronous one and the asynchronous one and while asynchronous one is great
2:47:34
since we're not blocking the event loop the problem is that if we're using this
2:47:39
callback approach well it gets messy pretty quickly right because we're nesting one callback
2:47:46
inside of the other one so now in the following videos i would want to show you the alternative that we'll use
2:47:53
throughout the course and why in my opinion it is much cleaner syntax and that's why of course we'll
2:48:00
use it and first what i would want is just to kill everything here and i'll
2:48:05
start with the nodemon since i'm done showing you the event loop and
2:48:10
we're just going to go with npm start right that was the proper one and now
2:48:16
i'll delete everything that i currently have not here sorry so i'll leave this
2:48:21
one the async one i would want to remove everything in the app.js and now i just want to quickly show you
2:48:28
the code that would block that event loop again this is going to be the video where
2:48:34
if you don't want to code along you don't have to you can just sit back and relax
2:48:39
and effectively you'll be in good shape and again we'll set up the server like i
2:48:45
mentioned before already 20 000 times don't worry about specific commands
2:48:50
we have rest of the course where we'll be building servers so trust me you'll get sick of it so go with http
2:48:59
and require and of course we're looking for http module and then remember the methods create
2:49:06
server and listen so we go with const and we create the server that is http
2:49:12
and create server we pass in callback a callback takes two objects request
2:49:18
object and response object so again essentially request object is what is coming in and response object just
2:49:25
represents what we're sending out what essentially we are responding and then i
2:49:30
would want to listen on a port again so i run server.listen and then i'll pass in the port of 5000 and then of course
2:49:38
we have that callback once the server is ready and in here we can just go with console.log
2:49:44
and we'll simply say server is listening on port 5000 server is
2:49:52
is listening or just listening listening on port and then of course in my case
2:50:00
port is 5000 let's set that up so we should have this listening on port 5000 and then of
2:50:07
course in my callback function i would want to check 40 urls because i want to
2:50:13
show you how even if we try to get a different resource we're still blocked
2:50:19
by other user if he or she is requesting some kind of resource where we have the blocking code
2:50:26
and don't worry if this sounds like gibberish you'll see what i mean in a second so remember on the request object
2:50:33
we could check for the url so effectively you could check what is the resource that the user is requesting
2:50:40
so for example home page would be forward slash and then the about page would be forward slash and about and
2:50:47
that is sitting in the property by the name of request and url so request is
2:50:53
the object and then url is the property so again we'll do a quick and dirty way
2:50:58
we'll just say request url is equal to a forward slash that means it's a homepage
2:51:05
and then we just need to go with a res.end and then we'll say home page again later
2:51:12
we'll have way more sophisticated approach but for now this will do and then we're checking for the about
2:51:19
page okay awesome so this is going to be an about page and then
2:51:25
if there's a page that doesn't match any of the resources then of course i'll just send back
2:51:32
i don't know error page i'm not going to set up the whole link nothing like that
2:51:37
all right we save it and then this should send back about page awesome and
2:51:43
then of course in home page i can just respond with the homepage so life is
2:51:48
beautiful users can come here and as a side note multiple users i'm representing with these tabs so imagine
2:51:56
these are my users and life is beautiful we are requesting resources and we're
2:52:02
just going on about our day now the problem is going to be if i go to about
2:52:08
and if i set up some kind of blocking code now what would be a blocking code well that could be
2:52:14
a nested for loop so i'm just going to go with blocking code and then i'll add some exclamation
2:52:20
points and let's simply set up a for loop let's say i
2:52:26
is equal to zero and then let's say i is less than
2:52:32
thousand and yep i plus plus so every iteration will increase by one
2:52:38
however i'll set it up as a nested portal so copy and paste and i'll just change
2:52:44
these values to j so j here and j here
2:52:51
and then let's just cancel log and we'll say j and i again doesn't
2:52:57
really matter what we type there just say i and j
2:53:02
now known dialogue question what do you think is gonna happen so if the user navigates to about i mean
2:53:10
we can kind of see that this will take some time right now you would expect though that
2:53:17
only the user who navigates here gets blocked and
2:53:22
you'd be wrong because we'll also block the other suckers who are just trying to
2:53:28
get to the homepage so let me navigate here and check this out so i run this one and
2:53:33
notice how we're loading now the same thing happens here now and here okay and only when we're done here
2:53:41
then these two can get the resource again now of course if i go
2:53:46
to my project i can see that in the console i have all these values right because i
2:53:53
have this blocking code i have the synchronous code that just takes a long
2:53:58
time and this is just a representation of why
2:54:04
we prefer this asynchronous now yes at the moment this is messy and don't worry in the next videos we'll fix
2:54:10
it but this hopefully gives you an idea why you should always strive setting up your code asynchronously
2:54:18
because what we've learned in the previous videos if we do that then those tasks
2:54:24
are offloaded and then only when the data is back only when it's ready
2:54:31
then we invoke it and that way we're not blocking the other users hopefully it is
2:54:36
clear and now of course let's take a look at some other patterns we can use so we still get the benefits so we're
2:54:43
not blocking that event loop but we also have a cleaner code
Async Patterns - Setup Promises
2:54:49
where we don't have this nested callback mess all right and once we have covered
2:54:56
why it's so important to use the asynchronous approach now of course let's clean up our f a a
2:55:04
sync so instead of using these nested callbacks let's see a nicer pattern and
2:55:10
as i say note if you want to see the code that we wrote in a previous video and
2:55:16
the one we are about to write then the files are located in two async patterns
2:55:23
folder so i'll close everything for now and then back in app.js
2:55:29
i can remove it like i said if you want to access that code it is sitting in the two async patterns folder and we'll
2:55:37
simply start by recreating the read file setup where i'm gonna go with
2:55:42
const and i'm right away accessing that from the file system module and i'll set
2:55:48
it equal to require of course and then file system all right that's awesome we
2:55:53
know that it is asynchronous so we need to set it up with three parameters we go
2:55:59
with read file and then we would want to pass in path first so again since i'm in app.js
2:56:06
i'm going to be looking for the content and then forward slash and then first txt the file we already created before
2:56:13
then we have encoding so comma and then again we're going to go with utf-8 and then last one is going to be that
2:56:20
callback where the first value is the error and then the second one is the
2:56:26
data that we're getting back okay awesome so once the file system responds
2:56:32
then of course we invoke this callback and inside of that callback we have our logic so if there's going to be an error
2:56:39
for time being i will just return like so and then if i have the data i'll set it
2:56:46
up as else so say here console log and data of course
2:56:52
and we shouldn't be surprised if we've seen a console hello this is a first text file because we already
2:56:58
covered the setup right so we're passing the path we pass in the encoding and
2:57:04
then we set up the callback now the problem starts if we would want to perform
2:57:10
multiple actions if i want to read two files and then for example write one
2:57:16
correct so what would be a better solution well a better solution would be turning this into a promise and
2:57:23
then eventually we'll set up async await now please keep in mind that the only reason why i will type out the promise
2:57:30
stuff is because i would want you to understand what is happening behind the scenes but don't worry throughout the
2:57:37
course we'll just stick with a sync and a weight syntax and essentially you
2:57:43
won't have to worry about what is happening behind the scenes but the first example yes i want you to
2:57:48
understand everything in detail so what we could do is create a new function
2:57:54
and we can just say const and then i'll call this get text now this get text will take a path
2:58:01
since i want to read two files and then eventually write one as well just like we did here and of course the goal here
2:58:08
is to showcase how we can make the code in the file fs async at least that's how
2:58:14
i called my file much cleaner and more readable so again we pass in the path
2:58:19
and then what i would want to return from this function is a promise so we go
2:58:25
with return new promise and then in the promise object we need to pass in is another
2:58:33
callback function so we pass in the callback function and in here we pass in two more functions one for resolve and
2:58:40
then one for reject and then once i have set up both of these parameters now of course what i would want is to move the
2:58:48
read file and place it inside of the promised one
2:58:53
okay so once we place it here first of all notice here how i'm passing in the path so of course i can change this one
2:59:00
around so i can say path and then the encoding stays the same as well as the callback however inside
2:59:07
of the callback once i have access to resolve and reject what i could simply
2:59:13
say that if there is an error i will spit back the error so say reject
2:59:18
an error and if everything goes great now of course let's go with resolve and
2:59:24
then we'll pass in the data and once we have this setup what's really cool that
2:59:29
now i can invoke get text and this is going to return a promise and then of
2:59:35
course we can chain that then and catch so below the get text i can go with get
2:59:41
text and of course we're looking for the path so we still would need to use dot and then forward slash and then content
2:59:47
of course and first txt so that's the path and then like i said
2:59:53
we are returning a promise so we can chain that then and of course here i can have the result
3:00:00
and i'll just cancel log it for now or result and then i can also chain that
3:00:06
catch and here i'm passing in the error so again we can't log it and we simply would want to see the
3:00:13
error i save it and beautiful again in a console i have hello this is
3:00:19
first text file so i know that it worked and also if i change the path
3:00:24
so if i make my path incorrect we should see in the console the error
3:00:30
where of course node cannot find file so if that works now of course we can take
Async Patterns - Refactor To Async
3:00:35
a look at how we can make it even cleaner by setting up async 08 and once
3:00:41
we have our initial setup once we have turned this into a promise
3:00:47
technically we're not out of the woods because if i would want to perform again
3:00:53
two file reads and then eventually write the file as well and if i would want to
3:00:58
do all of that asynchronously it's still going to be paying just by using the
3:01:03
promises so what would be a solution well since we're returning a promise if i use async await
3:01:11
i can wait till promise is settled and then decide what i would want to do
3:01:17
and the way we set that one up is by creating a new function now please keep
3:01:23
one thing in mind where eventually throughout the course those functions that i'm about to set up
3:01:31
are going to be provided to us so we'll just attach that async to the
3:01:36
callback functions that already provided us by the libraries okay but in this
3:01:41
example i'll have to create one from the scratch and again the whole point here is because i would want to create a
3:01:46
function a start function that i'm going to set up as a synchronous function and
3:01:52
i would want to attach a weight so i would only respond once the promise
3:01:57
is settled so in here i go const start and that's my function but i need to set
3:02:03
it up right away as async because i would want to use my await keyword correct and then we simply go with const
3:02:11
and i know that of course i'm looking for the first file and i'll just say first and that one is
3:02:17
equal to get text and basically i want to pass in the same thing here now i do need to
3:02:24
place this one in quotation marks so my bad i messed it up a little bit okay i passed it in and that should do it
3:02:31
now of course what i'm missing here is a weight so i had this await and now only
3:02:36
once the promise is resolved then i'll get my response so what i
3:02:42
could do here is just comment these two or you know what this one i cannot comment out yet
3:02:48
don't worry we will eventually this one i can comment out and then maybe
3:02:53
move this below okay so you don't think that i'm running this code and since i have my function
3:02:59
now of course i would need to invoke it so invoke start and check it out now of course i don't
3:03:07
have the error which is a good sign i guess and then we'll simply go with log and
3:03:12
none first and notice the difference where previously when we were setting up
3:03:18
the callbacks we had to nest everything now i'm waiting for this promise to be resolved and only once it's resolved
3:03:25
then of course i can do something with the value now every time we have this async await approach what we would want
3:03:32
is to wrap this e in the try catch block so if something goes wrong then we have
3:03:38
at least a little bit of control over it so i'll set up try catch block and then
3:03:44
i'll set up my first await and eventually we'll add here more and then in the error i'll simply go
3:03:52
with console.log and we'll console log the error and let's just save that one
3:03:57
so now we have nice try and catch block and by the way sorry i deleted it we'll
3:04:03
still take a look at the first one and then if we change the path then of course we'll get an error okay
3:04:09
so that's good now i have my start function it is the synchronous i'm waiting for the promises to resolve
3:04:16
they're all wrapped in try catch block so what's next well if you remember in
3:04:22
here what were the actions that we were doing well we read two files correct and then
3:04:30
we wrote one okay so let's try that one with this new approach where essentially i have first so just copy and paste and
3:04:38
then i'll look for the second file remember we should have that in the content so
3:04:44
this is going to be the second one second over here and then i would want
3:04:50
to write the file now of course you could say well the problem here is going to be that i'll have to
3:04:57
write a new wrapping function to set it up as a promise because
3:05:02
yes we can of course read the file but functionality for the write file again
3:05:07
we would need to wrap it don't worry there's a way how we can get this actually out of the node
3:05:14
first i just want to showcase how much cleaner this already is where i can just wait for first
3:05:21
second like so and now notice in the console hello this is the first text and hello this is the second file again i
3:05:28
fully understand that you're looking at this wrapper function and you're like well this definitely doesn't look that
3:05:35
much cleaner than this one don't worry there's a way for us to get those functions
3:05:41
in a way that they're already returning a promise what i would want you to focus
3:05:47
on is this code what i would want you to understand that this definitely
3:05:52
is much cleaner than what we have here we read the file and then we set up
3:05:58
another nested callback and another nested callback and hopefully you get the gist
3:06:04
waiting for these promises to resolve is definitely a cleaner and more readable
Async Patterns - Node's Native Option
3:06:11
approach all right so this works we have our start function it is asynchronous
3:06:16
we're waiting for prompts to resolve and we can see that it is already much
3:06:21
cleaner how we can set up this code without the wrapping function
3:06:27
well what's really cool that in node there is a module by the name of util
3:06:33
and we just go here const and we'll assign it to a variable and we'll just
3:06:38
be looking for require of course since we would want to import the module
3:06:43
and again the name is util and then instead of this module we have
3:06:48
a method by the name of promisify and with the use of this function we can
3:06:54
take our read file which of course was looking for the callback and turn it
3:06:59
into the function that returns a promise and again this is over simplified
3:07:05
version what is happening there but hopefully you understand that as a result we'll get again this promise back
3:07:12
now the way we'll set that up of course we have read file here already so i cannot use the same name that's why i'll
3:07:18
go with read file and we'll call this promise and that one is equal to util that is of
3:07:26
course my module dot and then notice the function promisify and then we pass in
3:07:31
that read file function so now i have my promise one so now what i could do
3:07:37
is first of all comment this out and move it down again so it stays for your reference
3:07:44
but it doesn't compromise my view and of course now i have the error
3:07:50
because well get text is not defined that's fine don't worry and i'll copy and paste and
3:07:57
since i also want to write a new file i will get from the file system one
3:08:04
the right file function and then i'll do the same thing where in this case it's going to be
3:08:10
called write file promise and then we pass in write file
3:08:16
and of course now instead of calling get text what i'm gonna do is go with
3:08:22
right file or i'm sorry in this case we're going for read file promise and
3:08:27
then keep in mind one thing where this is not a get text one so we're still
3:08:32
looking for the path as well as the encoding that's well copy and paste and then second argument we
3:08:39
pass in is the encoding and again our functionality shouldn't change where i
3:08:45
should see in console the results from the first txt now of course i want to do
3:08:52
the same thing with the second one so have read file promise second txt
3:08:58
again we have to pass in the encoding otherwise we'll get the buffer back
3:09:04
so copy this and paste and again if we cancel log it there it is we have hello
3:09:10
this is first text file and this is the second one and since in the line 4 we
3:09:15
passed in write file into promisify of course what
3:09:20
we could also do is right away write the file so i can go with await and i'm
3:09:25
simply not assigning this to a variable because well i'm getting back on the
3:09:31
finder as far as data and i'm just going to go with await write file promise and the same spiel we
3:09:39
pass in first the path and in this case of course if the file is not there
3:09:44
node will create one and the name will be result and i'll just call this mine
3:09:51
grenade and then txt and then the second one is data so for that one i'll set up
3:09:57
my template string and i'll just say this is awesome awesome
3:10:03
and then let's set up the colon and then we'll access both first
3:10:08
as well as the second one so we'll interpolate both of them
3:10:14
second and then once we save if we take a look at the content there
3:10:19
it is now we have the mind grenade one correct now there's probably one where i
3:10:24
was testing yep there's one where i was testing so i'll remove this one but if i
3:10:29
take a look at dtxd1 then of course i'll have this is awesome hello this is first
3:10:35
text file and then i have the second one now what's even more cool
3:10:41
that technically we can even skip this part as well again i'll leave this one for your reference
3:10:47
but if you go to require and then you require of course file
3:10:54
system module but if you add dot promises what do you think is going to return
3:10:59
well effectively the same thing so now of course i just need to change the name from read file promise and write file
3:11:07
promise back to read file and write file since those are the two functions that
3:11:13
i'm importing and that will right away return promises and again we save and
3:11:18
remember that by default we're just overwriting stuff so if i were to go
3:11:25
and add a third argument my options one and if i'm just going to say flag and i'll set it equal to upend once
3:11:34
we save well now we have this is awesome repeat it one more time again just to
3:11:39
showcase that our functionality still works i fully understand that there was a
3:11:45
little detour where we created our own wrapper function and then we covered how we would consume
3:11:54
promises but hopefully this helps you understand that this approach is
3:11:59
definitely way better so it is more readable it is more easier to wrap your head around and
3:12:07
that's why for the remainder of the course we'll stick with this one again
3:12:12
some things will be provided to us by default so libraries will provide the functions that return
3:12:19
promises will right away have the callback functions that we'll just set up as async and hopefully you get the
3:12:25
gist so a lot of things will be given to us but the core functionality won't
3:12:30
change where instead of using callbacks and nesting them inside of the other
3:12:35
callbacks and nesting more and more and more we'll set up everything with async await
Events Info
3:12:42
because the syntax is cleaner and way easier to read
3:12:48
excellent once we have covered async patterns we're going to use throughout the course now let's talk about events
3:12:55
in node.js when working on browser javascript apps a big part of our work
3:13:02
is to handle events for example user clicks a button
3:13:07
and of course in our program we handle that user hovers over the link
3:13:13
and again same deal in our program we are handling that and hopefully you get
3:13:18
the gist essentially as our program executes at least in part it is
3:13:24
controlled by events of course depending on a program but it's safe to say that in browser app
3:13:30
those events are mostly external now that style of programming is
3:13:35
actually called event driven programming and effectively it's just that a style
3:13:41
in which the flow of the program is at least in part determined by the events that occur
3:13:48
as the program executes now it's easier to imagine that of course
3:13:54
when you have a gui right the graphical interface just like the button and links example i
3:14:00
just mentioned but what about server side is it also possible and of course the
3:14:06
answer is yes in fact event driven programming is used heavily in node.js
3:14:11
and in the following videos we'll see some of the examples of it and basically the idea is following we
3:14:17
listen for specific events and register functions that will execute
3:14:22
in response to those events so once our event takes place callback function fires just like in our
3:14:30
imaginary button example now before we continue let me stress something our first examples are going
3:14:35
to be basic and even somewhat silly but don't let that fool you
3:14:41
many built-in modules in node.js do use events under the hood and therefore
Events Emitter - Code Example
3:14:46
making events and event driven programming a big part of nodejs all
3:14:52
right and once we have covered general concepts behind events as well as event-driven programming now let's set
3:14:59
up our own events in node and the way we do that we come up with a variable and
3:15:05
typically this name is event emitter because what we're getting back is the class
3:15:11
and we require the events module so require events module and we assign it
3:15:17
to a variable which essentially is a class and again a common practice is calling
3:15:23
this event emitter and at this point you have two options if you want to create something custom
3:15:29
you'll need to extend the class or if you simply want to
3:15:35
emit an event as well as listen for it then you can just create the instance so go with the
3:15:40
second route we'll go with const and then whatever name you would want in my case i'm just going to call this custom
3:15:47
emitter like so and i'll assign it to new emitter so event emitter or however you
3:15:55
call this variable and we just need to invoke it so now we have the instance of
3:16:00
our class so essentially we have the object now there are many methods in this object however two that we're
3:16:08
interested the most are on and emit so on we'll listen for specific amend
3:16:15
and then emit of course will emit that event and the way we set it up we go with
3:16:21
custom mirror or whatever name you used and then we go with on and at the very basic setup in the on
3:16:29
method we just pass in the string where we say the name of the event now
3:16:35
in my case i'll name my one response and then of course once i have subscribed to
3:16:40
it i also would want to pass in the callback function so essentially when this event takes place
3:16:47
well then i would want to do something and in my case i'll just go with console.log and we'll simply say data
3:16:54
received or i'll place this one in the template strings and you'll see in a second why so we'll go with data
3:17:01
received and then eventually there's going to be some more data and of course once we
3:17:06
have subscribed to this specific event now i would want to admit it and the way
3:17:12
we do that we just go with custom emitter and of course the method is
3:17:17
surprise surprise emit and of course at this point these strings need to match so if i'm
3:17:24
emitting the response event and just say here response and what
3:17:30
you'll see in the console is wherever you have in callback so of course in my
3:17:35
case i have console log data received and then once i run it i have data
3:17:40
received in console so that's the most basic setup when it comes to events
3:17:46
again we create an instance from the class that we get back from the events module and then we have two methods we
3:17:54
have on method as well as the emit method and then in the on method we pass
3:17:59
in the string so that's going to be the name of the event as well as the callback function
3:18:05
so once this event takes place then of course we would want to do something and in our case we'll just
3:18:12
console.log data received and then once we have subscribed to this event then of
3:18:19
course we need to emit it and the way we do that we just go with whatever the name is in my case custom
3:18:26
emitter then emit method and then we pass in the same string that we're
3:18:32
listening for in our case of course response and then the moment we do that
Events Emitter - Additional Info
3:18:38
we of course have whatever is in the callback function which in of course of course is just a simple log data
3:18:45
received all right and once we have covered the basic setup now let me show you some
3:18:50
things that i would want you to be aware of first we can have as many methods we would
3:18:57
want so for example we have the same event we have here response correct and
3:19:03
we are omitting it so nothing stops me here just copy and paste
3:19:09
and listen for the same event which of course in our case is this response and then do some other logic in
3:19:17
my callback again in my case it's just going to be simple different kinds of log so i'm going to
3:19:22
say some other logic here and i'm not going to copy and
3:19:27
paste the same function 20 000 times just to prove my point but hopefully understand
3:19:34
that yes we can emit our event and then yes also we can have as many functions
3:19:40
we would want here that our listening for that event and do some other logic so that's point number one point number
3:19:48
two that i would like to make is the fact that this order matters
3:19:54
so we first listen for event and then we emit it so for example if i will place
3:20:02
my emit above the second function or above both of the functions which you'll
3:20:07
notice that i have nothing in a console why well because i first emit the event
3:20:14
and only then i listen for it as you can see that doesn't make sense so first we would want to listen for the
3:20:20
event and only then we would admit it so in this case notice i don't have this some
3:20:26
other logic goes in here because i listen for response and then i right away admit the response and then again i
3:20:33
listen for the response but i already admitted the event correct so it doesn't
3:20:38
make sense to listen for the event once it has been already emitted so that's
3:20:44
the point number two and then thirdly our also on a showcase that we can pass the arguments when
3:20:50
we're omitting the event so for example i go here with my emit i pass in the
3:20:56
name which is of course response and then i can pass in more arguments for example here i'll go john and then the
3:21:04
id number 34. so string and a number and then in my callback function
3:21:11
i can access those arguments as parameters just like normal functions so
3:21:16
in this case i'll call them name and id and simply in my console.log i'll say
3:21:22
name and the second one will be with id and then whatever is that id
3:21:29
now i'll add here data received user and then save it and it's no
3:21:34
surprise that in the console i see data received user john with id34 now in the
3:21:40
second function as you can see i wasn't looking for those arguments i just don't have access to the arguments
Events Emitter - Http Module Example
3:21:45
because i don't have the parameters but it's not like everything broke just because in the event i passed in the
3:21:53
arguments and lastly i would just want to reiterate the point that even though you might not write
3:21:59
your own events events are a core building block of node and effectively
3:22:05
as you're building and writing out the code for your node application you are
3:22:10
using those events at the end of the day anyway because a lot of built-in modules
3:22:16
rely on them and as a quick side note if you'd like to see the code that we wrote
3:22:22
in previous two lectures you can just navigate to 13 event emitter and in
3:22:28
order to show that i'll quickly set up a server and again the code for this one you can
3:22:35
find at 14 and then request event so copy all the contents from the file
3:22:41
and then just copy and paste and notice something interesting where
3:22:46
again yes we're getting the http module and remember the setup that we have used
3:22:52
so far where we go with http create server and then we pass in this callback
3:22:57
function and then of course this callback function will be invoked every time
3:23:03
someone visits our server so every time the request
3:23:08
comes in now there's another way how we can set it up by using event emitter api
3:23:14
so we still create a server we go with http and then create server function but
3:23:21
instead of passing in the callback function like we did previously server has the method
3:23:27
on does that ring a bell remember our previous example we had our own instance and
3:23:35
it had the method of on correct so the same goes for server so server has the
3:23:40
method on and we listen for request event and when that request
3:23:47
comes in then of course again we have this callback function that handles it so
3:23:52
behind the scenes server emits the request event and then of course we can listen for it we can
3:23:59
subscribe to it listen for it or respond to it however you'd want to call it and the way we do that we go with server on
3:24:07
and then this is a specific name because of course it emits that specific
3:24:13
name behind the scene so make sure that it is a request and then the same spiel
3:24:18
now how do i know that well if we go to node documentation and if we look for
3:24:24
http we keep on scrolling keep on scrolling eventually we'll hit the server
3:24:29
and over here i can see that it has a clash okay that's a good start and that what
3:24:35
do you see here well i see the event right and what is the event well the name is request so
3:24:43
that's how i know that my server the instance that i create has the ability to listen for
3:24:50
request events and if you want to dig deeper you can just click on a server
3:24:55
you notice that it extends the net server and if we keep on digging check
3:25:01
it out so this one extends what it extends the event emitter so hopefully
3:25:08
that makes it clear that even though you might not be setting up events on your
Streams Intro
3:25:13
own a bunch of built-in modules rely heavily on this concept of events all right and
3:25:22
up next we have streams in node.js and at its simplest streams are used to
3:25:28
read or write sequentially basically when we have to handle and manipulate
3:25:33
streaming data for example continuous source or a big file streams come in
3:25:39
real handy and now there are four different types of streams we have writable used to
3:25:45
write data sequentially then we have readable used to read data sequentially duplex
3:25:50
used to both read and write data sequentially and also transform where data can be modified when writing or
3:25:58
reading just like with events many built-in modules in node implement streaming interface
3:26:04
and what's also interesting streams extend event emitters class which simply means that we can use events like data
3:26:12
and and on streams since streams are somewhat off an advanced topic in node i'll try to keep
Streams - Read File
3:26:19
it short and sweet mostly by showing you examples of streams and hopefully that
3:26:24
way you get the main idea without being overwhelmed all right and once we know the theory
3:26:30
behind the streams now let's take a look at the practical example and a very good use case is using
3:26:38
streams when we are reading files because we need to understand one thing
3:26:43
where when we use the sync or asynchronous approach what happens we're
3:26:49
reading the whole file and of course in our example we were setting this equal to a variable correct but if we have a
3:26:58
big file well first of all you're just using all that memory and second
3:27:04
as the file size gets bigger and bigger bigger eventually the variable is not
3:27:09
going to be good enough you will get an error that i mean the size is too big and you
3:27:14
cannot place everything in the string so what would be a solution one solution
3:27:21
would be read stream option and the way we'll set this up
3:27:27
i'm going to start app.js from scratch but if you take a look at the repo
3:27:34
you'll notice this 15 create big file so previously when we were working with
3:27:39
files i just had some small files right so i had the first txt blah blah blah
3:27:45
result and whatever now before we set up the read stream i would want to create a
3:27:51
big file again this is optional you don't have to do that but in my case in
3:27:56
order to show you how the streams work yes i'll have to set up a big file and
3:28:02
first i'll remove it because of course i already have it since i was testing it
3:28:07
and now i'll stop my server and of course in my case i'll run 15 the create
3:28:12
big file js if you want to set it on your own and if you don't want to use the repo you can
3:28:17
just get the right file sync from the fs module and then notice i have the loop
3:28:24
where i believe i have here 10 000 and then every iteration i just write a
3:28:32
big txt i of course i have the flag upend and then i'm just adding hello
3:28:37
world and starting a new line so if i'll run node
3:28:42
and then of course i'm going to go with my file name which is 15 then hyphen
3:28:48
create big file and js like so
3:28:54
then in the content i should have this big file and once i have my big file i'll go back
3:29:01
to app.js and i'll use my npm start since of course i have known mine in
3:29:06
place and then let's go with cons now i'm not going to show you how the setup
3:29:12
would look like with file sync or the asynchronous one again hopefully you
3:29:18
understand that the setup would be exactly the same like we have in 10 and
3:29:23
11 where we had the fa sync and fa async and now of course let's just go with the
3:29:30
stream option so the method name is create read
3:29:35
stream and we require that from the fs module like so
3:29:41
and then we create a new variable and in my case i'll call this stream and we invoke the
3:29:48
create read stream and the only thing by default we need to pass in is the path
3:29:54
so of course in my case i'm going to go with content and then forward slash and since i just created that text file the
3:30:00
big one of course i'm going to go with big txt and now remember the good old friends events well
3:30:07
once we create this instance we actually have access to them and the ones that
3:30:12
we're going to use is going to be data and error so we can go with stream
3:30:19
and then on and remember the event syntax and then the event that you would
3:30:25
want to listen for is a data and then we have our callback function and again it
3:30:31
is a parameter so we can call whatever we would want but in my case i'm going to go result and let's just console.log
3:30:38
the result like so and what you'll notice
3:30:43
is that we have 64 kilobytes here that's our first console log then we have another one 464
3:30:51
kilobytes and the reason why i know that is because by default that's the size we're getting and then we're getting the
3:30:58
reminder now just to prove my point i'm going to go to my folder
3:31:03
and i'm going to look for my content and then in there if you take a look the
3:31:10
big text file we created is 169 kilobytes so as you can see now
3:31:16
we're reading data in chunks and by default that chunk is 64
3:31:22
kilobytes and every time we cancel log we see that we have 64 64 and eventually
3:31:30
we have the remainder so instead of reading everything and placing that in
3:31:36
the variable we're doing that in chunks and as you can see we're using the event
3:31:42
and the event is data and in order to hammer this home why don't we take a look at the docs
3:31:48
so first i'm going to look for my file system and then let's look for
3:31:53
our create read stream so we go here as we can see we have this class read
3:32:00
stream and then on this class we have these three ones we have close open
3:32:05
and ready and as a side note we'll use this one a little bit later as well the
3:32:10
open one so keep an eye on this one and then as far as the read stream well as
3:32:16
you can see it is created when we go with create read stream and invoke it
3:32:22
right so i got the create read stream that's my function i just passed in the
3:32:28
past and i invoked it and in turn that returns
3:32:33
the read stream right then actual read stream extends from
3:32:40
stream.readable so right away i have these events i have close open and ready and like i said we use this open a
3:32:46
little bit later now since it is extending from the stream check it out
3:32:52
now of course i have the data one all right so this is a chunk of data and as you can see every time we are
3:32:59
getting that data we can do something with it now at the moment we're just going to logging it's
Streams - Additional Info
3:33:04
very simple but eventually as you can already imagine we can do way more
3:33:10
useful things than that beautiful once we understand the basics now let's take
3:33:15
a look at some additional info like i said by default the size of the buffer
3:33:21
is going to be 64 kilobytes however we can also control it and the way we do
3:33:27
that is by passing in the object when we're setting up create read stream so
3:33:34
first argument is going to be the path which again in my case is going to be that big text file that i created using
3:33:42
my file using my for loop and then i can pass in the options object and in there
3:33:48
the property that you're looking for the property that controls the size of the buffer
3:33:54
has the name of high water mark so for example if i go with 90 000 here then of
3:34:01
course you'll see that i'll have two console logs one for 90 kilobytes and the second one will be
3:34:08
remainder again keep in mind that our file size is
3:34:13
169 kilobytes that's number one number two we can right away set up the encoding as
3:34:20
well so i go with comma and then the property name is encoding and again
3:34:25
we'll set it up equal to utf-8 like so and then you'll see in a console of
3:34:31
course the hello world why well because that is the content coming from the file
3:34:36
and lastly i also would want to mention that we have the error event as well so
3:34:42
if i go with stream and then on and we're checking for the error and as
3:34:48
always we can do something once that error happens so that's our callback function and in this case i'll just
3:34:54
access the error property and i'll console.log the error so i'll say here error and the way we check that one out
3:35:02
is by providing wrong path so in my case i'm just going to add two dots and then
Streams - Http Example
3:35:07
once i save check it out in a console i'll have the error where it tells me
3:35:13
that no such file or directory all right and now let's take a look at
3:35:18
the practical example when streams come in handy now again this is going to be
3:35:24
one of those videos where you don't have to code along you can just sit back and relax and see how i struggle and first
3:35:33
what i want is to make it even a bigger file so remember d15 create big file
3:35:39
i believe i had 10 iterations right so i'm gonna add one more
3:35:45
meaning i'll add one more zero i'll stop my server right now again this is
3:35:50
optional you don't have to do that and i'll remove the big file like so
3:35:56
and then i'll run one more time the file with node and then of course this file is going to
3:36:03
be way bigger so let me navigate to my folder just to showcase that and i'm looking for content and now the
3:36:10
big file is 1.8 megs now once i have the big file
3:36:16
i'll go with npm start at the moment i just have the stream example but if you want to see
3:36:23
the whole code just take a look at the file number 17 and notice again we're creating a http server and i'm just
3:36:31
using the read file stick method i'm looking for big txt the encoding is
3:36:36
utf-8 and then i just place my variable my text one into
3:36:42
res dot and method and effectively i'm just sending my big text file
3:36:50
and let me restart the server here so let me go with npm start right
3:36:57
now so let me select everything from this file and copy and paste
3:37:03
and now if we navigate to localhost 5000
3:37:09
we should see a bunch of hello world now the problem with the setup is
3:37:14
following where if i go to developer tools and if i take a look at the network and if i refresh
3:37:21
yep this request was successful take a look at the size do you think
3:37:28
it is the smartest thing to send these type of files over the wire and of
3:37:33
course this is just going to make it very difficult to all your users because
3:37:38
you're just sending large chunks of data effectively i'm sending the whole file
3:37:44
and more specifically if i click check it out so i have the request url okay
3:37:49
that is good the method is get now as you can see the content length
3:37:55
is my 1.8 megs right and you'll see in a second that once we
3:38:01
refactor this to read stream method that we're sending data in the chunks
3:38:07
and again the best way to see that is by looking at the headers where at the moment i can see the content length and
3:38:14
that one is at 1.8 megs but once we refactor that the setup is going to be
3:38:20
different so at the moment i have this text i'm accessing that by read file
3:38:26
sync so comment this out and let's set it up with our create read stream so
3:38:31
i'll go with const and i'll call this file stream and this is going to be equal to
3:38:37
fs and then create read stream now use the same address
3:38:42
so use the same path and then i'll use the same encoding as well
3:38:48
so let's go with utf-8 okay awesome and once we set up the stream remember we have access to
3:38:55
to events file stream on and of course i'm going to be looking for the open
3:39:01
and i'll have my callback function and we'll set that functionality up in a second and the second one of course is
3:39:08
the error so go with file stream and then on and again we're looking for the
3:39:15
event by the name of error and then in our callback function we can access the error and i'll simply pass it in in my
3:39:23
response so if there is an error i'll just grab the error from my parameter
3:39:28
and pass it in now as far as the open here instead of setting it equal to
3:39:34
instead of going res dot end and then text file stream also have the pipe
3:39:40
method so we can go to file stream and then pipe and what the pipe is doing it
3:39:46
is pushing from the read stream into right stream so you can imagine that if
3:39:51
we can read data in chunks we can also write data in chunks and what happens
3:39:58
under the herd response object can be set up as a writable stream so we have
3:40:03
our file stream so that's our read stream we have method of pipe so we're piping this into a writable stream and
3:40:11
now of course i'll pass in my response object and if we go back to the browser
3:40:17
and if we'll refresh now notice something interesting yeah still same request right to localhost
3:40:24
5000 still same size but if i take a look at the headers now i
End Of Node Tutorial Module
3:40:30
can see that my response headers are chunked so instead of sending our file
3:40:37
back in one large instance we're sending it back in chunks awesome congrats on
3:40:43
completing section number three node fundamentals and hopefully after watching the section you have a good
HTTP Request/Response Cycle
3:40:50
general understanding of how node works and now that we're big shots let's apply
3:40:55
that knowledge and build some servers shall we and we're going to start section 4 with the general info of how
3:41:03
the web works more specifically how we exchange data on the web
3:41:08
and we're going to do that with the help of few slides now if you're one of the people who's
3:41:14
already reached a daily slide limit i hear you once we're done with these suckers i
3:41:20
promise we'll mostly actually write code for the remainder of the course
3:41:25
i do believe though that before we build an actual web server it's crucial for us to understand how it works under the
3:41:32
hood and that way we'll have clear understanding of what tasks need to be
3:41:37
done if something is iffy you can always go back to the slides you already know
3:41:42
where they're located and also as we're going to be progressing with the course
3:41:48
from time to time i will swing back to them when i'll need to emphasize a specific point
3:41:53
with that said let's talk about how we exchange data on the web
3:41:59
um it's safe to say that if you're watching this video you know how to use a web browser
3:42:06
but under the hood the way it works every time we open up a browser and we type the url so the web address
3:42:13
we're actually performing a request and we are performing a request to the
3:42:20
server that is responsible serving those resources so for example
3:42:26
when you look for cnn.com you're looking for a server that has
3:42:31
those resources and then that server sends you back the response and the same
3:42:37
works with youtube the same works with johnsmeld.com or whatever so you just pick a resource
3:42:44
you say hey can i get this data and then server who is responsible for those resources just
3:42:51
sends you back the response now that is done using http protocol and that's why
3:42:58
these ones are called http messages so the user sends the http
3:43:04
request message and then the server sends the http response message
3:43:11
and that's how we exchange data on web and for the remainder of the course
3:43:17
we'll be responsible for building such web server using node and more
3:43:24
specifically express now i'll talk about it while we use express as well show you
3:43:30
a few examples later on in a course but for now just remember that yes we'll use node but in
3:43:37
order to make our lives easier we'll use the framework by the name of express js
3:43:44
and lastly i would just want to mention that even though name server definitely sounds way cooler than the computer
3:43:51
at the end of the day they're just computers whose job is to always make that resource
3:43:59
available so yes those are computers and yes there
3:44:04
are some differences for example they most likely don't have the graphical interface or the gui
3:44:11
and also they're probably much bigger than your laptop but at the end of the
3:44:16
day they are computers whose job is to always make sure that that
3:44:22
resource is available because imagine if you would have a server that only works
3:44:28
from eight to five so if you go to your website at i don't know six o'clock at
3:44:34
night you cannot access the resource probably that's not the service that you
3:44:39
would pick so next time when someone asks you if it rains does the cloud
3:44:46
still work you know what to answer because at the end of the day when we talk about cloud cloud is just a bunch
Http Messages
3:44:53
of these servers bunch of these computers connected together beautiful
3:44:58
and once we have a general understanding how data is exchanged on a web let's also cover how http messages are
3:45:06
structured please keep in mind that since it's going to be a big part of our
3:45:11
job we'll come back to this particular slide more than once so if you're if you're
3:45:16
about something just please be patient and i'll answer all of your questions as
3:45:22
we move along with the course with that said the general structure for both messages is similar they both
3:45:29
have a start line they both have optional headers a blank line that indicates that all the meta
3:45:36
info has been sent and effectively headers are that meta info as well as
3:45:43
optional body and before we continue again let me stress something so request
3:45:49
messages are what the user is sending so for example if you open up the browser to
3:45:57
search the web or that could be your web application because remember with web
3:46:02
applications we also can make http requests correct and then response
3:46:09
is going to be our responsibility so we'll have to set up a proper server
3:46:15
that sends a correct response and in general when we talk about the
3:46:21
request message in start line there's going to be a method
3:46:26
then the url as well as the http version now
3:46:32
we are mostly going to be interested in these two things in the method as well as the url now there's going to be a
3:46:39
separate slide about the methods as well and don't worry we'll cover that in a
3:46:45
greater detail once we cover them with actual code examples so i'll come back
3:46:51
to that slide just understand the general idea that when we talk about methods effectively we're communicating
3:46:58
what we would want to do so for example if i want to get the resource i'm going
3:47:04
to set it up as a get request now if i want to add the resource then of course
3:47:09
this is going to be a post request and then of course you can read the rest now
3:47:15
why i'm displaying here this get because that is the default request
3:47:20
that the browser performs since when we open up the browser we want to get some kind of resource
3:47:27
correct that's why we're performing a get request and the url is just the
3:47:33
address and that could be for example johnsmilk.com or that could be i don't know espn forward slash basketball both
3:47:42
of them are just a web addresses now headers is essentially optional
3:47:48
where this is a meta information about our request and just to give you a
3:47:54
general idea how the headers would look like they would look something like this so it is a key value pairs now don't
3:48:01
freak out as you know when you search the web you don't need to add them manually and the
3:48:07
same is going to be with our server a lot of it is going to be taken care of
3:48:12
but yes some things we'll have to add on our own basically this is going to be
3:48:18
information about our message and then we also have optional body
3:48:25
so when the user is requesting something if you just want the resource there is
3:48:30
nobody there's nothing basically what to send however if we would want to add a
3:48:36
resource onto the server yes then you are expected to provide that data and it's also called payload so
3:48:45
again i might use them interchangeably so that's the general structure of the
3:48:50
request message we have the start line we have the headers that is the information about
3:48:56
our message as well as the black line which just indicates that we're done with the meta information and optional
3:49:03
body which we'll use from time to time and now of course we need to talk about the response message so response message
3:49:11
is what we're going to be creating again most of it will be done for us but some
3:49:17
parts yes we'll have to do it manually and it's going to be our responsibility
3:49:22
so the start line has the http version which most likely is going to be 1.1
3:49:28
then we have a status code and status text now when it comes to status code
3:49:36
it just signals what is the result of the request so for example notice here this 200
3:49:43
that means that request was successful so that's what we're sending back and
3:49:49
yes there's quite a few of those codes and as we move along with the course of course we will cover them but please
3:49:56
please please don't rush over to the search engine and start memorizing the
3:50:02
status codes pretty much as we're going to be building the application i'll tell you which code means what and for
3:50:09
example 400 means that there was some kind of request error
3:50:14
so the user was trying to request some kind of research and with 400 there was
3:50:21
a request error now for example the code 404 means that the resource is not found
3:50:28
so when i'm sending back the message i'm like hey listen here's the status code
3:50:33
for the message if you are successful here's 200 if there was an error for example you get a 400 if the
3:50:42
request is unauthorized then you can get 401 and hopefully you get the gist and
3:50:47
yes of course as we're progressing we will cover more status code then again
3:50:53
we have the headers where basically we provide info
3:50:59
about our message our response message and again like i said you won't have to
3:51:06
type everything line by line but effectively it is a setup of key value pairs and the ones
3:51:13
that i would like to mention are these ones notice this content type we have text html that is when we're sending
3:51:20
back the html but also our second option is going to be sending back the data
3:51:28
so hopefully you are aware that when you're building a web application when we communicate with api most of the time
3:51:34
we're getting back the json data because over the web effectively we just send
3:51:40
over the string so if for example i have some kind of array we transfer this into
3:51:47
application json and i clearly indicate that in my headers where i say that no
3:51:52
i'm not sending text and html i'm actually sending a application json and
3:51:58
then that application who is requesting the web application knows that hey from the server i'm getting a content type
3:52:05
which is application json so for example in that case i could send back here this
3:52:12
array with bunch of these objects and just to give you a real-world taste why
3:52:19
don't we do this open up a new browser tab and i'm simply going to course api because i think
3:52:25
there's going to be less data so there's going to be less clutter so go to course
3:52:30
api here and then you can either pick the slides or you can just look at the home page and if you inspect
3:52:38
and if you look in the browser tab you'll find a network and very useful one is this one where we
3:52:45
can just look for all the requests we refresh and then check it out so these
3:52:50
are the requests that browser performed and i'll talk about it a bit later why there's also
3:52:56
this style css in fact that's going to be one of our first examples but take a look at this one so i have this course
3:53:04
api and then forward slash and if you remember when we were building our original server what i said that if we
3:53:11
have this forward slash that just means home page so if we're just navigating to courseapi.com
3:53:17
and that is our homepage we simply add this forward slash now of course in the
3:53:23
browser that's automatically added but that's why when we're setting up the server one of the cases is going to be
3:53:28
if the user navigates to the homepage then we simply look for forward slash so
3:53:34
if for example you go to the slides you'll notice that uh in this case i
3:53:40
would have to refresh notice here i have the course api forward slash slides so that is already
3:53:48
a page in my website correct so i have the home page course api and then i have
3:53:55
the slides page where i have the slides and if you take a look if you click on
3:54:01
it notice all the useful data that we get over here so for example this is
3:54:07
going to be our request url which is going to be again course api.com so that
3:54:12
tells me well what the browser is trying to get then check it out the method why it's
3:54:18
get because that is default in the browsers every time you open up the browser and search something then of
3:54:24
course you'll be performing a get request now check out this one the status code it is 200 why because
3:54:30
everything is successful because servers send back the data then we have this remote address and basically that is the
3:54:37
ip address for my server as well as notice this colon 443
3:54:43
and we'll come back to this one when we set up our own server because if you remember we were always setting up the
3:54:49
5000 so you're probably wondering well what is this 443 and don't worry again
3:54:54
we'll cover that one once we set up our first server and then again we have response headers
3:55:02
for example and we also have the request adders so as you can see using this
3:55:07
network tab we can actually find a bunch of useful information now
3:55:13
notice here in the second set of tabs i can see this response and preview so if
3:55:21
you take a look at the preview this is going to be basically my site and also i can see the response so as
3:55:28
you can see pretty much sending back the html so i'm sending back the website so you
3:55:34
go into the browser you request a resource by default it is a get request
3:55:40
and then in that body when the server sends it back this is what we get back so we get back
3:55:47
the site so hopefully this gives you a clear understanding of how the http
Starter Project Install
3:55:53
messages are structured and now let's dive into creating our own server
3:55:59
awesome once we're done with the slides now let's start setting up our server
3:56:05
and in order to follow along with the course you'll need to have a starter
3:56:10
project and you can get it if you navigate to my site again the url is
3:56:16
johnsmilk.com so navigate there in the project or in home page look for node express tutorial
3:56:24
project in a home page is going to be at the bottom in latest project if you cannot find it there then look for all
3:56:32
projects page or simply projects page then filter for node in order to save some time and then like i already
3:56:38
previously mentioned any of these links will get you to the repo and then
3:56:44
bravely get the repo in my case i'm going to clone it so i'll copy the url i'll bump up the sound size in my
3:56:52
terminal navigate to the desktop get clone here
3:56:57
and then i'm gonna get the repo and then once the project is on my machine
3:57:03
i'm just gonna drag and drop and then the first thing that i would suggest
3:57:08
doing is removing the remote url and you can simply do that by just wiping out
3:57:14
the git folder so that way if you ever do decide you push this up to the github
3:57:20
you won't have some dumb permission errors so i'm just going to open up the integrated terminal now in my case i'm
3:57:26
not going to run the command but if you're on mac i suggest running rm
3:57:32
then hyphen rf and then get now if you are on windows
3:57:38
some students have just these two commands now i haven't tested them yet but some people have replied to
3:57:45
my tweet that yes they do work and if you want to see the whole tweet just navigate to my twitter the handle is
3:57:52
john underscore smilga and then as you can see here is the mac command and for
3:57:57
windows i have these two so run this command and then in next video
Starter Overview
3:58:02
i'll give you a brief overview of the repo all right and before we get busy
3:58:09
why don't i give you a brief overview of the ripple and if you take a look at the first
3:58:16
project this should look very very familiar because essentially this is all
3:58:22
the code we have written so far everything starting with our most basic
3:58:27
application and then of course we also have our last one our http streams
3:58:34
example so hopefully that is clear and if you ever need to jog your memory
3:58:39
essentially this is just here for your reference and then from now on we'll work in a
3:58:44
folder number two by the name of express tutorial and the idea is gonna be exactly the
3:58:51
same where basically we build a bunch of examples and in the process we learned what is express and
3:58:59
why we would prefer using express instead of straight up http module but again let me stress something where
3:59:06
express is built on top of node and more specifically on top of http module so it's not like you
3:59:13
can use express without node and in folder two the setup is following
3:59:20
where there are gonna be some assets that i provided just so we can make more real world
3:59:27
examples so hopefully that gives you a better idea how the express works and
3:59:33
i'm not going to cover them right now for example methods public or navbar app once we get there i'll explain
3:59:39
everything that's happening i think that it's going to be waste of our time if i do that right now however if you take a
3:59:45
look at the final folder you'll basically see all our examples so the same spiel
3:59:52
if you ever need to reference the code just navigate to the final look for the file name and
4:00:00
then of course you'll find the code just keep in mind that in order to run this code you'll have to copy and paste
4:00:07
and run it in the app.js why because in some cases there's going to be paths and since these files are
4:00:14
located already in the final the paths won't match okay hopefully that one is clear as well
4:00:22
and then we also should be familiar with these files as you can see i have package.json i
4:00:30
have package.json lock and then app.js now of course app.js could be renamed
4:00:35
server or whatever you would want but i already have in a package.json a script
4:00:40
that spins up the nodemon and effectively we have successfully set up a node application so package.json is of
4:00:48
course needed because we'll have some dependencies more specifically two one
4:00:53
is going to be nodemod and the second one is going to be express and in order to of course keep track of
4:01:00
those dependencies we have package.json and then if you notice i
4:01:06
don't have the node modules here and of course the reason for that is because i don't want this repo to be massive and
4:01:13
you can clearly see that in a git ignore where i have node modules included so when i was pushing this up to the github
4:01:20
and of course i omitted the node modules since i added them in the git ignore and then in the
4:01:27
package json like i said you'll find some dependencies and i'll talk about express once we get there the
4:01:33
moment let's not worry about it the one that we should be familiar with is node one which is going to be watching our
4:01:39
application and i have a script that sets up nodemon
4:01:45
and passes in the amp.js so any changes in our project nodemon will be watching
4:01:50
and restarting our application however we cannot do anything before we install
4:01:57
all dependencies otherwise you'll just get an error so that's why the first thing that i would want you to do is
4:02:03
navigate to the folder number two and the fastest way probably is just
4:02:08
going to be cd and then take the project number two and drag and drop
4:02:14
like so and then once you can see that you are in this folder
4:02:19
so not in a root not in node express course but once you are actually in the
4:02:25
folder number two before you do anything just run npm install first and then it's really up to
4:02:32
you you can either wait for all the dependencies to be installed and then run npm start or you can simply chain it
4:02:39
and say npm and once you run this one then of course you'll install
4:02:45
dependencies and if you see in a terminal express tutorial that means
4:02:51
that everything is correct and you can continue with the videos if you don't see that then please troubleshoot
4:02:58
because none of the things that we're about to do next are going to make sense if you're not running the project number
4:03:04
two with all the dependencies more specifically nodemon and express
4:03:10
and lastly i just want to mention yes there's also this data.js and again this is one of the assets that i added that
4:03:17
we're going to use a little bit later so if you see express tutorial in a console and the reason why it's there because
4:03:24
that's the only line of code i have in my app.js that means that everything is correct and we can move on to our next
Http Basics
4:03:31
topic and why don't we start the express tutorial part by setting up
4:03:37
the server one more time with straight up http module and in a process let's struggle a little
4:03:44
bit let's see why we would want to use express e in the first place
4:03:50
so yes we'll build one more time server with http module however now of course
4:03:58
we'll dive deep into the topics that we kind of skipped over before
4:04:03
and in order to set up the server we know that we would need to require the module right so i'm going to come up
4:04:10
with some kind of variable and in my case that is going to be http and of course the name is not required you can
4:04:16
call this whatever you'd want but it is somewhat off a convention to call this hdp as far as the variable name then we
4:04:23
go with require and we just go with http again keep in mind
4:04:29
this comes built in node so you don't have to install it we didn't install when we ran npm installed
4:04:36
in last video we installed two other dependencies but this one is built in so we don't have to
4:04:42
do anything we just say require and it's always going to be available to us
4:04:47
then we need to set up the server and again convention is calling the server but you can call this box bunny and in
4:04:54
order to do that we go with http and then on this object we have a method by
4:05:00
the name of create server now this method takes a callback which is going to be
4:05:06
invoked every time the user hits our server and in this callback we
4:05:13
have two parameters and again we can call them whatever we would want so again common convention is just shorten
4:05:21
this up a little bit and call it request and res so rec and res and the first
4:05:27
parameter references the request object and second one is the response object
4:05:33
and at this point it should be clear why we have access to those two parameters
4:05:39
because in the http cycle we have request message
4:05:44
that is coming in every time user requests the resource and also we have
4:05:50
the response message right so that's what we need to send out so that's why in this function
4:05:56
that runs every time user hits the server we have access to rec
4:06:02
and res so that way we can find info about the incoming request because it makes a
4:06:08
total sense if we have access to that info i do want to know what is the method so
4:06:14
what the user is trying to do i do want to know what resource the user is trying to get
4:06:20
whether that is the contact page or about page and also i would want to know
4:06:25
whether i'm getting some data whether user is trying to add something
4:06:31
onto the server and as far as the response well in order to
4:06:36
serve the data i need to be extremely specific about what i'm sending so i need to explain to
4:06:43
the browser what is coming in hopefully that is clear and in here we can just go
4:06:49
with log and we'll say user hit the server and then we return the object
4:06:56
from this create server and on that object we have a method by the name of listen so in order for the server to
4:07:04
work we need to invoke listen and we need to be a bit more specific and we need to say well what port are we
4:07:10
listening for and you're probably wondering well what's up with this port what's up with this 5000 value
4:07:18
and the best explanation i can give you is this one imagine scenario where you
4:07:23
have some kind of issue with your bank what do you do or that could be a phone company it doesn't really matter but i'm
4:07:30
just going to give you a bank example what do you do you call the customer service and what is the first question
4:07:36
that they ask you they say please describe your issue
4:07:41
so we may better assist with your call and what do they do they give you options right so they say if you want to
4:07:48
increase your credit limit this is going to be option number one all the way to canceling the account which maybe is
4:07:54
going to be option number eight so they don't just randomly assist you a person
4:08:00
they say hey what is the issue and this is the person that can serve you the best so if you press 8
4:08:07
you can assume that you're probably going to be speaking with someone who deals with that all the time
4:08:12
and same goes here so if you go online and if you search for port this is just
4:08:18
going to be a communication endpoint and we need to understand that for http
4:08:24
traffic we have specific ports so for http we actually have port 80
4:08:32
because there's other ports as well if you keep on scrolling here and by the way this is wikipedia example we have
4:08:38
port 20 which is for file transfer protocol so this is going to be for data transfer then we have
4:08:45
port 22 for secure shell so http traffic
4:08:50
is only one of the things that we set up on a server and once our
4:08:57
application is in deployment we have specific ports for that we have 80
4:09:02
that is going to be for just http and we also have 443 which is going to be 40
4:09:08
secure communication that's why when you go to course api or any other
4:09:14
website that uses https you'll notice that there is a ip address and then more
4:09:21
specifically 443 and you can also think of this as a apartment building
4:09:27
so every apartment building has the same exact address right but the apartments
4:09:33
differ so the same works here so on that server if i want to access it using ssh so
4:09:40
secure shell i'm going to use port 22 but then if for example
4:09:47
i want to use http protocol and if i want to access resource that way then
4:09:52
i'm going to use port 443 so once your server is already in production yes
4:09:59
these ports are not random there are specific ports for specific things we would want to do again back to our bank
4:10:06
example if i want to cancel the account then i'm always going to be directed to that person because i'm going to click
4:10:13
option number eight if i want to increase the limit then of course i'm going to be directed to a different
4:10:19
person now while we're in development this is really arbitrary
4:10:24
i can go here with five thousand i can go here with three thousand eight thousand wherever you would want i
4:10:30
believe the ports between zero and thousand twenty four are already taken so you shouldn't be
4:10:36
using them but in local development again this is an arbitrary number and that's why you can use anything you
4:10:43
would want and again the most common example create react app where we spin up the server on
4:10:51
localhost 3000 then gatsby has i believe eight thousand and then netlify cli has
4:10:58
8080 and i can go on and on and on so in my case i just went with 5000 but if you
4:11:04
don't like this number just use a different port but of course please
4:11:09
remember the actual value for the port because you'll need it once you need to
4:11:14
access now if you're wondering well what happens once we deploy our application
4:11:21
just put the pin on that and once we get to deployment of course i'm going to
4:11:26
cover how actually we set it up that we serve that traffic on the
4:11:32
port 80 for example for http or 443 for https
4:11:38
and now of course we can go and test it out so let me navigate to my browser
4:11:44
and i'm just going to go with localhost and eight thousand and or i'm sorry i
4:11:50
just said five thousand and for some reason i went to eight which is gonna be the gatsby one and you'll see this
4:11:56
interesting spinner so what's happening over here well the thing is yeah the user hit the server as
4:12:04
you can see user hit the server that is what i see in the terminal however
4:12:09
remember we have the response right so we have access to the response object and now we
4:12:15
need to send back some info to the browser otherwise the browser is like okay
4:12:20
so i hit this resource but nothing is happening and there's a method that we always
4:12:26
always need to include in our response and the method name is
4:12:31
and and i right away went to node docs of course again if you want to navigate there yourself please do so but i
4:12:38
already right away went for response dot end and as you can see this method signals to the server that all the
4:12:45
response headers and body have been sent and as a side note we'll do the headers in the next video because this one is
4:12:51
already getting quite long that server should consider this message complete the method response and
4:12:58
must be called on each response so for the browser not to be confused we
4:13:05
need to go with res that end so res dot and that is one of the methods that is
4:13:11
available on this response object and here we can either pass the text or we
4:13:17
can set up for example html and in this case i'm just going to say home page
4:13:23
that's it i'll just pass in the string and if we were to go back to localhost
4:13:28
5000 there it is now we have our homepage response and we can clearly see
4:13:35
that in our terminal because every time you refresh the browser you'll have this console log in a terminal user hit the
4:13:43
service hopefully everything is clear again we have access to http module and that is
4:13:49
built in node and we just set it up some kind of variable most common convention
4:13:54
is calling this http then on there we have create server method that takes in
4:14:01
the callback which is going to be invoked every time the user hits the server and as parameters we have a
4:14:08
request and response object and common convention is just calling the american res now of
4:14:14
course you can call this stockhold burrito if you want but again common convention is calling this iraq and res
4:14:21
and the reason why we have access to those objects is because in the http cycle
4:14:27
that's what happens we have a request message that is coming in where we can find a bunch of useful info about the
4:14:34
request that is coming in and then of course we need to respond to the browser
4:14:40
in a meaningful manner so that's why we also have the response object and in
4:14:46
every response we should always have end which is going to signal that the communication is over and then we just
4:14:54
need to set up the port and again in development we just come up with arbitrary numbers and in my case we go
4:15:01
with 5000 and we pass in that port in the dot listen method which is
4:15:07
available when we invoke create server because we get back the object hopefully the basics are clear and now we can
Http - Headers
4:15:13
start expanding on our knowledge all right we're done with the basics but there are two major issues with our
4:15:20
current setup first of all we don't provide any info about the data that
4:15:26
we're sending back so we don't have any metadata about the body that we're sending out so we're not
4:15:34
providing any information we just go rest that end and then pass in the string so that's issue number one and
4:15:40
then issue number two if i were to go to the local host 5000 and if i type
4:15:48
about or if i type contact or whatever you'll see that of course we're sending back
4:15:54
the same response each and every time so if we go with contact again this is
4:15:59
going to be a home page so why don't we deal with issue number one first where we provide more info to the
4:16:07
browser of what we're actually sending back and then in the next video we'll deal
4:16:13
with the request and the way we provide more info we just
4:16:18
need to add more methods now specifically one more method and that is going to be res dot
4:16:26
write head and in there you can probably already guess that we're just providing headers
4:16:32
so we're providing metadata about our response and we go here with res dot
4:16:38
and then we go with right head so right head and then we need to
4:16:44
provide a few things we start with a status code and i'll talk about the status code in a second and for time
4:16:51
being i'll just pass in 200 which just means that the request was successful
4:16:56
and then we pass in the headers and one of the most common headers is
4:17:02
the content type so this is where i specifically say to the browser hey listen i'm sending back
4:17:07
html or i'm sending back css so where i'm sending back the image so browser
4:17:12
knows well what to do how to render that content and like i mentioned already
4:17:18
previously this is done using key value pairs so we go with content type so
4:17:24
that's the name of the header and then we pass in text and then if for example i want to pass
4:17:31
in the html i go with text forward slash and then html and now of
4:17:37
course in this case where i have the res.end i can set up the html so for
4:17:42
example i could go with heading 1 and i'll say homepage same deal home page now if you
4:17:51
want you can keep it this way where you have res that end and you directly pass
4:17:57
in the html however i like to use better this approach where i go with res dot
4:18:03
write and we do the same thing we pass in essentially the body and i set up my
4:18:09
html here in the right or any content that i'm sending back and then
4:18:14
explicitly call res.n again if you want you can pass this heading 1 into the end
4:18:21
just make sure that you have the end and you saw that in a docs where it says if data is specified in a similar effect to
4:18:28
calling response.write and then we pass in the data followed by res.n but you
4:18:34
always always need to call res.n so this is really up to you if you want you can pass this directly into res.n
4:18:41
i like to write it a bit explicitly where i say res.right so that is my body
4:18:47
and then i just end the communication by calling res.n and now of course
4:18:54
if i go back to the browser again i'll still have the same issue where it's going to be displayed for every request
4:19:02
meaning either contact page homepage or whatever but now i provide way more
4:19:08
useful info to the browser where browser knows hey i'm getting back the html so
4:19:14
i'll need to render html and this stuff matters so let me show you if i change the content type back
4:19:22
for example to plain and if i save and if you refresh now
4:19:27
notice this is now treated as a text it's not treated as html so whatever you
4:19:34
set up over here in the content type yes it does matter now express takes care of
4:19:40
that so we won't have to do that but i just want to let you know that if you will be setting up the headers yourself
4:19:46
yes the stuff that you type here matters and as the note it is also called mime type or you can think of it as media
4:19:54
type so whatever we're sending back and now let's go over the status codes as
4:20:00
well as other options for mime types and this is where i would like to introduce
4:20:06
an awesome resource for anything http related and that is going to be no other
4:20:11
than the mozilla docs so if you go to http and status codes you'll see
4:20:18
probably the first link is going to be to the mdn and as you can see http response status
4:20:23
codes indicate whether specific http request has been successfully completed
4:20:30
and like i mentioned before there are quite a few groups over here and there are quite a few codes but i would
4:20:36
strongly discourage you from spending your weekend on memorizing the codes as we're going to be progressing with the
4:20:42
course as we're going to be creating more complex applications of course we'll introduce more and more status
4:20:49
codes but the main idea is following where when we send back the response
4:20:55
i'm just saying is it successful maybe the resource wasn't available so
4:21:01
then i sent back 404 or maybe there was a bad request that's why there's also
4:21:06
option 400 and hopefully you get an idea where we are setting up that status code
4:21:12
so the browser knows what is happening with the request was it successful
4:21:18
was there an error maybe i don't know you're not authorized to access it and on and on and on and if you keep on
4:21:27
scrolling notice so the 100 ones are going to be informational responses then
4:21:32
for successful one we have 200 so that probably is going to be the one that you'll use the most so that means
4:21:39
that request has succeeded then we have 201 also something that we'll use
4:21:44
throughout the course a lot and this one is once the post request is successful so
4:21:51
if you add the resource successfully onto the server then you just send back to one
4:21:56
we have 300s for redirect and then these are the ones that you probably don't
4:22:02
want to get if you are surfing the web so 400 is for bad requests
4:22:08
so for example you are requesting some kind of data or you're trying to do something on the server but you don't
4:22:14
provide the info so i don't know i'm trying to add the user but i don't provide the username
4:22:21
something along those lines then 401 is for unauthorized then 403 forbidden and
4:22:27
404 not found so in our case we'll set up a response if the user is trying to
4:22:33
access the resource that does not exist so hopefully it is clear that is the
4:22:40
status code again i wouldn't suggest memorizing it as we are moving along with the course of
4:22:47
course we'll cover more status codes just understand the main idea where you attach that status code to let
4:22:54
the browser know hey what's happening and it is very important that you use
4:23:00
the correct status codes because we are in charge here nothing stops me from sending back the 404 here meaning
4:23:08
the resource is not found and then when you navigate to the contact page for example
4:23:15
here and if you inspect again the browser network tab you'll see this
4:23:20
confusion info where 404 is technically not found
4:23:25
right but at the same time we are sending back the correct resource so yes
4:23:31
whatever we type as far as the status code it does matter it's not just some random info and that just reflects what
4:23:38
is happening with the request and then lastly let's talk about mime types same
4:23:44
deal just go to your favorite search engine and just type mime
4:23:49
and types and again i suggest using the mdn and these are just going to be media
4:23:55
types so whatever we're sending back there's quite a few out there now again
4:24:01
express takes care of that so we don't need to worry about it but
4:24:06
if you ever need to set it up i don't suggest memorizing them the ones that you'll need to use
4:24:12
you'll pretty much be able to google it right away you can also use the npm packages so no you don't need to go and
4:24:20
memorize them again just remember the main idea where you're sending back
4:24:26
something right and you need to describe to the browser well what are you sending
4:24:31
back are you sending back the image are you sending back css are you sending back the html and as you saw in a previous
4:24:39
example if you change that mime type if you change that content type header yes the
4:24:45
browser will interpret that differently and once we successfully have set up
Http - Request Object
4:24:51
more proper response now let's start dealing with the request object
4:24:57
beautiful and with our basic headers in place now let's deal with the request
4:25:03
object and like i already previously mentioned it's just a giant object and if of
4:25:09
course we can slog it then we'll see it in a terminal so i'm going to go back to my localhost 5000
4:25:16
and as i said note this is getting quite busy so i can just remove some of the
4:25:21
tabs and if i just refresh the browser i should see in a terminal a giant object
4:25:29
so what are we looking for well let's go back to our slide and remember the start line
4:25:36
we had a method so that signals what the user is trying to do either get the resource post a
4:25:42
resource or whatever and then we have the url now in order to save us a little bit of
4:25:47
time i won't cover the methods with http we'll just deal with the url but we will
4:25:55
cover of course methods once we hit the express for now i'm just going to assume
4:26:00
that the only thing that the users are trying to do they just want to get the resources from our server so that's why
4:26:08
we won't look for the method just keep in mind that yes of course those methods are available on this request object
4:26:15
there is a property by the name of i believe it was just simply a method so if we cancel log
4:26:22
and if i refresh notice here in a terminal it says get
4:26:28
so the user is performing a get request so the user is trying to get the
4:26:34
resource so that's one thing that we could take a look at and the other one is actually the url so let me uncomment
4:26:41
this one and i'm looking for the url property and again i refresh and now in the
4:26:47
console i should have this forward slash contact so that just means that the user is trying to access the
4:26:55
resource by the name of contact and if of course the resource is there awesome
4:27:01
we send something back if not then most likely would send back the 404 now if i
4:27:06
delete that contact and if i simply go with 5000 notice i'm going to have the forward slash so again this just signals
4:27:14
that we're getting the home page so forward slash is going to be the home page and then whatever other resource we
4:27:21
would want we would have port slash and then the resource now sometimes those resources are going to be forward slash
4:27:27
resource name and then another forward slash and another resource name and on and on and on you can really type here
4:27:34
whatever you want so again i go with localhost about and then info and i
4:27:39
don't know something john right so i can add that here and there it is now i'm requesting this resource and if it's not
4:27:47
there we send back 404 if it's there then of course we send back the useful info
4:27:53
so hopefully that is clear yes this will just mean that it is a homepage and whatever comes after the homepage well
4:28:00
that's the resource that the user is trying to access and now of course we can set up the if statement whereas say
4:28:07
yes if it is a home page please send back this html if it is about page then send
4:28:14
something else and then if i cannot find that resource that you're looking for then we'll send back 404.
4:28:22
now there's going to be a little bit of copy and pasting just so we can save a little bit of time we're just going to
4:28:28
go with if and actually we can set this up as a property so let's go to const url is equal to request url and then
4:28:37
we'll say if url is equal to forward slash what does that mean well that means that it is a homepage so let's
4:28:44
grab these three lines of code and move them up and now of course i want to set up else if
4:28:51
now i'll just set up one for the about page so if url is equal to about page
4:28:58
then we'll do something else and if none of those match well then i'll just
4:29:04
say else and i'll send back 404 now i will
4:29:09
add some comments here just so we are clear on what is happening so
4:29:14
this is going to be about page then this is going to be called home page
4:29:19
home page and then we're going to have the 404 so resource not found
4:29:26
so again in order to save us a little bit of time let's just copy and paste one and two and again content type will
4:29:33
be exactly the same so that is going to be html because we'll send back the html
4:29:38
i'll say about and i don't know page let's call that and then last one is going to be the 404
4:29:45
so in here of course we're not going to send back 200. 200 is for successful
4:29:51
request now of course i want to say hey listen the resource that you're trying to
4:29:56
access well it doesn't exist on my server so here i go with 404 and again i
4:30:03
go with the same content type text html and then let's just send back the
4:30:09
heading 1 with page not found so save this one
4:30:15
and now of course once i refresh check it out i get this page not found why well because there is no resource
4:30:21
forward slash about info and john but if i go to just about
4:30:27
there it is now of course i have my about page and then if i go back to the
4:30:32
homepage of course i have heading 1 with a home page now we optionally if we want
4:30:39
we can add the status text as well and in order
4:30:45
to see that let's just go back to the node docs so this is going to be the http
4:30:50
and of course i'm looking for right head and we have a right head here notice we
4:30:57
have status code optionally we can pass in status message and then we have the
4:31:02
headers so again let's go back to our slide this is the most important one status
4:31:07
code and then the status text essentially is just going to be added in this case we don't need to do anything
4:31:14
because again if we were to go back to the browser network tab
4:31:20
and if we take a look at our localhost there is first of all this is forward slash that just means that we're going
4:31:26
to the homepage and the status code is 200 and then we have this status text
4:31:32
now again if i navigate to a page that doesn't exist for example john then of
4:31:37
course i'm going to get the 404 so that's the status code and then the status text is not found
4:31:45
so hopefully it is clear now we have a bit more meaningful server where we have
4:31:53
multiple resources we have home page we have the about page and also we have the error page and with
Http - Html File
4:32:00
this in place now of course we can start working on more complex setup
4:32:06
nice and with our most basic example in place now i'm going to start throwing
4:32:11
mine grenades at you first of all i want to let you know that of course we're not limited to passing in the html directly
4:32:20
into the dot right or that end meaning imagine if you would have to every time
4:32:28
just set it up or your html in methods directly of course what we can do
4:32:33
instead is set up the file then require the file using the file system and then just pass it in now keep
4:32:41
in mind one thing though where we will be passing in the contents of the file not the file itself
4:32:49
and that's very important we'll be passing in the contents of the file so that means we still need to use this
4:32:54
content type just because we're going to be getting the data from the html file
4:32:59
doesn't really mean anything yes it's nice it's going to make our lives easier if you want to set up a
4:33:06
more meaningful web page but we still need to set up the content type now this
4:33:11
is going to be a temporary file because in the next video we'll cover a more
4:33:18
serious example and i already prepared all the files for you so this is where
4:33:23
we'll really struggle and this is where i'll show you why we use the express but
4:33:29
for now if you want to follow along just create a simple index html or about html doesn't really
4:33:36
matter how you call the file in the folder again this is really optional i'm going to go with new file
4:33:43
and i'm gonna call this index html and again the whole reason why i'm doing that because i wanna set up a more
4:33:50
proper page and i don't wanna type everything here in the right or end i
4:33:56
mean it's much more nicer here right so i'm just going to go with emma setup in visual studio code i get my basics and i
4:34:03
can say home page home page and then i'm just going to go with a
4:34:08
heading 4 of hello world again this is just a showcase that sky is the limit
4:34:14
just like you normally would set up to html you can do exactly the same thing and then i'm going to go back to app.js
4:34:22
and first of all i'm going to get the read file so i'm gonna go with const and then read file and sync and i'm gonna
4:34:29
talk about why i'm using this thing in a second so don't freak out i know i mentioned before that we need to be
4:34:35
mindful of the methods that we use that there is a difference between the
4:34:41
blocking and non-blocking and i'm just going to go with fs over here and we need to come up with some kind of
4:34:48
name and again in the next video there's going to be more data here so that's why i'll say
4:34:54
get all files for time being in this video i'll just get one and i'm going to call this home
4:34:59
page again call it whatever you would want you can call this bobby lee doesn't really
4:35:04
matter it's just a variable and we're going to go with read file and sync and of course where's the file it is in the
4:35:11
same folder so we go with relative path and i'm just going to call this index html now again we're getting the
4:35:18
contents now why i'm using here they read file sync well there's two reasons first of all we
4:35:25
need to keep in mind that we're not invoking this every time someone comes to the server
4:35:31
please keep in mind that we require that file when we instantiate our server
4:35:38
so basically that initial time when the server starts running so it's
4:35:43
not like when the request comes in then again every time we're requesting the file yes of course if i were to place
4:35:51
this in the if block yeah that's a different scenario meaning if i were to even place this in a create server again
4:35:57
same scenario but not in here again we're just requesting this once that's the first reason why i went with that
4:36:04
and second it's just an example so i want to make my life a little bit easier what i want to focus on is something
4:36:09
else with this home page in place now of course what i would want is to go back
4:36:15
to my if where i'm checking for the homepage and instead of going with res.right and then typing it out i'm
4:36:22
just going to go with our content now again we're still keeping this one the text.html and i'll show you in a second
4:36:28
what happens if we change it to a text plane and now we go with a homepage
4:36:34
and now be prepared to be amazed because if i go to not john
4:36:39
my resource of course doesn't exist there it is check it out we have home page as well as the hello world
4:36:46
so we can start making some meaningful html pages and we can serve them with
4:36:53
our awesome server and just to re-emphasize my point
4:36:58
if we change this to a plane and save and refresh now of course we're getting a text so
4:37:05
yes it is very important of what content type we are setting up so let's go back to html and now of
4:37:12
course we are in good shape awesome we have our homepage and now of course i
4:37:18
can go to index.html and go wild and crazy
Http - App Example
4:37:23
with my page setup not bad not bad now we know that we can access the contents of the file directly
4:37:31
so of course we can set up proper pages but now let me throw you a mine grenade
4:37:39
where we'll have to add way more code here if we want to really serve some
4:37:46
meaningful web page and the example is going to be following if you navigate to navbar app so that's
4:37:53
the folder you'll find index.html you'll find style css logo svg as well
4:37:59
as browser hyphen app.js and i simply call this browser app file so you're not
4:38:04
confused between the two so this is going to be for our server and this is our browser app and effectively this is
4:38:12
a complete app that we set up i believe in my javascript course when we were
4:38:18
building projects so effectively this is a little navbar with a toggle
4:38:24
functionality and let me assure you something right from the get go the app works
4:38:30
so if you get any issues along the way it's because the node is not working
4:38:35
the app itself is going to work and i can simply showcase that if i go to navbar app and i'm going to copy that
4:38:41
one and i'll place it on my desktop and then if you spin up the index html
4:38:49
i can guarantee you that this is going to work there it is that's my application
4:38:55
and i can make it smaller and there it is now i'm toggling again our goal is following
4:39:00
i want to take this project index.html with style css logo as well as the
4:39:08
javascript file so the html structure the styling the logo that you can see over
4:39:15
here as well as the logic i want to take all of it and serve it on my server
4:39:20
and i know that the app works so all that is good so let's see what struggles
4:39:27
we're going to have along the way so here i have the home page right and instead of getting it from the
4:39:33
index.html which by the way i'm going to delete because again this was just temporary now of course i would want to
4:39:38
access this one from the navbar app that's the folder name right and then i'm looking for the
4:39:45
index html and i simply just need to change my path where instead of getting
4:39:50
it index html from the root which doesn't exist anymore i'm going to go to
4:39:55
navbar hyphen app and then of course i still get the homepage
4:40:01
and as you can see i'm still serving also the contents from that index.html
4:40:07
the only thing i did is just change the path that's it and technically we should see exactly
4:40:14
the same right but here's the kicker we navigate here and if i refresh
4:40:21
what is happening i don't have the logo i don't have the button
4:40:26
i mean i do have the button but it doesn't do anything and i can see only the structure
4:40:32
and we have quite a few 404s here and actually to give you a good idea why
4:40:39
is this happening i want to navigate back to our project and let's just console log
4:40:45
the urls and i think this is going to give you a clear message why this is happening so
4:40:52
let me go back and i'm just going to refresh one more time and check it out so we're requesting the
4:40:59
homepage so that makes sense right so i come here i request the home page and i serve this html file
4:41:07
from the navbar app and then i have three more requests i have one for styles one for browser
4:41:13
and one for logo now why is that happening well because in my index html
4:41:19
if you check it out of course i do reference the style css because i want to add the styling right
4:41:25
i do reference the logo because the logo is right here in my folder
4:41:30
and also of course i do have the one for the app right the one where i have my
4:41:36
logic so this is what happens we send back the initial
4:41:42
html content and the browser starts reading the content and every time we have basically a path
4:41:49
to our server browser is like hey server give me this resource so give me style
4:41:54
css give me logo svg as well as whatever we have here the browser app right so
4:42:01
keep in mind that these ones are for icons and actually they are external so this
4:42:07
one goes to phantasm that's a little bit different scenario yes the browser still performs this request but of course this
4:42:14
is external resource now these ones are on our server but the problem is following
4:42:20
are we handling these requests in our create server and of course the answer is no we handle
4:42:28
forward slash we handle about and then for everything else we have this 404
4:42:34
so to answer your question yes now manually we'll have to request
4:42:41
all the files so lower svg style css as well as the browser app
4:42:47
assign them to some kind of variable and set up these paths again this is just an example if you don't want to follow
4:42:53
along if you just want to see how it's going to work just sit back and relax
4:42:59
but in my case i'm going to request all these resources here
4:43:04
and then set up more else if statements where if the browser wants to get the
4:43:10
css then of course we'll search css if the browser wants to have logo then of course the browser is going to get local
4:43:18
and again if you take a look here in the elements you'll again see exactly why
4:43:23
because we have our html structure and then there it is we have style css so
4:43:29
notice how browser is going to http localhost 5000 forward slash what well
4:43:35
style css right well do we have that path and again the answer is no so let's
4:43:42
do this way i'm going to copy and paste and i'm just going to come up with different names here i'm going to say
4:43:48
home styles and then the third one i guess is going to be home image
4:43:54
and then the fourth one will be home logic so that is going to be my app one
4:43:59
then we'll have to change some files here as well so i'm looking for styles css i believe right
4:44:06
that's the file name then i have logo svg that's where my logo is sitting so logo
4:44:14
svg and then finally let's just delete this one as well and call this browser
4:44:21
hyphen app and js so home styles home image and logic and like i said yes manually one
4:44:28
by one we'll have to add all these resources so instead of about page
4:44:34
i'll just call this styles and the value that i want to check for here is exactly
4:44:39
the same like in my browser so they need to match so then of course the browser
4:44:44
will get the contents of the css file in this example so i'm going to go with styles and then css
4:44:53
now i do want to change right now the content type because am i sending back the html of course the answer is no
4:45:00
we're sending back the css so we go text css now let me say this one more time please don't zero in on these mime types
4:45:08
if you will ever need them you'll be able to find them within a matter of seconds just
4:45:14
type along with me and we're going to be in good shape now as far as the right
4:45:20
in our body so in our response that we're sending back are we going to send back html of course the answer is no now
4:45:27
of course i want to send the styles right and the variable for that is home styles so that's where
4:45:34
my content is for the styles css and once i save check it out
4:45:41
now we are moving along in the right direction because i do have the styles
4:45:46
so it looks already somewhat decent now the logo is still missing and there's no
4:45:52
logic because i don't have the app.js or the logo svg but we are moving in the
4:45:59
right direction so copy and paste and you can probably already guess that we'll just repeat over here we'll say if
4:46:07
the url is equal to logo svg and i'll say image logo as far as the comment
4:46:14
and we're just going to go with logo and 3g and as far as the mime type for
4:46:19
this sucker it is image image forward slash svg and plus
4:46:26
xml like so and let's go with home and i believe i named this home and
4:46:34
image like so and then the last one of course is going to be our javascript so
4:46:40
let's say here logic and the resource that i would want to provide is browser app
4:46:46
js like so and then the content type is equal to text
4:46:54
and then javascript and of course now i would want to send
4:46:59
the home and logic so let's save this one and now if i go to my browser
4:47:06
and if i refresh check it out now of course we have everything we have the logo as well as
4:47:14
the proper functionality with browser app and notice how
4:47:19
all our requests are 200 instead of 404 where the previously browser wasn't able
4:47:26
to find those resources and now of course we are providing them and if we want to test out the functionality there
4:47:32
it is now i can just go here and notice how i can toggle the menu as well and now of
4:47:39
course we'll switch gears and start working with express because hopefully it's clear that yes we can
4:47:46
set up our server with just http module but imagine a scenario where you have a
4:47:54
website with tons of resources and then of course you need to set up every single resource in this matter now
4:48:01
i don't know about you but i would go nuts somewhat quickly
Express Info
4:48:07
all right and once we have struggled a bit now let's make our lives easier by
4:48:12
getting to know express js express is a minimal and flexible
4:48:17
node.js web app framework designed to make developing websites web apps and apis
4:48:25
much faster and easier if i have to be honest it's almost unfair how easy and
4:48:31
fast it is to spin up the api with the help of express
4:48:36
and while it's not officially part of node meaning unlike http module express
4:48:41
is not one of the built-in modules at this point in time express is pretty much a standard when creating web
4:48:48
applications with node.js express has awesome documentation which we will
4:48:54
reference from time to time and you can find the docs at expressjs.com again the site is expressjs.com
4:49:03
and as far as the install you simply need to run the command of npm install
4:49:09
and the package name is express now they do suggest this hyphen hyphen
4:49:15
save flag and effectively the reason why they do that is because in the earlier node
4:49:21
versions if you did not add this flag then package wasn't saved to the package
4:49:27
json meaning when you push this up to the github the next person who was getting your project well he or she
4:49:34
did not have the reference for the package so of course that caused the errors now currently that issue is fixed
4:49:42
so this is just a good precaution but technically you shouldn't have any issues if you don't run the command
4:49:48
again nothing bad is going to happen if you add this dash save but technically
4:49:53
these days you can skip it so just grab the command like so
4:49:58
and just navigate back to the project just keep in mind that of course i already installed the express
4:50:05
for the express tutorial this is just for your own project if you want to install the express if you set up your
4:50:12
own package.json and all that if you want to install the express just run this command now one thing that i would
4:50:18
like to mention though is that i'm using version 4.17
4:50:24
so maybe by the time you're watching this they already have a version 5. now at
4:50:30
the moment version 5 is in alpha meaning they're still testing everything but maybe by the time you're watching this
4:50:36
this is already stable now if that is the case when you run npm install on
4:50:42
express of course you'll get the latest version so your version is not going to
4:50:48
be this 4.17 now i wouldn't worry if it's for example four point i don't know
4:50:53
24 but if it's five there might be some breaking changes and at that point you
4:50:59
have two options if that is the case if the version is already five then you can
4:51:04
either reference the api docs for yourself meaning you can take a look at the
4:51:10
methods and all that what the version five provides or
4:51:15
if you want to use all the methods and properties that we use in tutorial simply install the same
4:51:22
version how you can do that well you just need to go to npm install express so this stays the same and again
4:51:30
you can remove it you can leave the dash dash save doesn't really matter and after express you go with add and four
4:51:38
and then again i'm gonna go with the same one just keep in mind as long as you have four you're not gonna have any
4:51:43
issues and then one so this is going to install express with this specific version hopefully
Express Basics
4:51:51
everything is clear and now let's get to know express all right and once we have covered the express library basics now
4:51:59
of course let's spin the sucker up and see how we can make a server
4:52:04
way easier and with way less headache and i'm going to start by removing all
4:52:10
the code in my app.js just keep in mind that if you ever need a reference
4:52:16
go to the final one and then of course http basics is going to be where we set up the basic http server and then for
4:52:24
example the http app example is going to be in the file number two
4:52:31
and the way we work with express we start by setting up some kind of variable and of course we'll have to use
4:52:38
the require so we go with require and then we're looking for express library again we can do that because we have
4:52:46
installed the library but if you haven't then of course you'll get the error keep that in mind and then
4:52:52
we go with const and then app is equal to express to whatever we imported and
4:52:58
then we invoke it now if you're a bit iffy about this syntax
4:53:04
just keep in mind that it is very similar to our previous example where we
4:53:09
went with http then created the server and as a result we had our
4:53:17
server instance correct so this is similar we're getting a function back from express and we just invoke it and
4:53:24
we right away have our server instance with bunch of cool methods now what
4:53:30
you'll also see on a web is something like this where since this is a function we can invoke
4:53:36
it right away and then just call this one app again this is really your preference but
4:53:43
mostly you'll see the first option where we first import the module and only then
4:53:50
we invoke it so once we have this setup then of course we have a object with bunch of
4:53:57
useful methods now the methods that we'll use the most are following amp.get and i'll just copy
4:54:04
and paste here and i'll just change it around a little bit post and put
4:54:10
as well as delete and also there's going to be all
4:54:16
use and a listen now listen we already covered before in the http
4:54:24
module and this one is pretty much the same where we just go with app.listen and then we just say what
4:54:31
port we're going to be listening on so in this case of course this is going to be 5000 and then we pass in the callback
4:54:37
function so when we instantiate that server we will run this function and a
4:54:43
common convention is just setting up a console log where we say that yeah the
4:54:49
server is listening on port such and such now for time being we're hard coding this value later i'll show you
4:54:55
how we can make this one dynamic so for now i'll just say console log and then server
4:55:02
is listening on port and then we go 5 000. so let's
4:55:09
save this one and i'll run my npm start and i should see in a console server is
4:55:15
running or listening on port 5000 awesome so what about the other methods
4:55:22
and the first four methods here just represent http verbs
4:55:27
now if you remember when we talked about the http request
4:55:33
and response messages well one of the things that we're looking for in the request message was
4:55:41
the http verb and yes i set up some more meaningful examples
4:55:46
where we'll see all of them in action for now just remember two things first
4:55:53
this just represents what the user is trying to do whether read the data insert data update
4:56:00
data or delete data and by default all browsers perform
4:56:05
a get request so that's why we have here amp.get that post put and delete now all
4:56:13
just works with all of them and we'll see that in a second when we set up the 404 page so essentially a response if we
4:56:22
cannot find the resource on a server and app.use is responsible for middleware
4:56:28
and since it's such a crucial part of express of course i prepared more
4:56:33
examples on that where we cover everything from the scratch so for now just remember this is middleware but
4:56:41
don't lose your sleep over it we'll cover it a little bit later in the course so we have app.listen beautiful
4:56:48
we're listening on port 5000 but since i know that all the browsers are performing a get request i simply go
4:56:55
with app dot get and then i need to specifically add two things a path so what resource the user
4:57:03
is trying to access and it would make sense if we would start with root
4:57:08
correct and then the second thing is the callback function so this callback function will be invoked every
4:57:16
time user is performing a get request on our route so basically on our domain
4:57:25
and then this callback function gets the same two arguments we go with request
4:57:31
as well as the response so this is going to deal with incoming request message
4:57:36
and then this is going to deal with our response and in express we go with res
4:57:43
and then the method name is send so in here we can pass the string we can pass in the html and i'm just going to simply
4:57:50
start with home and page so we save this one and now of course i'm going to navigate
4:57:56
to my browser i'm going to say localhost and then 5000 and there it is now we
4:58:04
should have homepage if you don't again please troubleshoot because otherwise it's not
4:58:09
going to make sense what we are about to do next but if you see the home page you are in good shape
4:58:16
so we're listening for get request on our route and then every time the user
4:58:23
navigates to the root then of course we just send back the homepage now if you want you can of course go to log
4:58:30
and user hit the resource or something like that doesn't really matter and then if you go
4:58:37
back to the browser and if you refresh there it is we have user hit the resource awesome
4:58:43
and just like in our previous example the basics one let's set up the about
4:58:49
page as well as the 404 so i'm going to go back to my app js
4:58:54
and right above the app that listen i'm going to go with another app that get
4:59:00
and in this case i'm looking for about so that's the resource and of course in
4:59:06
here again we have rec and res and then as far as the response well
4:59:12
i'll cheat a little bit and i'll just say res.send and we're going to go with about page
4:59:18
and then of course i would want to handle the 404 as well so if the user
4:59:25
comes to my server and tries to access a resource that doesn't exist well what am i going to send back
4:59:31
and we can take a look at the default one so if i'm going to go with about i should
4:59:37
see the about page but if i go with for example a contact page let's see what
4:59:43
the express is doing and in this case i have cannot get the contact and if i
4:59:48
inspect i can clearly see that in my network tab i have contact
4:59:54
and this is a404 so that's going to be the default response now i can alter this of course and i can set
5:00:02
up my own 404 response so i'm going to go with app and this is the case where
5:00:07
i'm going to use all methods because again user can do multiple things on a server
5:00:13
and i want to cover them all not just getting the resource or inserting the resource or whatever i
5:00:19
want to cover them all so that's why i'm going to use my own method again this just handles all http verbs whether get
5:00:28
post or whatever and again this method takes two arguments first one is going
5:00:34
to be the path and the second one is going to be a callback function and as far as the path i can say all of them
5:00:41
so whatever resource you're trying to access the response is going to be exactly the same if i cannot find the
5:00:47
resource then i'll just send back this response so again i have a callback function rec
5:00:53
and res in here and then we're going to go with res dot send and just like in
5:00:59
our http example i'm gonna go with heading one and we'll say resource
5:01:06
not found and let's close the heading one but of course i also would want to add the
5:01:12
status right so that would make sense i don't want to send back 200. that would
5:01:17
be very confusing so before we invoke send method i can also add status here and as you can see
5:01:25
i can chain it so i have res not status so this is where i'll pass in my status
5:01:30
code and then i go with send so in our not found example of course i would want
5:01:37
to pass in the status code of 404 that is going to be more correct and the same
5:01:42
goes here technically we can rely on express and it does a decent job of adding those
5:01:49
status codes but a more common approach is explicitly setting up the status code
5:01:55
so that way you have more control of what is sent back to the browser so in here i go with res and that send but
5:02:03
before i set up that method i set up a status one first and i go with
5:02:10
200 so this just means that the request was successful so similarly i'll do that
5:02:16
in the about where i go with status we pass in the 200 and then we set up a
5:02:23
chained send so now if i go back to my browser and if i refresh now of course i
5:02:29
have resource not found that is my heading 1 and i can clearly see my 404
5:02:35
and if for example i'm looking for about there it is i have my about page as well
5:02:41
as the homepage so if we go to localhost and 5000 that's going to be our route
5:02:47
that is going to be our homepage all right and we're done with our basic example hopefully you can see that it is
5:02:55
already way less code than just using the built-in http module
5:03:01
and in the next example you'll see how express truly shines when it comes to
Express - App Example
5:03:07
setting up a server beautiful we're done with our basic example now let's tackle
5:03:13
the big beast our navbar app and the setup for the following examples
5:03:20
is really up to you if you're not a fan of retyping
5:03:25
something you have already learned you don't have to do that you can just remove app.get
5:03:31
all the way to app.all so basically leave the import as well as
5:03:36
instantiation and listen as well however i am a fan
5:03:42
of repeating something because that way whenever i need to create something from
5:03:48
scratch i already have done it quite a few times so i don't have that blank page syndrome where you're like looking
5:03:54
at the empty file and you don't know what to do so in my case i'm going to remove everything and we'll start from
5:04:00
the scratch so const express is equal to require and of course we're looking for
5:04:05
express and then i'm going to set up my app that is equal to express we invoke it and
5:04:11
again we go with app.listen and we're going to go with 5000. now i'm not saying that i'm going to do that for
5:04:18
every example but i'm just showcasing what is in my approach when i'm starting something new
5:04:26
so when i'm learning something new yes i do like to retype some of the stuff quite a few times because
5:04:32
that just makes sure that i remember it better and in here i'm going to go with server here's listening
5:04:40
on port and we go with 5000 and then dot and in order to set
5:04:47
everything up we're going to go with app.get so again i'm looking for the root and of course i would want to start
5:04:54
with my index html correct that's the start and we go with app.get so we're
5:05:01
listening for all the incoming requests that go to our route and of course we're specifically
5:05:07
listening for get requests then we have our callback function rack and res
5:05:13
and we'll set up the functionality in a second before we do anything let's also set up all
5:05:18
and this is of course going to be for all the requests that will hit 404 so we're going to go
5:05:24
with rack and res and here let's say res and then status
5:05:29
so let's add here a 200 or i'm sorry four four my bad and then we're gonna go
5:05:36
with send and instead of the send let's just go with the resource not found
5:05:42
now when it comes to get in this case i would want to send the file more specifically i would want to
5:05:49
send back the index.html and in order to do that i need to use
5:05:55
send file method that comes with express now in there though i do need to provide
5:06:01
a absolute path so we'll have to use one of the modules we covered before and that is going to be a path module so i
5:06:08
go with const path is equal to require and i'm looking for path module again we
5:06:14
don't have to install it comes preinstalled with node so we are in good
5:06:20
shape and then where we have our callback function we go with res
5:06:25
and send file method and here let's pass in path and then resolve so path dot
5:06:33
resolve remember that was one of the methods we cover and effectively i would want to pass in
5:06:39
the dirt name so this is going to be path to our directory because we do need to provide
5:06:45
that absolute path and then of course we're looking for our index.html which is sitting in the navbar app so forward
5:06:52
slash and then navbar hyphen app and then we have another
5:06:58
forward slash index html now if i have to be perfectly honest in this case we
5:07:04
can also use path dot join it doesn't really matter since their name provides that absolute path but just to be a bit
5:07:12
explicit that we are providing absolute path i went with path dot resolve and then the their name and then
5:07:20
whatever is the path to my index html and the moment we save it
5:07:26
we'll have the same errors just like in the http module so i go to
5:07:31
my localhost 5000 and i still have the same issues i still don't have style css
5:07:37
there's no sign of browser app as well as the logo now in express though we don't have to
5:07:44
do this whole song and dance like in http module
5:07:49
in express i can simply go above all my app.gets and amp.alls and i can go with
5:07:56
app dot use and this is going to be the case where i'll type out the code and then
5:08:02
i'll explain everything that is happening and we'll pass in the express
5:08:07
so this is what we're importing so this is not going to be our server instance
5:08:12
instead we're going to go with express and then static that's the method and in
5:08:18
here again we just need to provide a path now common name is setting this up as the folder by the name of public
5:08:25
please keep in mind technically you don't have to do that you can just point to our navbar app but in my case i will
5:08:32
do that i will set up here dot forward slash and i'll call this
5:08:37
public so now of course what i need is to set up a folder by the name of public
5:08:43
and then all my static resources all my static files i would want to transfer there now
5:08:49
don't worry about it i'll cover in length what in a server land means static
5:08:54
resources for now what i would want you to do is go back to our folder
5:09:01
and that is going to be express tutorial and of course you can do that in visual studio code i just think that this is
5:09:06
going to be a bit easier to see so i'm going to create a new folder again common convention is calling this public
5:09:13
but you can call it whatever lobster it doesn't really matter and then in my
5:09:18
case i'm just going to copy these files so take browser app take logo and take
5:09:24
styles if you want you can move them just remember that the previous code is not going to work as far as the http
5:09:31
module setup so i'm going to copy these ones and paste it here in my public so now of
5:09:38
course i have browser app logo svg and style css so
5:09:43
of course now i can zoom out and once i save
5:09:49
check it out when we navigate to our route there it
5:09:54
is this is our application and what's really cool all those resources are
5:10:01
right away available so if i go to my localhost 5000 remember browser was
5:10:07
looking for what well it was looking for example for style css if you go here
5:10:12
there is a resource by the name of style css and of course in here i have all my
5:10:18
css code and notice how we didn't have to set up the statuses we
5:10:24
didn't have to set up the content types or any of that express takes care of it
5:10:30
all now of course you probably at this point have more questions than answers so let me start clearing them up and
5:10:37
first i'm just going to add a comment of setup static and middleware middleware
5:10:44
and like i mentioned app.use is for setting up the middleware and we have
5:10:51
more serious examples coming up so for time being please don't worry
5:10:56
about this line okay so please don't worry about app.use what is express static that is essentially a built in
5:11:02
middleware i will cover everything step by step in this video i would want you to
5:11:08
understand what the term static asset means and it simply means
5:11:13
that it is a file that server doesn't have to change it so instead of our http
5:11:20
example where we created a path for every such resource
5:11:26
and if i were to have i don't know 20 000 images i would have to repeat the same steps
5:11:33
instead since this is a static asset meaning an asset where the server
5:11:40
doesn't need to change it we simply place it in designated
5:11:45
folder again the common name for those folders are public or static
5:11:51
and then we just dump all those assets in there so if i were to have i don't
5:11:56
know 20 000 extra images in here i can just dump them
5:12:02
and express will take care of it all it will set up the paths it will set up the
5:12:07
mime types it will set up the status codes and all of that good stuff so
5:12:12
hopefully that is clear static assets are just files that server doesn't have
5:12:18
to change and an example of a static asset is an image file here's the style
5:12:24
file and also a javascript file and here comes the next question
5:12:30
what is this guy with weird eastern european accent talking about because all my life i've been told
5:12:37
that the javascript makes my apps dynamic
5:12:42
it adds all the functionality so how come this is just another static asset
5:12:48
and to answer your question yeah you're right javascript does make
5:12:54
our apps dynamic however think about it this is a browser app so it makes
5:12:59
dynamic on a browser as far as servers is concerned it is just a asset doesn't need to
5:13:06
change now if you're wondering well how to set up something dynamic just please put the pin on that and
5:13:13
we're going to cover that when we cover server-side rendering because there is such thing as template engines
5:13:20
and the simplest way for me to explain that is imagine the scenario where you
5:13:26
can actually log in or in other way just showcase whoever is
5:13:32
visiting the site and then dynamically i would display for example name so if the peter logs in then i'm sending
5:13:40
back the html with the text of hi peter now if the john logs in then of course
5:13:46
i'm sending back the username with the value of john so hopefully you get the
5:13:51
gist where in this case notice this is just same old index html that i'm sending
5:13:58
back regardless of who is visiting the site but yes there's also an option of setting this dynamically where depending
5:14:06
on who's visiting the site or what the user is trying to do i'm actually modifying my file before i'm sending it
5:14:14
back so hopefully it is clear how much easier it is to work with express
5:14:20
where if we have static assets we just set up designated folder and just dump
5:14:26
them all in and static asset just means a file that server doesn't need to
Express - All Static
5:14:31
change and of course we can start working on our next example nice hopefully we are
5:14:38
clear on static acids and before we cover more complex expressed topics i
5:14:45
would want to throw a mine grenade at attribute and it goes something like this
5:14:50
so if we put two and two together i talked about static assets in the
5:14:56
previous video but if we're looking at the index.html
5:15:02
isn't this a static asset as well and of course the answer is yes
5:15:08
so instead of sending this file we can add it to static assets and we're
5:15:13
going to be in good shape and if i have to be perfectly honest with you when it
5:15:19
comes to send file if we're using it to send back for
5:15:24
example index html actually we use other two methods
5:15:30
instead so first i'll show you the first one where we just dump everything
5:15:35
as far as the static assets so i'll just add index.html to all my static assets
5:15:41
in the public and that will effectively do exactly the same like we're doing here with send
5:15:48
file and the other one is going to be using templating engine so of course that one will cover when we go to server
5:15:55
set rendering so i'm just trying to showcase that yes there is this option of send file and we might use it from
5:16:01
time to time throughout the course but not for sending back index html files so
5:16:07
first let me just say that the other option one of the two other options that
5:16:12
we'll use the most throughout the course is just adding two static
5:16:19
assets like so and then the second one is going to be server side rendering
5:16:24
where basically we'll use template engine for that so in order to set everything up now of
5:16:30
course i just need to take my index html and again if you want you can just move it or in my case i'm just going to copy and
5:16:38
paste so again i'm going to go back to my folder i'll zoom in massively
5:16:44
so you can see better so express tutorial there is my navbar app and i'll just take the index.html
5:16:51
and i'll copy and paste and now it is in the public so what happens index.html
5:16:58
is always going to be a root so when the user hits the server by default
5:17:04
server will serve this index.html and since our index.html basically has all
5:17:09
the paths to browser app to logo svg and all that we're going to be in good shape more
5:17:15
effectively we don't even need to set up this send file option
5:17:20
so now of course i can just save it and once i refresh notice how nothing
5:17:26
changed i'm still serving my app so we're still in good shape and if you
5:17:32
take a look at the network tab notice everything still works correctly i'm still getting all the css all the
5:17:41
browser javascript functionality as well as the logo and to answer your question
5:17:47
yes that is effectively how you can set up the simple sites you can simply just
5:17:53
dump all your files in the public just make sure that you serve them up
5:17:58
and that's it and you're in good shape now we still have the 404 but as far as just serving straight up sites with html
5:18:06
css and javascript yes you can simply dump them into public you can simply set
5:18:11
up the middleware and serve all the static assets and you're going to be in
API Vs SSR
5:18:17
good shape beautiful we are successfully done with the initial express setup
5:18:22
and ready to cover more complex express topics before we do that though
5:18:28
there's something important i want to mention you see when it comes to express
5:18:33
in most cases you'll use one of the two following options you'll use it to set up api
5:18:39
or templates with server side rendering now since term api is probably one of
5:18:45
the most overused terms in the community and in various scenarios it can mean
5:18:51
different things let's start by understanding that in express or in http case
5:18:58
when we talk about api we mean setting up an http interface
5:19:03
to interact with our data now data is sent using json which stands
5:19:09
for javascript object notation and in order to send back our response we're
5:19:15
going to use res.json method which will do all the heavy lifting like for example setting
5:19:22
up the proper content type and stringify our data the other flavor we have is server side
5:19:29
rendering where we will set up templates and send back entire html and css and
5:19:36
javascript ourselves and we're going to do that using res.render method
5:19:43
now since i'm a big believer in actual examples over slides if you are a bit
5:19:48
iffy on either of these flavors just hold on a bit and once we cover some
5:19:53
examples i promise you it will all make sense now why am i telling you all of this you
5:19:59
see when it comes to more complex express topics it only makes sense if we
5:20:04
cover them properly using one of these flavors instead of just bunch of random
5:20:10
examples and the option i picked is the api one so in the following examples we're going
5:20:17
to construct api response using more advanced express setups the reason why i
5:20:23
picked apr route is because i believe it lets us focus more on the actual express
5:20:30
since templates by themselves add a bit more unnecessary overhead especially while we're just starting out with
5:20:36
express with that said let me be very clear if you grasp the concepts with api
5:20:42
so using the api flavor you'll have no problem implementing them with templates
5:20:48
as well since for the most part express concept setup is exactly the same
5:20:54
we'll cover server side rendering later in the course so you'll have to wait a bit for the actual example and since
5:21:00
we're going to start with api let me just stress the main point one more time and how it looks like in a real world
5:21:07
so like i said the main idea with apis is that our server provides data
5:21:14
and what that means that any front-end app that wants to access it and use it
5:21:19
can simply perform a http request and using our data set up the api and
5:21:26
functionality how does that look like in a real world well if you navigate again
5:21:32
back to course api and of course not the slides slides are just images but if you
5:21:39
take a look at any of these examples you'll notice something interesting where we're sending back the json and
5:21:46
you can clearly see that if you go again to your browser's network tab and here
5:21:53
again let's refresh and you'll see that this is our response react tabs project so again the full url
5:22:01
is course api.com and then react tabs project
5:22:07
and if we take a closer look we can see that this is the response that we're sending so we're sending back a
5:22:15
json data and i can clearly see that in my headers so in response headers as you
5:22:21
can see content type is application json now where is this data used if you took
5:22:29
either my react course or the vanilla javascript course you know that in the
5:22:35
course we build quite a few projects where we practice data fetching either using
5:22:42
vanilla jazz or react and in some examples we use external apis and in sum
5:22:49
we use the apis that are here in the course api so for example with this
5:22:56
react tabs project if you navigate to react project nutlify.app
5:23:02
and keep on scrolling keep on scrolling you'll hit the tabs project and here
5:23:08
this is the app that we build using the data so again on a server
5:23:14
i set up my data i set up the api and i share the data so i create the http
5:23:21
interface and then the frontend app just simply grabs this data and again if you
5:23:27
want you can check it out here if you refresh notice this request request goes to
5:23:33
course api react tabs project so we grab the data on a front end and then we set
5:23:40
up the functionality as well as user interface hopefully this is clear from
5:23:45
now on we are going to be responsible for sending back the data so now since
5:23:51
we're setting up the server it's not going to be our responsibility to do something with it like we were
5:23:58
doing on a front-end in this case we are responsible for setting up the responses
5:24:04
so we're going to be setting up apis that our http interfaces to interact
JSON Basics
5:24:09
with our data not bad not bad i think we clearly covered our two options so one is
5:24:17
sending back the json data and the second one is server set so why don't we start by covering the
5:24:23
most basic json response and here's what i'm trying to mimic
5:24:30
if you go to course api and then if you look for the tours
5:24:35
project you'll hook the url of course and here you can see that we're getting back a
5:24:41
json data it is an array and each object represents a tor and if you took my
5:24:48
react course you know that we were practicing data fetching in react and effectively we hit this url
5:24:56
and we got the data we got our json data back and then we built an app
5:25:01
using that data but again the whole point here is following where it doesn't have to be
5:25:07
react it can be vanilla javascript application it can be
5:25:13
swelled framework it can be any setup where you're able to fetch
5:25:19
that data so in here on the server we just share the json
5:25:24
so in this case of course that is stores and then anywhere anyone who wants to access this data
5:25:32
they can just access it and build something using that data and that's why it is so so powerful
5:25:40
and essentially this is what we're going to do we're just going to send back first a most basic array and then we'll see
5:25:48
how we can make this more dynamic please keep in mind two things first of course
5:25:53
eventually we'll use database for that and of course i will mention that probably 20 000 times as we're building
5:26:00
these examples and the second thing that i would like you to understand that when it comes to
5:26:06
express basics so essentially how we set up the server it doesn't really matter
5:26:12
whether we're using server side or whether we're using json again if we understand the principles we'll
5:26:18
have no problem using any of those options so first what
5:26:23
i would want is to navigate back to my project and again this is going to be
5:26:28
the time where i do write everything from scratch but then starting with next example i'll just use some options that
5:26:37
we already covered so for now yes i'll remove everything and again we'll set up express
5:26:43
one last time so we're gonna go with express require and express okay awesome then const app
5:26:50
is equal to require or i'm sorry not require we need to invoke the express
5:26:56
like so and then let's go with app.listen port 5000
5:27:01
and then let's call our callback function and then let's go again with console.log
5:27:07
and server is listening on port
5:27:12
on port and of course the port number is 5000. then again i want to set up
5:27:20
app.get because that is the http method that all browsers perform by default so
5:27:26
i'm going to go with app.get and i'm not going to go with specific path just keep in mind that you can and of course we'll
5:27:33
do that later for example i can go here with api and then i don't know i can call this
5:27:38
product or whatever for time being let's just make it simple and we'll just handle all the root requests so that way
5:27:45
we can save a little bit of typing in the browser and again we have our function our callback function rack and
5:27:52
res and as far as the response we're going to go with res and then the method name is json
5:28:01
now we will go to the docs just so you understand where i'm getting this
5:28:06
information from but before we do that let me just tell you that i might omit here and there the
5:28:13
status one just so we can save a little bit of typing but don't worry once we go
5:28:18
to some more serious examples of course we'll still use the statuses because in
5:28:24
my opinion that is just a better approach where we actually have control over the status
5:28:30
and as far as documentation if we go back to express documentation we're looking for api reference again we are
5:28:37
using four point something so we are using version four so make sure you look for
5:28:44
the same one and don't confuse with express json so this is going to be a
5:28:49
middleware that we pass in effectively we're looking for response in a docs and
5:28:54
then we're looking for this json option so res object as the json method and
5:29:02
what happens we send back the json response and this method sends a
5:29:07
response with correct content type that is a parameter converted to a json
5:29:13
string using json stringify this parameter can be any json type including
5:29:19
object array string and blah blah blah so hopefully you get the gist so the only thing we need to do is go back and
5:29:26
for example i'll provide an array where there's going to be two objects and
5:29:32
first one will be named john and the second one will be susan so
5:29:38
another object and we'll say name is equal to susan and we have our most
5:29:45
basic api so if i go back to my localhost 5000 and
5:29:50
refresh there it is so now anywhere in the world i can access this data
5:29:57
and build something using this data now there's tiny caveat when i say anywhere
5:30:02
in the world there's still going to be at the moment a course error and i'll cover that once we actually cover
5:30:09
middleware so again please please please please be patient we will get there
5:30:14
but hopefully you get the gist where this serves our data and now we can just
5:30:20
access that data and build the front-end app using this data now
5:30:26
this default setup is nice but of course we can do something more meaningful
5:30:31
where if you take a look at the folder you'll notice this data js now what is data.js
5:30:38
it is simply a file with some arrays and the first array is going to be
5:30:45
products and here as you can see i have objects and then each of these objects represents a
5:30:52
single product and all the way in the bottom we're exporting both arrays we're
5:30:57
exporting products as well as the people array that we're going to cover a bit later so now what i
5:31:03
would want to do is import product array in my address
5:31:09
and then instead of hard coding this value like so where i just pass in the
5:31:14
array with two objects i'll just dump the whole products data so let's go with
5:31:20
const we already know how to do that now since i'm exporting multiple things since i'm exporting an object i will be
5:31:28
explicit of what i would want so i'm going to go with product and basically i'm destructing right away
5:31:34
i'm going say product is equal to require and remember
5:31:39
the file is data js like so and then instead of passing array
5:31:45
directly i can simply go with product and what do you know when you navigate
5:31:52
to the root there it is now we have more meaningful json response where actually
5:31:58
this is a product data so on my front end i can grab it and i can build some
5:32:05
kind of nice front end using this data now lastly before we go let me just
5:32:10
showcase that of course there's going to be a content type set up correctly as well so if you go to network tab and
5:32:18
again if you refresh localhost like so and take a look now of course what is
5:32:24
the content type that is application json so now of course we're correctly getting our json
5:32:31
data so hopefully you have a clear understanding how to sound json data so
5:32:38
now of course let's make things a bit more interesting and cover some more advanced express topics nice once we're
Params, Query String - Setup
5:32:44
familiar with the most basic json setup now let's build a more meaningful api
5:32:52
and in a process we'll cover route parameters as well as query string
5:32:58
parameters and i would want to start in following way where essentially i'll leave all this
5:33:05
code but when it comes to my route when it comes to my home bridge i'll essentially send back the heading 1
5:33:12
with the link as well and that link will direct a user to a forward slash api and
5:33:20
then product and then later we'll cover the params as well as the query string so let's start
5:33:27
with sending back html instead so i'm not going with json one and i'm not
5:33:32
gonna send back the file i'll go directly and i'll say send and here we have the string of course so i'm gonna
5:33:38
go with heading one and then home page then i'll make sure that i close
5:33:46
because i believe in one of the previous videos i believe it was the express
5:33:51
basics i think i messed it up here notice i didn't add the closing one so now
5:33:57
everything is correct and now i'm gonna go with my link then as far as the href i'm gonna direct
5:34:03
a user to api and then forward slash
5:34:09
and then of course i'll also set up a text here so products
5:34:15
and i'll close my link so that should do it that is my home page and of course if
5:34:21
i go to localhost 5000 there it is i have my homepage and once i click the link i navigate to api products now of
5:34:29
course the moment i have the default response from the express
5:34:35
meaning the default 404 response where the resource cannot be found and as i
5:34:42
said note if you want to take a look what response do they send again go to the network this is going to be very
5:34:47
very useful tab refresh and take a look at their response so notice the response
5:34:53
that's the html that they send back so cannot get and then api products now we
5:35:00
already know why there is this get the http verb because that's the method that the
5:35:06
browser performs okay awesome so now of course our job is to set up a
5:35:12
get request for this resource so we go with app.get
5:35:18
and i specifically want to handle api and product so this one just looks a
5:35:24
little bit more realistic so in here i go with api and products and keep in mind of course
5:35:31
those values need to match otherwise you'll get that 404 again i have my callback function
5:35:37
and now of course i would want to send back the product however in this case we'll make it a little bit different
5:35:43
where previously notice the product we send back pretty much the whole thing right but
5:35:49
a more realistic approach is following where when you're requesting a bunch of
5:35:55
data so when you're requesting collection of the data you're not always returning everything for that one
5:36:02
specific product and to give you a real world example again i'm gonna go back to
5:36:07
my react projects and i'm simply using them because this gives you a visual representation during the course we
5:36:14
built a e-commerce and then in the products page notice how we're fetching
5:36:19
the products but you need to keep in mind one thing where we're only fetching about the
5:36:26
product the title the price the image and i believe also the id and only when
5:36:32
i go to that single product page this is where i get the rest of the data
5:36:37
whether that is for example a stars the reviews the description
5:36:44
the availability and all that stuff so what i'm trying to say is when you're requesting a collection
5:36:50
of data there's going to be cases where i simply want to send back some minimal
5:36:56
response so for example again that could be name image and the pricing scenario
5:37:01
and only if i look for this specific product then i send back everything
5:37:08
and in order to mimic that in our example in this response
5:37:13
what i'm going to do is i'm just going to iterate over my product i'll use the map method and i'll just remove
5:37:22
my description so when i'm sending back the product it's going to be without a description so again if we were to send
5:37:30
back everything i would simply go with response json and then i pass in the product so again if we go here and if we
5:37:38
refresh now everything is cool i'm getting my product on the api product route however
5:37:45
i'm going to make it a bit more realistic and we're going to go with const new product is equal to
5:37:52
product dot map so i'm mapping over and i'm creating a new array and i'll reference each item as a product and
5:38:00
then as far as the return well first i want to structure the properties out of
5:38:06
the product and the reason why i can access them is because those are the names that i used when i'm setting it up
5:38:13
so id name image and all that and that is equal to the product again i'm just
5:38:19
using simple javascript structuring and then as far as the return whatever i'm going to return
5:38:25
from my function well that is going to be the new value so now i'm going to go with id name as
5:38:32
well as the image and once i have this setup in place instead of returning product
5:38:37
now of course i'm going to go with new products and if i go back to my browser there it
5:38:44
is so now i'm getting a collection but i'm not sending
5:38:49
everything that i know about this specific item so i'm being selective of
5:38:54
what i'm sending back so yes there is a resource by the name of api product and we're sending back the array
5:39:02
but we know that if the user wants to access that description he or
5:39:08
she will have to look for a specific product and in the process we'll cover
Route Params
5:39:13
what are the url parameters all right so we're successfully sharing a list of
5:39:20
items so now of course let's take a look at how we can provide info
5:39:25
about that one specific product so for example if i navigate to
5:39:31
product and then forward slash and one and then i'm going to get only the info
5:39:36
about this first product because it has the id of one and
5:39:42
not only i'll get these three properties but also get the description
5:39:48
and our initial approach would go something like this where yes i see the product okay
5:39:54
beautiful and we already know how to set up the route now since i'll delete it
5:39:59
eventually anyway i'm just going to copy and paste so we can speed this up so i'm going to go with api products and then
5:40:05
forward slash one that just means that i'm going to be looking for item number one in here
5:40:12
and then instead of map we'll use the find method so i'm importing all my products and in
5:40:18
order to get the single product i'm going to write the following code where we're going to go with const
5:40:25
single product and don't worry we will reuse this code so
5:40:31
it's not like we're just randomly typing something so let's go with products and then find now again
5:40:38
i'll reference each product with a parameter of product in my callback function and then if the
5:40:45
product id product id matches one
5:40:50
because that is my route here then of course i'll return that single
5:40:56
product so i'm going to say single product and technically this works
5:41:01
so notice now of course i have only info about this one specific product and i
5:41:08
have the description however it feels like using bazooka on a cockroach yeah
5:41:14
it gets the job done but probably is an overkill because keep in mind at the moment we
5:41:21
have only four products so yes if i really wanted to i could set up
5:41:28
four routes but what if i have hundred two hundred three hundred well that's not gonna work and in
5:41:35
express we have something called route parameters which essentially is going to be way better solution
5:41:42
so instead of hard coding this 1 2 3 or whatever id we want we set up a route
5:41:50
parameter and it's going to look something like this where i go with my route and then i have forward slash and
5:41:56
then i go with colon and then whatever name out one so think of this
5:42:01
as a placeholder so you can call this bobby lee you can call this chicken burrito in my case i'm gonna go with
5:42:09
product and the id just to be explicit
5:42:14
of what i'm expecting over here but again naming here is really up to you
5:42:21
and what is more important is the fact how we can access it now if you want you
5:42:26
can actually console log the request object again this is just going to be a giant object and for now i'm just going
5:42:32
to leave this one the way it is so i'm still going to be returning a product number one and also let's look
5:42:40
for request and then we're looking for the params
5:42:45
property so let me count to lock this one and then again once i navigate back and if i refresh in the api products
5:42:54
number one what you'll notice again this giant request object where we have bunch of
5:43:00
useful properties and methods and of course i'm not going to cover all of them right now but similar to http of
5:43:07
course in the express we also have access to bunch of useful things in that
5:43:14
request object and one of them is the params so check it out now i have this
5:43:21
product id and the value is one now please keep in mind one thing that
5:43:26
whatever you're going to be setting up here in the url as that route parameter
5:43:33
is always going to come back as a string and this is important in this case because if you take a look at our data
5:43:41
the id is a number and of course we'll deal with that in a second
5:43:46
and whatever we set up as far as our name is going to be right in here it's going
5:43:52
to be in this request and then parameters object so now of course what i could do
5:43:58
is i could just destructure it from the params and then use it in order to find that
5:44:05
specific product so that way i don't have to hard code products number one product number two and on and on and on
5:44:13
instead i just set up my route parameter and just come up with whatever name i
5:44:18
would want just make sure that you add this colon here and then we'll access that value and get
5:44:24
a specific product so i'll leave these two suckers for your reference just in case you would ever
5:44:31
want to console log them and we'll simply go with const and the name is
5:44:36
product id and that is equal to request that's my request object and params
5:44:44
then i'm going to use this product id to get my product but remember
5:44:51
it is a string we can clearly see that and in fact here in the array
5:44:57
well the ids are numbers so if we'll just try to search it the way it is
5:45:02
of course we won't be able to get our product so instead what we want is pass in the number
5:45:08
and then product id now of course if your ids are set up as strings
5:45:15
which is somewhat typical setup for the databases and all that
5:45:20
as well as the headless cms is then of course you don't need to worry about it then you can just pass in the string and
5:45:26
now of course i'm going to be able to get my one product so now if i go back
5:45:33
and if i refresh everything still works and if i go to my
5:45:39
url and start changing these values hopefully you can see that now of course i'm getting a different product now i'm
5:45:46
getting product number two and i go to product number three and on and on and on so now with these few simple lines of
5:45:53
code i can access any product in my array now
5:45:58
of course there's also a case where we cannot find the product because keep in mind here i can type whatever i would
5:46:04
want so i can go with products and then let's imagine that the user types abc
5:46:11
now do we have a product with an id of abc of course the answer is no so what's
5:46:17
happening over here now i don't get anything back right well i don't get anything back because if i go to log and
5:46:24
then single product let's see what we're going to get back again let me refresh
5:46:30
abc and this one is undefined so that's what we're sending back as a single
5:46:36
product so what would be a solution well a solution is setting up a if statement
5:46:42
here where i say get me the single product if you cannot find that single product if
5:46:48
basically that product doesn't exist if the id that the user passed in does not make
5:46:55
sense you cannot find the product with that id then return 404 so how's that going to
5:47:02
look like well we can go here if and then single product so we set up a if
5:47:08
condition and of course i'm going to go with if single product doesn't exist so i'm going to add exclamation point and
5:47:15
of course this is going to be our case with undefined this will be true if it is undefined and
5:47:21
then we just go with a return res and in this case i will add a status
5:47:26
because that is extremely important that i go with 404 and then we go with send
5:47:32
and product does not does not
5:47:37
exist like so now if everything is correct then of course we go with res
5:47:43
and json so in here i say return and res dot json so once i go right now
5:47:51
to product and then abc there it is now of course i have proper 404
5:47:56
product does not exist and if i again take a look at the tab and i have my abc now if i'm going to
5:48:04
navigate to a route where i can find the product then of course i'm going to get
5:48:10
my proper product response so whenever you think of route parameters think of
5:48:16
them as placeholders where user provides a data and then using requests and
5:48:23
params we can access that data and then set up some kind of logic
Params - Extra Info
5:48:28
and before we continue and cover query string parameters let me just mention that route parameters can get way more
5:48:36
complex than this so for example imagine this scenario i can go with app.get
5:48:42
again i need to come up with some kind of routes i'm going to go with api
5:48:48
then products so i'm looking for specific products so i'm going to use a route parameter let's call this product
5:48:55
id then i'm going to look for all the reviews and then maybe there's a review
5:49:02
id so review and then id and now of course again i have rec and res like so and then i'm
5:49:10
simply going to send back some kind of dummy data but i would want to console
5:49:15
log the rec params just so you understand how everything works and now let me send
5:49:22
res.send so res not send and i'm just going to say simple hello world let's save this one
5:49:31
and again in the browser let's go here we have products again some kind of id
5:49:36
whether that's abc whether that is a number in this case it doesn't really matter since you can see that there's
5:49:43
not much functionality in there but we need to type in here reviews and then
5:49:48
for example the review id would be i don't know abc so once i navigate here
5:49:54
of course i'm going to get my hello world and then in the console notice how i'm accessing all of them so i have the
5:50:01
product id as well as the review id so again they can get way more complex than
5:50:08
just this simple approach and one more thing i would like to mention this reviews though is hard coded
5:50:16
so if i go back i can change the abc and 4 however i would like but if i'll
5:50:23
change from reviews to review i'm going to get a 404 why well because
5:50:30
review is not a route parameter so that's not a placeholder so if
5:50:36
this is incorrect then of course i get d404 hopefully that is clear and now let's talk about the query string
Query String
5:50:43
parameters all right and once we're familiar with rot parameters let's talk about the
5:50:49
query string parameters or they're also called url parameters
5:50:54
and essentially that is a way for us to send small amounts of information to the
5:51:00
server using the url now this information is usually used as
5:51:06
parameters to for example query database or filter results and that's really up
5:51:11
to the people who are setting up the server they decide what parameters are
5:51:16
going to be accepted and what functionality will depend on those values and to give you a real
5:51:24
world example let me go to my search engine and i'm just looking for hacker
5:51:30
news algolia api so when you're working on a front-end app i'm not sure whether you worked with
5:51:36
this api but that is a very cool api and essentially it's going to work as a good
5:51:43
example of how we should be setting up the server and this is as a side note but notice the url here
5:51:51
so they go with a domain which in our case is of course localhost 5000 but
5:51:57
here it is actually a algolia domain so algolia.com
5:52:02
forward slash api like i said that is a pretty common practice then a version number and then whatever
5:52:10
list you're getting so in here it is items now check out this one
5:52:16
doesn't that ring a bell of course that is a route parameter where they say yeah here's the list of
5:52:23
items but if you want to be more specific please provide the id
5:52:29
and then if you keep on scrolling you'll notice the same thing with the users again we have the main domain
5:52:36
api version one users that's the list and then if you want to get a specific
5:52:42
one then of course again there is a route parameter now this is just to showcase that i'm not randomly coming up
5:52:49
with those things no that's how actually the servers work in real world and let's
5:52:56
keep on scrolling and now we come to this interesting part where we can sort
5:53:01
so we're getting the data from the algolia api but then in my app
5:53:08
i can sort i can say hey you know what get me specific hacker news story or get
5:53:15
me stories based on some kind of search term and hopefully you get the gist
5:53:20
where instead of just grabbing the whole thing i can say you know what get me all the stories that match
5:53:28
through so again we go with the url and this is really up to you how you set this up in their case they use search
5:53:35
and then here we have this question mark and whatever is after this question mark
5:53:42
is not technically part of this url meaning it's just a way for us to send that data
5:53:47
to the server and then server decides what to do with this data so the url is still this one
5:53:54
the one that ends with search and then we have a question mark and basically this is just a specific info
5:54:02
about the data that i'm requesting so here the user adds a query parameter and
5:54:09
then the value is full and then also has tags of story and that means that we're
5:54:15
going to get all the stories matching full now what else you could set up here in a query string pretty much anything a
5:54:22
pretty typical is going to be page for example if you have a list of things and
5:54:27
i don't want to get 100 items at a time i can say you know what split it up in pages and get me initially page number
5:54:34
one and then only if the user clicks on a button that fetches the page number
5:54:39
two then i get the second page then for example in here they have hits per page so that is going to be how many items
5:54:46
per page so again after that question mark if the setup is
5:54:51
supported by the server then of course you can add those key value pairs and the way we add them as
5:54:58
you can see is by using key value pairs so we have question mark and then we have a key
5:55:04
which in this case is query and then the value now before we continue let me make something
5:55:10
very very clear it's not like you can randomly search the web and just start
5:55:15
adding these query string parameters and then expect that as a miracle you'll just get the
5:55:21
data that you're looking for a as far as the keys they're designed on a server so if i'll
5:55:28
set up a key of chocolate milkshake algolia api is going to be like i don't know what you're talking about and the
5:55:34
same goes for the value so where i'm going with this now we are in charge of that server so it's up to us to handle
5:55:42
those query string parameters and i'm going to go back to our project and i'll purposely set up a new route
5:55:50
please keep in mind one thing where a pretty typical setup is adding this to the list
5:55:57
so again we'll look for specific property on our request object and then
5:56:02
if that property is provided then of course we return a more detailed
5:56:09
response meaning there's maybe some filtering or something like that but if not then we'll send back all the
5:56:14
products now i'll purposely set up a new route just so we don't jam all our code
5:56:20
in this one route but then in the next video probably i'll show you
5:56:26
how we can combine both routes so let's keep on scrolling so this is going to be our more complex
5:56:32
params example and let's go with app.get and again
5:56:38
the route is really up to you i'm going to go with api now in order to make it interesting i'm going to add that
5:56:43
version 1 just like the api of algolia has it and then i'll say query now i
5:56:50
don't need to add question marks nothing like that i just set up query that is my route and then i have my callback
5:56:56
function rack and res now in this callback function in order to access those query string parameters
5:57:04
i need to go with rec and query so let's go with console.log and we're going to look for
5:57:10
request and not params sorry we're going to go with query over here and again let's go
5:57:17
with simple hello world just so we can speed this up and then if i go to the
5:57:23
local host and more specifically i'm going to look for
5:57:28
localhost then 5000 then api then version number one
5:57:34
and then query and then if i add this question mark i can add as many query
5:57:41
string parameters as i would like so here i'm going to go with the name that will be equal to john
5:57:47
then in order to combine them we just add this ampersand so we're going to go
5:57:52
with name john and then id4 just keep in mind that you can add as many query string parameters as you'd want and then
5:58:00
once i navigate there at the moment i'm just going to get the hello world so that's my default response from this
5:58:07
url but in a terminal notice i have name john and id number four again this is a
5:58:13
string and this is going to be important in a second but what this allows us to
5:58:19
do is access those parameters and then based on them do some kind of functionality now first of all i would
5:58:25
want to change this around a little bit where i'm not going to be looking for name or id i'm going to be looking for
5:58:31
search query parameter as well as the limit so if the user wants to search for
5:58:37
a specific product he or she needs to provide that search query parameter as well as limiting
5:58:44
where the user can limit of how many products they are getting back so let me
5:58:49
navigate back and just to showcase that so again instead of name i will zoom in
5:58:55
we'll say search is equal and then whatever i would want so in this case i'm just going to go
5:59:01
with a so effectively this will return all the products that start with a and
5:59:06
then the second one is the what that was the limit right so i'm gonna say limit
5:59:13
and for now let's just go with two of them so this will return two products
5:59:19
i'll zoom out and again i have search and i have limit after you so now of
5:59:25
course let's set up that functionality and we'll simply start by creating new instance of those products i'm gonna go
5:59:32
with let and you'll see in a second why so say sorted product and in here we'll use the spread
5:59:39
operator so we imported the product and now i'm just going to copy the values so this is going to be my new
5:59:46
array and the reason why i'm using let because we will modify this value a bit now instead of just
5:59:54
cancel logging the query i'll comment this out and we'll set it up as const
5:59:59
and then again i'm looking for two specific keys i'm looking for the search
6:00:04
and i'm looking for the limit so if the user doesn't provide them well then we'll send back all the
6:00:10
product so we're gonna go with query like so so i can see the search and
6:00:17
limit beautiful and now instead of just sending back hello world i'm going to check
6:00:23
if the search is in my query string parameters then i
6:00:28
would want to filter my product so i'm going to say if and then search like so
6:00:34
and we're going to go with sorted products since i'm using let i can do that i'm going to go with sorted product
6:00:40
and then filter method again straight up javascript again i'll call
6:00:45
this a product like so and what i would want to return
6:00:50
are the products that start with the value of my search term so here i can
6:00:57
say return product and name so if the product name starts
6:01:02
with now again this is straight up javascript and i'll pass in the search if that is the case that is going to be my value in
6:01:10
stored product and i can right away check for the limit as well where i'm going to say if
6:01:16
and then limit and if it exists so if the user has provided it again
6:01:22
let's go with sort product and filter more and in this case i'm going to use the slice method where i'm
6:01:29
just going to get specific items from the array so i'm going to start with 0 and then remember we're getting a string
6:01:36
so we need to go with number and then again we'll pass in the limit let's go here below both of them and let's just
6:01:44
say res dot and then status and we're going to go with 200 like so and then a
6:01:51
json response now when it comes to json response we're
6:01:56
just gonna go with our sword product right so we go back and let me just showcase something where
6:02:02
if none of the query string parameters are provided i'm gonna send back my whole
6:02:08
data why well because i copied my products right both of them were false
6:02:14
both of them were undefined and as a side note there is a error here
6:02:20
cannot send headers and i'll talk about it actually in a second that is one of my
6:02:25
next topics so let me just deal with this hello world by deleting it and
6:02:31
we're going to be in good shape but i'll cover why we got this error and what gotchas you should be aware of so let me
6:02:38
go back again let's see again we're getting all the products because the user did not
6:02:44
provide that specific query string parameter so if we right now navigate to the url
6:02:51
and i'm gonna start with a limit and if in the limit i'm gonna say that i'm only interested in two products
6:02:57
check it out now of course my limit is two so i only have two products and if
6:03:02
it's three then it's gonna be three and then four and hopefully you get the gist where whatever value i provide here in a
6:03:11
limit well i have the functionality for it now keep in mind again name needs to
6:03:16
match if this is going to be limi instead of limit again i'm just going to get back all the products regardless of
6:03:23
what is my value and the same goes for the value of the query string parameter
6:03:29
if this is limit but for example i decide to pass in abc
6:03:34
nothing i get empty array why because my value wasn't what my functionality was
6:03:40
looking for and similarly of course we can add the search option as well and i'm purposely showing them one by one so
6:03:47
you don't get confused so let's say search and again the functionality is set up
6:03:53
where you need to provide a starting character so in my case i'm looking only for the products that start with a and
6:04:01
there it is i have two of them now if i want a limit i can just add and here
6:04:07
and let's just type limit and i'm only going to be looking for one product and if i add this limit one
6:04:13
there it is now i only get one product now there's also obviously going to be the case where we return empty array
6:04:22
why well because i could go with search and look for the products of b
6:04:28
and unfortunately when it comes to my product data i don't have products that
6:04:34
start with b so we can handle that instead of sending back empty array i
6:04:39
could check what is the length of my array and if for example it is less than
6:04:45
one then i explicitly send back the response where i say yes the request was
6:04:51
successful but i couldn't return any product so we can go with if and then sorted product
6:04:59
if the length of this array is less than one
6:05:04
if it is less than one then of course i can just go with res dot status now this
6:05:11
is one gotcha where you're not sending back the 404 you're not saying the url doesn't exist or the
6:05:17
resource doesn't exist in this case you're trying to filter the product but
6:05:24
nothing came back so whatever query string parameters were provided they didn't yield any results
6:05:32
so you're simply saying status and then you can go with send and we can go with
6:05:37
no products products matched your
6:05:42
search like so so we can go here and then if we refresh again with the same ones we have no product match your
6:05:50
search so that is one option you can send back the string but a more common one is this one where i'm
6:05:57
going to comment this out for your reference again and instead you go with return
6:06:02
and you're going to go with res dot status and again we have this error in
6:06:08
the server and again i'll talk about it in the next video why we have that one so
6:06:14
we're going to go with res dot status and we pass in the 200 and instead we
6:06:20
send back the json one and in that json again you can pass the string if you want but a more common approach is
6:06:28
setting up the object where you explicitly say that the request was
6:06:33
successful or a failure so you go with success and that is equal to true and
6:06:39
then again you come up with whatever name you would want a generic one is data and then you send back the array
6:06:47
again you are in charge here you can really do whatever you want i'm just showing you
6:06:52
a pretty common approaches to the situation so again i'm looking for some kind of product
6:06:59
using my query string parameter now unfortunately server can return
6:07:04
any data meaning any product and then of course i just get this success true because the
6:07:11
request was successful there was nothing wrong with my url however
6:07:16
i'm just yielding a empty data so that's it i can just delete it and if i don't
6:07:23
provide anything then i'm going to get all the products hopefully that is clear how the query string parameters work and
6:07:30
now we can cover a few gotchas all right and two things that i would like to emphasize are following first
Additional Params And Query String Info
6:07:37
remember those errors that we're getting in a server when we're setting up if
6:07:42
conditions in javascript if we don't explicitly
6:07:47
return then of course javascript just keeps reading the code correct so if i'm going
6:07:54
to omit that return i'm actually going to get the server error where i send
6:07:59
back one response and then javascript just keeps reading the code and then
6:08:04
express is confused express is like hey wait a minute i already sent back the response so while you're sending another
6:08:10
now keep in mind that it is happening in the same request so you cannot send basically two responses in the same
6:08:18
request one after the another yeah of course you can send one based on the
6:08:23
condition so for example if there are no products you send back one response and if you can yield some product then
6:08:30
great then you send the second one but you cannot send both of them one after another in the same request
6:08:38
and if you want to see that error again in action go to the query you'll add a
6:08:44
question mark here and we're going to go with search and again it is equal to b for example that
6:08:51
is my value that's the starting value that i'm looking for and once i do that notice yeah i'm getting back the success
6:08:58
true and data but again i have this big fat error in my server and it says
6:09:04
cannot set headers after they are sent to the client so we can have only one response per
6:09:11
request and in order to avoid that we just go with return so always always when you're
6:09:16
setting up the condition make sure that you go with return so that way we are returning from our callback function and
6:09:23
one we set up over here and that way you'll avoid those errors now of course
6:09:28
in this case there's no more code to read so yeah it is a better practice if you just
6:09:34
put this return here but you won't get the error since again there's nothing after that and one more thing that i
6:09:40
would like to mention normally you're not going to set up a separate one just for the query yeah
6:09:48
there might be some cases maybe there's some apis who do that but normally again
6:09:53
you can just add it to where you're getting a list so basically if
6:09:59
there's a query beautiful you're maybe gonna sort that data you're gonna filter
6:10:04
it you're gonna i don't know set up some pages or whatever and if
6:10:09
no query string parameters are there then you send back the whole product and
6:10:15
if you take a look pretty much nothing stops me here from just changing this to api and products
6:10:22
and the functionality is going to work where if there are some query string parameters
6:10:28
present beautiful notice how we're filtering our product if not then i always send
6:10:35
back these products anyway and as you can see those are just copies of the
6:10:41
products that are coming from my data js hopefully that is clear and now let's
Middleware - Setup
6:10:46
move on to our next topic nice and once we're familiar with route params and query string let's really
6:10:54
kick things into gear and talk about middleware in express.js express middleware are functions that
6:11:01
execute during the request to the server each middleware function has access to
6:11:07
request and response objects and when it comes to functionality literally sky is the limit in order to
6:11:15
hammer this home i have prepared quite a few examples where we cover middleware step by step since in my opinion actual
6:11:22
code examples are far more helpful than text based explanations before we
6:11:27
continue though let me just stress something middleware is literally everywhere in express
6:11:33
you can even make an argument that express apps are nothing but a bunch of middleware functions stuffed together to
6:11:40
make one nice express cake or dessert if you are in that sort of thing
6:11:46
and since that is the case middleware is not one of those topics you can just skip or avoid
6:11:52
it is at the heart and soul of express so please don't dismiss it with that said since you'll encounter it more than
6:11:59
once if you struggle with it in the beginning don't panic the more examples you'll do the better you will understand
6:12:06
it now let me start by cleaning out my app.js and this is going to be the case
6:12:12
where i will leave the code at least some of the code from the previous lecture so let me delete
6:12:20
all the middle part and i'm just going to leave express we are instantiating our app and we're listening on port 5000
6:12:29
and let's just start by adding a comment here for your reference so there is a
6:12:35
incoming request and so far we have been just sending responses right
6:12:40
so what middleware does it sits in between hence the name so middle where over here
6:12:48
and then we pass the response so the request comes in we'll do something so
6:12:56
we'll have access to the both to the request and response we'll do some kind of functionality again the most basic
6:13:02
you can just cancel log something and then we'll send out the response and again i know it probably looks confusing
6:13:10
at the moment but trust me the more examples you'll do the better you'll understand
6:13:15
and let's start by simple scenario where i have two routes i have the home route
6:13:21
and i have the about route and in those routes i would just want to log
6:13:27
the method that the user is using the url that the user is trying to access
6:13:33
and for example a date and if you think that's silly there's actually npm packages that do that
6:13:38
because as your express apps grow bigger and bigger it is very useful to see those
6:13:46
incoming requests in that manner so let's start here by setting up add.get
6:13:52
again this is going to be my home page and for time being i have my callback function i pass it in and i just go with
6:14:00
the res dot send and i send back the home and i'll do the
6:14:05
same thing here with my about so there's going to be two routes at the moment home and about unless it's just
6:14:13
going to say about so i'll save it and it's not going to be surprised if i
6:14:18
navigate to localhost 5000 if i refresh this is my home
6:14:23
and this is my about again something we have covered already before now here's
6:14:29
the kicker if i go with logger and if i set up that functionality in
6:14:36
the route forward homepage i'll also have to do that in the about so let me
6:14:41
showcase that so i have request object and in there i have method i have url
6:14:47
and i'll simply set up the year because i don't want to deal with javascript types so let's go with method now that
6:14:52
one was on request dot method property then we also have the url so url here and that is going to
6:15:00
be a request url property like so and then like i said i'm going
6:15:05
to go with const and i'll name this time but in order to make it easier i'm actually going to get a full year so i'm
6:15:12
going to go with new date and i'll invoke it and i'll say get full year and
6:15:17
invoke it as well and of course i'm sending back home yeah that is nice but before i do anything i
6:15:25
would also want to cancel console.log all three of them so method url
6:15:30
as well as the time like so so i save it and now every time
6:15:36
user is gonna hit this resource of course i'll see that in a console log so
6:15:41
there it is if i go back to my home page like so and if i refresh quite a few
6:15:48
times there it is now in a console i can see that the method was get so the user was
6:15:54
trying to get the resource and then the path was the homepage that's my url and
6:16:00
then the year is 2021. okay awesome but here's the problem if i want to have
6:16:07
the same functionality in about what do i need to do right now well again i need to copy and paste
6:16:14
now if i have 15 routes does that sound like a reasonable approach of course the
6:16:20
answer is no a better solution would be if we set up a function
6:16:26
and in that function we have all this logic and then i can just attach it really nearly to all my routes and when
6:16:33
i say well in italy it just just means that for some routes i maybe want to attach it and for some maybe i don't
6:16:40
so here's the deal i can go above both of my routes and i can just simply say
6:16:47
that there's going to be a function by the name of and for time being we're not going to
6:16:53
look for any parameters but yes there will be there and then we just take
6:16:59
all our i believe four lines of code right and we just cut it out and pass it
6:17:05
here okay awesome and now of course where do we attach this function so we
6:17:11
don't have to duplicate our code and the place is following where we have the path and then we have the callback
6:17:17
function now in between them we can stuck a middleware so in this case as
6:17:23
you can see i'm referencing the function please keep that in mind so i'm going to go with logger that's my middleware
6:17:30
function but now there's the second question well in the logger i'm accessing request
6:17:38
object right so how can i do that because at the moment i'm not passing it
6:17:44
in well the good news is that express passes it in to our middleware function
6:17:51
so in here i just set up the reference for my function and express will do that behind the scenes it will supply the rec
6:18:00
res and also a next and you'll see in a second why we need this next function as
6:18:07
well so again we don't have to do anything we just pass here the middleware express
6:18:12
supplies them but of course it's our job to access them as parameters and then
6:18:18
set up our logic so for them being i'm not going to do anything with next i will save
6:18:24
and we should see something where in the console i'm still going to get my log
6:18:30
but the problem is going to be in the browser so if i navigate back and if i refresh
6:18:36
notice something where i have this spinner okay so what's happening here well i
6:18:43
successfully logged but i didn't pass it on to the next middleware so here's the deal when you
6:18:50
work with middleware you must must must must must pass it on to a next
6:18:56
middleware unless you're terminating the whole cycle by sending back the response
6:19:01
and don't worry there's going to be examples where we do that as well so for now just keep in mind that when you have
6:19:07
a middleware where you set up some kind of logic unless you're sending back to response
6:19:13
yourself for example since i have access to response i simply can go with res dot
6:19:20
and send and again i'm going to come up with testing or whatever it doesn't really matter what we send back if we
6:19:27
refresh notice it doesn't really matter if i try to access the home page since i
6:19:32
have my middleware i'm actually sending back the testing and this is why the middleware is so so
6:19:38
powerful because you can literally do whatever you want over here you can set up all kinds of cool logic
6:19:44
and you have two options either you pass it on to the next middleware which in our case of
6:19:51
course are going to be our methods our get methods or
6:19:56
you simply terminate the whole cycle and you just say res dot send and i'm sending back my own data so let's not be
6:20:03
brutal over here i will actually remove this line of code and if
6:20:09
i want to pass it on to the next function meaning in our case that is
6:20:15
going to be my method app.get i simply go with next and we have to invoke it
6:20:21
again please keep that in mind there's going to be more functionality later in these middleware functions but you
6:20:27
always always either you terminate so either you send back your own
6:20:32
response or you pass it on to the next middleware that is very crucial so now
6:20:38
if i go again to my homepage there it is i successfully navigate to
6:20:43
my homepage i can clearly see that that is my response and i also successfully
6:20:48
logged in my console the method the url as well as the full year and now of course instead of adding
6:20:56
this logic line by line to every request simply can go and i say yep i would like
6:21:04
to invoke the logger here as well so if we go to logo host 5000 and if we're
6:21:11
brave enough and we navigate to about there it is now i have get request about
6:21:18
url as well as the full year hopefully that gives you a good initial
6:21:24
understanding how the middle works and now i can talk about more complicated topics beautiful we are
APP.USE
6:21:32
familiar with the middleware we have our first middleware function
6:21:38
but there are two issues with this current setup first our appdress is getting somewhat clunky
6:21:45
because i mean we have this logger then we have the methods it's definitely nicer if we have this
6:21:52
logger function in a separate file it's just going to keep our app.js lean
6:21:58
and in turn it's just going to make it easier for us to navigate and
6:22:03
essentially work with our application and the second issue what if i have 50
6:22:09
more routes and i don't want to add this function manually to all of them
6:22:15
wouldn't be nicer if there would be a method that essentially just adds my middleware function to any route and of
6:22:23
course the answer is yes there is such a function in fact we used it a few videos
6:22:28
ago now let's start though by moving this sucker into a separate file
6:22:35
so i'm gonna go to my not navbar app sorry this is what happens when you have a
6:22:41
bunch of projects open meaning a bunch of folders open let me go here where i have my
6:22:47
app.js and i'm just going to create a new file
6:22:53
and this is still going to create it in the final sorry so let me go here and i'll create a new file and i'll call
6:22:59
this logger js now if you really want you can add the middleware there in name as well but
6:23:06
in my case i'm just going to add the name of my function then i'll cut it out
6:23:12
and what's really cool that we know how to export this right so we have cons logger and then we go with module
6:23:19
exports and we'll just set it equal to our logger so now we have default export
6:23:25
that's our logger so of course in the app js i simply need to go with const logger is equal
6:23:32
and then i require it i go with logger and if i navigate to localhost 5000
6:23:41
i still should see in a console my log and if you do then everything is correct
6:23:48
so that's the first part now the second how can i apply this logger to all my routes
6:23:56
so for example let me just copy and paste these ones and i'll say api
6:24:03
and then product and then api
6:24:08
and i don't know not about maybe items again doesn't really matter what you
6:24:13
place here i'm gonna go with products as well as items
6:24:19
again i can add them manually but the more routes i'm going to have
6:24:24
well the bigger issue this is going to become right because for every route i need to
6:24:30
manually add this logger so a better solution is this one where i select all of them i just remove
6:24:38
them like so now of course if i go to any of these routes i'm not going to have anything in a console but
6:24:46
there is a method by the name of app dot use and in that app.use
6:24:52
this is what we do we pass in the middleware so we simply go with logger
6:24:58
and once i save check it out now if i go to about for
6:25:04
example or if i go to home or api and then products and hopefully you get
6:25:11
an idea all the time you'll get this log in
6:25:16
console why well because app.use will invoke this for any route now
6:25:23
please do keep in mind two things first order matters here if i'm gonna place this below
6:25:30
app.get and if i'm going to try to do that in a home page i'm not going to see anything
6:25:36
in the console why well because i invoke my use only after get and express
6:25:44
everything goes in order so if app get is before the used one the one that
6:25:51
applies to all the routes then yes well first we'll hit the home route and then we'll send back home so there is no
6:25:58
logger so that's why you'll see all the middleware functions all the app.uses at
6:26:04
the top of the document so you'll have your middleware functions first and only then you'll have all your
6:26:12
roth methods whether that's get post and you get an idea so that's the first
6:26:17
thing that i would like to mention now the second thing that i would like to mention is the fact that we can add here a path
6:26:25
so if i go to app.use that's my method and instead of providing only one argument which in my case is the logger
6:26:33
i can set up a first one and that is going to be path and i just need to come up with a value now in my case i'm going
6:26:39
to type api and you'll see e in a second why so if you save with an api you'll notice
6:26:46
something interesting where this is going to be apply to both of them to the
6:26:52
products as well as the items so here's the deal once you apply this path over
6:26:58
here basically it's gonna apply to any route after this api so for example if i
6:27:05
go with api and then some crazy one home about and then products all the time is
6:27:12
going to keep on applying this middleware so that's something new right because previously we worked only with a
6:27:18
specific route so forward slash or about or products here in this case so of
6:27:23
course these are different now when we add this path to use then of course it's
6:27:29
going to be applied pretty much to anything that comes after the path that
6:27:35
you provide over here so in my case since i provided api and of course it's going to go for any path that's after
6:27:42
that now if you want to find out more info about app.use i suggest navigating
6:27:48
to docs again we're looking for api reference in our case that is four and if you take a look at the app.use
6:27:55
mounts specified middleware function or functions and we're gonna cover that later as well at the specified path and
6:28:04
middleware function is executed when the base of the request path matches so this
6:28:09
is going to be our base and then whatever comes after will still
6:28:14
invoke that middleware function and if you omit the path then it's just going
6:28:21
to be applied to all of your requests so if i were to remove the path
6:28:29
now it's going to be applied to home about api product as well as api items nice we're familiar
Multiple Middleware Functions
6:28:37
with app.use and now i want to make our example even more interesting by adding another
6:28:43
middleware function and in the process we'll take a look at how we can execute them in that use what is the syntax in
6:28:51
order to add it as well as what is the execution order and let's start simply by creating a new
6:28:58
file and i'm going to call this authorize authorize dot js again
6:29:06
i'll zoom in just so you can see that is the file name and in here i'll just set
6:29:11
up a function similarly to how we worked in the logger one so i'm going to go with const authorized
6:29:19
or authorized it doesn't really matter now it's going to be a middleware function so of course i know that i'll
6:29:24
have access to rec res as well as next and then in function
6:29:30
body for time being i'll just invoke next and maybe i'll cancel log i'll say
6:29:36
log and authorize like so okay let's save that one remember that we need to export it so
6:29:43
module exports and that's equal to authorized awesome and then in the
6:29:50
app.js i'll just copy and paste and i'll say authorize like so
6:29:56
and of course the file name is also different it's not a logger so we can go with authorize
6:30:03
and once i have this setup in place the way we execute multiple middleware functions in app.use
6:30:11
we simply place them in the array so i'm gonna go with my logger first so logger
6:30:18
and then we're gonna go with authorize and now once you navigate to a localhost
6:30:24
5000 again any of them in this case because notice there is no path
6:30:30
first in a console i'll see this get and then authorize and that's something to
6:30:36
keep in mind where they will be executed in the order so if we flip this one
6:30:42
if i go with authorized first and then i go with logger then of course
6:30:48
in the console i'll have the opposite order where i'm going to have authorized
6:30:53
first and only then get so that's something to keep in mind now i'm going to go back to my previous setup the
6:31:00
logger and then authorized and now let's take a look at how we can have the if
6:31:05
condition in our middleware function now before we do anything let me just stress something very very important where this
6:31:13
is just for demonstration purposes this is just an example and it's not how
6:31:18
we're going to authorize users in our express applications i just
6:31:24
don't want to overwhelm you from the get go so i'm just going to show you simple example using the query string but again
6:31:31
this is not this is not how we authorized users in our express applications and with that said i'm
6:31:38
going to navigate back to my authorized middleware and in here
6:31:44
i'm just going to set up a query string so i'm going to say if the user
6:31:50
provides a query string in my url then i'm good to go then i'll
6:31:57
send back the resource that the user is requesting however if the user doesn't
6:32:03
provide the user query so query string parameter in the url then i'll just send
6:32:09
back 401 which just stands for unauthorized so let's start i'm going to
6:32:15
go with const and i'm going to be looking for specific query string i'm going to be looking for the user my url
6:32:21
parameter and of course we know that it is available in rec dot query like so
6:32:28
and i'm going to say if the user exists so if it's there with any value it
6:32:33
doesn't really matter which one or i don't know maybe if you want to make it more interesting let's go if the user
6:32:40
equals john okay if that is the case then i'm going to go with rec.user
6:32:45
and notice what i'm doing here i'm actually adding a property of user
6:32:51
onto the rack object and i'll show you why it's so powerful so i'm going to go with recuser that one
6:32:58
is equal to whatever i mean that could be a object for example and i'll say here name john
6:33:05
again this is just for demonstration purposes and then id i don't know four or three or whatever so that's my user
6:33:13
now i still need to call next if i won't do that then the whole setup is gonna go
6:33:19
bananas so i'm gonna go with next here and now of course i just need to set up
6:33:24
a response if the user or whoever is visiting
6:33:29
doesn't provide the query string with a key of user and then value on john and
6:33:36
in that case i'm going to go with my else and i'll say res and then let's add a status and the 401
6:33:45
is going to be for unauthorized and let's just say send and simply let's
6:33:51
try to spell this sucker unauthorized let's save that one
6:33:56
and now notice something interesting if i'm going to go for example to my home page or product again any of the
6:34:02
routes because there is no path in my app.used check it out i have
6:34:08
unauthorized and if i inspect and in the network tab the same deal i have 401
6:34:15
because i'm not authorized to access this resource i have my authorized
6:34:20
middleware whereas say you didn't provide the query stream parameter with
6:34:26
a key of user and more specifically you didn't provide here a value of john
6:34:32
and since you didn't do that you cannot access the resource so now of course if we change things around and if i go
6:34:40
with my question mark and if i say user equals john what do you know i have my home why well
6:34:47
because now the condition is met and now we just go to next now why it is so
6:34:53
powerful because in the authorized we add the user right so now of course not
6:34:59
only i can check for that query string parameter but and also access this info
6:35:04
again this is just demonstration normally what you're going to do you'll check for the
6:35:11
json web token and then if the token exists then we communicate with database
6:35:17
and actually get the user again this is coming up for time being we're simply
6:35:22
hard coding these values so back in the app.js in any of the routes now i'm not
6:35:28
going to add in all of them but just to showcase i'm gonna add for example in app items
6:35:34
i'm gonna set up here a log and i'll look for rec and user and you'll notice something
6:35:41
really cool where if i leave this query string parameter and if i go to
6:35:47
api and items check it out first of all i have the items and second in console what do i
6:35:54
see over here i see that user and that's why it's so powerful because we can add our middleware
6:36:00
we can do some kind of functionality and now basically i'm attaching this to my request object so i have the request
6:36:08
object and now i'm attaching this property here and now in any of my routes now of course i went with items
6:36:14
but in any of my routes i'll have access to that user that's why middleware is so
6:36:21
so crucial and that's why it is a big part of express applications because it
6:36:27
truly allows us to structure our applications as lego blocks so we have this piece of functionality we have that
6:36:33
piece of functionality and when we combine them we have this nice working
Additional Middleware Info
6:36:39
express server now like i already previously mentioned middleware is all over express
6:36:46
so just because we're done with our initial introduction doesn't mean that
6:36:51
you're not going to see middleware you'll see it all over the place but just to complete our initial
6:36:58
introduction i want to cover two common questions first well if we have access
6:37:05
right now to app.use since we know how to use it are we going to add the middleware in a
6:37:12
route and actually the answer is yes because imagine the scenario where i don't want to apply this app.use to
6:37:20
all my routes for example i only want to check for authorized users in the api forward
6:37:27
slash items what do i do well i simply add my authorized middleware correct so
6:37:34
now i'll be able to access all these routes without any issues but the items want yes
6:37:40
i'll check for that silly query string parameter and if you're wondering well
6:37:46
how we can pass two middlewares if you would want in a single route
6:37:51
same we just simply grab this array so we copy and paste and now of course once
6:37:58
i hit the items not only i will log but i'll also authorize
6:38:04
so let's go back and i'm going to take a look where in this case everything is fine
6:38:10
i was able to access the resource since i provided the john so notice here name
6:38:16
john id number three i also have my console log but if i were to go
6:38:21
to just my home page like so i have the home and as you can see i don't get
6:38:27
anything in a console i don't get my logger and i'm also not looking for any kind of
6:38:34
authorized user so that's the first thing that i would like to cover second
6:38:39
what are our options when it comes to middleware so far we have covered the
6:38:46
first one our own so we can always set up our own middleware now our other two
6:38:52
options are express so express provides quite a few built in middleware functions again in
6:38:59
this case we don't have to worry about setting up the functionality we just need to reference the docs to see what
6:39:06
options are provided and then of course supply those values and if you remember
6:39:14
the express app example we used app.use and i said put the pin
6:39:20
on this i'll explain this a little bit later if you want you can retype this but in my case i'm just going to copy
6:39:26
this from the for express app.js and if we copy and paste and if i place
6:39:34
it here notice so this is a app.use method now what argument the app.user is
6:39:40
expecting it is expecting a middleware so in express we have a built in middleware by the
6:39:48
name of static again somewhere in the express source code there is a code
6:39:55
similar to this now of course this is silly they have way more complicated setup but hopefully you get the gist so
6:40:02
there is a method and the only thing this method is looking for our public folder and then i already told you that
6:40:09
it basically places all the contents of public folder as our static assets so they're publicly
6:40:16
available so we already covered that one and now let me show you a simple example of third-party middleware now for a
6:40:24
third-party malware we'll have to install it and one of the most popular
6:40:30
ones i guess for the login is this morgan npm so again just go to your
6:40:35
search engine and type morgan npm that is going to direct you to the
6:40:40
docs i guess for the morgan and as you can see in order to install we just run
6:40:47
npm i morgan so that's how we install the package and the syntax is following
6:40:52
where we just go with morgan we required a morgan and then we just pass in morgan
6:40:58
tiny now of course this one we need to set it up in our app.use so this is really optional
6:41:06
you don't have to install it you don't have to run it but in order for me to hammer this home i will do that so let's
6:41:12
go back i'll stop my server and remember the command was npm
6:41:17
i and morgan okay i installed this one so now of course this package
6:41:23
is going to be in my dependencies like so so not only i have expressed i also have the morgan
6:41:30
and then in the app.js of course i'm going to have to require it so i'm going to go with const morgan and that is
6:41:37
equal to require and then again i don't have to provide the path
6:41:43
that's the module that i installed so i go with morgan and then where i have app.use
6:41:49
and go with app.use since i would want to add to all my rows again if you want to add for specific one there's a
6:41:56
different scenario but if you want to add for all the routes you just go with morgan
6:42:02
and then they basically give you multiple options and the tiny one is just going to provide you the most
6:42:08
essential data and again if you want to reference the docs please do so so i'm
6:42:13
going to go with morgan and now i just need to spin up my app and i go with npm
6:42:18
start now i will remove logger and authorized from my api items
6:42:24
just because i think the terminal is getting quite busy and now of course once i navigate for
6:42:31
example home page in a console i have get i have forward slash now this is a status code and then
6:42:38
i have 2.8 milliseconds and that essentially just signals how long it
6:42:44
took for the server to respond and if i were to go to localhost and forward
6:42:51
slash about now of course i'll see that i have get request i have about the 200
6:42:58
and now of course time is a bit different as well so hopefully this gives you a general idea
6:43:05
why middleware functions are so crucial and how powerful they are and yes the
6:43:12
bigger your express applications will get most likely the more middleware
6:43:17
functions you'll have now they could be your own ones they could
6:43:23
be the ones that provided by the express or there's also going to be tons of
Methods - GET
6:43:29
third-party middleware functions not bad not bad we have general understanding how middleware works in
6:43:37
express and now i want to cover rest of the http methods
6:43:43
so if you remember which seems like an eternity ago we covered the cycle the
6:43:49
request message as well as response and in request well
6:43:55
get was by default performed by browser but of course we have other methods as
6:44:00
well and i also provided a second slide just for these methods and here you can
6:44:06
see rest of the methods so get is again by default set up in a browser and this
6:44:13
allows us to read data then we have post that is for inserting data so for
6:44:19
example if we have some kind of api orders route we can add an order so user
6:44:26
makes an order and we just place that order on the server so of course
6:44:31
eventually we would say that in a database then we have put if we want to
6:44:36
update data and of course we also have one for deleting the data and before we
6:44:42
continue let me just mention something we're not going to persist this data so
6:44:47
yes we'll have working examples of post put and delete and hopefully i'll be
6:44:53
able to convey my message in a manner where you understand the
6:44:58
general setup for rest of the methods but since we haven't covered how to connect to database we won't persist
6:45:05
this data now i could have went the file system route where essentially we are persisting this
6:45:11
data by writing in a file but i thought it's a waste of your time because most
6:45:16
likely you're going to work with database anyway so we might as well skip that part so once we understand how we
6:45:22
can connect to the database what are the methods by working with data in our
6:45:27
database then we'll have a proper example where we're persisting in
6:45:33
as well and in order to kick things off i'm going to navigate back to my address
6:45:38
again the previous example is going to be in the file number 10 middleware options
6:45:44
and again we're just removing pretty much everything starting with morgan so
6:45:50
right after app and all the way to app.listen
6:45:56
like so now there's not going to be a home route however i'm going to go with api and
6:46:02
people now why do i go with api people because in the data file in the data js
6:46:08
where we had the product there's also this one people people is
6:46:13
an array each person is an object there's an id as well as the name as you
6:46:18
can see very simple example so with this data array i want to showcase
6:46:26
how we can read this data how we can add for example an extra person
6:46:31
using the post how we can modify the person as well as deleting one and now of
6:46:38
course i want to navigate to app.js and first i want to get my people so we
6:46:43
simply go with import i'll structure it right away and as a side note since i might make
6:46:50
some modifications i'll use let in this case and i'll set it equal to require
6:46:56
and then data hopefully this part is clear since we have covered it quite a
6:47:02
few times and let's start with the one that we already know and that is going to be a get method so i'm going to go
6:47:09
with app dot get like i said i'll purposely set up my route with a value
6:47:15
of api and people so that's going to be my path i'll say api
6:47:20
and then people now this is a get method and simply will return
6:47:26
this array so rec and res and again i'm just going to go with res status let's
6:47:33
hard code the value of 200 then let's set up our json and since i want to be
6:47:38
kind to my users i'll send back the object i'll say that the success property is true so the request was
6:47:46
successful and as far as data property well i'll set it equal to people so
6:47:52
let's navigate back to our browser and we're going to go with 5000 and of
6:47:59
course cannot get so this is going to be 404 if i just go to the homepage
6:48:05
and instead i have a route for api and i believe the whole path was people
6:48:12
like so so we run that and now of course i have zoomed in already massively here so let me zoom
6:48:19
out in my browser and we should see that we're getting our object the
6:48:26
success property is true beautiful and then of course we have the data property
6:48:31
and in there we have the people's array so a bunch of people in here so of
6:48:37
course that is our first http method that is the get one where effectively we
6:48:45
read the data and like i already have mentioned probably 20 000 times
6:48:50
that's the default method that the browser performs so
6:48:55
when you set up a request with your browser you right away use the http verb
Methods - POST
6:49:01
by the name of get and that's why you can read the data
6:49:06
all right so we're clear with get method that's how we can read there however how
6:49:13
we can add data onto the server so how we can insert data
6:49:19
and in order to do that we need to use a post method but it's not like i can somehow
6:49:25
configure browser and start making post requests unfortunately that's not how it
6:49:31
works that's why i provided a little bit of help now keep in mind one thing where
6:49:37
after we set up a post method effectively once we take a look at two flavors of how we can set up post
6:49:44
request we will install one more tool which is going to be crucial
6:49:49
in our express server development which is just going to allow us to
6:49:56
test everything much faster but since for the post i do want to show
6:50:02
you two flavors that we can have we'll use a little bit of static data
6:50:07
meaning there's an app that i prepared but don't worry it's not like you'll have to do that each and every time to test any of these
6:50:15
methods and you'll see what i'm talking about in the following videos so first let's start by jogging our memory a bit
6:50:22
we have app.use now what app.use is doing is just applies the
6:50:29
middleware to all our routes correct and i also mentioned that we have this option
6:50:35
of setting up a public folder now we can call whatever we would want
6:50:40
but for this methods example i prepared a
6:50:46
methods.public as you can see it is just a folder with index.html with javascript html
6:50:53
some css and once we navigate there of course i'll show you how the functionality
6:50:59
works so this is just prepared so we can test those other methods meaning more
6:51:05
specifically the post method because we cannot simply just perform a post request from the browser so first let's
6:51:13
set up that methods public as our public folder that's step number one so let's set it
6:51:19
up as our static assets and in order to do that i'm just going to add first a
6:51:24
comment and i'll say assets and then i'm going to go with app.use again remember
6:51:31
that is our method and this is going to be a built in middleware and the name is express static so i just
6:51:39
grab my express instance i look for the method of static and if you remember we
6:51:45
just need to provide here a path and instead of going public or static
6:51:50
like i showed you previously i'm just going to go with forward slash and then methods and then public
6:51:58
because this is where i set up my static files for these examples we invoke it
6:52:06
and now if we go to the home page we shouldn't get this error so once you invoke
6:52:12
there it is we have a somewhat decent looking html file with
6:52:18
two options we have this javascript option which we're going to cover second
6:52:23
and first one is going to be a traditional form example and again the
6:52:30
reason why we do that is because you cannot simply just configure
6:52:36
your browser to perform a post request you either need to use a
6:52:41
tool which we're going to install by the name of postman or insomnia here's another popular one
6:52:49
or you need to set up basically a working application and if you take a look in the methods
Methods - POST (Form Example)
6:52:57
public we have this working application all right and once we have the basic setup in place now let's take a look at
6:53:04
our two flavors when it comes to the post method
6:53:09
and i want you to navigate to index html and in there you'll find pretty typical
6:53:17
index.html file with some styling with nav as well as deform
6:53:23
and in form we have two attributes we have action one
6:53:28
as well as the method and as you can clearly see the value for the method is post
6:53:34
and this action one just says where we're going to send it and notice now we have forward slash login so that
6:53:41
means that this url this path is on our server but of course we know that in the app.js
6:53:48
we're not handling that so for the form there's going to be one path and then for the second example
6:53:54
when we used straight up javascript then of course there's going to be a different path for that so this is going
6:54:01
to be the url or path where we're submitting the form and inside of the form we have label we have input
6:54:08
so basically we have name attribute for this one we have the id
6:54:13
as well as the autocomplete so we'll type in some kind of value and then
6:54:18
we'll send this to forward slash login so localhost and then forward slash login and of course
6:54:26
we also have a submit button so now let's start by taking a look what
6:54:32
happens when we simply submit this form so go here type some kind of gibberish
6:54:38
in my case i'm going to go with john bravely press enter and of course we do
6:54:44
have kind of post login okay that's fine we're not expecting anything anyway
6:54:49
right we know that there is no route that handles the post
6:54:55
for the login but what's really interesting here is in the network tab of course i can
6:55:02
see my request in this case this is login now this is
6:55:08
404 and again i'm going to repeat this 20 000 times but check out the method so
6:55:13
method is not get method is post and then we're going to localhost 5000 and then forward slash
6:55:21
login now what's also really interesting all the way in the bottom
6:55:26
what do you see here you see this forum data and then we have key value pair we have
6:55:33
name and john and if you remember when we talked about http messages i
6:55:40
said that the body is optional so for example when we're sending a get request we're not sending a body
6:55:46
but when we're sending a post request it's very crucial so if i want to add
6:55:51
something onto the server of course i want to get that data
6:55:56
i mean otherwise how i'm going to know where to add to the server doesn't that make sense i hope it does so let's go
6:56:04
back okay i see this name and i see john and if you're not familiar basically the
6:56:10
way it works is whatever you provide here for the name is going to be a key
6:56:16
so for example if i'm going to set this up as testing you'll see that now when we
6:56:23
perform the same request the same post request again with the same value different value it doesn't really matter
6:56:29
now of course that key name is going to be testing so whatever value you provide over here that is
6:56:36
going to be the key and of course the value is whatever you're submitting so
6:56:41
in my case it's either peter or john okay
6:56:46
that's out of the way so i'm going to change it back to name and now we need to understand something
6:56:53
where the request is coming in but a we're not handling that
6:56:59
and b we don't have the middleware that actually adds this data that the form in
6:57:06
this case is sending to our request so let's see how we can fix the first one
6:57:12
and we simply need to come up with a round now in this case remember we're dealing with post this is not get
6:57:19
and we're going to go with forward slash and then log in here because of course
6:57:25
that's what i have in my form again we go with rec and res and technically we can come up with some
6:57:32
kind of info i can say send and i'm simply going to say post
6:57:38
and that's it just so we can save time on typing again let's navigate back and
6:57:44
in this case let's try susan let's send it yeah i see the post so i don't have
6:57:50
the 400 anymore or 404 so that's cool but unfortunately i have no access at
6:57:58
this point to whatever i'm being sent so unfortunately i cannot access that
6:58:04
susan or john or whatever value so unfortunately i cannot add for example to my list if i
6:58:12
wanted to now how do we add it well this is where the middleware comes in so
6:58:18
previously we covered static assets with express static in order to get the form data
6:58:25
we need to go with url and coded middleware so i'll add here
6:58:32
parse form data and essentially this is just going to parse that data and add the
6:58:38
values to rec.body so where we have a post request
6:58:45
in the rec.body property we'll find all the info
6:58:50
and in order to use this middleware surprise surprise we're going to use app.use
6:58:55
and then we'll pass in express and then url encoded and then you also
6:59:02
pass in flag where you go with extended and you set up false and if you're
6:59:08
wondering why are we adding this extended false flag or you just want to get more info about this url in coded
6:59:17
middleware simply let's head back to the documentation in this case we're looking
6:59:22
for the express and notice here i have express url encoded this is a built-in
6:59:30
middleware function in express it parses incoming requests with url and coded
6:59:36
payloads and it is based on the body parser so in the previous versions of
6:59:42
express you have to actually install the body parser now in this case you don't
6:59:48
it already comes built in and as far as this extended this option allows to
6:59:53
choose between parsing url encoded data with query string library when false
6:59:59
meaning this is our case or the qs library when
7:00:05
true again i wouldn't lose my sleep over this one then the common approach is
7:00:10
using this extended and false and once we can access it then we can do some
7:00:16
cool functionality so first let's just scroll down a bit where we have the login and first i'm just going to start
7:00:23
by console logging rec and body let's save that one and again back to our browser
7:00:31
again i'm going to go with susan this was 200 so everything was successful and
7:00:38
now of course in the right dot body i also have a name and the value is susan
7:00:45
so now we can start doing something with this data now i purposely set up two
7:00:50
examples one is going to be for form which of course is this one and then one is for
7:00:56
javascript now with the javascript example this is where we'll actually
7:01:01
manipulate this people array fourth time being with login this is a separate
7:01:07
issue we're just dealing with the form so we'll just try to make things interesting by checking for the name
7:01:14
if the name is provided then we'll send back welcome and then pass in that name
7:01:19
if the name is not provided so for example if the user is trying to submit the form empty for
7:01:26
example like so we'll just send back 401 please provide credentials again
7:01:32
please keep in mind this is just a example and i'm fully aware that we can check for empty values here on the front
7:01:39
end again the goal of this example is to show you how to handle this on the
7:01:44
server so i have wrecked that body okay i can see that in this case i have
7:01:50
name but it is empty so now of course let's set up our logic first i'm going
7:01:56
to go with const name and that one is equal to rec that body so i'm destructuring my name
7:02:03
property and i'll just check if the name exists whatever the value that could be
7:02:09
b that could be bobby lee not could be again taco burrito whatever you want and
7:02:15
as you can see i'm getting quite hungry so let's go with return res dot status
7:02:22
then let's set up a 200 which just says that we were successful
7:02:29
and we're gonna go with send and we'll set up a template string
7:02:34
welcome and i'm just going to access my name so if there's some value i'll send back
7:02:40
200 and i'll say welcome whatever is the value if not well here we're going to go with res
7:02:48
and let's just add status here and again just for kicks i'm going to go with 401
7:02:54
and we're going to go with send and of course let's say please provide
7:03:00
and credentials like so let's save this one and now we should
7:03:07
truly see how it works in the action now i'll leave i guess the tab for now
7:03:14
and let's just try to submit so for example if i submit with empty values
7:03:21
i'm going to say please provide credentials and as far as my login it is 401
7:03:26
that's what the server is sending back however if i type in some kind of value
7:03:31
for example anna comes to mind i have welcome and anna so that's our first
7:03:37
flavor when it comes to post request where we use the form and again this is
7:03:42
just front end where we come up with an action and since this index.html is on
7:03:48
the same server we simply go with forward slash and login of course if
7:03:54
your front-end application is separate from your server then you're going to
7:03:59
provide a full path where the server is hosted so basically a full domain and
7:04:06
then we go with method post now this is technically a front-end part but it is crucial that we understand it so then we
7:04:14
perform of course a post request we hit our url
7:04:20
so in this case we hit our forward slash login and this is the part where we
7:04:25
handle that on a server in order to get that data whatever we are being sent we need to
7:04:33
use a middleware this one is built into express so again we simply just need to
7:04:38
use app.use which is going to apply this middleware to all our incoming requests
7:04:46
and then we just pass an extended false flag and the moment we do that
7:04:52
indirect.body will have access to our form values so whatever
7:04:58
is set up here as a value that is going to be our key and whatever is passed
7:05:03
into our form well of course that is going to be the actual value that we're getting so if i go here with name i'm
7:05:10
gonna see either susan anna or whatever user provides now like i already
7:05:16
previously mentioned this is just for demonstration this is just so we have a bit more interesting example e instead
7:05:23
of just sending back the name so hopefully this part is clear
7:05:30
and now we can focus on our second flavor where we use javascript to
Methods - POST (Javascript Example)
7:05:36
send the request all right and once we have the form set up out of the way now
7:05:43
let's take a look at the javascript option before we do though there's one more thing that i would like to mention
7:05:50
if you take a look at the headers you'll notice something interesting
7:05:55
where we have a content type for the request header and of course this is
7:06:01
going to be application and then we have this form url encoded
7:06:07
and the reason why i'm showing that because of course for javascript it is going to be a bit different so just keep
7:06:14
this one for your reference now let's navigate back to our
7:06:20
static files basically to our front end and now let's take a look at the
7:06:25
javascript approach and interestingly here where i have the javascript i do have
7:06:30
the form keep in mind we'll still handle this form but in this case it's going to be
7:06:35
done strictly using javascript and we'll use javascript to send our http requests
7:06:42
and that is very very crucial that is going to be the difference where instead of form now i'll be sending that request
7:06:49
using javascript and of course the content type will be different that's why i showed you the
7:06:54
form example but what you'll also notice that right away we have our list and if
7:07:00
you don't believe me you can double check in data we have john peter susan anna and emma so what's happening well
7:07:08
let's go to javascript html this is where we have our frontend logic
7:07:13
and again let's take a look at our index html a little bit of css
7:07:19
nav and then we have the form now in this case i don't have the action and i don't
7:07:24
have the method okay interesting so i have name attribute it still has a value of name
7:07:31
so i should expect probably that this is going to be the value that's coming in
7:07:37
with my request then i have a little bit of form alert this is where we'll display a little bit of functionality as
7:07:44
well as the result now if you're not familiar there's a package called axios which
7:07:51
essentially just makes it easier to set up http requests so
7:07:57
instead of using the built-in fetch which i could have used i think axios provides a cleaner api and better error
7:08:05
messages and since i don't want to spend three hours on explaining all this code
7:08:13
i simply went with axios and the way i set it up i just set up the cdn link so
7:08:21
this just gets me the axios library and then the moment i install it of course i have axios in my front-end project
7:08:29
please keep that in mind those are two separate things this is a front-end project and
7:08:35
in order not to confuse you more i just set up a few script tags instead of
7:08:40
going with a separate javascript font so as you can see here i'm selecting the
7:08:46
result so that is my div and i have this fetch people
7:08:52
so that is the function that fetches people from my server now notice the
7:08:59
path it is api and people why well because
7:09:05
in my server i have also api people so this is for get requests
7:09:10
that's the default one however in this case we're not doing that with a browser we're doing with javascript so axios
7:09:18
has the method by the name of surprise surprise get that just means that on the
7:09:23
front end we're performing a get request to the same server that's why we go
7:09:29
forward slash api and then people so make sure these urls match
7:09:35
so if these paths won't match then you'll have an error and to showcase that if i go with p poles
7:09:42
then if you navigate to the front end and if you refresh can't fetch data so we try to fetch people from our
7:09:49
server then we do a little bit of logic and this is just vanilla.js not going to cover it basically we tear it over and
7:09:56
then we just set up a nice heading 5s and all that and then we invoke the
7:10:02
function but if there is an error we'll look for the error property now in this case i'm not
7:10:08
the structuring it i'm actually not using it i just say can't fetch data so
7:10:14
that's step number one now the second one is of course using the form
7:10:19
so then i select the submit button i select the form i also select the alert
7:10:26
because we will display an alert if the value is empty and again let me repeat
7:10:31
i'm fully aware that we can check for that in the front end i just wanted to showcase the server setup and then
7:10:39
notice something interesting where i have this try and catch block in my
7:10:44
functionality so the moment the user is submitting the form of course i invoke
7:10:49
my callback function it is a sync because for the actuators i can wait for
7:10:54
response and notice this one so i have axios and again surprise surprise the
7:11:00
method name is post why because we are sending a post request and this is just an axiorys thing but
7:11:07
again we provide the value in this case the url value is api and people so
7:11:13
something that we're not handling yet on our server and this is the value
7:11:19
so again this is just axio syntax where in order to set up whatever data you're
7:11:25
sending you just pass it as a second argument and you set it up as a key value pair now what's really cool that
7:11:31
would axios they set up all the content types and all that good stuff for you so again you just save a little bit of time
7:11:38
now if there is an error in our case that is going to be if we're trying to submit something and in fact there's no
7:11:46
value meaning we just try to submit empty form value then we will display
7:11:51
the error message and again this is really cool because axiorys just provides a very useful
7:11:58
error api unlike the fetch where you really need to jump through the hoops so let me save it
7:12:04
back to people so we can see of course all the people that
7:12:10
we have in our array currently and then of course we'll focus on this post one
7:12:17
so as you can see i get the input value and i just passed it in as a
7:12:23
name property awesome so now back in our app js of course we need to handle it
7:12:29
and please keep in mind one thing where app dot post and then api
7:12:35
and people is not the same as api get and api people
7:12:41
even though the url is the same methods are different and that goes for all the methods we're going to use
7:12:47
whether you're talking about put delete or whatever so just because the urls are the same
7:12:53
doesn't mean that they mean the same thing no the method is different here i'm just
7:12:59
reading the data i'm reading data from api people here i'm actually trying to
7:13:05
add data and again we're going to go with wreck and res
7:13:10
and let's just go with some simple response now for time being i'm just going to say
7:13:17
that my response is going to be 201 now that's the response that we send back if we are performing a post request and we
7:13:25
are successful so i'll just say res that status 201
7:13:31
and for time being let's just say send and i'm just gonna say success and of
7:13:36
course now what i would want is to navigate back to my javascript one
7:13:42
hour fresh i'm getting all my people and now let's try it out so i'm gonna send
7:13:48
this one so i sent again here nothing changed but if i take a look at my network tab
7:13:56
i should see and by the way sorry i'll have to do that one more time let's go with i don't know susan here let's try
7:14:04
to submit and there it is now of course i have api people and 201
7:14:11
so that's the response that i'm getting on my front end so let's bravely click
7:14:16
on this one and we can see that the request url is api people okay
7:14:23
the method was post now the response was 201 so it was successfully created and
7:14:30
now check it out when we look at the request headers of course we have
7:14:35
application json so on our front end we do need to add this content type
7:14:41
when we are sending the data now again what's really cool about axios it adds
7:14:47
for us but in general you need to keep that in mind and there it is again we have this
7:14:52
request payload and the name is equal to susan so whatever i'm going to pass it in if i'm
7:14:59
going to send it empty then i'm going to still have the key name and the value will be empty now the
7:15:05
gotcha here is even though we're handling a form submissions we're not handling the
7:15:11
json data so yes we know how we can send back the json data but we're not
7:15:17
handling the incoming json data and this is where another middleware comes into
7:15:22
play so i'm going to say parse json here
7:15:28
and we simply need to go again with app.use and we go with express
7:15:33
and json now in this case i'm not going to go to documentation if you want you can do that in my case i
7:15:40
will try to save us a little bit of time and we'll skip that and here we have api
7:15:46
people and now similarly to our login we have access to the form data that is
7:15:54
being sent with javascript in the rec dot body previously
7:15:59
before this was added no we have no access yes when it comes to form that
7:16:05
was one setup now when it comes to straight up http requests for example in
7:16:11
this case sent with javascript no we had no access so we were getting a json
7:16:16
and now we added a specific middleware that handles that so of course in this
7:16:21
case now we can set up more logic correct we can say that we're looking for the name and if the name is provided
7:16:30
then awesome then i'm going to send back that new person that was created so we
7:16:36
can add it to our front end and again this is the case where we're not persisting this data anywhere later
7:16:42
we'll learn how to do that for now i already have the code that adds it to our front end however if the user tries
7:16:50
to submit without any values well then there's going to be a error message so
7:16:56
in the api people in the post method let's set up our logic
7:17:02
where i'm going to go with const name is equal to rec.body
7:17:07
the middleware makes it possible now and then i'm going to say if the name is
7:17:12
not provided well then i'm going to send back the 400 then i'm going to say please provide name value so there's
7:17:19
going to be a error message so i'll say here if and exclamation point and if the name is not
7:17:26
provided then let's go to return res dot status and for the request error we
7:17:34
go with 400 that's the status code and then let's go again with json and in
7:17:40
this case we're gonna go with success now this success will be false and then
7:17:45
we're going to go with message again i would suggest using the same properties because of course i'm handling them on
7:17:52
the front end as well so in here i'll say please provide name value like so now if the value is
7:18:00
provided whatever it is then of course we can send back res.status 201. hey
7:18:06
guys it's john from the future with a small update as you'll see in a second while i was
7:18:12
recording i forgot to change the methods so instead of writing json i just left
7:18:18
it as send and while we can get away with it in this example normally you always want to
7:18:24
use json instead so make sure you change your method from send to json and in
7:18:31
this case let's just set up a proper object we'll say success is true so now we're being
7:18:38
successful and i'm just gonna send back that person now i'm going to set it up with person key and the value will be
7:18:45
named whatever i'm getting again please use the same ones if you want to have a same result now
7:18:52
let's navigate back we can refresh just so we are all on the same page and if we
7:18:59
type susan now we should see another susan added to our list and then again we can go with john and
7:19:07
i'm just being lazy on coming up with original names and as you can see every time we add
7:19:14
value in our form we're being successful we're actually getting back this value
7:19:19
from our server and then we dynamically added to our front end and again the
7:19:24
reason why we're doing this way is because we're not persisting this data so that's why the setup is following
7:19:31
later of course we'll learn how to persist this in a database as well and if i try to submit with empty value
7:19:39
check it out now of course i have people and this one is what 400 right
7:19:45
notice here and it says please provide name value now if you want to do a bit
7:19:51
of console logging you're welcome to do that on the front end if for example you
7:19:56
are iffy about the syntax but just to let you know when we talk about axios
7:20:02
here effectively we're getting back the whole thing so when we perform a request http
7:20:09
request with axiorys we're actually getting back a giant object
7:20:15
now what we're interested in that object is a data property so that's the response that is coming
7:20:22
back from the server and then in here as you can see i set up
7:20:27
a heading 5 with data.person so that's the person that we're sending back from
7:20:33
our server now if for example there is an error we go with error response again data property
7:20:41
because that's where the useful information sits because the object of course is giant with lots of useful
7:20:48
information but as far as what we're sending back it is sending in data and then message now i'm looking for the
7:20:54
message property of course here because i set up a message property
7:20:59
on the server hopefully it is clear this is our second flavor
7:21:05
where effectively we perform a post request from the application
7:21:10
and of course in that case we do need to provide content type as well as the data and next video we'll install
7:21:17
and cover some basic setup for a very useful tool that is going to save us a lot of
Install Postman
7:21:24
trouble when we work with post delete as well as put methods
7:21:31
all right so at this point we're familiar with two ways how we can send a
7:21:37
post request so we covered how we can do that using the form as well as straight up http request in
7:21:45
our case using javascript however there's a major problem in our
7:21:50
current setup and the problem here is following if we need to create a frontend to test
7:21:58
something for every route as you can see i mean our development is going to be
7:22:03
extremely slow because we can clearly see that it's probably going to take us way longer
7:22:10
just to set up a front end than setting up just one simple route so every time i
7:22:16
create a route i'm probably going to spend i don't know five six times more on setting up the front end where i can
7:22:23
test this route and of course there has to be a better option and that better option
7:22:29
is a tool called postman and postman is just awesome for quickly
7:22:36
testing our apis so at this point i strongly suggest that you navigate to
7:22:41
postman.com again it's a free tool so you're not going to have to pay anything but for mainer of the course yes we'll
7:22:49
use this so if you're kind of iffy about installing something new this is something that is required so navigate
7:22:57
to postman.com and then they'll try to sign you up you
7:23:02
don't have to do that just keep scrolling down keep scrolling down and all the way in the bottom you'll see
7:23:09
this download app option go here and they'll right away detect which operating system you're using of course
7:23:15
in my case that is mac so download the application once it's on my computer i'm
7:23:20
going to navigate back to the desktop i'm going to go to downloads i'll crack it open then of course i'll just move it to my
7:23:27
applications like so and i already had one on my computer but i removed it so
7:23:33
we can do these steps together then this is the application let me zoom in that's
7:23:38
the postman so just click on it and then it's going to spin up the app
7:23:45
and eventually you'll hit the dashboard and i'm not going to spend half an hour on this
7:23:52
setup but of course as we're progressing we the course as we're progressing with
7:23:58
our examples we will cover more features that this app provides
7:24:04
and basically here you'll have all your requests that you can actually group in
7:24:10
collections and again that's something that we'll cover a bit later and this is where we can make those requests and in
7:24:17
order to create a new request we just click on this plus sign and check it out so at the moment i have untitled a
7:24:24
request in here i need to enter the url and i can send my request not orders here on
7:24:31
left hand side what do i have i have get but what's really cool i have all these
7:24:38
methods available as well so first let's test out the get route and then we'll
7:24:43
see how we can deal with post route as well now as far as our url what it is
7:24:49
well it is localhost 5000 and of course the full url is api and
7:24:57
people now this is for the post as well as the get and since we're testing it of
7:25:02
course that's why we have a method with the value of get so let's go here local
7:25:09
host and then five thousand then forward slash api
7:25:15
and people and the moment i click send check it out what do i see here in the
7:25:20
bottom i see my object the success value is true and there i have my data so as
7:25:27
you can see the moment i create my route for example post route or put route or
7:25:33
whatever i can test it immediately i can test it within a few seconds instead of
7:25:40
building the whole front end just so i can test one route and of course once we
7:25:46
have covered get route now let's see how we can deal with a post route so we need to change the method of course
7:25:53
now the url still stays the same because i do have a route for the post as you
7:25:58
can see and in here what i'm looking for i'm looking for the name in the body
7:26:05
and how do we construct a post request in a postman well we do that in a
7:26:10
following way first we go to the body and we look for raw and instead of text i go with json
7:26:19
because i'm going to be sending a json data so this is not the case where we're working with the forms in this case
7:26:26
we're sending a json data and what you'll notice something really interesting in headers right away
7:26:34
there's going to be a content type so let's see let's set up first the body
7:26:39
and you'll see how it gets added so we're gonna go here with a name again
7:26:44
this is what i'm looking for that's why i need to pass it and then i'm gonna set up some kind of value now since i'm
7:26:50
setting up the json please remember that we need to use double quotation marks so i'm going to go here with john and if
7:26:57
you paid attention previously we had eight headers and now we have nine so
7:27:02
i'm gonna go back and there it is now i have content type application json so
7:27:09
that's really cool we don't have to do anything the header gets added for us and of course the moment i click send
7:27:16
check it out now i have success true and person john why do i have that well
7:27:22
because that is my response i have success true and of course whatever name
7:27:28
i received i just sent it back so now of course let's quickly test out our 400 as
7:27:33
well so i'm going to navigate back and then in the body i'm just going to send
7:27:39
a empty string or you can remove name altogether that's really up to you and
7:27:44
now of course i have 400 bad requests and success is false and of course i can
7:27:51
see the message so as you can see we can test it within seconds and to really hammer this home why don't we create
7:27:58
another post route and quickly set up some kind of response and let's test it
7:28:04
out in our postman as well so i'm going to go in between the post and login i'm
7:28:10
just going to go with app.post and the route is going to be following
7:28:15
i'm going to go with path of api people people
7:28:20
and i'm going to add a postman here or you know what let's do it this way let's go postman
7:28:27
and then people like so and then as far as the callback function
7:28:32
again we get rec res and then in the body again i'm going to be
7:28:39
looking for the name property so i want to get that name so i'm going to say
7:28:44
that i'm expecting it we'll go with name rec dot body again if you want to cancel log
7:28:51
the body you can do so but i think we have done that quite a few times so i'm going to omit that then i'll copy and
7:28:58
paste my response so again if the name is not provided meaning if the property is not
7:29:05
there or if it's just empty i'm sending back to 400 however if i'm successful
7:29:11
then i'm just going to take my array i'll add that extra person and i'll send
7:29:16
it back now i'm not going to add the id i'll leave that one blank because eventually database will do that for us
7:29:23
so i don't really see the point of doing that manually so i'm going to go back to
7:29:28
my api postman people and then again this is my error response and now let's
7:29:34
copy and paste our status and then instead of sending that one person we
7:29:40
created why don't we do this why don't we go with data and then of course the array name is
7:29:46
people and now as you can see i'm using the spread operator and i'm just going to add that one single person so i'll
7:29:54
save now of course we do need to change the route so it's not going to be api
7:29:59
it's going to be postman and then people like so now let's add
7:30:05
for example peter and the moment i click send there it is i have my success true
7:30:11
and as far as data all the way somewhere should be peter as well so again we just grabbed that peter
Methods - PUT
7:30:19
and then we added to our array hopefully this makes sense and now of course we can work on other http methods as well
7:30:28
all right and once we're familiar with postman now let's work on the other two
7:30:34
methods so now we're gonna be working on put method as well as the delete
7:30:40
so i'm gonna scroll down and below the post login route i'm gonna go with app
7:30:47
and then put now again this method is for editing the data so put method is
7:30:55
for update and again the convention is following where if we have a list for example in
7:31:02
this case that would be api and orders if we want to edit or delete we go with our route parameter
7:31:11
where effectively we set up a route for api orders and then we go with colon id
7:31:18
and this is going to get me that one specific item now please keep in mind one thing where this is a convention so
7:31:26
technically there are multiple other ways how you can set it up but there's a reason why that convention exists and
7:31:32
that's why throughout the course we'll stick with this convention i'll cover the official name of this convention a
7:31:39
little bit later as well as a bit more details about it for now i just quickly want to cover both of the methods so i'm
7:31:47
going to navigate back i have my put method that is for modifying the data
7:31:52
and in our case what is the url for the whole list because that is api people so
7:31:59
this was just for testing correct and then we go with api forward slash
7:32:05
and then we go with people and then of course i also want to add that id so this is going to get me that
7:32:13
one specific item and again the reason why we're doing that because when we'll send our
7:32:19
put or delete requests we'll send to a specific path
7:32:24
so this is going to be that one item and if that item exists then in the body there's going to be
7:32:31
data to update or in the case of delete there's going to be nothing in the body we'll just
7:32:37
remove that item and you'll see how it works in a second so please be patient so we're going to go with people and
7:32:43
then remember again we have route params and in this case i'm not going to call this person id i'm just going to say id
7:32:51
just remember that we can call it technically whatever we would want and now in this case there's two things that
7:32:57
i'm looking for first i want to get the value here in the params and remember we
7:33:02
access that using the rec params and the second thing when it comes to update
7:33:08
when it comes to the put request i'm also going to send something in the body why well because if i'm updating
7:33:15
for example if i'm changing the name from peter to susan or whatever of course i also need to supply this value
7:33:22
so you need to understand that there's two sides of this request not only we're looking for that specific
7:33:29
item that's why we use the params that's why i specifically say hey i would like to get the item number one or item
7:33:37
number two i also need to supply this value because otherwise what's the point of updating something so let's access
7:33:44
both of those things let's say that i'm gonna get the id from rec params so this
7:33:51
is going to tell me which item and then the second thing since of course i want to update that item i need that value as
7:33:58
well correct so we're going to go here with const and i'm going to be again looking for
7:34:04
the name and we'll say reg dot body and that's it that should do it so these
7:34:10
are the two values that we're gonna get from our question and just to make
7:34:15
things interesting i will console log them right now so i'm gonna go back to
7:34:20
the postman and remember we need to change the url it's not gonna be api
7:34:26
postman in this case it is going to be people and now you can select any of the
7:34:31
ids whether that's one all the way up to the five so we go here with one
7:34:38
and then as far as the value what is the value for the first one it is john so kind of makes sense if i'm updating that
7:34:45
i go with peter correct so we have put request we have api and then people and
7:34:51
then check it out the moment we send it now of course the request is hanging don't worry about that but in a console
7:34:59
we should get api people and then the id and of course the reason why i don't see
7:35:05
anything because i was smart enough and i didn't console log anything so i'm gonna go back with id name and you know
7:35:12
what for timing let me just send back hello world okay let's go here
7:35:17
let's actually send it one more time as you can see could not get the response that was the error this time in this
7:35:24
case i am getting hello world so that worked beautifully and as you can see the status code is 200 as well and then
7:35:32
in the console i have one and i have the repeater so this is going
7:35:37
to be the id and of course this is going to be the value now if i'll change it of course if
7:35:42
i'll say number two and if i'll send it again i get back my response and now the
7:35:48
value for the id is due hopefully this makes sense so now of course at this
7:35:54
point we need to set up the logic again we are going to set up the logic with
7:35:59
our local data with our people array eventually in next examples we'll work
7:36:05
actually with database but the main idea is exactly the same where from the postman while we're
7:36:11
testing we're sending the id in the url basically we add that url
7:36:17
parameter and then in the body we'll send the value so that part won't change
7:36:23
just the functionality in here and as far as this functionality well since we have a simple javascript array first i
7:36:31
would just want to get the person with that id if the person doesn't exist
7:36:37
then i'll send back the error response and if the id does exist then i'll just
7:36:44
change the value now i'm not going to be looking for the error message if the value is not provided we're going to
7:36:50
cover that once actually we work with database i think is just going to be at
7:36:55
the moment waste of our time so let's do it people i'm going to remove both of these
7:37:00
console logs hopefully you understand how we supply both values in the postman
7:37:06
and i'm going to start by creating a person and this is going to be equal to people
7:37:12
dot find again i have the array so i have access to all the array methods and
7:37:17
then if the person id matches to my params id then of course i'm going
7:37:24
to get the person now let me check in the data notice i still have it as a
7:37:30
number so i'll have to change the type as well so i'll say if person id is
7:37:35
equal to a number and i'll pass in the id that i'm getting from my params
7:37:41
whether that's one five or maybe it's going to be id that doesn't make sense all right good and if the person doesn't
7:37:48
exist well then i'll send back the response now again in order to save us a
7:37:54
little bit of time i'll scroll up and i'll look for any of my error messages
7:37:59
since i just want to copy and paste and change some values around so in this case i'm going to look for this name if
7:38:06
it doesn't exist then of course we have the error and in our case of course we just need to
7:38:12
change it around if the person doesn't exist so if we cannot find that in the array then we're sending back 404
7:38:21
remember that was the status code if we cannot find the resource and as far as
7:38:27
the response we have success and of course it's going to be false and now let's go with message and in the message
7:38:34
we're going to use a template string we'll say no person with id
7:38:39
and then i'm just going to pass in the id so that's the first response if
7:38:45
of course the person doesn't exist so if in the primes we enter for example value
7:38:50
six we know that we have only one to five or abc now the second thing if the person
7:38:57
doesn't exist now of course i just want to iterate over the array and for that specific person for the
7:39:05
person whose id matches my params value i'll change the name since i'm expecting
7:39:12
that one to be in the body again we're not going to deal with this error for now we'll do that once we work with
7:39:18
database and we're going to go with new people new people here and we'll say people
7:39:25
map so i'm iterating over my array again i'll reference each and every person as
7:39:32
a person and i'll say if person id matches to that one i have in params so
7:39:40
number id again then i'm going to say person name since that is the only other property i have
7:39:48
is equal to my name now where i'm getting the name because i'm getting it
7:39:53
from the body so if the id of the person matches to that one in the params then please
7:40:00
change the name that i can find in the body if not then simply return a person return
7:40:07
a person and now of course all the way in the bottom i'm going to go with res dot
7:40:13
status and then we're sending back 200 since the request was successful as far
7:40:19
as the json we go with success or sorry not super we're gonna go with success
7:40:26
true and then as far as data well now i'm sending back the new people so let's go
7:40:33
back at this point i have two so let me change it back to 1 because i
7:40:38
know for sure the first value was john so again the path is api
7:40:45
people and then id of 1 and i just want to change it from john
7:40:51
to peter so let me double check in data this should be john uh it's a good thing
7:40:57
i didn't go with the idf2 since that one is already peter so now let me send it and check it
7:41:04
out now i have success true and data of course is my array and instead of
7:41:12
name being john for the person number one now the name is peter and of course if i'll do the
7:41:19
same thing for example for the person number three again we send it back of course now i have three
7:41:25
peters because i just keep changing those values again we're not persisting that data but while we're making
7:41:32
requests you can clearly see how we are modifying this data and we do that using
7:41:38
http put method and then of course the path
Methods - DELETE
7:41:44
is api people and then whatever the id and again the whole reason why is that
7:41:49
happening because on our server we are handling that all right and the last method i would
7:41:56
like to cover is a delete method so below the put method below the modify option i'm going
7:42:04
to go with app and the method name is delete again the convention if you have
7:42:10
a list is going with a list url and then add that specific id because the setup
7:42:17
is going to be extremely similar to a put one now the only difference is going to be that of course in this case when
7:42:24
we're deleting we're not expecting anything in the body
7:42:29
the user hits the url for example api people and then one we just remove that
7:42:35
sucker from our list that's it so let's go down where we have
7:42:41
app delete and again the path is following where we go with api
7:42:46
and then people and again let me stress one more time something where these routes are
7:42:54
different when we talk about app.get and api people when we talk about
7:43:01
app.post and api people or even if we talk about app.put and app.delete
7:43:09
just because the path is the same since the method is different these are different requests that is
7:43:16
crucial please don't think that just because you have a different method you have to set up a whole new path no
7:43:24
you can have the same value for the path if the method is different that is totally different request so let's go
7:43:31
here again with our callback function we should already be comfortable with this one we have rack and res and in this
7:43:38
case i'm not gonna the structure out the id from the prompts i just want to showcase that we also have this option
7:43:45
of accessing the params directly so first again i want to look for the
7:43:50
person then we'll send back this response and yes oftentimes put and
7:43:55
delete are going to be extremely similar and then if the person does exist then
7:44:01
of course i'll just filter out the array and remove that person from the array
7:44:06
since again the whole point of this request is to remove that person from
7:44:11
the array so in this case you can actually copy and paste and i
7:44:17
know that some of you might find that annoying but at the same time we do need
7:44:22
to speed this up and start working with a database so hopefully you can forgive
7:44:27
me i'm just gonna grab everything starting with the person all the way until the end of our error response d404
7:44:36
let's scroll down copy and paste and this is what we're trying to do so i'm trying to find a person whose id
7:44:45
matches that in the params and of course in this case i haven't destructured out
7:44:50
the id right so i just need to change this around where i go with rack and then params and the id again the
7:44:58
setup is exactly the same the difference is that i'm directly accessing the
7:45:03
params object and if the person doesn't exist then we send back d404 so let's try this
7:45:11
response i'm gonna go back to my postman again the api is people but we need to change
7:45:20
the method right so now i would want to delete and since i want to test out the error and as a sign up you can send the
7:45:27
body doesn't really matter we're not handling that on server anyway so it's
7:45:32
really irrelevant but since i want to test out the error i'm going to go with abc so again the path is localhost api
7:45:40
people and then abc and if everything is correct i should see the error and of
7:45:46
course there is but something tells me that this is a different error so let's go back and check it out and of course
7:45:53
the issue is following notice here in the json how i'm accessing the id now of
7:45:59
course i haven't destructured it right in this case i went with rec params and then the id so i'm going to go with rack
7:46:06
params and the id let's save it and let's try one more time again i'm
7:46:12
looking for a person whose id doesn't exist so i'm gonna get the error and
7:46:18
there it is i have success false and as far as the message no person with
7:46:24
id of abc so i was looking for the person
7:46:30
with id that's not in my array so that's why of course i got back the error response so
7:46:37
now i'm gonna go back to our app delete request and here i just want to filter
7:46:43
out the array and the way we're going to do that i'm going to go with const new people
7:46:49
is equal to people.filter that's my array and i'm just filtering
7:46:54
it i'll pass in my callback function and i'll reference each
7:47:00
object with the person parameter and i'll just say if person
7:47:06
id does not match the id found in rec dot params then
7:47:12
return that person if it does match then it's not going to be included that's why we go with
7:47:18
exclamation point and remember that we still get our id as a string so we must
7:47:23
do the number one first and then only we go with params and the id so that's our
7:47:30
new array without that specific person whose id matched the one in params so now of
7:47:37
course let's just go with our return return res dot status
7:47:43
here and this is going to be 200 of course and i'm going to go with json and we'll
7:47:49
set up our object success is true and i'll send back the new people array
7:47:56
so we're going to go with data and then new people let's save it
7:48:02
and let me test that out e in the postman where of course now i'm gonna go with id
7:48:08
that is in the array and that's gonna be number one so if i send notice how it is
7:48:14
irrelevant if i send body again because i'm not handling that on the server anyway but
7:48:21
if i take a look at my data well the person with id number one
7:48:27
john is missing why well because his id matched to the one that i passed in the
7:48:33
primes so now of course he was removed from the array so if i'll go with five
7:48:39
same deal now the john is back here because again we're not persisting data but the person with id of five has been
7:48:47
removed from the array hopefully this gives you a good understanding how we
7:48:53
use other methods as well not just get and why we go with postman instead of
7:49:00
setting up the front-end but before we cover router in express let me just stress
7:49:06
something that yes while we're developing our server of course we'll use postman because you can
7:49:12
clearly see how much faster it is i set up the route and i quickly tested
7:49:18
otherwise if i would have to build a front end for every route that i'm creating i mean the process would be
7:49:24
just very very long but at the end of the day when you set up the api
7:49:32
the expectation is that there is going to be someone who's using that data now
7:49:37
that could be on your own server so for example if you're building a full stack application with mern that's one of the
7:49:44
options that could be decoupled application remember how i showed you a example where i have the api on my
7:49:52
server but then there is a react application that uses it it doesn't mean
7:49:57
that you have to build that front-end application yourself just be mindful that the whole idea of
7:50:03
setting up the api is that someone is going to be using
Express Router - Setup
7:50:08
that data that's it that's all i want to say and now of course we can talk about
7:50:14
router in express all right i think we're moving along
7:50:19
quite nicely but as you can see the moment we're starting to have
7:50:25
more routes and more functionality we have another issue and that issue of
7:50:31
course is the fact that our app.js is getting quite busy and technically we
7:50:37
don't even have that many routes so what is the solution well the solution is
7:50:43
using express router where we can group those routes together
7:50:48
and then as far as the functionality and actually set them up as separate
7:50:53
controllers now eventually in the next example when we work with database i'll cover again the common
7:51:01
setup which is called mvc basically it is a pattern it's not a rule but it is a
7:51:08
nicely used pattern when you're setting up the api but we are missing the model
7:51:13
part in the mvc pattern because we haven't connected the database so i'll just leave it at that just please keep
7:51:20
in mind whatever i'm about to show you in this video and in the next yes it is
7:51:25
a pretty common convention and pattern so i also suggest sticking to that now also
7:51:32
i want to mention that in this video we will do a bit of copy and pasting
7:51:38
meaning we'll have to refactor the code because i think this is a perfect example for us to set up the router
7:51:44
where we already have some code so you can clearly see the benefits of setting
7:51:49
up the router instead of me coming up with some empty routes and then saying that yes that is the best pattern so
7:51:58
with that said first where we have the request the post request for api postman
7:52:04
people i want you to change this around a little bit so as you can see i keep going back and forth in this case i want
7:52:11
to go with api people and then let's just say postman again it doesn't really matter we're not going to make requests
7:52:17
anymore from the postman in these examples anyway this is just about our
7:52:22
code structure and then once we change this around i also want to move this
7:52:27
login up just so it's a bit clearer what we're doing so take this login route and keep moving moving moving moving and
7:52:34
just place it on top of your routes and there it is now of course i have my
7:52:40
login and now notice the pattern whereas i have one route for the login
7:52:46
but then rest of them i have api people api people api people postman
7:52:53
api people id and hopefully you get the gist again i have api people id
7:53:00
so wouldn't it be nicer if i could somehow group all the api
7:53:06
people and also add one for the login but basically in a separate file and the
7:53:12
way we can do that is by setting up the router now again common convention
7:53:18
is just creating another folder so i just want to make sure that i'm
7:53:23
actually doing that in the express tutorial let's create a new folder and common convention is calling this
7:53:30
route and then you just come up with whatever name you want now in my case i'm gonna go
7:53:37
off for the login because we're just gonna imagine that maybe there's going to be one for register one
7:53:43
for logout or whatever and then there's going to be one 40 people so that's going to be for my
7:53:50
api and people so let's set up these two files i will zoom in massively just so
7:53:56
you don't think that i'm cheating so let's go here with alt js this is where i'll place my login one and also right
7:54:03
away set up my people people just okay awesome i'll start working in
7:54:11
people.js because it's going to be a bit interesting and then we'll do the same thing in the auth as well
7:54:17
and the way we set this up we simply start by requiring the express so we go
7:54:22
here express require and of course the module name is express and then instead
7:54:28
of setting up the app we go with router and we explicitly get the router from
7:54:35
the express so this is going to be a router instance that takes care of the routing instead
7:54:42
of the app so we're not going to do the routing anymore in our app.js well sort of we
7:54:48
will we'll use the middleware but as far as the specific urls we'll handle that
7:54:54
in this routes people file and the way we set up the router we go with router
7:55:00
and that one is equal to like i said express dot and then we go with capital
7:55:05
letter router and then we invoke it awesome that's a great start we can save this
7:55:13
sucker and now i want you to go back to app.js and don't grab the login that's why i
7:55:19
set it up separately above all the routes but grab all of the ones with api
7:55:25
and people so take these suckers here all the way
7:55:31
up to delete basically stop at listen cut it out
7:55:36
and then copy and paste in people like so okay great so now of course i have all my
7:55:43
routes here now our next step is actually changing from app
7:55:49
to router because i want the router to handle the routing so in my case i'm
7:55:55
going to select all of my apps like so so i'm just doing that with command d in the visual studio code and
7:56:03
at this point i should have multiple cursors like so and i'll set up my router
7:56:09
and now all the way in the bottom i want to go with module
7:56:14
not exports and of course at the moment i'm exporting my router
7:56:20
and then once we export a router of course in the app.js i want to set up a app.use where i'll
7:56:28
say yes for the path that starts with api and people
7:56:33
i want to use my people router and the way it's going to look like we're going
7:56:39
to go back and at this point we have people here and as a side note actually we need to cut it
7:56:45
out but we're not going to use it here as well eventually the setup is going to be different so for now yes
7:56:53
please cut it out and copy and paste in people but since we'll be setting up the
7:56:58
controls we'll have to do that one more time anyway so i guess i'm going to go below the router i'm going to look for
7:57:05
my people otherwise my functionality won't make sense and in this case remember
7:57:10
we are sitting already in routes so i need to go two levels up and i still
7:57:17
need to look for my data correct so now of course our functionality should work
7:57:23
hopefully we don't have some weird bugs and then like i said in the app jess now
7:57:30
of course i would want to use my app.use so i'm going to go below express
7:57:36
json and i'm going to say app.use and now i need to set up that base route now
7:57:41
what is my base route here well it is api and people correct
7:57:46
because this is just my route and then in some cases i have the postman or i have the
7:57:54
id that's it but the base stays the same okay awesome so we provide this path we
7:58:00
say api and then people and now i want to set up that router
7:58:05
and of course in order to set up the router i need to import it and you can call it people router you
7:58:12
can just call it people again that is really up to you i'm just going to say people is equal and now we need
7:58:19
to require it and remember we have a folder by the name of what routes
7:58:25
and then we also have people file okay awesome we require our router
7:58:32
here correct so that's our router and we're exporting awesome so we get the people and like i
7:58:40
said with use we can use the path if we want so this is not going to be applied to all of them this is only going to be
7:58:46
applied to the ones that start with api people and then we
7:58:52
pass in the people we'll save it but there is a problem you see once we set up this router
7:58:58
with a base path in the people actually we have a mess right now
7:59:05
because we already have the base for our router in app js where we have
7:59:10
api people and now in the people.js if you check it out we actually have api people forward slash api people so i
7:59:18
fully understand that this is going to look a bit drastic but in order for this to work we
7:59:26
actually remove everything we remove that base so we go here with just a forward slash why well because we
7:59:32
already have the base here we have api people so that's how the route is going to
7:59:38
start and then we just have the forward slash so this will match whatever i have in the
7:59:46
address and since in the get and in a post both of them just have api people well i
7:59:52
simply go with forward slash again i fully understand that this might look a bit confusing in the beginning but again
8:00:00
the more routers you'll set up the easier it's going to get so this will
8:00:05
just match whatever path i have here whatever base path i set up in my app.js so i'm just
8:00:13
saying yes i'm using this people router and in the people since i already have
8:00:18
base path in place i can simply reference it using the forward slash so
8:00:23
this is going to match whatever i have in app and once i have spent what seems like an
8:00:30
eternity on the base path i can keep on scrolling and again notice i have api
8:00:36
people and then postman so what's the only thing that i need here it's just a
8:00:41
postman because i already have api people so i remove this sucker here keep on scrolling
8:00:47
then the same with id right we only care about this one that's the whole point of setting up the router so we can start
8:00:54
splitting up our functionality in multiple files same goes with this last
8:01:00
id and even though i think i said that we're not going to use the postman i do want to quickly check
8:01:07
and i'm going to go with get simple if the get works trust me the other ones work as well so we go here with api
8:01:14
people we send but unfortunately i get the error hmm that's interesting so let
8:01:20
me check i think the problem here is in the app.js i don't have the forward slash so let me
8:01:27
try this one let me send it one more time and there it is now of course everything works so
8:01:34
my apologies i forgot to add here forward slash that's why we were getting
8:01:39
the error and of course everything works i can go with get i can get my list
8:01:46
if i want i can also maybe delete a person so i'm going to go delete and
8:01:51
we're gonna test three so let's see we send and as you can see the person with id of three is missing
8:01:59
so as you can see our route works so that's the first step so now here's the
8:02:04
challenge try to repeat the same thing with login now with login
8:02:10
it is going to be a bit simpler because we don't have that long of a path but
8:02:15
again stop the video and try to set up the login yourself and then once you're
8:02:20
ready resume it and we're going to do it together how was it hopefully you were successful
8:02:27
and i'm going to give it a shot so first remember we needed a file so in this
8:02:33
case i do have auth js awesome so i'm just gonna cut this sucker out
8:02:40
from my app.js and place it in off then of course i do
8:02:46
need to have the boilerplate for the router so again let's go with express
8:02:51
require we require the module by the name of express of course then we set up our
8:02:57
router router and that one is equal to express dot router we invoke it then we change
8:03:06
this value around like so and then we're just gonna go with module
8:03:14
and then export and that one is equal to our router we do this
8:03:20
then we navigate back to app.js and we'll have to import it as well so we go
8:03:26
with auth i guess let's call it that and we're looking for auth file
8:03:32
that's where our router is coming in and then of course i just need to set up my middleware myapp.use where i provide a
8:03:40
path of what well of login and in this case i'm going to be more careful and i
8:03:45
will add the forward slash and of course i'll set it up as auth so let's save
8:03:51
this one and then the only thing we need to do in the login is simply change it around where i'm
8:03:58
already handling the login in the app.js so forward slash login so again my route
8:04:03
now is forward slash login so i simply go with the forward slash i already
8:04:09
covered the route in the objects so i don't need to do that anymore in here
8:04:15
and you know for this sucker just to make things a bit more interesting why don't we use the browser now keep in
8:04:21
mind you can still use the postman if you want but i'm gonna go the browser out so we're gonna go with new window
8:04:28
i'm gonna go with 5 000 here and of course this is going to be the
8:04:34
small screen i have traditional form so let's go with some kind of name peter
8:04:39
and i send and i have welcome peter and of course if that is the case i know
8:04:44
that my functionality works so we are in good shape again probably the most
8:04:50
confusing thing is this one where we use app.use to set
8:04:56
up our route so all the routes that will start with this api people are
8:05:02
going to be located in the people.js in the routes folder and in there instead
8:05:08
of using app we use the router and then since we already have the base setup in the app.js
8:05:16
when we have a route that exactly matches the base we just go with forward slash now if there is something else
8:05:23
after the base route so some additional info of course then we go with forward
8:05:29
slash which just means that we match the base path and then we add whatever value
8:05:35
we want and hopefully you can see how much cleaner is our app.js
Express Router - Controllers
8:05:42
where now we're splitting up the functionality in separate files for our routes beautiful i think we
8:05:50
really clean up our app js but we're not out of the woods yet
8:05:56
if we take a look at our auth js yeah this one looks somewhat clean but we
8:06:01
need to keep in mind that we only have one request we only have one post request to our
8:06:08
login however if we take a look at our people.js it is still somewhat of a mess because
8:06:16
we have a bunch of functionality since of course we have more routes
8:06:22
and of course a better setup is if we would be able to split this up into a
8:06:29
separate file and i'm talking about the functions so imagine this scenario where
8:06:35
we only would have a router then i'm gonna set up my method whether
8:06:41
that's get post or whatever then i'm still gonna have the route but the
8:06:46
functionality this one the controller is going to be in a separate file so it's going to be a separate function and
8:06:53
you'll see how much cleaner our file is going to look like just in a second so
8:06:59
again we need to head back to our express tutorial
8:07:04
now i'll zoom in i'll create a new folder and again common convention is calling
8:07:11
this controllers for the reason that there is a pattern called mvc so model view controller and
8:07:20
then again we come up with the name in my case i'm going to go with jobs or i'm sorry not jobs i'm going to go with
8:07:26
people and i'm not gonna set up one for the other one for the auth since there's
8:07:32
only one but for people i will set up a controllers file by the name of
8:07:37
people.js and here i just to set up first my functions
8:07:44
and the way it's going to work we're going to go with const and then again you just need to come up with a name so
8:07:49
for example for get request where i'm getting people i'm just going to call this get people keep in mind this is
8:07:55
just a function so the name is really up to you and since i'm going to have the same functionality of course i need to
8:08:01
keep in mind that i do need to have access to rack and res now it's really
8:08:07
cool that once i pass this function as a reference it's still going to work so i simply go here with this rack res and
8:08:15
set up the functionality now probably faster is just going to be doing like this where i cut out
8:08:22
and then back into controllers i copy and paste now i know that some people might find this annoying but yes i'm
8:08:28
purposely refactoring the code so you can see the benefits right away and i'm
8:08:34
going to do that for all the functions and for a little bit it's gonna probably look messy
8:08:40
where i'm gonna do the same thing for the post so i guess first i'm just gonna cut it out and then back in the
8:08:47
controllers nothing routes in the controllers let's come up with that function as well so const and in this
8:08:54
case i'm going to call this create person i'll copy and paste the code okay awesome
8:09:00
back in the routes let's get the postman one so in a controller let's also call
8:09:05
this const and create person and postman like so copy and paste
8:09:13
that's my function then back in routes i have one for put so i think it would make sense if i call
8:09:22
this for example update person again cut out everything starting with a function and then all
8:09:30
the way to the closing parenthesis cut it out back in controllers we're going to call
8:09:37
it const update person like so copy and paste and lastly let's
8:09:44
deal with a delete one as well so let's keep scrolling
8:09:50
again we cut everything out like so and then back in the controller let's
8:09:56
create one for deleting the person so const cons delete person
8:10:03
and copy and paste and if you remember which seems like an eternity go
8:10:09
when we covered the exports i said that of course we can also use right away
8:10:14
module exports and then whatever so for example in this case that could be get
8:10:20
people or create person or create person postman now in my case i
8:10:26
always prefer to do my exports all the way on the bottom where i say module exports now this is going to be
8:10:33
the object and now i just want to access all the functions keep in mind it doesn't change the functionality
8:10:39
functionality is the same where i'm basically exporting an object with bunch of functions so here i just
8:10:45
need to reference their names so it's get people it is create person
8:10:50
create person postman then update person and lastly it is also
8:10:56
for deleting the person now one thing that is missing of course is the people like i said this is just going to be
8:11:02
temporary so i'm going to go to the controller here and i'll copy and paste now in this case
8:11:09
the path is correct because the route was already in a separate folder so
8:11:14
that should still work and of course now i can save my controllers and in the
8:11:20
routes what i need to do is of course import all of them so in this case we go with const and
8:11:27
again i'll write away the structure all of them so let me just copy and paste i
8:11:32
think it's going to be faster like so since the names of course are going to be exactly the same i
8:11:38
destructure them and i'd structure them from require and then of course we're looking
8:11:44
for controllers and then more specifically i'm looking for the people like so and once we have required them
8:11:51
of course now we pass in the function reference so for example here i can say
8:11:56
get people now i do need to add a comma and if everything is correct our
8:12:02
functionality is still going to work so in the controllers we're still
8:12:07
accessing rack and arrays and we're still sending back the response but of course the benefit of
8:12:14
all of this work is the fact that our routes file is gonna get much cleaner so in here
8:12:21
remember the name was create person like so and then we have one for create person
8:12:28
postman and let's set it up like so then we have also one for update
8:12:34
person and lastly we have one for the leading person right so we go here with
8:12:40
delete person i save again i'm not gonna test all of them out but i'm gonna go
8:12:45
with for example delete and i'm gonna look for four this still works
8:12:51
i remove the person number four and also if i check out the get one
8:12:57
for the people this also should get me back the array so i know that my
8:13:02
functionality still works but i nicely cleaned out my file now lastly before we
8:13:08
talk about the databases i just want to mention that when it comes to setting up
8:13:13
the routes we actually have two flavors so i'm gonna comment these ones out and i'll
8:13:20
show you another way how we can set up the routes and effectively the benefit is that we can set it up in fewer lines
8:13:28
of code keep in mind the functionality is going to be exactly the same so again
8:13:33
this is going to be the case where it comes down to your preference if you prefer setting up your routes this way
8:13:40
you can definitely do so there's no rule against it if you prefer the method that
8:13:45
i'm about to show you then of course you can use that one instead so we go with a
8:13:51
router and then we go with route and then in the route i set up the path
8:13:57
and again since there's get and post that match exactly what i have in base
8:14:04
same situation i just set up the forward slash and instead of setting up them separately for example get and post i
8:14:12
can just chain them so chain one after another so i go with get that is of
8:14:17
course my method that is not changing and then i need to pass in my controller function okay as
8:14:25
you can see almost the same in this case however i can change it now the method names did
8:14:32
not change the paths did not change they're still actually referencing the base path in
8:14:38
here what we have in app.js but since we can chain it we can simply write it in
8:14:43
one line of code so of course the callback function is gonna be create and
8:14:49
i believe it was person so create and person like so then we have of course one for the
8:14:56
postman so in this case of course it's not going to change it's pretty much going to be the same logic where we go
8:15:03
the router route like so and then we go with forward slash postman and then of course i want
8:15:10
to chain dot and i believe it was post right and then we go with create person postman
8:15:17
and then we can again set up one line of code for the put and delete so in this
8:15:23
case i think i'm going to just copy where i have router dot route then we set up our route and in this case it is
8:15:31
going to be forward slash and then id and then we have two we have one for put
8:15:37
and we have one for delete so we go with delete and then as far as the callback
8:15:42
functions we go with update person and also we have delete person and
8:15:50
finally let me just stress it one more time where whichever setup you choose is
8:15:55
really up to your preference functionality is exactly the same we go with router route and then we can just
8:16:03
chain our methods and add the callback functions now in this case we set up each route
8:16:11
separately so for example if you have multiple urls that match yeah you're in
8:16:16
good shape you can just set up router route pass in the url and then chain all
8:16:22
the methods and lastly let me just quickly test it one more time since i made some changes i send it and there it
8:16:29
is i successfully get back my people so with this in place
8:16:35
with our router in place with the fact that we have covered all the methods
8:16:40
the get post put and delete i think we're ready for the next level where we
8:16:46
connect our server
