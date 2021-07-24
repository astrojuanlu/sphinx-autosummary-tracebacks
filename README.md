# Autosummary Tracebacks

See discussion at https://github.com/sphinx-doc/sphinx/issues/7989

```bash
(.venv) $ pip install -r requirements.txt
(.venv) $ python -c "import test_pkg.A; print(test_pkg.A)"
Traceback (most recent call last):
  File "<string>", line 1, in <module>
  File "/home/juanlu/Projects/RTD/tmp/sphinx-autosummary-tracebacks/.venv/lib/python3.7/site-packages/test_pkg.py", line 7, in <module>
    import attrs  # Do not install to surface problem
ModuleNotFoundError: No module named 'attrs'
(.venv) $ make html
Running Sphinx v4.1.1
loading pickled environment... done
[autosummary] generating autosummary for: index.rst
WARNING: [autosummary] failed to import 'test_pkg.A': no module named test_pkg.A
building [mo]: targets for 0 po files that are out of date
building [html]: targets for 0 source files that are out of date
updating environment: 0 added, 0 changed, 0 removed
looking for now-outdated files... none found
no targets are out of date.
build succeeded, 1 warning.

The HTML pages are in build/html.
(.venv) $ python -m sphinx -W -b html source/ build/html
Running Sphinx v4.1.1
[autosummary] generating autosummary for: index.rst

Warning, treated as error:
[autosummary] failed to import 'test_pkg.A': no module named test_pkg.A
```
