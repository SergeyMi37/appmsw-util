![](https://github.com/SergeyMi37/appmsw-util/blob/master/doc/appmsw-util-database.png)
## appmsw-util
[![Gitter](https://img.shields.io/badge/Available%20on-Intersystems%20Open%20Exchange-00b2a9.svg)](https://openexchange.intersystems.com/package/appmsw-telestat-1)

Creating and deleting db, namespace, resource and role with one command
Forked from https://openexchange.intersystems.com/package/isc-generate-db

Added resource and role creation for the database. (Many modules ZPM require MatchRoles=":{$dbrole}")
Added deletion of DataBases, role resources and Namespace.
Adding rest application is optional.

## Installation with ZPM

zpm:USER>install appmsw-util

## Installation with Docker

## Prerequisites
Make sure you have [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and [Docker desktop](https://www.docker.com/products/docker-desktop) installed.

## Installation 
Clone/git pull the repo into any local directory

```
$ git clone https://github.com/SergeyMi37/appmsw-util.git
```

Open the terminal in this directory and run:

```
$ docker-compose build
```

3. Run the IRIS container with your project:

```
$ docker-compose up -d
```

## How to Test it
Open IRIS terminal:

```
$ docker-compose exec iris iris session iris
USER>
USER>zpm
zpm:USER>install appmsw-util
...
example:
write $System.Status.GetErrorText(##class(appmsw.util.database).CreateDBNS("TESTDB2"))
write $System.Status.GetErrorText(##class(appmsw.util.database).DeleteDBNS("TESTDB2"))
...
```




