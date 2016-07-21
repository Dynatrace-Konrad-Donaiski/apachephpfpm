# Magento PHP-FPM

## Overview

* [Requirements](#requirements)
* [How to start](#how-to-start)
* [Architecture](#architecture)
* [Configuration](#configuration)


## Requirements
* __docker-engine__
* __docker-compose__

## How to start
* Use only docker-compose commands. e.g "__docker-compose up__" that starts containers from scratch.

##Architecture
* Architecture is defined in the __docker-compose.yml__ file.
* There are three docker containers total.

 * __NGINX__
 * __PHP__
 * __MYSQL__

* MySQL container is linked to the php container and resolved as mysql.
* PHP container is linked to the nginx container and resolved as php.
* The NGINX container is build from official nginx image and volumed with configure files placed in the __config/nginx__ folder.
* The MYSLQ container is build from official mysql image and volumed with sql schema file placed in the __database__ folder.
* The PHP container is build from __images/php__, there is a docker file based on the official PHP5.6-FPM image and additional php configuration files.