************************
Schemathesis-x-contracts
************************

Schemathesis-x-contracts is a plug-in for `Schemathesis`_ to make the tests more accurate by considering endpoints' `pre-conditions`_.

Schemathesis-x-contracts uses the convention introduced by `fastapi-icontract`_ to understand pre-conditions.
The pre-condition are thus read from an additional schema field, ``x-contracts``, specified per an endpoint.

As `Schemathesis`_ randomly generates test requests, the requests are guaranteed to satisfy the data schema, but might violate the pre-conditions.
In spite of such requests being invalid, `Schemathesis`_ would report them as errors -- they are clearly `false positives`_.
To reduce the noise, Schemathesis-x-contracts ignores the responses whenever the status code matches the status code specified for one of the pre-conditions.

.. _Schemathesis: https://schemathesis.readthedocs.io/en/stable/
.. _pre-conditions: https://en.wikipedia.org/wiki/Precondition
.. _fastapi-icontract: https://pypi.org/project/fastapi-icontract/
.. _false positives: https://en.wikipedia.org/wiki/False_positives_and_false_negatives

Usage
=====
TODO

Installation
============
TODO

Contributing
============

Feature requests or bug reports are always very, very welcome!
Please see quickly if the issue does not already exist in the
`issue section`_ and, if not, create `a new issue`_.

You can also contribute in code.
Please see `CONTRIBUTING.rst`_.

The current approach is based on `rejection sampling`_, a rudimentary (and hence inefficient) way to generate samples which satisfy a set of pre-conditions.
In the future, we would like to integrate `icontract-hypothesis`_ with `schemathesis-x-contracts`_ so that the APIs can be tested more effictively.
If you think this is something you would like to work on, please let us know by `commenting on this issue`_!

.. _issue section: https://github.com/mristin/crosshair-pycharm/issues
.. _a new issue: https://github.com/mristin/crosshair-pycharm/issues/new
.. _CONTRIBUTING.rst: https://github.com/mristin/schemathesis-x-contracts/blob/main/CONTRIBUTING.rst
.. _rejection sampling: https://en.wikipedia.org/wiki/Rejection_sampling
.. _icontract-hypothesis: https://pypi.org/project/icontract-hypothesis/
.. _commenting on this issue: https://github.com/mristin/schemathesis-x-contracts/issues/1

Versioning
==========
We follow `Semantic Versioning`_.
The version X.Y.Z indicates:

* X is the major version (backward-incompatible),
* Y is the minor version (backward-compatible), and
* Z is the patch version (backward-compatible bug fix).

.. _Semantic Versioning: http://semver.org/spec/v1.0.0.html
