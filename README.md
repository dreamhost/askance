# askance
An at-a-glance dashboard showing the status of a configurable set of Jenkins jobs over the last 24 hours.

## Pre-installation
1. You'll need to copy `config.json.example` to `config.json`
2. Edit `config.json` and put in the proper values for your Jenkins server, username, and at the moment, password (should be changed to use an authentication token but for now it works with the password, so don't use an admin user account).
3. There are two options for installation (in theory) but only one has been tested so far. Using a static-file-capable webserver like Apache or Nginx is the tested and confirmed-working method at the moment, with instructions below. It should also be possible to host these files inside the Jenkins server itself, but that has not yet been tested or confirmed to work.

### Webserver installation
1. Move `config.json` and `index.html` to a web-hosted directory and make sure the files and folder are readable by the web-server user.
2. Install the CORS Filter plugin for Jenkins.
3. Add the server's hostname and the 'GET' method to the CORS Filter settings in Jenkins.
4. Done!

### Jenkins installation
NOTE: Not tested yet! Theoretically it should be possible to host this inside the Jenkins server.
1. It should be possible to create a directory containing `config.json` and `index.html` inside `$JENKINS_HOME/userContent`, which would then be available from the Jenkins server.
