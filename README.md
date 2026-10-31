# gmezah.github.io

Personal website built with [Quarto](https://quarto.org).

## Structure

| Folder / file            | Contents                                                     |
|--------------------------|--------------------------------------------------------------|
| `index.qmd`              | Home page                                                    |
| `data/`                  | One subfolder per topic, each with its `index.qmd` and data  |
| `data/_template/`        | Template for a new topic (not published)                     |
| `media/media.yml`        | Columns, interviews and articles                             |
| `reports/reports.yml`    | Reports and technical papers                                 |
| `about.qmd`              | Bio                                                          |
| `styles/`                | Colours and fonts (light and dark mode)                      |
| `files/`, `images/`      | PDFs (CV, thesis), profile photo and favicon                 |

## Previewing on your computer

1. Install Quarto and the Python packages: `pip install -r requirements.txt`.
2. Run `quarto preview` to see the site.

## Publishing on GitHub Pages

1. Push to the `master` branch. The GitHub Action installs Python, renders the site (downloading the data and drawing the charts) and publishes it to the `gh-pages` branch.
2. The first time, go to Settings > Pages on GitHub and choose the `gh-pages` branch as the source.
3. Optional: if you run `quarto render` locally and commit the `_freeze/` folder, the Action reuses those results instead of running the code again.

To add the thesis, copy it to `files/thesis-gustavo-meza.pdf` and uncomment its block in `reports/reports.yml`.

## Adding content

- **Media appearance:** copy a block in `media/media.yml` and edit it.
- **New data topic:** copy `data/_template` to `data/topic-name`, edit its `index.qmd` and run `quarto render` again.
- **Update a topic's data:** delete its `data.csv` and run `quarto render` again.
