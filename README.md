# Docker for Drupal 7

### I'm lazy and don't want to read nothing about Docker.
So, you need to install docker engine and docker compose. Google for it.
This stack uses Apache, PHP 5.6, MySQL 5.6, Drush 7 and Solr 4.4. This is a combo for Drupal 7, an old stack for legacy projects.

The Apache/PHP container has a volume that syncronyze the folder ../docroot. If you want to change this, you can do this at line 20. You just need to change ../docroot for whatever you want.

     - ../docroot:/var/www/html

After that you just need to run this command:

    docker-compose up --build 


### If you need to import some dump to your MySQL container:

    docker exec -i drupal-mysql mysql -uroot -proot drupaldb < dumpfile
    
### How to run Drush commands?
    
    docker-compose run drush bash
    
Inside this bash you can run your drush commands.
    
### How can I access my project?

To access your Apache you need to access:
    
    localhost:8080

To acess your Solr you need to access:
    
    localhost:8081 
