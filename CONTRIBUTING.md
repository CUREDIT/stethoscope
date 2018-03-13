How to Contribute to Stethoscope
================================

Thanks for considering contributing to Stethoscope! We're open to all kinds of contributions. 
If you're looking for ideas, take a look at the issues labeled [help 
wanted](https://github.com/Netflix/stethoscope/labels/help%20wanted). Some easier issues for 
a newcomer to tackle are also labeled with [difficulty: newcomer](https://github.com/Netflix/stethoscope/labels/difficulty%3A%20newcomer). 

Feel free to join us on [Gitter](https://gitter.im/Netflix-Stethoscope/Lobby) to chat about 
ideas or ask questions.  

Python Coding Style Guidelines
------------------------------

### Code Style

The code style is based on [PEP8](http://legacy.python.org/dev/peps/pep-0008/),
with a few important exceptions:

1. Indentation should be two spaces (`E111`, `E114` in `setup.cfg`).
2. Maximum line-length is 100. Exceptions are allowed where breaking a line
   would be extremely prejudicial to readability (e.g., for a URL; any such
   exceptions should include the `# noqa` comment at the end of the line).
3. Hanging indents are silly (`E121`, `E128`, `E125`).
4. Do not use single-letter variable names (e.g., `x = 1`) except inside list comprehensions. They
   are not descriptive and make it difficult to search the codebase. Suggestions for common loop
   variables: use `idx` instead of `i` and `key, value` instead of `k, v`.

If you're using the [pep8 tool](https://pep8.readthedocs.io/), these should be
covered by the `ignore` directive in `setup.cfg`.


### Testing

Tests are performed by [pytest]. First, you'll want to set up a [virtualenv] and clone the
repository. Then you can install the dependencies for the test suite with either:

```sh
make install-python-requirements
```

or:

```sh
pip install -r requirements.txt
```

Run the tests under your current `virtualenv` using either:

```sh
make test
```

or:

```sh
py.test
```

Tests for other versions can be run via [tox] after installing all the relevant versions of Python
(2.7, 3.4, 3.5, 3.6). Using `make tox` will run `detox` in place of `tox` if available.

```sh
make tox
```

You can run the tests and output a test coverage report (via the `pytest-cov` plugin) with either:

```sh
make coverage
```

or:

```sh
py.test --cov-report html --cov=stethoscope
```

This generates a coverage report in the `htmlcov/` directory (see [coverage] for more information).


[coverage]: https://coverage.readthedocs.io
[tox]: https://tox.readthedocs.io/en/latest/
[virtualenv]: https://virtualenv.pypa.io/en/stable/
[pytest]: http://pytest.org/latest/
