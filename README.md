# small ops

_EXPERIMENTAL_

Like fig was and docker-compose is, but with some more specific options.


## Installation

    apt-get install ruby
    gem install fige

## Tools

Run docker containers from a yml file, inspired by [fig](http://orchardup.github.io/fig/) and later [docker-compose](http://docs.docker.com/compose/), but simpler and more limited, as it is just a "docker-compose start".

Follow the same yml format, but do not support extend nor build.

An important difference is that the name of the container started is defined in the yml.

It can insert a "prefix" param on the name and env of the containers to run.

Usage:

    $ fige # will run the docker-compose.yml containers

Parameters:

    -c cmd, --command cmd : run "cmd" after each docker run
    -f, --foreground : keep fige on foreground and stop containers on exit
    -t name, --tagert name : only run specified container
    -i file, --input file : use "file" as yml
    -u, --update : pull container before run 
    -d FOO=BAR,FUZ=BAZ, --data FOO=BAR : insert data into the container env
    -n, --dry : Does not run commands, only simulate and output the commands it would run
    -a args, --append args : append args to docker run command

It will also insert HOST variable into the container env.

## License

MIT

