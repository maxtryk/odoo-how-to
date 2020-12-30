Setup and Run
=============
#. clone https://github.com/odoo/odoo.git branch **12.0** into **/odoo**
#. create directories **/filestore**, **/addons**
#. create **venv**
#. ::

    pip install -r odoo/requirements.txt

#. comment out **'pyldap'** from **odoo/setup.py** before install::

    pip install -e odoo

#. create db user

    https://www.odoo.com/documentation/12.0/setup/install.html#postgresql

#. create **odoo.conf** and edit relevant values::

    python odoo\odoo-bin --save

#. run in dev modes with modules upgrade::

    python odoo\odoo-bin -c odoo.conf -u module1 --dev=xml,qweb

