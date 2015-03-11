Notes
=====

Aim - a script which can pull down the core code and any extra components (e.g. plugins or themes) of a content management system installation, and perform any other steps needed to build or update the installation. It should be configurable to work with various different cmses.

Written in bash so can run on any unix system. Also, scripting extra actions in bash is easy.

Elements of the system
----------------------

Schemas - a schema is a file (a bash dot file) which configures the program to work with a particular cms. It contains settings and also functions that are particular to that cms.

Components - a component of a cms installation. E.g. a theme or plugin.

Installations - a unique installation of a cms, which uses a given schema. Each installation has an INI file which describes what cms it is an installation of, and which components and actions are needed to build it.

Retrievers - functions which can retrieve a version of a component. E.g. for wordpress, a function to pull a given plugin version (specified in x.x.x form). The retrievers can be defined either in the main program file or in the schema for each cms.

Actions - mini scripts which can be called in the course of building an installation. There are pre-build actions and post-build actions. Some of these are provided by the schemas; others might be specific to an installation. E.g. an action to put a site into maintenance mode while updates are done, or to copy the settings into a wordpress installation.


Configuration directory layout
------------------------------

`cobbles`
`cobbles/config.ini`
`cobbles/schemas` 
`cobbles/schemas/wordpress`
`cobbles/schemas/wordpress/retrievers.sh`
`cobbles/schemas/wordpress/actions.sh`
`cobbles/schemas/wordpress/config.ini`
`cobbles/schemas/dokuwiki`
`...`
`cobbles/installations/highfellow`
`cobbles/installations/highfellow/actions.sh`
`cobbles/installations/highfellow/config.ini`
`...`
