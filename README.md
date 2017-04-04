# docker-discourse

discourse image for discourse service

# How to use this image

The easiest is to use our `docker-compose.yml`.

Make sure you have [docker-compose](http://docs.docker.com/compose/install/) installed. And then:

```
git clone https://github.com/indiehosters/discourse.git
cd discourse
echo "POSTGRES_USER=discourse" > env
docker-compose run app bash -c "sleep 3 && rake db:migrate assets:precompile"
docker-compose up

## Discourse plugins

This image supports installing Discourse plugins at build time, via the `DISCOURSE_ADDITIONAL_PLUGINS` [build arg](https://docs.docker.com/engine/reference/builder/#/arg). Set it to a whitespace (space, tab, newline) separated list if valid `git` URLs of plugins to be installed at build time.
