Release Procedure
-----------------

#. Dependening on the magnitude of the changes in the release, consider testing
   some of the large downstream users of ln_pluggy against the upcoming release.
   You can do so using the scripts in the ``downstream/`` directory.

#. From a clean work tree, execute::

    tox -e release -- VERSION

   This will create the branch ready to be pushed.

#. Open a PR targeting ``main``.

#. All tests must pass and the PR must be approved by at least another maintainer.

#. Publish to PyPI by pushing a tag::

     git tag X.Y.Z release-X.Y.Z
     git push git@github.com:SundayZhuozhou/ln_pluggy.git X.Y.Z

   The tag will trigger a new build, which will deploy to PyPI.

#. Make sure it is `available on PyPI <https://pypi.org/project/ln_pluggy>`_.

#. Merge the PR into ``main``, either manually or using GitHub's web interface.
