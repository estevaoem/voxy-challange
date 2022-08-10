# Voxy Word Counter

This project tackles the following acceptance criteria:

```
As a user when I view the application then I see a form containing a text box to enter a body of text and when I submit the form with some text then I see a result containing the number of words in the text box
and when I submit the form with an empty text then I see a form error telling me that some text input is required.

As an engineer when I look at your project then I should understand how to install and run it.
```

## Dependencies

- [Docker](https://docs.docker.com/engine/install/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Container for development

Run on the project root from terminal

```
docker-compose up
```

And watch for the network addresses that pops on the terminal. Will be something like this:

```
vue_dev_app |   App running at:
vue_dev_app |   - Local:   http://localhost:8080/
vue_dev_app |   - Network: http://192.168.0.2:8080/
```

Both Local and Network addresses can be entered on the browser, `Local` beeing your localhost and Network beeing the docker container address (to check it, run `docker container inspect vue_dev_app`)

## Container for production

Run on the project root from the terminal

```
docker build . -t vue-production && docker run -p 8080:80 vue-production
```

The production page can be accessed (from the localhost) as `http://localhost:8080/`
