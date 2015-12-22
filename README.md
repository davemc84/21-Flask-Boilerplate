# Flask 21 Boilerplate

![License](http://img.shields.io/:license-mit-blue.svg)

This provides a boilerplate template to provide 21 devs with the infrastructure necessary to develop consumer or public facing apps. 

## 21 Specific Features

- [ ] Plugging in the two1 lib to provide access to cli functionality
- [ ] Admin panel to provide information on 21 diagnostics
- [x] Per user, individually provisioned wallets
- [ ] HD child address generation with QR code support
- [ ] Wallet send flow
- [ ] Public listing of 402 endpoints (nice to have)
- [ ] Public access to 402 endpoint for each user, will be centralized through 21-user for now (nice ot have)
- [ ] Admin panel accessible by the 21 owner
- [ ] All information available through 21-cli displayable for admins (flush, mine, etc.)
- [ ] All functionality available with the 21-cli available to admins (flush, mine, etc.)

Please feel free to fill in anything else that you feel would be useful or to create an issue with your suggestion, with an emphasis on tools that have broad use cases

## Generic Boilerplate Features

- [x] User account sign up, sign in, password reset, all through asynchronous email confirmation.
- [x] Form generation.
- [x] Error handling.
- [x] HTML macros and layout file.
- [x] "Functional" file structure.
- [x] Python 3.x compliant.
- [x] Asynchronous AJAX calls.
- [ ] Application factory.
- [x] Online administration.
- [ ] Static file bundling, automatic SCSS to CSS conversion and automatic minifying.
- [ ] Websockets (for example for live chatting)
- [x] Virtual environment example.
- [ ] Heroku deployment example.
- [x] Digital Ocean deployment example.
- [ ] Tests.
- [ ] Logging.
- [ ] Language selection.

## Libraries

### Backend

- [Flask](http://flask.pocoo.org/).
- [Flask-Login](https://flask-login.readthedocs.org/en/latest/) for the user accounts.
- [Flask-SQLAlchemy](https://pythonhosted.org/Flask-SQLAlchemy/) interacting with the database.
- [Flask-WTF](https://flask-wtf.readthedocs.org/en/latest/) and [WTForms](https://wtforms.readthedocs.org/en/latest/) for the form handling.
- [Flask-Mail](https://pythonhosted.org/Flask-Mail/) for sending mails.
- [itsdangerous](http://pythonhosted.org/itsdangerous/) for generating random tokens for the confirmation emails.
- [Flask-Bcrypt](https://flask-bcrypt.readthedocs.org/en/latest/) for generating secret user passwords.
- [Flask-Admin](https://flask-admin.readthedocs.org/en/latest/) for building an administration interface.

### Frontend

- [Semantic UI](http://semantic-ui.com/) for the global style. Very similar to [Bootstrap](http://getbootstrap.com/).
- [Leaflet JS](http://leafletjs.com/) for the map. I only added for the sake of the example.

## Structure

I did what most people recommend for the application's structure. Basically, everything is contained in the ``app/`` folder.

- There you have the classic ``static/`` and ``templates/`` folders. The ``templates/`` folder contains macros, error views and a common layout.
- I added a ``views/`` folder to separate the user and the website logic, which could be extended to the the admin views.
- The same goes for the ``forms/`` folder, as the project grows it will be useful to split the WTForms code into separate files.
- The ``models.py`` script contains the SQLAlchemy code, for the while it only contains the logic for a ``users`` table.
- The ``toolbox/`` folder is a personal choice, in it I keep all the other code the application will need.


## Setup

### Vanilla

- Install the required libraries.

	``pip install -r requirements.txt``

- Create the database.

	``python createdb.py``

- Run the application.

	``python run.py``

- Navigate to ``localhost:5000``.


### Virtual environment

```
pip install virtualenv
virtualenv venv
venv/bin/activate (venv\scripts\activate on Windows)
pip install -r requirements.txt
python createdb.py
python run.py
```


## Deployment

- Heroku
- [Digital Ocean](deployment/Digital-Ocean.md)


## Configuration

The goal is to keep most of the application's configuration in a single file called ``config.py``. The one that is included is basic and yet it covers most of the important stuff.

there is a working Gmail account to confirm user email addresses and reset user passwords, although in production you should't include the file if you push to GitHub because people can see it. The same goes for API keys, you should keep them secret. You can read more about secret configuration files [here](https://exploreflask.com/configuration.html).

Read [this](http://flask.pocoo.org/docs/0.10/config/) for information on the possible configuration options.


