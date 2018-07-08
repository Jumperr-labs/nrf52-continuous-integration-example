# nRF52 Continuous Integration example 
A sample repo to demonstrate how continuous integration works on nRF52 projects. This sample is based on the [following tutorial](https://blog.jumper.io/nrf52-continuous-integration/). Follow the instructions in the [link](https://blog.jumper.io/nrf52-continuous-integration/) to set this up yourself.

Click here to see the latest build result and artifact on CircleCI - [![CircleCI](https://circleci.com/gh/Jumperr-labs/nrf52-continuous-integration-example.svg?style=svg)](https://circleci.com/gh/Jumperr-labs/nrf52-continuous-integration-example)

Here's another example of a working continuous integration tool using Travis CI - [![Build Status](https://travis-ci.org/Jumperr-labs/nrf52-continuous-integration-example.svg?branch=master)](https://travis-ci.org/Jumperr-labs/nrf52-continuous-integration-example)


## What's in this sample

1. We used an mBed nRF52 deboucer project to demonstrate how to test a button with a debouncer. The code turns on an LED every time the button is pressed.
2. We then created a Docker container with the toolchain installed.
3. We create a Jumper test script that presses the button multiple times, but thanks to the debouncer it should only count as one.
4. Next, we configured CircleCI and TravisCI to build and run our testsour project every time we push new code to GitHub.

For full details and walkthrough, [head to the following link](https://blog.jumper.io/nrf52-continuous-integration/).

## How to run the build server locally

### Prerequisites
Docker - (if you’re looking to implement a continuous integration process, Docker is one of the building blocks you’ll need).

### Run these commands
```
docker pull jumperio/vlab-gcc-arm
git clone https://github.com/Jumperr-labs/nrf52-continuous-integration-example.git
cd nrf52-continuous-integration-example
docker run -v $PWD:/my_files_in_docker --entrypoint /usr/bin/make jumperio/vlab-gcc-arm -C my_files_in_docker
docker run -v $PWD:/my_files_in_docker -w /my_files_in_docker --entrypoint python jumperio/vlab-gcc-arm test.py
```

# Next steps

The following post demonstrates how to use CircleCI, TravisCI and Docker to create a continuous integration process with test automation. [See this link for more details](https://blog.jumper.io/nrf52-continuous-integration/).

Check out this [test automation and continuous integration for embedded software blog](https://blog.jumper.io) to learn more.

To Start using the Jumper Virtual Lab, [click here for more details](https://jumper.io).
