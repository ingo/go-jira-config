
# go-jira-config
Configuration files for go-jira (https://github.com/Netflix-Skunkworks/go-jira)

## Installation
* OSX: brew install go-jira
* Windows/Linux: Download from [https://github.com/Netflix-Skunkworks/go-jira](https://github.com/Netflix-Skunkworks/go-jira)

### OSX-Only
1. Create a file under ~/.jira.d/config.yml
2. Make it executable (chmod a+x config.yml)
3. Add the following (modify to suit)
    ```
	#!/usr/bin/env bash

	# Write out the current values of the config file
	cat ~/Documents/Projects/go-jira-config/config.yml

	# parse the JIRA project out of the package.json. Perhaps need to do this differently for JAVA projects.
	echo "project: $(jq '.bugs.url | sub(".*/";"")' -r package.json)"
	```

### Windows
TBD

## Commands

Note, the templating language is https://gohugo.io/templates/introduction/

* epics: list epics
* gantt: create a gantt chart based on a list of issues
* members: members of a particular role on a project
* mine:  display issues assigned to me
* neglected: display issues in progress but no longer being worked on
* premature: display issues started before the Epic is ready
* print-project: print the name of the configured project
* project: list a project
* projects:  list all projects
* ruhroh:  display issues in progress but somehow marked as included in a release
* filter: write out the configuration information for a filter
* boards list: list all Agile boards (that you can see)
* board active: display if a board has any active sprints
* remote-links list: list remote links on an issue
