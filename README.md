processparser
=============

An unofficial, open-source CherryPy-based parser of RfD taxonomy process data using the NVMAN HTTP-based API.

**Requires:**

* Python 2.7.x (no current support for Python 3.x)
* CherryPy 3.2
* pylibmc (tested on pylibmc 1.2.2)
* memcached (tested on latest stable version; set to listen on 127.0.0.1:11211)

**File requirements:**

* processFile: The output from `curl http://api.eresourcecenter.org/nvman/processes` (default is
  "baseprocess.txt" - should be updated if new processes/categories are added and baseprocessUpdateAuto
  is not enabled in the configuration section). 

**Optional configuration file:**

* config.conf: If config.conf exists, processparser will load it as optional CherryPy configuration
  directives. This file can be safely omitted or left blank if you do not have special CherryPy
  configuration options (needing such options is very rare).

**Usage:**

Before running for the first time, if you are not using the default baseprocess.txt file and/or have placed
 baseprocess.txt in a different directory than the python script, open processparser.py in a text
 editor and change the `processFile` value in the configuration section (below the import statements).

Run `python processparser.py >> /LOG_FILE_LOCATION_HERE 2>&1 &` from a non-privileged account (such as www-data).

Server will begin listening on 127.0.0.1:8080

**View live usage:**

A live version of processparser can be seen at https://www.friendlyvault.com/app/

**Documentation:**

Sphinx-generated documentation available at:

https://www.friendlyvault.com/docs/

**Developer:**

Joshua Roth-Colson (joshua@friendlyvault.com)

Please note: processparser is a personal project and is not officially approved by, or a product of, my employer

**License:**

Copyright 2013, Joshua Roth-Colson

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
