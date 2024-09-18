# docker-multi-php

Run multiple PHP versions with Docker.


## Usage

First, build your desired image, for example:

```shell
cd php74
docker build -t localphp:74 .
```

Now, in your `.bash_aliases` or `.zsh_aliases` add:

```shell
_php74 () {
  docker run -it --rm -v "$PWD":/opt/yeyo -w /opt/yeyo localphp:74 php "$@"
}

_composer_php74 () {
  docker run -it --rm -v "$PWD":/opt/yeyo -w /opt/yeyo localphp:74 composer "$@"
}
```

This will create a temporary container and pass all the arguments to it.
Remember to restart your terminal or do `source .the_aliases_file`.

Finally, you can run PHP or Composer with:

```shell
_php74 artisan serve

_composer_php74 install
```
