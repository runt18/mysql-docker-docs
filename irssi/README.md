# Supported tags and respective `Dockerfile` links

-	[`0.8.17`, `0.8`, `0`, `latest` (*Dockerfile*)](https://github.com/jfrazelle/irssi/blob/dfefff246e4a04dee588feafc1d720b5247a112e/Dockerfile)

For more information about this image and its history, please see the [relevant manifest file (`library/irssi`)](https://github.com/docker-library/official-images/blob/master/library/irssi) in the [`docker-library/official-images` GitHub repo](https://github.com/docker-library/official-images).

# What is irssi?

Irssi is a terminal based IRC client for UNIX systems. It also supports SILC and ICB protocols via plugins. Some people refer to it as 'the client of the future'.

> [irssi.org](http://irssi.org)

![logo](https://raw.githubusercontent.com/docker-library/docs/master/irssi/logo.png)

# How to use this image

Because it is unlikely any two irssi users have the same configuration preferences, this image does not include an irssi configuration. To configure irssi to your liking, please refer to [upstream's excellent (and comprehensive) +documentation](http://irssi.org/documentation).

Be sure to also checkout the [awesome scripts](https://github.com/irssi/scripts.irssi.org) you can download to customize your irssi configuration.

## Directly via bind mount

On a Linux system, build and launch a container named `my-running-irssi` like this:

	docker run -it --name my-running-irssi -e TERM -u $(id -u):$(id -g) \
	    -v $HOME/.irssi:/home/user/.irssi:ro \
	    -v /etc/localtime:/etc/localtime:ro \
	    irssi

On a Mac OS X system, run the same image using:

	docker run -it --name my-running-irssi -e TERM -u $(id -u):$(id -g) \
	    -v $HOME/.irssi:/home/user/.irssi:ro \
	    irssi

You omit `/etc/localtime` on Mac OS X because `boot2docker` doesn't use this file.

Of course, you can name your image anything you like. In Docker 1.5 you can also use the `--read-only` mount flag. For example, on Linux:

	docker run -it --name my-running-irssi -e TERM -u $(id -u):$(id -g) \
	    --read-only -v $HOME/.irssi:/home/user/.irssi \
	    -v /etc/localtime:/etc/localtime \
	    irssi

# License

View [license information](https://github.com/irssi/irssi/blob/master/COPYING) for the software contained in this image.

# Supported Docker versions

This image is officially supported on Docker version 1.5.0.

Support for older versions (down to 1.0) is provided on a best-effort basis.

# User Feedback

## Issues

If you have any problems with or questions about this image, please contact us through a [GitHub issue](https://github.com/jfrazelle/irssi/issues).

You can also reach many of the official image maintainers via the `#docker-library` IRC channel on [Freenode](https://freenode.net).

## Contributing

You are invited to contribute new features, fixes, or updates, large or small; we are always thrilled to receive pull requests, and do our best to process them as fast as we can.

Before you start to code, we recommend discussing your plans through a [GitHub issue](https://github.com/jfrazelle/irssi/issues), especially for more ambitious contributions. This gives other contributors a chance to point you in the right direction, give you feedback on your design, and help you find out if someone else is working on the same thing.
