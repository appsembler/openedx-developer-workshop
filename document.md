<!-- uncomment this commented section if you're using Madoko to edit the markdown
[INCLUDE=presentation]
Title         : Getting Started with Open edX Development
Sub Title     : Open edX Conference 2019
Author        : Nate Aune
Affiliation   : Appsembler
Email         : nate@appsembler.com
Reveal Theme  : sky
Beamer Theme  : singapore
-->

<!-- these slides were crafted using the approach outlined in this blog post: 
http://www.markusz.io/posts/2018/03/16/revealjs-docker-markdown-slides/

Using the embedding external Markdown feature of Reveal.js
https://github.com/appsembler/2018-openedx-developer-workshop#external-markdown

To render these slides as navigable HTML:

$ npm install
$ npm start   (<-- this will launch a browser and connect to localhost)

If you want a printable PDF, go to http://localhost:8000?print-pdf
-->

## Getting Started with Open edX Development
### Open edX Conference 2019
### San Diego, CA
### March 26, 2019



## Housekeeping

Follow along with these slides at:

[bit.ly/openedx-workshop-slides](http://bit.ly/openedx-workshop-slides)

Make yourself a printable PDF version:
https://appsembler.github.io/openedx-developer-workshop?print-pdf

*Please* complete the short survey at the end of the workshop.



## Introductions

Your esteemed workshop facilitators! 

- Nate Aune (nate@appsembler.com)
- John Baldwin (john@appsembler.com)
- Bryan Wilson (bryan@appsembler.com)
- David Ormsbee (dormsbee@edx.org)

We will be on hand to help you if you get stuck or have questions.


## Who are you?

Welcome! Share a few words about yourself...

- Your name
- Your affiliation 
- Your level of experience with Open edX



## Agenda

* Why develop Open edX?
* What do I need to know?
* How do I do it? (hands-on exercises)
* Where can I go for help?
* Questions?



## WHY?

Why might you want to do development on Open edX?

![Example image](images/butterfly.png) <!-- .element height="25%" width="25%" style="border: 0; background: None; box-shadow: None" -->


## Some reasons... 

What are some other reasons that you might want to learn about Open edX?


## Curious how it works

Example of a scalable Django app serving millions of users.


## Customize your own instance

One of the benefits of Open Source software is that you can customize the software to meet your specific needs.

You can create a branded site with your own theme using your own domain name.



## What do I need to know?

* Key skills and competencies
* Technologies used by Open edX
* Open edX system architecture


## Key skills and competencies

* Full-stack web development (Python/Django/JS)
* DevOps experience (Linux, Cloud hosting)
* Open source experience helps


## Technologies

Technologies that Open edX uses:

* Django (web development framework)
* Python (scripting language)
* ReactJS/BackboneJS (frontend javascript)
* MySQL (DB where student data is stored)
* MongoDB (DB where course data is stored)
* RabbitMQ (process background tasks)
* Ansible (configuration management)
* Hadoop (distributed processing)


## edX architecture #1

![architecture](images/openedx-services.png) <!-- .element height="80%" width="80%" -->


## edX architecture #2

![architecture](images/edx-architecture.png)


## edX architecture #3

![architecture](images/edx-architecture-2015.png) <!-- .element height="70%" width="70%" -->



## Exercises for today

* Import a course into an existing Open edX site
* Start/stop the LMS and CMS (Studio)
* Create a superuser
* Change the platform name
* Make a small change to a custom theme
* Install and enable a 3rd party XBlock


## What we're not going to cover

* Deploy an Open edX site to production
* Build a custom theme from scratch
* Create an XBlock from scratch
* Discuss every feature Open edX provides
* Localization and translations


## Questions?

Who's ready to get started!?



## Set up a site

First we need to set up a site. We'll use our handy signup wizard to provide you with an Open edX site that will deliver the course content for the workshop.

Go to [bit.ly/tahoe-signup-wizard](http://bit.ly/tahoe-signup-wizard)


![step1](images/step1.png) <!-- .element height="80%" width="80%" -->


![step2](images/step2.png) <!-- .element height="80%" width="80%" -->


![step2a](images/step2a.png) <!-- .element height="80%" width="80%" -->


![step3](images/step3.png) <!-- .element height="80%" width="80%" -->


![step4](images/step4.png) <!-- .element height="80%" width="80%" -->


![step5](images/step5.png) <!-- .element height="80%" width="80%" -->


![step6](images/step6.png) <!-- .element height="80%" width="80%" -->


![step7](images/step7.png) <!-- .element height="80%" width="80%" -->


![step8](images/step8.png) <!-- .element height="80%" width="80%" -->


![step9](images/step9.png) <!-- .element height="80%" width="80%" -->


![management_console](images/management_console.png) <!-- .element height="80%" width="80%" -->


![lms](images/lms.png) <!-- .element height="80%" width="80%" -->


![studio1](images/studio1.png) <!-- .element height="80%" width="80%" -->


![studio2](images/studio2.png) <!-- .element height="80%" width="80%" -->


![studio3](images/studio3.png) <!-- .element height="80%" width="80%" -->


![studio4](images/studio4.png) <!-- .element height="80%" width="80%" -->


## Download course

Go to this URL to download the course that you'll be importing into your site.

[http://bit.ly/openedx-dev-course](http://bit.ly/openedx-dev-course)


![studio5](images/studio5.png) <!-- .element height="80%" width="80%" -->


![studio6](images/studio6.png) <!-- .element height="80%" width="80%" -->


![studio7](images/studio7.png) <!-- .element height="70%" width="70%" -->


## Check point

Was everyone able to get a site set up, and import the course?

If not, raise your hand and someone will come around to help you.



## Start your engines!

Once you're viewing your live course, navigate to the "Start here" section. You should see this button:

![launchlab](images/launch_lab_button.png) <!-- .element height="70%" width="70%" -->


## And... voila!

![labresults](images/launch_lab_results.png) <!-- .element height="60%" width="60%" -->


## Open edX dev "in the cloud"

Go to http://8888-xxxxxxx.demo-avl.appsembler.com/entry.html

Where `xxxxxxx` identifies your personal development environment.
(Every student will have their own unique URL)

Be sure to bookmark or open in new tabs the two edX links.


## What you should see

![labresults](images/edx_dev_environment.png) <!-- .element height="50%" width="50%" -->


## Check point

Was everyone able to launch their dev environment?

If not, raise your hand and someone will come around to help you.



## Start the LMS

```shell
$ supervisorctl start lms
lms: started
```

Go to `8000-xxxxxxx.demo-avl.appsembler.com` 
to see LMS running. 

If you get "Bad Gateway", just wait a min or two, and reload the page.

Find log files here: `/var/log/supervisor/lms-stderr.log` and `lms-stdout.log`


## Start the CMS (Studio)

```shell
$ supervisorctl start cms
cms: started
```

Go to `8001-xxxxxxx.demo-avl.appsembler.com` 
to see Studio running. 

If you get "Bad Gateway", just wait a min or two, and reload the page.

Find log files here: `/var/log/supervisor/cms-stderr.log` and `cms-stdout.log`


## Check point

Was everyone able to start the LMS and CMS (Studio) and view their home page?

If not, raise your hand and someone will come around to help you.


## Another way to start/stop services

```shell
$ cd /openedx/edx-platform
$ ./manage.py lms runserver 0.0.0.0:8000
$ ./manage.py cms runserver 0.0.0.0:8001
```

Both of these commands run in the foreground, which is why we use supervisor to run them in the background.



## Create a superuser

```shell
$ cd /openedx/edx-platform
$ ./manage.py lms createsuperuser
...
Username (leave blank to use 'root'): staff
Email address: staff@example.com
Password:
Password (again):
Superuser created successfully.
$
```

Now try logging into the LMS and Studio using these credentials.


## Check point

Was everyone able to login to the LMS and Studio?

If not, raise your hand and someone will come around to help you.



## Django settings

The Django settings files inherit from `common.py` and the `*.json` files overwrite these settings.

![settings](images/lms_settings.png) <!-- .element height="50%" width="50%" -->


## Inspect common.py

Inspect `/openedx/edx-platform/lms/envs/common.py`

![settings](images/inspect_common_py.png) <!-- .element height="75%" width="75%" -->


## lms.env.json

Editing the `lms.env.json` file.

![settings](images/edit_lms_env_json.png)


## Change platform name

Edit the `lms.env.json` file and change this line:

```json
  "PLATFORM_NAME": "Open edX 2018 demo",
```

To:

```json
  "PLATFORM_NAME": "Sunny in San Diego",
```

Now restart the LMS to see your change.

```shell
$ supervisorctl restart lms
```


## Go to the register page

![settings](images/sunny_in_san_diego.png) <!-- .element height="50%" width="50%" -->


## Questions?

Any questions about the settings files or feature flags?

For further reading about what features are available, check out the [feature toggles OEP-17](https://open-edx-proposals.readthedocs.io/en/latest/oep-0017-bp-feature-toggles.html) on OEP Read the Docs site.



## Intro to themes

Rather than using the default theme, you might want to try one of the other themes that ship with Open edX. You can find these in the `/themes` directory.

```shell
$ cd /openedx/edx-platform/themes
$ ls
README.rst  conf  edge.edx.org  edx.org  red-theme  stanford-style
```


## Install a new theme

Let's install the `blue-theme`, hand-crafted by Omar, one of our engineers at Appsembler!

```shell
$ cd /openedx/edx-platform/themes
$ git clone https://github.com/appsembler/blue-theme
```


## Tell Open edX to use your new theme

Edit the `lms.env.json` file and add the last 3 lines:

```json
{
  "SITE_NAME": "localhost",
  "BOOK_URL": "",
  "LOG_DIR": "/openedx/data/logs",
  "LOGGING_ENV": "sandbox",
  "OAUTH_OIDC_ISSUER": "http://localhost:8000/oauth2",
  "PLATFORM_NAME": "Sunny in San Diego",
  "FEATURES": {
    "PREVIEW_LMS_BASE": "preview.localhost"
    },
  "ENABLE_COMPREHENSIVE_THEMING": true,
  "COMPREHENSIVE_THEME_DIRS": ["/openedx/edx-platform/themes"],
  "DEFAULT_SITE_THEME": "blue-theme",
...
}
```


## Update assets

If you restart the LMS and look at the site, it won't look quite right.

That's because we still need to compile the theme assets with this command:

```shell
$ cd /openedx/edx-platform
$ paver update_assets lms --settings=universal.development --themes=blue-theme
...
[...this might take awhile...]
...
Finished collecting lms assets.
```


## Bask in the blue skies

Now restart the LMS to see your new theme in all its glory.

```shell
$ supervisorctl restart lms
```

![settings](images/blue_theme.png) <!-- .element height="50%" width="50%" -->


## Make some customizations

Let's replace the logo with our own.

```shell
$ cd /openedx/edx-platform/themes/blue-theme/lms/static/images
$ curl -LO http://bit.ly/appsembler-logo
$ mv appsembler-logo appsembler-logo.svg
```


## Change the footer template

In the code editor, navigate to the file `/openedx/edx-platform/themes/blue-theme/lms/templates/footer.html`

Find this HTML code:

```html
<img alt="organization logo" src="${footer['logo_image']}">
```

And replace it with:

```html
<img alt="organization logo" src="${static.url("images/appsembler-logo.svg")}">
```


## See your changes

When you refresh the LMS home page, you should now see the Appsembler logo in the footer.

![settings](images/logo_in_footer.png) <!-- .element height="50%" width="50%" -->


## Questions?

Any questions about changing the theme?

For further reading, check out the comprehensive theming documentation.



## XBlocks

What is an XBlock?


## Where do I find these XBlocks?

* [XBlocks Directory in edX wiki](https://openedx.atlassian.net/wiki/display/COMM/XBlocks+Directory)
* [Search Github for "xblock" - 532 at last count!](https://github.com/search?q=xblock&type=Repositories)


## Let's install an XBlock!

There's a cool in-video quiz XBlock from Stanford. Let's add it to our Open edX instance.

```
$ pip install -e git+https://github.com/Stanford-Online/xblock-in-video-quiz.git#egg=xblock-in-video-quiz
...
Successfully installed invideoquiz-xblock
$ cd /openedx/edx-platform
$ paver update_assets lms --settings=universal.development
$ paver update_assets cms --settings=universal.development
```

The URL is: https://github.com/Stanford-Online/xblock-in-video-quiz.git

Remember to restart the LMS and CMS (Studio):

```shell
$ supervisorctl restart lms cms
```


## Activate the XBlock

Login to Studio, create a course, and go to Advanced Settings. Then add the in-video quiz XBlock:

![advanced settings](images/advanced_settings.png) <!-- .element height="75%" width="75%" -->


## Add to your course

Add a new unit, choose Advanced, and pick the in-video quiz.

![new unit](images/advanced_beaker_button.png) <!-- .element height="50%" width="50%" -->

![new unit](images/In-Video-Quiz-XBlock.png) <!-- .element height="50%" width="50%" -->

## Check point

Were you able to add the in-video quiz XBlock to your course?

If not, raise your hand and someone will come around to help you.


## Extending Open edX

![new unit](images/Options_for_Extending_the_edX_Platform.png
) <!-- .element height="60%" width="60%" -->

Read more at [Options for extending Open edX](http://edx.readthedocs.io/projects/edx-developer-guide/en/latest/extending_platform/extending.html)

Also, check out [Django App Plugins](https://github.com/edx/edx-platform/blob/master/openedx/core/djangoapps/plugins/README.rst)

## Questions?

Any questions about XBlocks or extending Open edX?

For further reading, check out the [XBlocks documentation](https://xblock.readthedocs.io) and [XBlock Tutorial](https://edx.readthedocs.io/projects/xblock-tutorial).



## Where to go for help

* Documentation
	* Official docs
	* Confluence wiki
	* Slides and videos

* Community
	* Mailing list
	* Slack community
	* Stackoverflow

* Tutorials / Workshops


## Documentation

* [Official docs.edx.org](https://docs.edx.org)
* [Building and Running Open edX](https://edx.readthedocs.io/projects/open-edx-building-and-running-a-course/en/latest/)
* [Installing, Configuring and Running Open edX](https://edx.readthedocs.io/projects/edx-installing-configuring-and-running/en/latest/)
* [Open edX Developer Guide](https://edx.readthedocs.io/projects/edx-developer-guide/en/latest/)
* [edX's Confluence Wiki](http://openedx.atlassian.net/wiki)
* [Open edX Youtube Channel](http://youtube.com/c/openedx)
* [edX Architecture Onboarding](https://docs.google.com/presentation/d/1X3QaSw4sqPLvkXBhC8phoFA7j8dhsL08MCZWwIDMIBE/)
* [Open edX Named Releases](https://edx.readthedocs.io/projects/edx-developer-docs/en/latest/named_releases.html)


## Community

* [edx-code Mailing list](http://groups.google.com/group/edx-code)
* [Slack community](https://openedx.slack.com/)
* [Stackoverflow](https://stackoverflow.com/questions/tagged/openedx)
* [edXchange](https://edxchange.opencraft.com)


## Tutorials @ 1:30-3pm

* [Deploying Open edX in Production using Docker and Kubernetes](https://openedx2019.sched.com/event/KcTf/open-edx-production-ready-in-10-steps)
* [Building Open edX frontend applications with create-edx-react-app, Part 1](https://openedx2019.sched.com/event/L6bV/building-open-edx-frontend-applications-with-create-edx-react-app-part-1)
* [Learning and Teaching How to Contribute to Open edX, Part 1](https://openedx2019.sched.com/event/L6SY/learning-and-teaching-how-to-contribute-to-open-edx-part-1)


## Tutorials @ 3:15-5pm

* [Installfest](https://openedx2019.sched.com/event/KcTf/open-edx-production-ready-in-10-steps)


## Tutorials @ 3:30-5pm

* [Building Open edX frontend applications with create-edx-react-app, Part 2
](https://openedx2019.sched.com/event/Mkcr/building-open-edx-frontend-applications-with-create-edx-react-app-part-2)
* [Get Started with Figures](https://openedx2019.sched.com/event/L6Zu/get-started-with-figures)
* [Learning and Teaching How to Contribute to Open edX, Part 2](hhttps://openedx2019.sched.com/event/MgRF/learning-and-teaching-how-to-contribute-to-open-edx-part-2)



## Credits

* Nimisha for her help with the workshop last year and sharing her awesome slides
* Filip for putting together the dev environment. Huge timesaver!
* Lawrence McDaniel for his How to install an XBlock tutorial
* Matthew for trying out the tutorial and providing feedback



# Thank you!

Please share your feedback with this quick survey
[http://bit.ly/2019-openedx-workshop](http://bit.ly/2019-openedx-workshop)

Contact me with any questions: nate@appsembler.com

![new unit](images/QR_code_LDVZJ7N.png)