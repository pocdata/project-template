# POC Visualization Project Template

## Project Purpose
**For your project, replace this description as needed**

This is a starter template for visualization projects. It includes the basic style, module files and structure that we expect of new visualizations as well as instructions for how to write and include content.

## Implementation Overview

**For your project, replace or augment this description as needed**

This project is a complete development package for creating new JavaScript-based visualizations. It is platform-agnostic and assumes the use of flat data files, but you can use the built-in PHP framework to connect to a database if that is preferable for the project.

This starter kit includes a Vagrantfile for a basic LAMP stack, which is close enough to the `pocweb` server to be adequate for development purposes. It also includes Gulp for task management to streamline your development and build processes.

## Get Started

**For your project, replace or augment these instructions as needed**

1. Install software as needed for your OS:
  * [Node.js](https://nodejs.org/download/)
  * [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
  * [Vagrant](http://www.vagrantup.com/downloads)

2. Open up the terminal or command prompt and type:
  * `cd path/to/folder` where you want to store this project
  * `git clone https://github.com/pocdata/project-template.git my-project`
  * `cd my-project/public/assets`
  * `npm install`
  	* This command installs all of the modules needed for the project and may take a while.
  * `cd ../../`
  * `vagrant up`
  	* The first time you type this command, it will need to download the virtual box we're using for the development environment, so don't be surprised if it takes a little while.
    * The virtual box we are using is [Scotch Box](https://scotch.io/bar-talk/introducing-scotch-box-a-vagrant-lamp-stack-that-just-works), a basic LAMP stack that will work for any PHP/JavaScript work we need to do.

3. If everything went smoothly, you should now be able to visit the home page for the starter project at http://192.168.33.10/. If you got error messages along the way, please consult the Node, VirtualBox or Vagrant documentation depending on what threw the error.

4. Once you have verified that the project is up and running, set up a new repo for that project so that you can start committing your work.
  * Create a new, empty repo for your project in GitHub (we can't fork within the organization)
  * Then run the following commands from the root of your project:

  ```
  git remote set-url origin https://github.com/pocdata/NEWREPOSITORY.git
  git remote -v //Verify that it has changed
  git push -u origin master
  ```

5. To start writing JavaScript/CSS, `cd` into the `public/assets` directory and type `gulp watch`. Gulp will listen for changes (saves) on your Sass and Jacascript files and bundle the changes into minified files for production.

6. When you are done working, type `vagrant destroy` at the project root and remember to commit your changes!


## Assets

This folder includes all of the styles and functionality for a given page. It uses NodeJS with Gulp to process modular Sass and JavaScript and output the results as production-ready files. Please refer to the documentation in the subfolders for more details about code style.

* CSS
	* styles.css and styles.min.css are built from the files in the sass folder

* Font
	* Includes default fonts for Materialize.css

* JS
	* app.min.js is build from app.js, which requires and initializes the modules in the `modules` folder. This is preferable to putting all of the functions in one file because it maintains separation of different parts of the app.

* Sass
	* Stylesheets are organized into `base`, `components` and `theme` folders to keep CSS simple and separated. These files are included into `styles.scss`; comment out the lines of any files you don't need for your project.

* Vendor
	* Third party assets that the site builds on. We are using Materialize for base styles so that we don't have to write everything fom scratch. Please refer to the [Materialize](http://materializecss.com/) documentation for details.

* gulpfile.js
	* Basic configuration options for bundling JavaScript and Sass and outputting the results as JS and CSS. Please see the [Gulp documentation](http://gulpjs.com/) for details about how to add to or modify this file.
* package.json
	* Defines which Node modules are used by Gulp

## Content

A sample content file is included with this project. If you want to create more than one instance of the project, you should create a separate repository for the content files and include it in this repo as a [git subtree](https://medium.com/@v/git-subtrees-a-tutorial-6ff568381844). That way the content can live separately from the framework and be included in/consumed by the DAta Portal index site as well as this framework.

## Data
Use this section to describe what data is consumed by the application and how.

## Data Generation
Use this section to describe how the data is generated, including any dependencies.

## Router

This folder contains the [Slim microframework](http://www.slimframework.com/), which is used to provide simple routing functionality for the application. In other words, all you have to do is add content Markdown files and Slim will transform them into working web pages.

If you need a database connection, please refer to the Google Charts project for details about how to handle more complex data requests.

## Templates

Basic PHP templates that define the areas of the page. `Header.php` and `footer.php` contain the stylesheet and script links, while `content.php` provides the page structure for your application and can be modified to fit your needs.