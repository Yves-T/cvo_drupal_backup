#Backup drupal website scripts

##backupdrupal script

###Prerequisites

* Dropbox installed and running
* Mamp installed and running
* A folder named CVO in your drop box folder
* Your drupal sites must be in a directory named drupal inside your htdocs folder

**Important ! The database name and the name of the drupal site folder in htdocs must be the same !!**

###What it does

This script will create a .sql dump of a drupal site and compress it. Then it will be moved to your dropbox folder. After that the site folder in **htdocs/drupal** will be zipped and also be moved to the dropbox folder.

###Usage

* Clone the repo
* Install the script in your ~/bin folder.
* Make it executable with **chmod u+x ./backupdrupal**
* Execute with **./backupdrupal <sitename>**

###Example usage

Present on the computer

* A database named tweedewebsite where the drupal tables are stored
* A drupal site in **htdocs/drupal/tweedewebsite**


		./backupdrupal tweedewebsite

This will create a **tweedewebsite.sql.gz** and a **tweedewebsite.zip** file in your dropbox/ CVO folder.

##extractdrupal script

###Prerequisites

* Dropbox installed and running
* Mamp installed and running
* A folder named CVO in your drop box folder containing 2 files created with the backupdrupal script in the ~/Dropbox/CVO folder: **<drupal_site_name>.sql.gz** and **<drupal_site_name>.zip**

###What it does

This script will restore your drupal site by creating a MySQL database ( if it doesn't exist already ) and then an extract and import operation of the **<drupal_site_name>.sql.gz** file in the MySQL database. After that it will unzip the **<drupal_site_name>.zip** in htdocs/drupal.

###Usage

* Clone the repo
* Install the script in your ~/bin folder.
* Make it executable with **chmod u+x ./extractdrupal**
* Execute with **./extractdrupal <sitename>**

###Example usage

	./extractdrupal tweedewebsite

This will restore your tweedewebsite in htdocs/drupal.
