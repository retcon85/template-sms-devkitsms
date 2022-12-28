# A basic devkitSMS (C programming language) template for an SMS game

## Features

- Basic Makefile to build the project
- SMS TMR header generation

## Prerequisites

### Using toolkit-sms Docker image

A Docker image is available at https://hub.docker.com/repository/docker/retcon85/toolkit-sms

`docker pull retcon85/toolkit-sms`

The entrypoint is `bash`, and although it is possible to simply `docker run retcon85/toolkit-sms`, I recommend setting up an alias function in your shell to run individual commands,

e.g. a zsh function, to go into `~/.zshrc`:

```
export SMS_HOME="/Users/<your_username>/<your-sms-projects-folder>/"
# User settings
function sms() {
  TMPVAR=$@;
  docker run --rm -it -v $SMS_HOME:/home/root/host/$SMS_HOME -w /home/root/host/$(pwd) retcon85/toolkit-sms -c $TMPVAR
}
```

This will then allow you to run commands like `sms make` directly from your project folders.

**Note:** this Docker image has currently only been tested under MacOS, although it would be expected to work under Linux also.

or

### Installing dependencies manually

- [devkitSMS](https://github.com/sverx/devkitSMS)
- [GNU Make](https://www.gnu.org/software/make/)

## Build instructions

1. Download and install prerequisites
1. Run `make` or `make build` to build a .sms file into the `build` folder
1. Read the docs at https://github.com/sverx/devkitSMS/wiki
1. Have fun

## Cleaning

Run `make clean` to clean the build

## Example program

!TODO: include one...