---
title: Download
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

Ratis is a *library* which is supposed to be used from java code.


{{< highlight xml>}}
<dependency>
   <artifactId>ratis-server</artifactId>
   <groupId>org.apache.ratis</groupId>
</dependency>
{{< /highlight >}}


You also need to include *one* of the transports:

{{< highlight xml>}}
<dependency>
   <artifactId>ratis-netty</artifactId>
   <groupId>org.apache.ratis</groupId>
</dependency>
{{< /highlight >}}

{{< highlight xml>}}
 <dependency>
   <groupId>org.apache.ratis</groupId>
   <artifactId>ratis-grpc</artifactId>
</dependency>
{{< /highlight >}}

{{< highlight xml>}}
    <dependency>
      <groupId>org.apache.ratis</groupId>
      <artifactId>ratis-hadoop-shaded</artifactId>
    </dependency>
{{< /highlight >}}

Please note that hadoop dependencies are shaded, so it's safe to use hadoop transport with different versions of hadoop.
