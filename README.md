# Copyright © Tyler R. Drury (vigilance.eth™) 20-04-2022, All Rights Reserved

---
# ssf-php

ssf-php is the Official Secure Signature Format PHP implementation.


---
## Project Structure

All Vigilance project directories have the following basic structure template

* **/_output** - directory for logging console output and errors durring exection, generally ignored
* **/_src** - directory with all working source code, generally ignored
* **/build** - distribution directory, containing project's PHARs and other appropriate documents
* **/docs** - html documentation directory used by Doxygen for output
* **/README.md** - primary readme file
* **/LICENSE.md** - project license file
* **/AUTHORS.md** - containes all authors who contributed to the project
* **/CONTRIBUTNG.md** - containes instructions for successfully branching the project and contributing a change of bug fix
* **/.gitignore** - file specifying which files and directory patterns not to include when pushing commits t github repo

In unit testing directories, there is not build.php, build.bat,
replaced instead with a run.bat, for executing the PHPUnit Unit Test Runner

Additionally all CGI applications come with a run.php in the **build** directory.
as a convenience wrapper for the contained PHAR,
rather than having to configure the host system uniquely to handle PHARs as executable,
it is easier to simply include PHAR inside a **run.php** script,
executing it with a PHP interpreter from the project root directory

```
>php build/run.php --d=3 --v --A
```

Also the bootstrap file for a CGI project becomes **main.php**,
instead of **meta.php**, with a non-executable library PHAR.

In this case the reason for differentiation is justified as such:

1) **meta.php** recursively includes all PHP code within a project directory which does not execute any commands or produce side-effects,
containing **only** declarations for defines/constants, namespace, interfaces, functions and classes for use as a library in other projects
2) **main.php** includes PHP code which executes commands, running a CGI application,
typically involving parsing command line arguments and executing modules which produce either side-effects in the interpreter or generates output


## Getting the Official Library

The Official ssf.phar is avaialble for [here]().

This library is available as is and can be linked to to from the build directory of a cloned repository.


---
## Getting Started

This project is designed to be stand alone,
built with no (or preferably minimal) external dependencies.

All project files are contained within **/build/ssf56_1_0.phar**

After cloning the repo onto a local machine,
from a PHP souce file add the following line (on Windows):


```
require_once "phar://C:/projects/ssf-php/build/ssf.phar/Transcoder32.php";

```

Replace **/project/** with the path of the locally installed repository.


--- 
## License

ssf-php is released under the Apache 2.0,
please see [LICENSE.md](https://github.com/vigilance91/ssf-php/blob/main/LICENSE.md) for more details.


---
## Links

The Official 32 Byte SSF Specification is avaialble [here](https://vigilance91.github.io/ssf32.html).

The Official 64 Byte SSF Specification is avaialble [here](https://vigilance91.github.io/ssf32.html).

The PHP API documentation is available [here]().

Authors and contributors are listed in [AUTHORS.md]().


---