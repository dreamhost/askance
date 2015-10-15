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
1. Check out the askance repo (including `config.json.example` and `index.html`) inside `$JENKINS_HOME/userContent`
2. Copy `config.json.example` to `config.json` and edit for your Jenkins details
3. Load `https://$YOUR_JENKINS_SERVER/userContent/askance/index.html` to see your jobs and tabs!
