---
title: Getting started
---
<!---
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License. See accompanying LICENSE file.
-->

Ratis is a *library* which is expected to be used form java code. It's not a standalone server application like Zookeeper or Consul.

But to demonstrate how to use Ratis from the code, the project providers multiple examples where an example state machine / server log is implemented.

As of now we have two examples:

 * Arithmetic example: where the Ratis statemachine implementation stores the values of the variables and you can modify the variables arithmetic expressions.
 * FileStore example: where the Ratis statemachine implemetation stores files with a simplified (read/write) interfaces.

The source code the examples could be found in the ratis-examples subproject.

Arithmetic example also has some simple cli script to start it:

1. First do a full build on the ratis source code: ```mvn clean install -DskipTests```
2. Go the the bin directory of the examples: ```cd ratis-examples/src/main/bin```
3. Start three Ratis server (with arithmetic state matchine): ```./start-all```
4. Create a new variable in the state machine: ``` ./client.sh assign --name a --value 3```
5. Assign a new variable: ```./client.sh assign --name b --value a+5```
6. Get a variable from the state machine: ```./client.sh get --name b```
