# Gammapy LTS Workflow
Repository to practice the Gammapy LTS workflow

## Versioning Scheme
We will follow the [Astropy versioning scheme](https://github.com/astropy/astropy-APEs/blob/main/APE2.rst#version-numbering).
This means for Gammapy we will use a numbering scheme like:
```
x.y.z
```
Where, `x = major`, `y = minor`, `z = bugfix`.

Within each "category" the numbers are counted from 0. Check the following examples:

```
* 1.0.0 (LTS release)
* 1.0.1 (LTS bugfix release)
* 1.0.2 (2nd LTS bugfix release)
* 1.1.0 (feature release, six months after 1.0.0)
* 1.1.1 etc.
* 1.0.3 (3rd LTS bugfix release)
* 1.1.2
* 1.2.0 (six months after 1.1.0)
* 1.2.1
* 1.3.0 (six months after 1.2.0)
* 1.0.4
* 1.3.1
* 2.0.0 (LTS release)
```

As a rough guideline:
- LTS are maintained with bugfix releases for ~ 2 years, changes cannot break the API
- Minor releases every ~6 months, changes can break the API using a deprecation system, which thnan breaks backward compatibility two minor versions later
- Bugfix relases cannot break the API


- On the feature freeze date a new release branch is created, named e.g. `v1.0.x`.
- A feature freeze will mean **no more major new feature pull requests will be accepted for that version**, but minor improvements, bug fixes, or documentation additions are still acceptable.
- From this point on the release happens from this branch `v1.0.x`. 
- First create a release candidate i.e. tag `v1.0rc1`, collect feedback from beta testers and developers for ~1 week.
- If additonal issue are found those should be fixed and a new release candidate `v1.0rc2` is tagged. A new testing period starts
- Tag `v1.0` and release

## How to do a release

If you would like to take the role of a release manager you need an account for [TestPyPi](https://test.pypi.org). If you don't have one, create one here: https://test.pypi.org/account/register/.

Upload test release:
```
twine upload --repository testpypi dist/*
```

## Ressources
