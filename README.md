# cloudytamil
# Hearzap-Console
Hearzap-Console-v3

# Python and Django
*********************
Python version 3.10.x
Django version 4.0.x



# setting up venvs
****************
> cd workspace (located in /~/workspace/)

> sudo apt-get install python3.10-venv

> mkdir virtualenvs

> python3.10 -m venv virtualenvs/hearzap.env

# setting up alias
****************
> cd ~

> vi .bashrc

> alias hearzap='source /opt/workspace/virtualenvs/hearzap.env/bin/activate'

# setting up webapp (git)
*******************
> cd Workspace (located in /opt/workspace)

> git clone git@github.com:IZA-MEDI-TECHNOLOGIES-PRIVATE-LIMITED/hearzap-console.git

# setting up HearZap console venv
**************************
> cd /opt/workspace/hearzap-console/

> pip install -r requirements.txt

#maria db configration
> sudo apt update
> sudo apt install mariadb-server
> sudo systemctl start mariadb
> sudo systemctl enable mariadb
> sudo mysql_secure_installation
> sudo mariadb

# create db
***********************
> mysql -u root -p

> mysql > drop database hearzap_db;

> mysql > create SCHEMA hearzap_db CHARACTER SET utf16 COLLATE utf16_general_ci;

# running the dxp-core
***********************
> cd /opt/workspace/hearzap-console/appsource/dxp/

> python3 manage.py runscript script_db_init

> python3 manage.py runscript script_fixtures_build

> python3 manage.py runscript script_fixtures_run

> python3 manage.py runserver
> 
> # Install mysql server locally
*********************************************
> sudo apt update

> sudo apt install mysql-server

> sudo systemctl status mysql

> sudo mysql_secure_installation

> mysql -u root -p

> mysql > ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'secret';

> mysql > FLUSH PRIVILEGES;

> mysql > exit;

> sudo service mysql restart

> sudo apt-get install mysql-client

> sudo apt-get install libmysqlclient-dev
