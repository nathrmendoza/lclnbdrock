# Bedrock x Sage x Acorn
Boilerplate and guide built for running bedrock, sage and acorn on local by flywheel.

## Creating an instance on local

- Create a site on flywheel, select custom environment.
- Php version should be >= 8.2. For the web server select nginx, if you're on linux and have not yet installed nginx run `sudo apt update` then `sudo apt install nginx`. No prefernce for DB. 
- Navigate to site folder (you should see, app, conf, and logs) and go to app. 
- Clone the repo from this directory
- Go back to site directory, open up `conf/nginx/site.conf.hbs` on your preferred code editor.
- Replace the path on root with your own path to the same directory. This should point to app/bedrock/web at the end.
- Remove the public folder from the app folder, since we've pointed nginx to start from the bedrock instance this is no longer needed.
- Navigate to the `/app/bedrock` run `composer install`
- Create a copy of .env.example, rename it to .env
- Set DB_NAME to local and set both DB_USER and DB_PASSWORD to root, replace WP_HOME with your own local domain.
- From here you can also generate your own keys for bedrock auth, this will only matter on production.
- Navigate to `web/app/themes/sample-theme-sage` run `composer install` then `npm install` or `yarn`. After installing all packages run `npm run build` or `yarn build`.
- Start up local server and you're good to go.