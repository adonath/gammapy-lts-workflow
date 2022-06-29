# Gammapy LTS Workflow
Repository to practice the Gammapy LTS workflow

## Semantic Versioning
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




## How to do a release

If you would like to take the role of a release manager you need an account for [TestPyPi](https://test.pypi.org). If you don't have one, create one here: https://test.pypi.org/account/register/.

Upload test release:
```
twine upload --repository testpypi dist/*
```

## Ressources
