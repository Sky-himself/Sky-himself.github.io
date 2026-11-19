# Ehsan Moradi’s Academic Website

The source for my academic website and project portfolio. It brings together my research in edge computing, software projects, coursework, and teaching.

## Find the content

- [Pages](_pages) contain my bio and the main site sections.
- [Projects](_projects) includes thesis work, app case studies, and coursework in distributed systems and machine learning.
- [Teaching](_teachings), [bibliography](_bibliography), and [site settings](_config.yml) organize the remaining content.

## Preview locally

With Docker and Docker Compose installed, run the following from the repository root.

```sh
docker compose up
```

Open http://localhost:8080 for the preview. [Installation notes](docs/INSTALL.md) include a local Ruby and Bundler alternative.

## Publishing and credits

The [deployment workflow](.github/workflows/deploy.yml) builds the Jekyll site and publishes to the `gh-pages` branch. See [the workflow notes](docs/WORKFLOW_SECURITY.md) for how build and deployment permissions are scoped.

The site is based on [al-folio](https://github.com/alshedivat/al-folio), an academic Jekyll starter. See the [starter documentation](docs/README.md) and [MIT license](LICENSE).
