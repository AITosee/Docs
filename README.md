[![doc-build](https://readthedocs.org/projects/toseedocs/badge/?version=latest)](https://toseedocs.readthedocs.io/zh/latest/?badge=latest)

# Tosee-docs

Tosee Inc. documents

Website: https://toseedocs.readthedocs.io/

## Local edit

refer to [Read-the-Docs Getting Started with Sphinx](https://read-the-docs.readthedocs.io/en/latest/intro/getting-started-with-sphinx.html#)

- 1.Assuming you have Python already, install Sphinx:

    ```bash
    $ pip install sphinx>=2.6
    ```

- 2.Install `recommonmark` for markdown files(.md):

    ```bash
    $ pip install recommonmark
    ```

- 3.Install theme `sphinx_rtd_theme`:
    ```bash
    $ pip install sphinx_rtd_theme
    ```

- 4.Make file:

    ```bash
    $ cd ${your_project_path}/Tosee-docs/
    $ make html
    ```

- 5.Open file `index.html` in path `${your_project_path}/Docs/_build/html/index.html`
