# GolangNetlifyFunctions

# Purpose
Netlify's documentation on deploying multiple Golang functions has a few pain points. First, deploying multiple functions on their system without the constant need to update the Makefile as this [example](https://github.com/netlify/aws-lambda-go-example) would have required. Second, deploying without a frontend introduces some small changes. This example attempts to streamline Netlify's already easy-to-use deployment system even further.

# Assumptions
This example makes a few assumptions about the Netlify deployment system to make this low-maintenance solution work:
1. Netlify's build repo root will always be: /opt/build/repo
2. Your Netlify functions folder will be called: functions

# How to deploy this example...
*The following assumes you have a Netlify account authorized to access your GitHub repos.

1. Fork this repo. TODO Insert Link to Forking
1. Change your GIT_IMPORT_PATH to your forked repo's URL.
1. Change the name of your functions folder in the netlify.toml.
   - If you make this change, be sure to change this appropriately. For instance, if your functions folder name is llama, you should change this line to: GOBIN=/opt/build/repo/llama.
1. Go to app.netlify.com to login.
1. Click on "New site from Git".
1. Select "GitHub".
1. Select or Find "GolangNetlifyFunctions" from the list.
1. Ensure the "Branch to deploy" drop-down field is set to master.
1. Click on "Deploy site".
1. Click on "Deploys" tab at the top of the page.
1. Wait for the first entry to change its status to: PUBLISHED.
1. Click on "Functions" tab at the top of the page.
1. You should see one function for "hello" and another for "goodbye".
1. If you click on either one, and visit the URL <insert url here>, you will see either the words "Hello, World!" or "Goddbye, World!"
1. Congratulations, you've just deployed a pure backend filled with Golang Netlify functions!

# How do I add more functions to this...
Simply create a directory on the first level of this repo, next to the "hello" and "goodbye" directories, and fill it with go files! This setup takes care of the rest!!! Have fun!

# References
* [Publishing a Golang Netlify Function](https://www.netlify.com/docs/functions/#go-lambda-functions)
* [netlify.toml Reference](https://www.netlify.com/docs/netlify-toml-reference/)