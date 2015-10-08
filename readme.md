#Backup drupal website

##backup drupal script

###Prerequisites

* Dropbox installed and running
* Mamp installed and running
* A folder named CVO in your drop box folder
* Your drupal sites must be in a directory named drupal inside your htdocs folder

**Important ! The database name and the name of the drupal site folder in htdocs must be the same**

###What it does

This script will create a .sql dump of a drupal site and compress it. Then it will be moved to your dropbox folder. After that the site folder in htdocs/drupal will be zipped and also be moved to the dropbox folder.

###Usage

* Clone the repo
* Install the script in your ~/bin folder.
* Make it executable with chmod u+x ./backupdrupal
* Execute with ./backupdrupal <sitename>

###Example usage

Present on the computer

* A database named tweedewebsite where the drupal tables are stored
* A drupal site in **htdocs/drupal/tweedewebsite**


		./backupdrupal tweedewebsite

This will create a **tweedewebsite.sql.gz** and a **tweedewebsite.zip** file in your dropbox/ CVO folder.
