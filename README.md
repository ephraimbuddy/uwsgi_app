# Running pyramid with uwsgi
A sample project to teach running python pyramid application using uwsgi.

# Follow these steps to run this sample project
First you need to install some dependencies in your system

`sudo apt install -y uwsgi-core uwsgi-plugin-python3`

Clone the application to your local machine

`git clone https://github.com/ephraimbuddy/uwsgi_app.git`

Create a virtualenv. Here, I'm using conda

`conda create -n uwsgi-env python=3.7`

Activate it with `conda activate uwsgi-env`

Then install `uwsgi` with conda:

`conda install -c conda-forge uwsgi`

Go to the `[uwsgi]` section in the development.ini file and change the path to your virtualenv path.
Then install the application in editable mode:

`pip install -e .`

Run the application

`uwsgi development.ini`

# Troubleshooting

## ModuleNotFoundError: No module named 'pyramid'

If you get this error, you need to run `which` command:

`which uwsgi`

This will help you to know where the `uwsgi` is located.
If the virtualenv is in `conda`, then install `uwsgi` with conda.

`conda install -c conda-forge uwsgi`

If however you used pipenv or venv to create your virtualenv. Make sure that uwsgi is installed in the environment.

## !!! UNABLE to load uWSGI plugin: ./python3_plugin.so: cannot open shared object file: No such file or directory !!!
 If you get this error, it means you are using the plugin option. The solution is to remove the plugin option from your configuration
