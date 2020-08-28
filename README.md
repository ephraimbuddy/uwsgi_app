# Running pyramid with 
A sample project to teach running python pyramid application using uwsgi.

# Running the applicatiion
First you need to install some dependencies in your system

`sudo apt install -y uwsgi-core uwsgi-plugin-python3`

Clone the application to your local machine

`git clone https://github.com/ephraimbuddy/uwsgi_app.git`

Create a virtualenv. Here I'm using conda

`conda create -n uwsgi-env python=3.7`

Activate it with `conda activate uwsgi-env`

Then install `uwsgi` with conda:

`conda install -c conda-forge uwsgi`

Run the application

`uwsgi development.ini`

# Troubleshooting

## ModuleNotFoundError: No module named 'pyramid'

If you get this error, you need to run `which` command:

`which uwsgi`

This will help us to know where the uwsgi we are using is located.
If the location is in `conda`, then install `uwsgi` with conda.

`conda install -c conda-forge uwsgi`

If however you used pipenv or venv to create your virtualenv. Make sure that uwsgi is stored there

## !!! UNABLE to load uWSGI plugin: ./python3_plugin.so: cannot open shared object file: No such file or directory !!!
 If you get this error, it means you are using the plugin option. The solution is to remove the plugin option from your configuration
 


