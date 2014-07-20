Project Templates
=================

## What is the goal of this repository?
The goal of this repository is to classify and enumerate methods of (re)generating project archetypes.


## Directory Templates
There are two different was to describe a project's directory schema:

1. Declare the schema in some DSL and then use a tool to generate the directories.

  ```sh
  # TODO: Add an example where directories, files, and attributes are declared in some prescribed manner that other tools   parse and assemble.
  ```

2. Create an archive of an example of the directory structure.

  ```sh
  #!/bin/sh -eu

  echo "What do you want to call the project template?"
  read name

  mkdir -p ${name}/src/{main,test,script,doc}

  touch ${name}/README.md ${name}/src/script/bootstrap.sh
  chmod u+x ${name}/src/script/bootstrap.sh
  tar -c -z -f ${name}.tar.gz ${name}
  ```

  The `${name}.tar.gz` package can now be distributed by many means (HTTPS,FTPS,SCP,…).

  … and then later expanded:

  ```sh
  #!/bin/sh -eu

  echo "Enter the project template file URL:"
  read url && wget ${url} | tar -x -z
  ```

### Implementations
| name | platform | permissions |
|------|:--------:|:------------------:|
| [j2](https://bitbucket.org/cavanaug/j2) | all | yes |
| [Apache Maven Archetype Plugin](https://maven.apache.org/archetype/maven-archetype-plugin/) | all | yes |
| [Buildout](http://www.buildout.org/) | all | ? |
| [Yeoman](http://yeoman.io/) | all (node.js) | ? |


## Text File Templates

### Implementations
| name | platform |
|------|:--------:|
| [Velocity](http://velocity.apache.org/) | all |
| [FreeMarker](http://freemarker.org/) | all |
| [stringtemplate](http://www.stringtemplate.org/) | all |
