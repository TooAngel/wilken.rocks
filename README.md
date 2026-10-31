# wilken.rocks

Public page for www.wilken.rocks. Plain static HTML, no build step.

Served as a static dokku app (`wilken-rocks` on server; the empty
`.static` file selects dokku's nginx buildpack). A push to `main` triggers
`.github/workflows/deploy.yml`, which asks the dokku-bridge to sync and
build this repo, then waits until the live page matches the commit.

`app-nginx.conf.sigil` is the buildpack's default nginx config plus a 301
from every other host name (wilken.rocks) to `https://www.wilken.rocks`.

At home, Pi-hole resolves the wilken.rocks names to the local services
on vogt instead.
