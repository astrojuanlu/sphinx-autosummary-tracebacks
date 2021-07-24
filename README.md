# Autosummary Tracebacks

See discussion at https://github.com/sphinx-doc/sphinx/issues/7989

```bash
(.venv) $ pip install -r requirements.txt
(.venv) $ python -c "from test_pkg import A; print(A)"
<class 'test_pkg.A'>
(.venv) $ make html
Running Sphinx v4.1.1
loading pickled environment... done
building [mo]: targets for 0 po files that are out of date
building [html]: targets for 1 source files that are out of date
updating environment: [config changed ('autosummary_generate')] 2 added, 0 changed, 0 removed
reading sources... [100%] index
/home/juanlu/Projects/RTD/tmp/sphinx-autosummary-tracebacks/source/index.rst.rst:13: WARNING: autosummary: stub file not found 'test_pkg.A'. Check your autosummary_generate setting.
looking for now-outdated files... none found
pickling environment... done
checking consistency... /home/juanlu/Projects/RTD/tmp/sphinx-autosummary-tracebacks/source/autogen/test_pkg.A.rst: WARNING: document isn't included in any toctree
done
preparing documents... done
writing output... [100%] index
generating indices... genindex done
writing additional pages... search done
copying static files... done
copying extra files... done
dumping search index in English (code: en)... done
dumping object inventory... done
build succeeded, 2 warnings.

The HTML pages are in build/html.
(.venv) $ python -m sphinx -W -b html source/ build/html
Running Sphinx v4.1.1
building [mo]: targets for 0 po files that are out of date
building [html]: targets for 2 source files that are out of date
updating environment: [new config] 2 added, 0 changed, 0 removed
reading sources... [100%] index

Warning, treated as error:
/home/juanlu/Projects/RTD/tmp/sphinx-autosummary-tracebacks/source/index.rst.rst:13:autosummary: stub file not found 'test_pkg.A'. Check your autosummary_generate setting.
```
