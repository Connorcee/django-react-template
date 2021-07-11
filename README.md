### What
Template for a Django Web App fronted with React and some additional services if you need them

 - Solr
 - Rabbit
 - Postgres

There is also a makefile to make common tasks easy.

### How

General usage is to have this as the basis of a project. Super lightweight so you'll need to make a lot of decisions
yourself, but a lot of them should be dependent on the target platform you want to send this too.

NOTE: There is a django secret key in this repository. This is fine because it isn't the production key. I suggest you
modify `production.py` settings file to pull from the infra secrets store. (If you've bothered to set one up)