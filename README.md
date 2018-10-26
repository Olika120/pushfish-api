
<h1 align="center">
  <br>
  <a href="http://www.gitlab.com/PushFish/PushFish-API"><img src="https://user-images.githubusercontent.com/9034013/47518993-25c20880-d895-11e8-9e1f-bed2811fd433.png" alt="PushFish" width="200"></a>
  <br>
  PushFish API
  <br>
</h1>

<h4 align="center">A self-hosted alternative to services like PushBullet.</h4>

<p align="center">
  <a href="">
    <img src="http://img.shields.io/badge/license-BSD-blue.svg?style=flat"
         alt="License">
  </a>
</p>

<p align="center">
  <a href="#key-features">Key Features</a> •
  <a href="#how-to-use">How To Use</a> •
  <a href="#download">Download</a> •
  <a href="#license">License</a>
</p>

## Key Features

* Self-Hosted
  - Host your own instance, be in control of your data.
* Third-party service free
  - The API server needs no third-party services to function.
* Cross platform
  - Uses Docker, so Windows, macOS and Linux ready.

## Configuration

The pushfish API server reads various options from a configuration file. This configuration file can be specified by setting the environment variable `PUSHROCKET_CONFIG`. If this variable is not set, then the file is searched for in a default path.

```
     ~/.config/pushfish-api/pushfish-api.cfg # on Linux 
     %APPDATA%\pushfish-api\pushfish-api.cfg # on Windows
     ~/Library/Application Support/pushfish-api/pushfish-api.cfg # on OSX
```

where the value for "user" will be changed to your current username. If this file does not exist, then the API server will generate a default configuration, which looks like this:

```
[database]
#for mysql, use something like:
#uri = 'mysql+pymysql://pushfish@localhost/pushfish_api?charset=utf8mb4'

#for sqlite (the default), use something like:
uri = sqlite:////home/pushfish/.local/share/pushfish-api/pushfish-api.db

[dispatch]
google_api_key = 
google_gcm_sender_id = 509878466986
#point this at the pushfish-connectors zeroMQ pubsub socket
zeromq_relay_uri = 

[server]
#set to 0 for production mode
debug = 1

```

the format of the database URI is an SQLAlchemy URL as [described here](http://docs.sqlalchemy.org/en/latest/core/engines.html)

## How To Use

To clone and run this application, you'll need [Git](https://git-scm.com) and [Docker](https://www.docker.com/get-started) installed on your computer. From your command line:

```bash
# Clone this repository
$ git clone https://gitlab.com/PushFish/PushFish-API

# Go into the repository
$ cd PushFish-API

# Build docker
$ docker build -t pushfish-api:latest .

# Run the app
$ docker run pushfish-api:latest
```

## Download

You can [download](https://gitlab.com/PushFish/PushFish-API) the latest version of the PushFish API server for Windows, Linux and MacOS.

## Clients

* [Android](https://www.gitlab.com/PushFish/PushFish-Android)

* More coming soon

## License

BSD

---

> [push.fish](https://push.fish) &nbsp;&middot;&nbsp;
> GitLab [@PushFish](https://gitlab.com/PushFish) &nbsp;&middot;&nbsp;
> GitHub [@PushFish](https://github.com/PushFish)
