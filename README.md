# Docker Exploration
I'm using Docker at ReRent, but I've never taken the time to set it up and really understand what its all about.  In this repo, I'm going to follow a tutorial found [here](https://docs.docker.com/compose/django/) so I can get a better understanding of how to use Docker.


### After completion here's what I've learned.
__Docker must be running:__ Unfortunately, when I first started to get this working I was getting `ConnectionError: ('Connection aborted.', ConnectionRefusedError(61, 'Connection refused'))` which was very frustrating because I was literally following a tutorial.  After some research and some thinking, I realized the docker app must be running.... :facepalm:

__.env files need to be 'imported' to docker builds:__ Early on with Django apps, I realized they would expose the Django `SECRET_KEY` on original setup.  I normally hide those using something like python-dotenv or pipenv.  Unfortunately in my docker builds, they weren't being picked up.  I got around this by passing varibles from .env into docker-compose.yml.

## In conclusion:
I've now got a base django app running at `localhost:2000` connected to a PSQL DB through a docker container!  While not feeling like a docker pro yet, I have successfully set up a container, hidden some important environmental vars, and have a better understanding of how to use docker and why to use it.  Hopefully I find some new uses for it in the near future.
