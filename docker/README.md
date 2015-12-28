# Reveal.js on Docker

This Docker image runs the [Reveal.js](https://www.github.com/hakimel/reveal.js) HTML presentation framework on a NodeJS web server. The image can be used for editing and serving your presentation.

## Basic usage

Easiest way to run this image is to use [Docker Compose](https://ww.docker.com/docker-compose).

1. Install [Docker Toolbox](https://www.docker.com/docker-toolbox)  

1. Start the Docker Quickstart Terminal

1. Clone the git repo
  ```sh
  git clone https://github.com/rvdmei/reveal.js.git my-presentation
  ```
1. Run Docker Compose
  ```sh
  cd my-presentation/docker
  docker-compose up
  ```
1. That's it! Setup is done, go edit your presentation ...

## Add custom stylesheets

1. Copy a sass stylesheet to css/theme/source

2. Process the sass file in the container to create the css file
```sh
$ docker exec -ti $(docker ps -lq) grunt sass
```

  Replace ```$(docker ps -lq)``` with docker container id if you started containers after ```docker-compose up```.
