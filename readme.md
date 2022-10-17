Show directories of plots on a CERN EOS webpage with some interactive features

Taken from [simonepigazzini](https://github.com/simonepigazzini/php-plots), originally from [musella](https://github.com/musella/php-plots) with slight adjustements.

### Disclaimer
This worked for me, I didn't test this with any other users or sites.

# Instructions
1. Create CERN EOS website [here](https://webeos.docs.cern.ch/create_site/#creating-a-webeos-site). Follow the sections Prerequites and Site Creation Form.
    1. Go to your site under the [Web Services Portal](https://webservices-portal.web.cern.ch/webeos/)
    2. Enable "Use .htaccess files"
2. Go to the [Application Portal Home](https://application-portal.web.cern.ch/) of CERN:
    1. Click the green edit button
    2. Click the orange edit button "Edit role details" and check if the "This role applies to all authenticated users" is not checked. Clock submit or go back.
    3. Click the green button "Assign role to groups" and link a group that you want to give access to e.g. `atlas-active-members` so only people from ATLAS can access it.
3. Installation:
```
cd your-eos-directory     # in my case www
mkdir top-level-plotting-folder     # in my case ditau
cd top-level-plotting-folder
git clone --recursive https://gitlab.cern.ch/muellerr/php-plots.git
```
4. Adjust the line `DirectoryIndex index.php index.html index.htm /ditau/index.php` in the .htaccess file with the path to your index.php file. In the provided .htaccess I pointed to my directory `www/ditau/` where `www` is my EOS folder created for the website.
5. Drop any plotting directory in your top-level-plotting-folder