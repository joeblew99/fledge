[![pub package](https://img.shields.io/pub/v/fledge.svg)](https://pub.dartlang.org/packages/fledge)
[![Build Status](https://travis-ci.com/mmcc007/fledge.svg?branch=master)](https://travis-ci.com/mmcc007/fledge)
<a href="https://saucelabs.com"><img src="art/Powered_by_Sauce_Labs_badges_gray.svg" alt="drawing" width="67.5"/></a>

<img src="https://upload.wikimedia.org/wikipedia/commons/1/15/Passarinho-azul-02.png" width="30%" title="Fledge" alt="Fledge">


See https://medium.com/@nocnoc/cicd-for-flutter-fdc07fe52abd for introduction to Fledge.

# Fledge: A CICD tool for Flutter
Automatically build, test, sign and release your Flutter app to both Apple and Google stores. 

Supports public and private build servers in the cloud (Travis, Cirrus, etc...) and in-house (Jenkins, GitLab, etc...).

There are many steps involved each time an app, or an app upgrade, is delivered to both stores. Fledge exists to document and automate these steps.

# Quick start
For example, with GitHub and Travis:

1. Install Fledge  
    ```
    $ pub global activate fledge
    ```

1. Add secrets  
    Set your secret variables in:  
    ```
    https://travis-ci.org/<your name>/<your repo>/settings
    ```
    ![secret variables](art/travis_secret_env.png)  
    These variables are used for signing and uploading to both stores.

1. Add app to Fledge  
    Install the Travis config file and Fastlane files
    ```bash
    $ fledge config -b travis
    ```

1. Start a beta  
    Run pipeline on Travis
    ```
    $ fledge beta
    ```
    This will build your app, upload to both store consoles and release to beta testers.

1. Release to users  
    ```
    $ fledge release
    ```
    This will release the app to users.

# Documentation
As with any mobile app, there are several one-time setup tasks (most of which you have to do anyway… even without a CICD tool).

To avoid having to gather together all the bits and pieces of information required to deliver a Flutter app, the Fledge project has created complete documentation to walk you thru all the setup tasks for the more common scenarios.

One of the reasons the Fledge projects exists is to document these one-time setup tasks and progressively automate them where possible (and then remove from documentation).

[![Fledge Docs](art/fledge_docs.png)](https://mmcc007.github.io/fledge/)

[View the documentation site](https://mmcc007.github.io/fledge/) for complete usage and configuration information.

# Demo
For a demo of Fledge in action see: https://github.com/mmcc007/todo. Links are included to view the pipeline on Travis that delivers betas and releases to both stores.

The demo app was delivered automatically to both Google and Apple stores using a Fledge pipeline.

You can download the demo app to your android or iOS device:  
[![GitErDone](https://play.google.com/intl/en_us/badges/images/badge_new.png)](https://play.google.com/store/apps/details?id=com.orbsoft.todo)
[![GitErDone](https://linkmaker.itunes.apple.com/en-us/badge-lrg.svg?releaseDate=2019-02-15&kind=iossoftware)](https://itunes.apple.com/us/app/giterdone/id1450240301)
 
### Fledge trace-back feature  
This feature allows you to track what version of your app is running on any device. Useful for support and bug-fixing.
 
 To use the Fledge trace-back feature, tap on the app title 'GitErDone' to view the 'About'. 
 
 On an android device you will see:  
 ![android screenshot](./art/android_screenshot.png)
 
 On an iOS device you will see:  
 ![ios screenshot](./art/ios_screenshot.png)
 
 You can then trace back to the Fledge pipeline that delivered the app (click on image below for link to actual pipeline):  
 [![fledge pipeline](./art/fledge_pipeline.png)](https://travis-ci.org/mmcc007/todo/builds/493633473)
 
# License

Fledge is distributed by an [MIT license](https://github.com/mmcc007/fledge/tree/master/LICENSE.txt).

# Contributing

When contributing to this repository, please feel free to discuss via issue or pull request.

[Issues](https://github.com/mmcc007/screenshots/issues) and [pull requests](https://github.com/mmcc007/screenshots/pulls) are welcome.

Your feedback is used to guide where development effort is focused. So feel free to create as many issues and pull requests as you want. You should expect a timely and considered response.

BTW: to contribute to the manual, fork the project and make updates to the gh-pages branch. Then create a PR. The manual is a collection of markdown docs (like the README.md).

# Code of Conduct

Fledge is committed to fostering a welcoming community.

### Big Thanks

Mobile Testing Platform and Open Source <3♥ Provided by [Sauce Labs][sauceLabsHomepage]

[sauceLabsHomepage]: https://saucelabs.com