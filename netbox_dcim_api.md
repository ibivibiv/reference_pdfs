**dcim**

**GET**

/dcim/\_choices/

dcim\_\_choices_list

**Parameters**

**Try it out**

No parameters

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Provider**

**Custom fields**
:::

[]{#40}

::: {#page40-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

40/543

**GET**

/dcim/\_choices/{id}/

dcim\_\_choices_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**string\
(path)

**Responses**

**Response content type**

**application/json**

Code

Description

200

**GET**

/dcim/connected-device/

dcim_connected-device_list

This endpoint allows a user to determine what device (if any) is connected to a given peer device and peer\
interface. This is useful in a situation where a device boots with no con guration, but can detect its neighbors\
via a protocol such as LLDP. Two query parameters must be included in the request:

peer-device: The name of the peer device\
peer-interface: The name of the peer interface

**Parameters**

**Try it out**

Name

Description

**peer-device \*\
**string\
(query)

The name of the peer device

**peer-interface \*\
**string\
(query)

The name of the peer interface

**Responses**

**Response content type**

**application/json**

**required**

**required**

**required**
:::

[]{#41}

::: {#page41-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

41/543

Code

Description

200

**Model**

Example Value
:::

[]{#42}

::: {#page42-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

42/543

Code

Description

{

id

integer

title: ID

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

device_type\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-

9\_\]+\$

maxLength: 50

}

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

device_role\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

tenant\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 30

**Device**

**Device type**

**Manufacturer**

**Device role**

**Tenant**
:::

[]{#43}

::: {#page43-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

43/543

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

platform\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this device

site\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

rack\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

display_name

string

title: Display name

readOnly: true

}

position\*

integer

title: Position (U)

maximum: 32767

minimum: 1

The lowest-numbered unit occupied by the device

face\*

{

value\*

integer

x-nullable: true

label\*

string

}

parent_device

string

Code

Description

**Platform**

**Site**

**Rack**

**Face**
:::

[]{#44}

::: {#page44-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

44/543

title: Parent device

readOnly: true

status\*

{

value\*

integer

label\*

string

}

primary_ip\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

}

primary_ip4\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

}

primary_ip6\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

}

cluster\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 100

}

virtual_chassis\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

**GET**

/dcim/console-connections/

dcim_console-connections_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

connection_status\
string\
(query)

site\
string\
(query)

device\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**Status**

**Primary ip**

**Primary ip**

**Primary ip**

**Cluster**

**Virtual chassis**

Example Value
:::

[]{#45}

::: {#page45-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

45/543

title: Url

readOnly: true

master\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

}

vc_position\*

integer

title: Vc position

maximum: 255

minimum: 0

vc_priority

integer

title: Vc priority

maximum: 255

minimum: 0

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device\*

{\...}

name\*

string

title: Name

maxLength: 50

cs_port\*

{\...}

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}\]

}

**GET**

/dcim/console-port-templates/

dcim_console-port-templates_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

devicetype_id\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

**Device**

**Custom fields**

**ConsolePort**

**Device**

**Cs port**
:::

[]{#46}

::: {#page46-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

46/543

Code

Description

200

**Model**

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device_type\*

{\...}

name\*

string

title: Name

maxLength: 50

}\]

}

**POST**

**P**

/dcim/console-port-templates/

dcim_console-port-templates_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

Example Value

**ConsolePortTemplate**

**Device type**

**required**

Example Value

**WritableConsolePortTemplate**
:::

[]{#47}

::: {#page47-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

47/543

Code

Description

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**GET**

/dcim/console-port-templates/{id}/

dcim_console-port-templates_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this console port template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**WritableConsolePortTemplate**

**required**

Example Value
:::

[]{#48}

::: {#page48-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

48/543

Code

Description

{

id

integer

title: ID

readOnly: true

device_type\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-

9\_\]+\$

maxLength: 50

}

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

name\*

string

title: Name

maxLength: 50

}

**PUT**

/dcim/console-port-templates/{id}/

dcim_console-port-templates_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**ConsolePortTemplate**

**Device type**

**Manufacturer**

**required**

Example Value
:::

[]{#49}

::: {#page49-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

49/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this console port template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**PATCH**

**PA**

/dcim/console-port-templates/{id}/

dcim_console-port-templates_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableConsolePortTemplate**

**required**

Example Value

**WritableConsolePortTemplate**

**required**

Example Value
:::

[]{#50}

::: {#page50-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

50/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this console port template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**DELETE**

**DEL**

/dcim/console-port-templates/{id}/

dcim_console-port-templates_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this console port template.

**WritableConsolePortTemplate**

**required**

Example Value

**WritableConsolePortTemplate**

**required**
:::

[]{#51}

::: {#page51-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

51/543

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/console-ports/

dcim_console-ports_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

device_id\
string\
(query)

device\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#52}

::: {#page52-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

52/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device\*

{\...}

name\*

string

title: Name

maxLength: 50

cs_port\*

{\...}

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}\]

}

**POST**

**P**

/dcim/console-ports/

dcim_console-ports_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

cs_port

integer

title: Console server port

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**Responses**

**Response content type**

**application/json**

**ConsolePort**

**Device**

**Cs port**

**required**

Example Value

**WritableConsolePort**
:::

[]{#53}

::: {#page53-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

53/543

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

cs_port

integer

title: Console server port

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**GET**

/dcim/console-ports/{id}/

dcim_console-ports_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this console port.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**WritableConsolePort**

**required**

Example Value
:::

[]{#54}

::: {#page54-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

54/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

name\*

string

title: Name

maxLength: 50

cs_port\*

{

id

integer

title: ID

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

name\*

string

title: Name

maxLength: 50

connected_console

string

title: Connected console

readOnly: true

}

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**PUT**

/dcim/console-ports/{id}/

dcim_console-ports_update

**Parameters**

**Try it out**

**ConsolePort**

**Device**

**Cs port**

**Device**
:::

[]{#55}

::: {#page55-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

55/543

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

cs_port

integer

title: Console server port

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**id \*\
**integer\
(path)

A unique integer value identifying this console port.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

cs_port

integer

title: Console server port

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**PATCH**

**PA**

/dcim/console-ports/{id}/

dcim_console-ports_partial_update

**required**

Example Value

**WritableConsolePort**

**required**

Example Value

**WritableConsolePort**
:::

[]{#56}

::: {#page56-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

56/543

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

cs_port

integer

title: Console server port

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**id \*\
**integer\
(path)

A unique integer value identifying this console port.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

cs_port

integer

title: Console server port

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**required**

Example Value

**WritableConsolePort**

**required**

Example Value

**WritableConsolePort**
:::

[]{#57}

::: {#page57-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

57/543

**DELETE**

**DEL**

/dcim/console-ports/{id}/

dcim_console-ports_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this console port.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/console-server-port-templates/

dcim_console-server-port-templates_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

devicetype_id\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

**required**
:::

[]{#58}

::: {#page58-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

58/543

Code

Description

200

**Model**

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device_type\*

{\...}

name\*

string

title: Name

maxLength: 50

}\]

}

**POST**

**P**

/dcim/console-server-port-templates/

dcim_console-server-port-templates_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

Example Value

**ConsoleServerPortTemplate**

**Device type**

**required**

Example Value

**WritableConsoleServerPortTemplate**
:::

[]{#59}

::: {#page59-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

59/543

Code

Description

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**GET**

/dcim/console-server-port-templates/{id}/

dcim_console-server-port-templates_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this console server port template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**WritableConsoleServerPortTemplate**

**required**

Example Value
:::

[]{#60}

::: {#page60-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

60/543

Code

Description

{

id

integer

title: ID

readOnly: true

device_type\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-

9\_\]+\$

maxLength: 50

}

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

name\*

string

title: Name

maxLength: 50

}

**PUT**

/dcim/console-server-port-templates/{id}/

dcim_console-server-port-templates_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**ConsoleServerPortTemplate**

**Device type**

**Manufacturer**

**required**

Example Value
:::

[]{#61}

::: {#page61-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

61/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this console server port template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**PATCH**

**PA**

/dcim/console-server-port-templates/

{id}/

dcim_console-server-port-templates_partial_u\
pdate

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableConsoleServerPortTemplate**

**required**

Example Value

**WritableConsoleServerPortTemplate**

**required**

Example Value
:::

[]{#62}

::: {#page62-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

62/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this console server port template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**DELETE**

**DEL**

/dcim/console-server-port-templates/{id}/

dcim_console-server-port-templates_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this console server port template.

**WritableConsoleServerPortTemplate**

**required**

Example Value

**WritableConsoleServerPortTemplate**

**required**
:::

[]{#63}

::: {#page63-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

63/543

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/console-server-ports/

dcim_console-server-ports_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

device_id\
string\
(query)

device\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#64}

::: {#page64-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

64/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device\*

{\...}

name\*

string

title: Name

maxLength: 50

connected_console

string

title: Connected console

readOnly: true

}\]

}

**POST**

**P**

/dcim/console-server-ports/

dcim_console-server-ports_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

**Cs port**

**Device**

**required**

Example Value

**WritableConsoleServerPort**

Example Value
:::

[]{#65}

::: {#page65-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

65/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**GET**

/dcim/console-server-ports/{id}/

dcim_console-server-ports_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this console server port.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableConsoleServerPort**

**required**

Example Value
:::

[]{#66}

::: {#page66-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

66/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

name\*

string

title: Name

maxLength: 50

connected_console

string

title: Connected console

readOnly: true

}

**PUT**

/dcim/console-server-ports/{id}/

dcim_console-server-ports_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this console server port.

**Responses**

**Response content type**

**application/json**

**Cs port**

**Device**

**required**

Example Value

**WritableConsoleServerPort**

**required**
:::

[]{#67}

::: {#page67-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

67/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**PATCH**

**PA**

/dcim/console-server-ports/{id}/

dcim_console-server-ports_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this console server port.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**WritableConsoleServerPort**

**required**

Example Value

**WritableConsoleServerPort**

**required**

Example Value
:::

[]{#68}

::: {#page68-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

68/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**DELETE**

**DEL**

/dcim/console-server-ports/{id}/

dcim_console-server-ports_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this console server port.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/device-bay-templates/

dcim_device-bay-templates_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

devicetype_id\
string\
(query)

limit

Number of results to return per page.

**WritableConsoleServerPort**

**required**
:::

[]{#69}

::: {#page69-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

69/543

Name

Description

integer\
(query)

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device_type\*

{\...}

name\*

string

title: Name

maxLength: 50

}\]

}

**POST**

**P**

/dcim/device-bay-templates/

dcim_device-bay-templates_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**DeviceBayTemplate**

**Device type**

**required**

Example Value
:::

[]{#70}

::: {#page70-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

70/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**GET**

/dcim/device-bay-templates/{id}/

dcim_device-bay-templates_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device bay template.

**Responses**

**Response content type**

**application/json**

**WritableDeviceBayTemplate**

Example Value

**WritableDeviceBayTemplate**

**required**
:::

[]{#71}

::: {#page71-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

71/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-

9\_\]+\$

maxLength: 50

}

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

name\*

string

title: Name

maxLength: 50

}

**PUT**

/dcim/device-bay-templates/{id}/

dcim_device-bay-templates_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**DeviceBayTemplate**

**Device type**

**Manufacturer**

**required**

Example Value
:::

[]{#72}

::: {#page72-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

72/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this device bay template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**PATCH**

**PA**

/dcim/device-bay-templates/{id}/

dcim_device-bay-templates_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableDeviceBayTemplate**

**required**

Example Value

**WritableDeviceBayTemplate**

**required**

Example Value
:::

[]{#73}

::: {#page73-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

73/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this device bay template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**DELETE**

**DEL**

/dcim/device-bay-templates/{id}/

dcim_device-bay-templates_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device bay template.

**WritableDeviceBayTemplate**

**required**

Example Value

**WritableDeviceBayTemplate**

**required**
:::

[]{#74}

::: {#page74-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

74/543

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/device-bays/

dcim_device-bays_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

device_id\
string\
(query)

device\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#75}

::: {#page75-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

75/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device\*

{\...}

name\*

string

title: Name

maxLength: 50

installed_device\*

{\...}

}\]

}

**POST**

**P**

/dcim/device-bays/

dcim_device-bays_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

installed_device

integer

title: Installed device

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

**DeviceBay**

**Device**

**Device**

**required**

Example Value

**WritableDeviceBay**

Example Value
:::

[]{#76}

::: {#page76-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

76/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

installed_device

integer

title: Installed device

}

**GET**

/dcim/device-bays/{id}/

dcim_device-bays_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device bay.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableDeviceBay**

**required**

Example Value
:::

[]{#77}

::: {#page77-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

77/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

name\*

string

title: Name

maxLength: 50

installed_device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

}

**PUT**

/dcim/device-bays/{id}/

dcim_device-bays_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**DeviceBay**

**Device**

**Device**

**required**

Example Value
:::

[]{#78}

::: {#page78-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

78/543

Name

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

installed_device

integer

title: Installed device

}

**id \*\
**integer\
(path)

A unique integer value identifying this device bay.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

installed_device

integer

title: Installed device

}

**PATCH**

**PA**

/dcim/device-bays/{id}/

dcim_device-bays_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableDeviceBay**

**required**

Example Value

**WritableDeviceBay**

**required**

Example Value
:::

[]{#79}

::: {#page79-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

79/543

Name

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

installed_device

integer

title: Installed device

}

**id \*\
**integer\
(path)

A unique integer value identifying this device bay.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

installed_device

integer

title: Installed device

}

**DELETE**

**DEL**

/dcim/device-bays/{id}/

dcim_device-bays_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device bay.

**WritableDeviceBay**

**required**

Example Value

**WritableDeviceBay**

**required**
:::

[]{#80}

::: {#page80-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

80/543

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/device-roles/

dcim_device-roles_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

slug\
string\
(query)

color\
string\
(query)

vm_role\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#81}

::: {#page81-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

81/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

vm_role

boolean

title: VM Role

Virtual machines may be assigned to this role

}\]

}

**POST**

**P**

/dcim/device-roles/

dcim_device-roles_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

vm_role

boolean

title: VM Role

Virtual machines may be assigned to this role

}

**DeviceRole**

**required**

Example Value

**DeviceRole**
:::

[]{#82}

::: {#page82-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

82/543

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

vm_role

boolean

title: VM Role

Virtual machines may be assigned to this role

}

**GET**

/dcim/device-roles/{id}/

dcim_device-roles_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device role.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**DeviceRole**

**required**

Example Value
:::

[]{#83}

::: {#page83-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

83/543

Code

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

vm_role

boolean

title: VM Role

Virtual machines may be assigned to this role

}

**PUT**

/dcim/device-roles/{id}/

dcim_device-roles_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

vm_role

boolean

title: VM Role

Virtual machines may be assigned to this role

}

**id \*\
**integer\
(path)

A unique integer value identifying this device role.

**DeviceRole**

**required**

Example Value

**DeviceRole**

**required**
:::

[]{#84}

::: {#page84-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

84/543

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

vm_role

boolean

title: VM Role

Virtual machines may be assigned to this role

}

**PATCH**

**PA**

/dcim/device-roles/{id}/

dcim_device-roles_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

vm_role

boolean

title: VM Role

Virtual machines may be assigned to this role

}

**id \***

A unique integer value identifying this device role.

Example Value

**DeviceRole**

**required**

Example Value

**DeviceRole**

**required**
:::

[]{#85}

::: {#page85-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

85/543

Name

Description

integer\
(path)

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

vm_role

boolean

title: VM Role

Virtual machines may be assigned to this role

}

**DELETE**

**DEL**

/dcim/device-roles/{id}/

dcim_device-roles_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device role.

**Responses**

**Response content type**

**application/json**

Example Value

**DeviceRole**

**required**
:::

[]{#86}

::: {#page86-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

86/543

Code

Description

204

**GET**

/dcim/device-types/

dcim_device-types_list

**Parameters**

**Try it out**

Name

Description

model\
string\
(query)

slug\
string\
(query)

part_number\
string\
(query)

u_height\
number\
(query)

is_full_depth\
string\
(query)

is_console_server\
string\
(query)

is_pdu\
string\
(query)

is_network_device\
string\
(query)

subdevice_role\
string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.
:::

[]{#87}

::: {#page87-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

87/543

Name

Description

q\
string\
(query)

manufacturer_id\
string\
(query)

manufacturer\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#88}

::: {#page88-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

88/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

manufacturer\*

{\...}

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

part_number

string

title: Part number

maxLength: 50

Discrete part number (optional)

u_height

integer

title: Height (U)

maximum: 32767

minimum: 0

is_full_depth

boolean

title: Is full depth

Device consumes both front and rear rack

faces

interface_ordering\*

{\...}

is_console_server

boolean

title: Is a console server

This type of device has console server ports

is_pdu

boolean

title: Is a PDU

This type of device has power outlets

is_network_device

boolean

title: Is a network device

This type of device has network interfaces

subdevice_role\*

{\...}

comments

string

title: Comments

custom_fields

{\...}

instance_count

integer

title: Instance count

readOnly: true

}\]

}

**POST**

**P**

/dcim/device-types/

dcim_device-types_create

**Parameters**

**Try it out**

Name

Description

**data \***

**DeviceType**

**Manufacturer**

**Interface ordering**

**Subdevice role**

**Custom fields**

**required**
:::

[]{#89}

::: {#page89-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

89/543

Name

Description

(body)

**Model**

{

id

integer

title: ID

readOnly: true

manufacturer\*

integer

title: Manufacturer

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

part_number

string

title: Part number

maxLength: 50

Discrete part number (optional)

u_height

integer

title: Height (U)

maximum: 32767

minimum: 0

is_full_depth

boolean

title: Is full depth

Device consumes both front and rear rack faces

interface_ordering

integer

title: Interface ordering

Enum:

Array \[ 2 \]

is_console_server

boolean

title: Is a console server

This type of device has console server ports

is_pdu

boolean

title: Is a PDU

This type of device has power outlets

is_network_device

boolean

title: Is a network device

This type of device has network interfaces

subdevice_role

boolean

title: Parent/child status

x-nullable: true

Parent devices house child devices in device bays. Select "None" if

this device type is neither a parent nor a child.

Enum:

Array \[ 3 \]

comments

string

title: Comments

custom_fields

{

}

}

**Responses**

**Response content type**

**application/json**

Example Value

**WritableDeviceType**

**Custom fields**
:::

[]{#90}

::: {#page90-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

90/543

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

manufacturer\*

integer

title: Manufacturer

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

part_number

string

title: Part number

maxLength: 50

Discrete part number (optional)

u_height

integer

title: Height (U)

maximum: 32767

minimum: 0

is_full_depth

boolean

title: Is full depth

Device consumes both front and rear rack faces

interface_ordering

integer

title: Interface ordering

Enum:

Array \[ 2 \]

is_console_server

boolean

title: Is a console server

This type of device has console server ports

is_pdu

boolean

title: Is a PDU

This type of device has power outlets

is_network_device

boolean

title: Is a network device

This type of device has network interfaces

subdevice_role

boolean

title: Parent/child status

x-nullable: true

Parent devices house child devices in device bays. Select "None" if

this device type is neither a parent nor a child.

Enum:

Array \[ 3 \]

comments

string

title: Comments

custom_fields

{

}

}

**GET**

/dcim/device-types/{id}/

dcim_device-types_read

**Parameters**

**Try it out**

Example Value

**WritableDeviceType**

**Custom fields**
:::

[]{#91}

::: {#page91-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

91/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device type.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value
:::

[]{#92}

::: {#page92-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

92/543

Code

Description

{

id

integer

title: ID

readOnly: true

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

part_number

string

title: Part number

maxLength: 50

Discrete part number (optional)

u_height

integer

title: Height (U)

maximum: 32767

minimum: 0

is_full_depth

boolean

title: Is full depth

Device consumes both front and rear rack faces

interface_ordering\*

{

value\*

integer

label\*

string

}

is_console_server

boolean

title: Is a console server

This type of device has console server ports

is_pdu

boolean

title: Is a PDU

This type of device has power outlets

is_network_device

boolean

title: Is a network device

This type of device has network interfaces

subdevice_role\*

{

value\*

boolean

x-nullable: true

label\*

string

}

comments

string

title: Comments

custom_fields

{

}

instance_count

integer

title: Instance count

readOnly: true

}

**DeviceType**

**Manufacturer**

**Interface ordering**

**Subdevice role**

**Custom fields**
:::

[]{#93}

::: {#page93-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

93/543

}

Code

Description

**PUT**

/dcim/device-types/{id}/

dcim_device-types_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

manufacturer\*

integer

title: Manufacturer

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

part_number

string

title: Part number

maxLength: 50

Discrete part number (optional)

u_height

integer

title: Height (U)

maximum: 32767

minimum: 0

is_full_depth

boolean

title: Is full depth

Device consumes both front and rear rack faces

interface_ordering

integer

title: Interface ordering

Enum:

Array \[ 2 \]

is_console_server

boolean

title: Is a console server

This type of device has console server ports

is_pdu

boolean

title: Is a PDU

This type of device has power outlets

is_network_device

boolean

title: Is a network device

This type of device has network interfaces

subdevice_role

boolean

title: Parent/child status

x-nullable: true

Parent devices house child devices in device bays. Select "None" if

this device type is neither a parent nor a child.

Enum:

Array \[ 3 \]

comments

string

title: Comments

custom_fields

{

}

}

**required**

Example Value

**WritableDeviceType**

**Custom fields**
:::

[]{#94}

::: {#page94-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

94/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device type.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value
:::

[]{#95}

::: {#page95-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

95/543

Code

Description

{

id

integer

title: ID

readOnly: true

manufacturer\*

integer

title: Manufacturer

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

part_number

string

title: Part number

maxLength: 50

Discrete part number (optional)

u_height

integer

title: Height (U)

maximum: 32767

minimum: 0

is_full_depth

boolean

title: Is full depth

Device consumes both front and rear rack faces

interface_ordering

integer

title: Interface ordering

Enum:

Array \[ 2 \]

is_console_server

boolean

title: Is a console server

This type of device has console server ports

is_pdu

boolean

title: Is a PDU

This type of device has power outlets

is_network_device

boolean

title: Is a network device

This type of device has network interfaces

subdevice_role

boolean

title: Parent/child status

x-nullable: true

Parent devices house child devices in device bays. Select "None" if

this device type is neither a parent nor a child.

Enum:

Array \[ 3 \]

comments

string

title: Comments

custom_fields

{

}

}

**PATCH**

**PA**

/dcim/device-types/{id}/

dcim_device-types_partial_update

**Parameters**

**Try it out**

Name

Description

**data \***

**Model**

**WritableDeviceType**

**Custom fields**

**required**

Example Value
:::

[]{#96}

::: {#page96-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

96/543

Name

Description

(body)

{

id

integer

title: ID

readOnly: true

manufacturer\*

integer

title: Manufacturer

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

part_number

string

title: Part number

maxLength: 50

Discrete part number (optional)

u_height

integer

title: Height (U)

maximum: 32767

minimum: 0

is_full_depth

boolean

title: Is full depth

Device consumes both front and rear rack faces

interface_ordering

integer

title: Interface ordering

Enum:

Array \[ 2 \]

is_console_server

boolean

title: Is a console server

This type of device has console server ports

is_pdu

boolean

title: Is a PDU

This type of device has power outlets

is_network_device

boolean

title: Is a network device

This type of device has network interfaces

subdevice_role

boolean

title: Parent/child status

x-nullable: true

Parent devices house child devices in device bays. Select "None" if

this device type is neither a parent nor a child.

Enum:

Array \[ 3 \]

comments

string

title: Comments

custom_fields

{

}

}

**id \*\
**integer\
(path)

A unique integer value identifying this device type.

**Responses**

**Response content type**

**application/json**

**WritableDeviceType**

**Custom fields**

**required**
:::

[]{#97}

::: {#page97-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

97/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

manufacturer\*

integer

title: Manufacturer

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

part_number

string

title: Part number

maxLength: 50

Discrete part number (optional)

u_height

integer

title: Height (U)

maximum: 32767

minimum: 0

is_full_depth

boolean

title: Is full depth

Device consumes both front and rear rack faces

interface_ordering

integer

title: Interface ordering

Enum:

Array \[ 2 \]

is_console_server

boolean

title: Is a console server

This type of device has console server ports

is_pdu

boolean

title: Is a PDU

This type of device has power outlets

is_network_device

boolean

title: Is a network device

This type of device has network interfaces

subdevice_role

boolean

title: Parent/child status

x-nullable: true

Parent devices house child devices in device bays. Select "None" if

this device type is neither a parent nor a child.

Enum:

Array \[ 3 \]

comments

string

title: Comments

custom_fields

{

}

}

**DELETE**

**DEL**

/dcim/device-types/{id}/

dcim_device-types_delete

**Parameters**

**Try it out**

Example Value

**WritableDeviceType**

**Custom fields**
:::

[]{#98}

::: {#page98-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

98/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device type.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/devices/

dcim_devices_list

**Parameters**

**Try it out**

Name

Description

serial\
string\
(query)

position\
number\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

manufacturer_id\
string\
(query)

manufacturer\
string\
(query)

device_type_id\
string\
(query)

**required**
:::

[]{#99}

::: {#page99-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

99/543

Name

Description

role_id\
string\
(query)

role\
string\
(query)

tenant_id\
string\
(query)

tenant\
string\
(query)

platform_id\
string\
(query)

platform\
string\
(query)

name\
string\
(query)

asset_tag\
string\
(query)

site_id\
string\
(query)

site\
string\
(query)

rack_group_id\
string\
(query)

rack_id\
string\
(query)

cluster_id\
string\
(query)
:::

[]{#100}

::: {#page100-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

100/543

Name

Description

model\
string\
(query)

status\
string\
(query)

is_full_depth\
string\
(query)

is_console_server\
string\
(query)

is_pdu\
string\
(query)

is_network_device\
string\
(query)

mac_address\
string\
(query)

has_primary_ip\
string\
(query)

virtual_chassis_id\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**
:::

[]{#101}

::: {#page101-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

101/543

Code

Description

200

**Model**

Example Value
:::

[]{#102}

::: {#page102-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

102/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

device_type\*

{\...}

device_role\*

{\...}

tenant\*

{\...}

platform\*

{\...}

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this device

site\*

{\...}

rack\*

{\...}

position\*

integer

title: Position (U)

maximum: 32767

minimum: 1

The lowest-numbered unit occupied by the

device

face\*

{\...}

parent_device

string

title: Parent device

readOnly: true

status\*

{\...}

primary_ip\*

{\...}

primary_ip4\*

{\...}

primary_ip6\*

{\...}

cluster\*

{\...}

virtual_chassis\*

{\...}

vc_position\*

integer

title: Vc position

maximum: 255

minimum: 0

vc_priority

integer

title: Vc priority

maximum: 255

minimum: 0

comments

string

title: Comments

custom_fields

{\...}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

**Device**

**Device type\
Device role\
Tenant\
Platform**

**Site\
Rack**

**Face**

**Status\
Primary ip\
Primary ip\
Primary ip\
Cluster\
Virtual chassis**

**Custom fields**
:::

[]{#103}

::: {#page103-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

103/543

p

g(

)

title: Last updated

readOnly: true

}\]

}

Code

Description

**POST**

**P**

/dcim/devices/

dcim_devices_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**required**

Example Value
:::

[]{#104}

::: {#page104-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

104/543

Name

Description

{

id

integer

title: ID

readOnly: true

name

string

title: Name

maxLength: 64

device_type\*

integer

title: Device type

device_role\*

integer

title: Device role

tenant

integer

title: Tenant

platform

integer

title: Platform

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this device

site\*

integer

title: Site

rack

integer

title: Rack

position

integer

title: Position (U)

maximum: 32767

minimum: 1

The lowest-numbered unit occupied by the device

face

integer

title: Rack face

Enum:

Array \[ 2 \]

status

integer

title: Status

Enum:

Array \[ 6 \]

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

cluster

integer

title: Cluster

virtual_chassis

integer

title: Virtual chassis

vc_position

integer

title: Vc position

maximum: 255

minimum: 0

vc_priority

integer

title: Vc priority

maximum: 255

minimum: 0

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**WritableDevice**

**Custom fields**
:::

[]{#105}

::: {#page105-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

105/543

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

Example Value
:::

[]{#106}

::: {#page106-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

106/543

Code

Description

{

id

integer

title: ID

readOnly: true

name

string

title: Name

maxLength: 64

device_type\*

integer

title: Device type

device_role\*

integer

title: Device role

tenant

integer

title: Tenant

platform

integer

title: Platform

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this device

site\*

integer

title: Site

rack

integer

title: Rack

position

integer

title: Position (U)

maximum: 32767

minimum: 1

The lowest-numbered unit occupied by the device

face

integer

title: Rack face

Enum:

Array \[ 2 \]

status

integer

title: Status

Enum:

Array \[ 6 \]

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

cluster

integer

title: Cluster

virtual_chassis

integer

title: Virtual chassis

vc_position

integer

title: Vc position

maximum: 255

minimum: 0

vc_priority

integer

title: Vc priority

maximum: 255

minimum: 0

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**WritableDevice**

**Custom fields**
:::

[]{#107}

::: {#page107-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

107/543

Code

Description

**GET**

/dcim/devices/{id}/

dcim_devices_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value
:::

[]{#108}

::: {#page108-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

108/543

Code

Description

{

id

integer

title: ID

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

device_type\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-

9\_\]+\$

maxLength: 50

}

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

device_role\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

tenant\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 30

**Device**

**Device type**

**Manufacturer**

**Device role**

**Tenant**
:::

[]{#109}

::: {#page109-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

109/543

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

platform\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this device

site\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

rack\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

display_name

string

title: Display name

readOnly: true

}

position\*

integer

title: Position (U)

maximum: 32767

minimum: 1

The lowest-numbered unit occupied by the device

face\*

{

value\*

integer

x-nullable: true

label\*

string

}

parent_device

string

Code

Description

**Platform**

**Site**

**Rack**

**Face**
:::

[]{#110}

::: {#page110-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

110/543

title: Parent device

readOnly: true

status\*

{

value\*

integer

label\*

string

}

primary_ip\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

}

primary_ip4\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

}

primary_ip6\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

}

cluster\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 100

}

virtual_chassis\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

**PUT**

/dcim/devices/{id}/

dcim_devices_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Status**

**Primary ip**

**Primary ip**

**Primary ip**

**Cluster**

**Virtual chassis**

**required**

Example Value
:::

[]{#111}

::: {#page111-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

111/543

title: Url

readOnly: true

master\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

}

vc_position\*

integer

title: Vc position

maximum: 255

minimum: 0

vc_priority

integer

title: Vc priority

maximum: 255

minimum: 0

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

Name

Description

{

id

integer

title: ID

readOnly: true

name

string

title: Name

maxLength: 64

device_type\*

integer

title: Device type

device_role\*

integer

title: Device role

tenant

integer

title: Tenant

platform

integer

title: Platform

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this device

site\*

integer

title: Site

rack

integer

title: Rack

position

integer

title: Position (U)

maximum: 32767

minimum: 1

The lowest-numbered unit occupied by the device

face

integer

title: Rack face

Enum:

Array \[ 2 \]

status

integer

title: Status

Enum:

Array \[ 6 \]

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

cluster

integer

title: Cluster

virtual_chassis

integer

title: Virtual chassis

vc_position

integer

title: Vc position

maximum: 255

minimum: 0

vc_priority

integer

title: Vc priority

maximum: 255

minimum: 0

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**Device**

**Custom fields**

**WritableDevice**

**Custom fields**
:::

[]{#112}

::: {#page112-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

112/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value
:::

[]{#113}

::: {#page113-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

113/543

Code

Description

{

id

integer

title: ID

readOnly: true

name

string

title: Name

maxLength: 64

device_type\*

integer

title: Device type

device_role\*

integer

title: Device role

tenant

integer

title: Tenant

platform

integer

title: Platform

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this device

site\*

integer

title: Site

rack

integer

title: Rack

position

integer

title: Position (U)

maximum: 32767

minimum: 1

The lowest-numbered unit occupied by the device

face

integer

title: Rack face

Enum:

Array \[ 2 \]

status

integer

title: Status

Enum:

Array \[ 6 \]

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

cluster

integer

title: Cluster

virtual_chassis

integer

title: Virtual chassis

vc_position

integer

title: Vc position

maximum: 255

minimum: 0

vc_priority

integer

title: Vc priority

maximum: 255

minimum: 0

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**WritableDevice**

**Custom fields**
:::

[]{#114}

::: {#page114-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

114/543

Code

Description

**PATCH**

**PA**

/dcim/devices/{id}/

dcim_devices_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**required**

Example Value
:::

[]{#115}

::: {#page115-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

115/543

Name

Description

{

id

integer

title: ID

readOnly: true

name

string

title: Name

maxLength: 64

device_type\*

integer

title: Device type

device_role\*

integer

title: Device role

tenant

integer

title: Tenant

platform

integer

title: Platform

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this device

site\*

integer

title: Site

rack

integer

title: Rack

position

integer

title: Position (U)

maximum: 32767

minimum: 1

The lowest-numbered unit occupied by the device

face

integer

title: Rack face

Enum:

Array \[ 2 \]

status

integer

title: Status

Enum:

Array \[ 6 \]

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

cluster

integer

title: Cluster

virtual_chassis

integer

title: Virtual chassis

vc_position

integer

title: Vc position

maximum: 255

minimum: 0

vc_priority

integer

title: Vc priority

maximum: 255

minimum: 0

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**WritableDevice**

**Custom fields**
:::

[]{#116}

::: {#page116-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

116/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value
:::

[]{#117}

::: {#page117-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

117/543

Code

Description

{

id

integer

title: ID

readOnly: true

name

string

title: Name

maxLength: 64

device_type\*

integer

title: Device type

device_role\*

integer

title: Device role

tenant

integer

title: Tenant

platform

integer

title: Platform

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this device

site\*

integer

title: Site

rack

integer

title: Rack

position

integer

title: Position (U)

maximum: 32767

minimum: 1

The lowest-numbered unit occupied by the device

face

integer

title: Rack face

Enum:

Array \[ 2 \]

status

integer

title: Status

Enum:

Array \[ 6 \]

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

cluster

integer

title: Cluster

virtual_chassis

integer

title: Virtual chassis

vc_position

integer

title: Vc position

maximum: 255

minimum: 0

vc_priority

integer

title: Vc priority

maximum: 255

minimum: 0

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**WritableDevice**

**Custom fields**
:::

[]{#118}

::: {#page118-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

118/543

Code

Description

**DELETE**

**DEL**

/dcim/devices/{id}/

dcim_devices_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/devices/{id}/napalm/

dcim_devices_napalm

Execute a NAPALM method on a Device

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this device.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

**required**

Example Value
:::

[]{#119}

::: {#page119-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

119/543

Code

Description

{

id

integer

title: ID

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

device_type\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-

9\_\]+\$

maxLength: 50

}

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

device_role\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

tenant\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 30

**Device**

**Device type**

**Manufacturer**

**Device role**

**Tenant**
:::

[]{#120}

::: {#page120-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

120/543

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

platform\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this device

site\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

rack\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

display_name

string

title: Display name

readOnly: true

}

position\*

integer

title: Position (U)

maximum: 32767

minimum: 1

The lowest-numbered unit occupied by the device

face\*

{

value\*

integer

x-nullable: true

label\*

string

}

parent_device

string

Code

Description

**Platform**

**Site**

**Rack**

**Face**
:::

[]{#121}

::: {#page121-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

121/543

title: Parent device

readOnly: true

status\*

{

value\*

integer

label\*

string

}

primary_ip\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

}

primary_ip4\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

}

primary_ip6\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

}

cluster\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 100

}

virtual_chassis\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

**GET**

/dcim/interface-connections/

dcim_interface-connections_list

**Parameters**

**Try it out**

Name

Description

connection_status\
string\
(query)

site\
string\
(query)

device\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**Status**

**Primary ip**

**Primary ip**

**Primary ip**

**Cluster**

**Virtual chassis**

Example Value
:::

[]{#122}

::: {#page122-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

122/543

title: Url

readOnly: true

master\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

}

vc_position\*

integer

title: Vc position

maximum: 255

minimum: 0

vc_priority

integer

title: Vc priority

maximum: 255

minimum: 0

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

interface_a\*

{\...}

interface_b\*

{\...}

connection_status\*

{\...}

}\]

}

**POST**

**P**

/dcim/interface-connections/

dcim_interface-connections_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

interface_a\*

integer

title: Interface a

interface_b\*

integer

title: Interface b

connection_status

boolean

title: Status

Enum:

Array \[ 2 \]

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

**Device**

**Custom fields**

**InterfaceConnection**

**Interface a\
Interface a\
Connection status**

**required**

Example Value

**WritableInterfaceConnection**

Example Value
:::

[]{#123}

::: {#page123-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

123/543

Code

Description

{

id

integer

title: ID

readOnly: true

interface_a\*

integer

title: Interface a

interface_b\*

integer

title: Interface b

connection_status

boolean

title: Status

Enum:

Array \[ 2 \]

}

**GET**

/dcim/interface-connections/{id}/

dcim_interface-connections_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this interface connection.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableInterfaceConnection**

**required**

Example Value
:::

[]{#124}

::: {#page124-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

124/543

Code

Description

{

id

integer

title: ID

readOnly: true

interface_a\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

name\*

string

title: Name

maxLength: 64

form_factor\*

{

value\*

integer

label\*

string

}

enabled

boolean

title: Enabled

lag\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 64

}

mtu

integer

title: MTU

maximum: 32767

minimum: 0

mac_address

string

title: MAC Address

mgmt_only

boolean

title: OOB Management

This interface is used only for out-of-band

management

description

string

title: Description

maxLength: 100

}

interface_b\*

{

id

integer

title: ID

readOnly: true

**InterfaceConnection**

**Interface a**

**Device**

**Form factor**

**Lag**

**Interface a**
:::

[]{#125}

::: {#page125-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

125/543

url

string(\$uri)

title: Url

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

name\*

string

title: Name

maxLength: 64

form_factor\*

{

value\*

integer

label\*

string

}

enabled

boolean

title: Enabled

lag\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 64

}

mtu

integer

title: MTU

maximum: 32767

minimum: 0

mac_address

string

title: MAC Address

mgmt_only

boolean

title: OOB Management

This interface is used only for out-of-band

management

description

string

title: Description

maxLength: 100

}

connection_status\*

{

value\*

boolean

x-nullable: true

label\*

string

}

}

Code

Description

**PUT**

/dcim/interface-connections/{id}/

dcim_interface-connections_update

**Device**

**Form factor**

**Lag**

**Connection status**
:::

[]{#126}

::: {#page126-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

126/543

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

interface_a\*

integer

title: Interface a

interface_b\*

integer

title: Interface b

connection_status

boolean

title: Status

Enum:

Array \[ 2 \]

}

**id \*\
**integer\
(path)

A unique integer value identifying this interface connection.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

interface_a\*

integer

title: Interface a

interface_b\*

integer

title: Interface b

connection_status

boolean

title: Status

Enum:

Array \[ 2 \]

}

**PATCH**

**PA**

/dcim/interface-connections/{id}/

dcim_interface-connections_partial_update

**Parameters**

**Try it out**

**required**

Example Value

**WritableInterfaceConnection**

**required**

Example Value

**WritableInterfaceConnection**
:::

[]{#127}

::: {#page127-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

127/543

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

interface_a\*

integer

title: Interface a

interface_b\*

integer

title: Interface b

connection_status

boolean

title: Status

Enum:

Array \[ 2 \]

}

**id \*\
**integer\
(path)

A unique integer value identifying this interface connection.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

interface_a\*

integer

title: Interface a

interface_b\*

integer

title: Interface b

connection_status

boolean

title: Status

Enum:

Array \[ 2 \]

}

**DELETE**

**DEL**

/dcim/interface-connections/{id}/

dcim_interface-connections_delete

**Parameters**

**Try it out**

**required**

Example Value

**WritableInterfaceConnection**

**required**

Example Value

**WritableInterfaceConnection**
:::

[]{#128}

::: {#page128-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

128/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this interface connection.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/interface-templates/

dcim_interface-templates_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

form_factor\
string\
(query)

mgmt_only\
string\
(query)

devicetype_id\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**required**
:::

[]{#129}

::: {#page129-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

129/543

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device_type\*

{\...}

name\*

string

title: Name

maxLength: 64

form_factor\*

{\...}

mgmt_only

boolean

title: Management only

}\]

}

**POST**

**P**

/dcim/interface-templates/

dcim_interface-templates_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

mgmt_only

boolean

title: Management only

}

Example Value

**InterfaceTemplate**

**Device type**

**Form factor**

**required**

Example Value

**WritableInterfaceTemplate**
:::

[]{#130}

::: {#page130-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

130/543

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

mgmt_only

boolean

title: Management only

}

**GET**

/dcim/interface-templates/{id}/

dcim_interface-templates_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this interface template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**WritableInterfaceTemplate**

**required**

Example Value
:::

[]{#131}

::: {#page131-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

131/543

Code

Description

{

id

integer

title: ID

readOnly: true

device_type\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-

9\_\]+\$

maxLength: 50

}

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

name\*

string

title: Name

maxLength: 64

form_factor\*

{

value\*

integer

label\*

string

}

mgmt_only

boolean

title: Management only

}

**PUT**

/dcim/interface-templates/{id}/

dcim_interface-templates_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**InterfaceTemplate**

**Device type**

**Manufacturer**

**Form factor**

**required**

Example Value
:::

[]{#132}

::: {#page132-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

132/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

mgmt_only

boolean

title: Management only

}

**id \*\
**integer\
(path)

A unique integer value identifying this interface template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

mgmt_only

boolean

title: Management only

}

**PATCH**

**PA**

/dcim/interface-templates/{id}/

dcim_interface-templates_partial_update

**Parameters**

**Try it out**

**WritableInterfaceTemplate**

**required**

Example Value

**WritableInterfaceTemplate**
:::

[]{#133}

::: {#page133-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

133/543

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

mgmt_only

boolean

title: Management only

}

**id \*\
**integer\
(path)

A unique integer value identifying this interface template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

mgmt_only

boolean

title: Management only

}

**DELETE**

**DEL**

/dcim/interface-templates/{id}/

dcim_interface-templates_delete

**required**

Example Value

**WritableInterfaceTemplate**

**required**

Example Value

**WritableInterfaceTemplate**
:::

[]{#134}

::: {#page134-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

134/543

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this interface template.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/interfaces/

dcim_interfaces_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

form_factor\
string\
(query)

enabled\
string\
(query)

mtu\
number\
(query)

mgmt_only\
string\
(query)

device\
string\
(query)

device_id

**required**
:::

[]{#135}

::: {#page135-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

135/543

Name

Description

number\
(query)

type\
string\
(query)

lag_id\
string\
(query)

mac_address\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#136}

::: {#page136-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

136/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device\*

{\...}

name\*

string

title: Name

maxLength: 64

form_factor\*

{\...}

enabled

boolean

title: Enabled

lag\*

{\...}

mtu

integer

title: MTU

maximum: 32767

minimum: 0

mac_address

string

title: MAC Address

mgmt_only

boolean

title: OOB Management

This interface is used only for out-of-band

management

description

string

title: Description

maxLength: 100

is_connected

string

title: Is connected

readOnly: true

interface_connection string

title: Interface connection

readOnly: true

circuit_termination\*

{\...}

mode\*

{\...}

untagged_vlan\*

{\...}

tagged_vlans\*

\[\...\]

}\]

}

**POST**

**P**

/dcim/interfaces/

dcim_interfaces_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Interface**

**Device**

**Form factor**

**Lag**

**Circuit termination\
Mode\
Untagged vlan**

**required**

Example Value
:::

[]{#137}

::: {#page137-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

137/543

Name

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

enabled

boolean

title: Enabled

lag

integer

title: Parent LAG

mtu

integer

title: MTU

maximum: 32767

minimum: 0

mac_address

string

title: MAC Address

mgmt_only

boolean

title: OOB Management

This interface is used only for out-of-band management

description

string

title: Description

maxLength: 100

mode

integer

title: Mode

Enum:

Array \[ 3 \]

untagged_vlan

integer

title: Untagged VLAN

tagged_vlans

\[

uniqueItems: true

integer

title: Tagged VLANs\]

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

**WritableInterface**

Example Value
:::

[]{#138}

::: {#page138-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

138/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

enabled

boolean

title: Enabled

lag

integer

title: Parent LAG

mtu

integer

title: MTU

maximum: 32767

minimum: 0

mac_address

string

title: MAC Address

mgmt_only

boolean

title: OOB Management

This interface is used only for out-of-band management

description

string

title: Description

maxLength: 100

mode

integer

title: Mode

Enum:

Array \[ 3 \]

untagged_vlan

integer

title: Untagged VLAN

tagged_vlans

\[

uniqueItems: true

integer

title: Tagged VLANs\]

}

**GET**

/dcim/interfaces/{id}/

dcim_interfaces_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this interface.

**Responses**

**Response content type**

**application/json**

**WritableInterface**

**required**
:::

[]{#139}

::: {#page139-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

139/543

Code

Description

200

**Model**

Example Value
:::

[]{#140}

::: {#page140-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

140/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

name\*

string

title: Name

maxLength: 64

form_factor\*

{

value\*

integer

label\*

string

}

enabled

boolean

title: Enabled

lag\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 64

}

mtu

integer

title: MTU

maximum: 32767

minimum: 0

mac_address

string

title: MAC Address

mgmt_only

boolean

title: OOB Management

This interface is used only for out-of-band management

description

string

title: Description

maxLength: 100

is_connected

string

title: Is connected

readOnly: true

interface_connection string

title: Interface connection

readOnly: true

circuit_termination\*

{

id

integer

title: ID

readOnly: true

circuit\*

{

id

integer

title: ID

readOnly: true

**Interface**

**Device**

**Form factor**

**Lag**

**Circuit termination**

**Circuit**
:::

[]{#141}

::: {#page141-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

141/543

url

string(\$uri)

title: Url

readOnly: true

cid\*

string

title: Circuit ID

maxLength: 50

}

term_side\*

string

title: Termination

Enum:

Array \[ 2 \]

port_speed\*

integer

title: Port speed (Kbps)

maximum: 2147483647

minimum: 0

upstream_speed

integer

title: Upstream speed (Kbps)

maximum: 2147483647

minimum: 0

Upstream speed, if different from port speed

xconnect_id

string

title: Cross-connect ID

maxLength: 50

pp_info

string

title: Patch panel/port(s)

maxLength: 100

}

mode\*

{

value\*

integer

label\*

string

}

untagged_vlan\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

tagged_vlans\*

\[

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}\]

Code

Description

**Mode**

**Untagged vlan**

**Untagged vlan**
:::

[]{#142}

::: {#page142-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

142/543

}

**PUT**

/dcim/interfaces/{id}/

dcim_interfaces_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

enabled

boolean

title: Enabled

lag

integer

title: Parent LAG

mtu

integer

title: MTU

maximum: 32767

minimum: 0

mac_address

string

title: MAC Address

mgmt_only

boolean

title: OOB Management

This interface is used only for out-of-band management

description

string

title: Description

maxLength: 100

mode

integer

title: Mode

Enum:

Array \[ 3 \]

untagged_vlan

integer

title: Untagged VLAN

tagged_vlans

\[

uniqueItems: true

integer

title: Tagged VLANs\]

}

**id \*\
**integer\
(path)

A unique integer value identifying this interface.

**Responses**

**Response content type**

**application/json**

**required**

Example Value

**WritableInterface**

**required**
:::

[]{#143}

::: {#page143-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

143/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

enabled

boolean

title: Enabled

lag

integer

title: Parent LAG

mtu

integer

title: MTU

maximum: 32767

minimum: 0

mac_address

string

title: MAC Address

mgmt_only

boolean

title: OOB Management

This interface is used only for out-of-band management

description

string

title: Description

maxLength: 100

mode

integer

title: Mode

Enum:

Array \[ 3 \]

untagged_vlan

integer

title: Untagged VLAN

tagged_vlans

\[

uniqueItems: true

integer

title: Tagged VLANs\]

}

**PATCH**

**PA**

/dcim/interfaces/{id}/

dcim_interfaces_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**WritableInterface**

**required**

Example Value
:::

[]{#144}

::: {#page144-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

144/543

Name

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

enabled

boolean

title: Enabled

lag

integer

title: Parent LAG

mtu

integer

title: MTU

maximum: 32767

minimum: 0

mac_address

string

title: MAC Address

mgmt_only

boolean

title: OOB Management

This interface is used only for out-of-band management

description

string

title: Description

maxLength: 100

mode

integer

title: Mode

Enum:

Array \[ 3 \]

untagged_vlan

integer

title: Untagged VLAN

tagged_vlans

\[

uniqueItems: true

integer

title: Tagged VLANs\]

}

**id \*\
**integer\
(path)

A unique integer value identifying this interface.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableInterface**

**required**

Example Value
:::

[]{#145}

::: {#page145-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

145/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 64

form_factor

integer

title: Form factor

Enum:

Array \[ 39 \]

enabled

boolean

title: Enabled

lag

integer

title: Parent LAG

mtu

integer

title: MTU

maximum: 32767

minimum: 0

mac_address

string

title: MAC Address

mgmt_only

boolean

title: OOB Management

This interface is used only for out-of-band management

description

string

title: Description

maxLength: 100

mode

integer

title: Mode

Enum:

Array \[ 3 \]

untagged_vlan

integer

title: Untagged VLAN

tagged_vlans

\[

uniqueItems: true

integer

title: Tagged VLANs\]

}

**DELETE**

**DEL**

/dcim/interfaces/{id}/

dcim_interfaces_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this interface.

**Responses**

**Response content type**

**application/json**

**WritableInterface**

**required**
:::

[]{#146}

::: {#page146-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

146/543

Code

Description

204

**GET**

/dcim/interfaces/{id}/graphs/

dcim_interfaces_graphs

A convenience method for rendering graphs for a particular interface.

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this interface.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value
:::

[]{#147}

::: {#page147-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

147/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

name\*

string

title: Name

maxLength: 64

form_factor\*

{

value\*

integer

label\*

string

}

enabled

boolean

title: Enabled

lag\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 64

}

mtu

integer

title: MTU

maximum: 32767

minimum: 0

mac_address

string

title: MAC Address

mgmt_only

boolean

title: OOB Management

This interface is used only for out-of-band management

description

string

title: Description

maxLength: 100

is_connected

string

title: Is connected

readOnly: true

interface_connection string

title: Interface connection

readOnly: true

circuit_termination\*

{

id

integer

title: ID

readOnly: true

circuit\*

{

id

integer

title: ID

readOnly: true

**Interface**

**Device**

**Form factor**

**Lag**

**Circuit termination**

**Circuit**
:::

[]{#148}

::: {#page148-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

148/543

url

string(\$uri)

title: Url

readOnly: true

cid\*

string

title: Circuit ID

maxLength: 50

}

term_side\*

string

title: Termination

Enum:

Array \[ 2 \]

port_speed\*

integer

title: Port speed (Kbps)

maximum: 2147483647

minimum: 0

upstream_speed

integer

title: Upstream speed (Kbps)

maximum: 2147483647

minimum: 0

Upstream speed, if different from port speed

xconnect_id

string

title: Cross-connect ID

maxLength: 50

pp_info

string

title: Patch panel/port(s)

maxLength: 100

}

mode\*

{

value\*

integer

label\*

string

}

untagged_vlan\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

tagged_vlans\*

\[

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}\]

Code

Description

**Mode**

**Untagged vlan**

**Untagged vlan**
:::

[]{#149}

::: {#page149-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

149/543

}

**GET**

/dcim/inventory-items/

dcim_inventory-items_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

part_id\
string\
(query)

serial\
string\
(query)

asset_tag\
string\
(query)

discovered\
string\
(query)

device_id\
string\
(query)

device\
string\
(query)

q\
string\
(query)

parent_id\
string\
(query)

manufacturer_id\
string\
(query)

manufacturer\
string\
(query)
:::

[]{#150}

::: {#page150-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

150/543

Name

Description

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device\*

{\...}

parent\*

integer

title: Parent

name\*

string

title: Name

maxLength: 50

manufacturer\*

{\...}

part_id

string

title: Part ID

maxLength: 50

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this item

discovered

boolean

title: Discovered

description

string

title: Description

maxLength: 100

}\]

}

Example Value

**InventoryItem**

**Device**

**Manufacturer**
:::

[]{#151}

::: {#page151-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

151/543

**POST**

**P**

/dcim/inventory-items/

dcim_inventory-items_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

parent

integer

title: Parent

name\*

string

title: Name

maxLength: 50

manufacturer

integer

title: Manufacturer

part_id

string

title: Part ID

maxLength: 50

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this item

discovered

boolean

title: Discovered

description

string

title: Description

maxLength: 100

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

**required**

Example Value

**WritableInventoryItem**

Example Value
:::

[]{#152}

::: {#page152-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

152/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

parent

integer

title: Parent

name\*

string

title: Name

maxLength: 50

manufacturer

integer

title: Manufacturer

part_id

string

title: Part ID

maxLength: 50

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this item

discovered

boolean

title: Discovered

description

string

title: Description

maxLength: 100

}

**GET**

/dcim/inventory-items/{id}/

dcim_inventory-items_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this inventory item.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableInventoryItem**

**required**

Example Value
:::

[]{#153}

::: {#page153-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

153/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

parent\*

integer

title: Parent

name\*

string

title: Name

maxLength: 50

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

part_id

string

title: Part ID

maxLength: 50

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this item

discovered

boolean

title: Discovered

description

string

title: Description

maxLength: 100

}

**PUT**

/dcim/inventory-items/{id}/

dcim_inventory-items_update

**Parameters**

**Try it out**

**InventoryItem**

**Device**

**Manufacturer**
:::

[]{#154}

::: {#page154-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

154/543

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

parent

integer

title: Parent

name\*

string

title: Name

maxLength: 50

manufacturer

integer

title: Manufacturer

part_id

string

title: Part ID

maxLength: 50

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this item

discovered

boolean

title: Discovered

description

string

title: Description

maxLength: 100

}

**id \*\
**integer\
(path)

A unique integer value identifying this inventory item.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value

**WritableInventoryItem**

**required**

Example Value
:::

[]{#155}

::: {#page155-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

155/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

parent

integer

title: Parent

name\*

string

title: Name

maxLength: 50

manufacturer

integer

title: Manufacturer

part_id

string

title: Part ID

maxLength: 50

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this item

discovered

boolean

title: Discovered

description

string

title: Description

maxLength: 100

}

**PATCH**

**PA**

/dcim/inventory-items/{id}/

dcim_inventory-items_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableInventoryItem**

**required**

Example Value
:::

[]{#156}

::: {#page156-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

156/543

Name

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

parent

integer

title: Parent

name\*

string

title: Name

maxLength: 50

manufacturer

integer

title: Manufacturer

part_id

string

title: Part ID

maxLength: 50

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this item

discovered

boolean

title: Discovered

description

string

title: Description

maxLength: 100

}

**id \*\
**integer\
(path)

A unique integer value identifying this inventory item.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableInventoryItem**

**required**

Example Value
:::

[]{#157}

::: {#page157-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

157/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

parent

integer

title: Parent

name\*

string

title: Name

maxLength: 50

manufacturer

integer

title: Manufacturer

part_id

string

title: Part ID

maxLength: 50

serial

string

title: Serial number

maxLength: 50

asset_tag

string

title: Asset tag

maxLength: 50

A unique tag used to identify this item

discovered

boolean

title: Discovered

description

string

title: Description

maxLength: 100

}

**DELETE**

**DEL**

/dcim/inventory-items/{id}/

dcim_inventory-items_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this inventory item.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/manufacturers/

dcim_manufacturers_list

**Parameters**

**WritableInventoryItem**

**required**
:::

[]{#158}

::: {#page158-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

158/543

**Try it out**

Name

Description

name\
string\
(query)

slug\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}\]

}

**POST**

**P**

/dcim/manufacturers/

dcim_manufacturers_create

Example Value

**Manufacturer**
:::

[]{#159}

::: {#page159-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

159/543

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

**GET**

/dcim/manufacturers/{id}/

dcim_manufacturers_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer

A unique integer value identifying this manufacturer.

**required**

Example Value

**Manufacturer**

Example Value

**Manufacturer**

**required**
:::

[]{#160}

::: {#page160-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

160/543

Name

Description

(path)

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

**PUT**

/dcim/manufacturers/{id}/

dcim_manufacturers_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this manufacturer.

Example Value

**Manufacturer**

**required**

Example Value

**Manufacturer**

**required**
:::

[]{#161}

::: {#page161-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

161/543

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

**PATCH**

**PA**

/dcim/manufacturers/{id}/

dcim_manufacturers_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this manufacturer.

**Responses**

**Response content type**

**application/json**

Example Value

**Manufacturer**

**required**

Example Value

**Manufacturer**

**required**
:::

[]{#162}

::: {#page162-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

162/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

**DELETE**

**DEL**

/dcim/manufacturers/{id}/

dcim_manufacturers_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this manufacturer.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/platforms/

dcim_platforms_list

**Parameters**

**Try it out**

Name

Description

name\
string

Example Value

**Manufacturer**

**required**
:::

[]{#163}

::: {#page163-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

163/543

Name

Description

(query)

slug\
string\
(query)

manufacturer_id\
string\
(query)

manufacturer\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#164}

::: {#page164-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

164/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

manufacturer\*

{\...}

napalm_driver

string

title: NAPALM driver

maxLength: 50

The name of the NAPALM driver to use when

interacting with devices

rpc_client

string

title: Legacy RPC client

Enum:

Array \[ 3 \]

}\]

}

**POST**

**P**

/dcim/platforms/

dcim_platforms_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Platform**

**Manufacturer**

**required**

Example Value
:::

[]{#165}

::: {#page165-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

165/543

Name

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

manufacturer

integer

title: Manufacturer

Optionally limit this platform to devices of a certain manufacturer

napalm_driver

string

title: NAPALM driver

maxLength: 50

The name of the NAPALM driver to use when interacting with devices

rpc_client

string

title: Legacy RPC client

Enum:

Array \[ 3 \]

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

manufacturer

integer

title: Manufacturer

Optionally limit this platform to devices of a certain manufacturer

napalm_driver

string

title: NAPALM driver

maxLength: 50

The name of the NAPALM driver to use when interacting with devices

rpc_client

string

title: Legacy RPC client

Enum:

Array \[ 3 \]

}

**WritablePlatform**

Example Value

**WritablePlatform**
:::

[]{#166}

::: {#page166-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

166/543

**GET**

/dcim/platforms/{id}/

dcim_platforms_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this platform.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

napalm_driver

string

title: NAPALM driver

maxLength: 50

The name of the NAPALM driver to use when interacting with devices

rpc_client

string

title: Legacy RPC client

Enum:

Array \[ 3 \]

}

**required**

Example Value

**Platform**

**Manufacturer**
:::

[]{#167}

::: {#page167-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

167/543

**PUT**

/dcim/platforms/{id}/

dcim_platforms_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

manufacturer

integer

title: Manufacturer

Optionally limit this platform to devices of a certain manufacturer

napalm_driver

string

title: NAPALM driver

maxLength: 50

The name of the NAPALM driver to use when interacting with devices

rpc_client

string

title: Legacy RPC client

Enum:

Array \[ 3 \]

}

**id \*\
**integer\
(path)

A unique integer value identifying this platform.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value

**WritablePlatform**

**required**

Example Value
:::

[]{#168}

::: {#page168-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

168/543

Code

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

manufacturer

integer

title: Manufacturer

Optionally limit this platform to devices of a certain manufacturer

napalm_driver

string

title: NAPALM driver

maxLength: 50

The name of the NAPALM driver to use when interacting with devices

rpc_client

string

title: Legacy RPC client

Enum:

Array \[ 3 \]

}

**PATCH**

**PA**

/dcim/platforms/{id}/

dcim_platforms_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

manufacturer

integer

title: Manufacturer

Optionally limit this platform to devices of a certain manufacturer

napalm_driver

string

title: NAPALM driver

maxLength: 50

The name of the NAPALM driver to use when interacting with devices

rpc_client

string

title: Legacy RPC client

Enum:

Array \[ 3 \]

}

**WritablePlatform**

**required**

Example Value

**WritablePlatform**
:::

[]{#169}

::: {#page169-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

169/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this platform.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

manufacturer

integer

title: Manufacturer

Optionally limit this platform to devices of a certain manufacturer

napalm_driver

string

title: NAPALM driver

maxLength: 50

The name of the NAPALM driver to use when interacting with devices

rpc_client

string

title: Legacy RPC client

Enum:

Array \[ 3 \]

}

**DELETE**

**DEL**

/dcim/platforms/{id}/

dcim_platforms_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this platform.

**required**

Example Value

**WritablePlatform**

**required**
:::

[]{#170}

::: {#page170-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

170/543

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/power-connections/

dcim_power-connections_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

connection_status\
string\
(query)

site\
string\
(query)

device\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#171}

::: {#page171-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

171/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device\*

{\...}

name\*

string

title: Name

maxLength: 50

power_outlet\*

{\...}

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}\]

}

**GET**

/dcim/power-outlet-templates/

dcim_power-outlet-templates_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

devicetype_id\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

**PowerPort**

**Device**

**Power outlet**
:::

[]{#172}

::: {#page172-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

172/543

Code

Description

200

**Model**

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device_type\*

{\...}

name\*

string

title: Name

maxLength: 50

}\]

}

**POST**

**P**

/dcim/power-outlet-templates/

dcim_power-outlet-templates_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

Example Value

**PowerOutletTemplate**

**Device type**

**required**

Example Value

**WritablePowerOutletTemplate**
:::

[]{#173}

::: {#page173-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

173/543

Code

Description

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**GET**

/dcim/power-outlet-templates/{id}/

dcim_power-outlet-templates_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this power outlet template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**WritablePowerOutletTemplate**

**required**

Example Value
:::

[]{#174}

::: {#page174-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

174/543

Code

Description

{

id

integer

title: ID

readOnly: true

device_type\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-

9\_\]+\$

maxLength: 50

}

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

name\*

string

title: Name

maxLength: 50

}

**PUT**

/dcim/power-outlet-templates/{id}/

dcim_power-outlet-templates_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**PowerOutletTemplate**

**Device type**

**Manufacturer**

**required**

Example Value
:::

[]{#175}

::: {#page175-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

175/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this power outlet template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**PATCH**

**PA**

/dcim/power-outlet-templates/{id}/

dcim_power-outlet-templates_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritablePowerOutletTemplate**

**required**

Example Value

**WritablePowerOutletTemplate**

**required**

Example Value
:::

[]{#176}

::: {#page176-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

176/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this power outlet template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**DELETE**

**DEL**

/dcim/power-outlet-templates/{id}/

dcim_power-outlet-templates_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this power outlet template.

**WritablePowerOutletTemplate**

**required**

Example Value

**WritablePowerOutletTemplate**

**required**
:::

[]{#177}

::: {#page177-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

177/543

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/power-outlets/

dcim_power-outlets_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

device_id\
string\
(query)

device\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#178}

::: {#page178-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

178/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device\*

{\...}

name\*

string

title: Name

maxLength: 50

connected_port

string

title: Connected port

readOnly: true

}\]

}

**POST**

**P**

/dcim/power-outlets/

dcim_power-outlets_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

**Power outlet**

**Device**

**required**

Example Value

**WritablePowerOutlet**

Example Value
:::

[]{#179}

::: {#page179-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

179/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**GET**

/dcim/power-outlets/{id}/

dcim_power-outlets_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this power outlet.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritablePowerOutlet**

**required**

Example Value
:::

[]{#180}

::: {#page180-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

180/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

name\*

string

title: Name

maxLength: 50

connected_port

string

title: Connected port

readOnly: true

}

**PUT**

/dcim/power-outlets/{id}/

dcim_power-outlets_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this power outlet.

**Responses**

**Response content type**

**application/json**

**Power outlet**

**Device**

**required**

Example Value

**WritablePowerOutlet**

**required**
:::

[]{#181}

::: {#page181-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

181/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**PATCH**

**PA**

/dcim/power-outlets/{id}/

dcim_power-outlets_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this power outlet.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**WritablePowerOutlet**

**required**

Example Value

**WritablePowerOutlet**

**required**

Example Value
:::

[]{#182}

::: {#page182-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

182/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

}

**DELETE**

**DEL**

/dcim/power-outlets/{id}/

dcim_power-outlets_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this power outlet.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/power-port-templates/

dcim_power-port-templates_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

devicetype_id\
string\
(query)

limit

Number of results to return per page.

**WritablePowerOutlet**

**required**
:::

[]{#183}

::: {#page183-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

183/543

Name

Description

integer\
(query)

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device_type\*

{\...}

name\*

string

title: Name

maxLength: 50

}\]

}

**POST**

**P**

/dcim/power-port-templates/

dcim_power-port-templates_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**PowerPortTemplate**

**Device type**

**required**

Example Value
:::

[]{#184}

::: {#page184-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

184/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**GET**

/dcim/power-port-templates/{id}/

dcim_power-port-templates_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this power port template.

**Responses**

**Response content type**

**application/json**

**WritablePowerPortTemplate**

Example Value

**WritablePowerPortTemplate**

**required**
:::

[]{#185}

::: {#page185-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

185/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

manufacturer\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-

9\_\]+\$

maxLength: 50

}

model\*

string

title: Model

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

name\*

string

title: Name

maxLength: 50

}

**PUT**

/dcim/power-port-templates/{id}/

dcim_power-port-templates_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**PowerPortTemplate**

**Device type**

**Manufacturer**

**required**

Example Value
:::

[]{#186}

::: {#page186-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

186/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this power port template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**PATCH**

**PA**

/dcim/power-port-templates/{id}/

dcim_power-port-templates_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritablePowerPortTemplate**

**required**

Example Value

**WritablePowerPortTemplate**

**required**

Example Value
:::

[]{#187}

::: {#page187-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

187/543

Name

Description

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**id \*\
**integer\
(path)

A unique integer value identifying this power port template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device_type\*

integer

title: Device type

name\*

string

title: Name

maxLength: 50

}

**DELETE**

**DEL**

/dcim/power-port-templates/{id}/

dcim_power-port-templates_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this power port template.

**WritablePowerPortTemplate**

**required**

Example Value

**WritablePowerPortTemplate**

**required**
:::

[]{#188}

::: {#page188-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

188/543

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/power-ports/

dcim_power-ports_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

device_id\
string\
(query)

device\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#189}

::: {#page189-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

189/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

device\*

{\...}

name\*

string

title: Name

maxLength: 50

power_outlet\*

{\...}

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}\]

}

**POST**

**P**

/dcim/power-ports/

dcim_power-ports_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

power_outlet

integer

title: Power outlet

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**Responses**

**Response content type**

**application/json**

**PowerPort**

**Device**

**Power outlet**

**required**

Example Value

**WritablePowerPort**
:::

[]{#190}

::: {#page190-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

190/543

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

power_outlet

integer

title: Power outlet

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**GET**

/dcim/power-ports/{id}/

dcim_power-ports_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this power port.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**WritablePowerPort**

**required**

Example Value
:::

[]{#191}

::: {#page191-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

191/543

Code

Description

{

id

integer

title: ID

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

name\*

string

title: Name

maxLength: 50

power_outlet\*

{

id

integer

title: ID

readOnly: true

device\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

name\*

string

title: Name

maxLength: 50

connected_port

string

title: Connected port

readOnly: true

}

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**PUT**

/dcim/power-ports/{id}/

dcim_power-ports_update

**Parameters**

**Try it out**

**PowerPort**

**Device**

**Power outlet**

**Device**
:::

[]{#192}

::: {#page192-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

192/543

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

power_outlet

integer

title: Power outlet

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**id \*\
**integer\
(path)

A unique integer value identifying this power port.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

power_outlet

integer

title: Power outlet

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**PATCH**

**PA**

/dcim/power-ports/{id}/

dcim_power-ports_partial_update

**required**

Example Value

**WritablePowerPort**

**required**

Example Value

**WritablePowerPort**
:::

[]{#193}

::: {#page193-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

193/543

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

power_outlet

integer

title: Power outlet

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**id \*\
**integer\
(path)

A unique integer value identifying this power port.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

name\*

string

title: Name

maxLength: 50

power_outlet

integer

title: Power outlet

connection_status

boolean

title: Connection status

Enum:

Array \[ 2 \]

}

**required**

Example Value

**WritablePowerPort**

**required**

Example Value

**WritablePowerPort**
:::

[]{#194}

::: {#page194-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

194/543

**DELETE**

**DEL**

/dcim/power-ports/{id}/

dcim_power-ports_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this power port.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/rack-groups/

dcim_rack-groups_list

**Parameters**

**Try it out**

Name

Description

site_id\
string\
(query)

name\
string\
(query)

slug\
string\
(query)

site\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer

The initial index from which to return the results.

**required**
:::

[]{#195}

::: {#page195-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

195/543

Name

Description

(query)

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

site\*

{\...}

}\]

}

**POST**

**P**

/dcim/rack-groups/

dcim_rack-groups_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**RackGroup**

**Site**

**required**

Example Value
:::

[]{#196}

::: {#page196-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

196/543

Name

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

site\*

integer

title: Site

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

site\*

integer

title: Site

}

**GET**

/dcim/rack-groups/{id}/

dcim_rack-groups_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this rack group.

**WritableRackGroup**

Example Value

**WritableRackGroup**

**required**
:::

[]{#197}

::: {#page197-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

197/543

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

site\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

}

**PUT**

/dcim/rack-groups/{id}/

dcim_rack-groups_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**RackGroup**

**Site**

**required**

Example Value
:::

[]{#198}

::: {#page198-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

198/543

Name

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

site\*

integer

title: Site

}

**id \*\
**integer\
(path)

A unique integer value identifying this rack group.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

site\*

integer

title: Site

}

**PATCH**

**PA**

/dcim/rack-groups/{id}/

dcim_rack-groups_partial_update

**Parameters**

**Try it out**

Name

Description

**data \***

**WritableRackGroup**

**required**

Example Value

**WritableRackGroup**

**required**
:::

[]{#199}

::: {#page199-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

199/543

Name

Description

(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

site\*

integer

title: Site

}

**id \*\
**integer\
(path)

A unique integer value identifying this rack group.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

site\*

integer

title: Site

}

**DELETE**

**DEL**

/dcim/rack-groups/{id}/

dcim_rack-groups_delete

**Parameters**

**Try it out**

Example Value

**WritableRackGroup**

**required**

Example Value

**WritableRackGroup**
:::

[]{#200}

::: {#page200-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

200/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this rack group.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/rack-reservations/

dcim_rack-reservations_list

**Parameters**

**Try it out**

Name

Description

created\
string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

rack_id\
string\
(query)

site_id\
string\
(query)

site\
string\
(query)

group_id\
string\
(query)

**required**
:::

[]{#201}

::: {#page201-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

201/543

Name

Description

group\
string\
(query)

tenant_id\
string\
(query)

tenant\
string\
(query)

user_id\
string\
(query)

user\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#202}

::: {#page202-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

202/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

rack\*

{\...}

units\*

\[\...\]

created

string(\$date-time)

title: Created

readOnly: true

user\*

{\...}

tenant\*

{\...}

description\*

string

title: Description

maxLength: 100

}\]

}

**POST**

**P**

/dcim/rack-reservations/

dcim_rack-reservations_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

rack\*

integer

title: Rack

units\*

\[integer

title: Units

maximum: 32767

minimum: 0\]

user\*

integer

title: User

tenant

integer

title: Tenant

description\*

string

title: Description

maxLength: 100

}

**RackReservation**

**Rack**

**User\
Tenant**

**required**

Example Value

**WritableRackReservation**
:::

[]{#203}

::: {#page203-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

203/543

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

rack\*

integer

title: Rack

units\*

\[integer

title: Units

maximum: 32767

minimum: 0\]

user\*

integer

title: User

tenant

integer

title: Tenant

description\*

string

title: Description

maxLength: 100

}

**GET**

/dcim/rack-reservations/{id}/

dcim_rack-reservations_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this rack reservation.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**WritableRackReservation**

**required**

Example Value
:::

[]{#204}

::: {#page204-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

204/543

Code

Description

{

id

integer

title: ID

readOnly: true

rack\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

display_name

string

title: Display name

readOnly: true

}

units\*

\[integer

title: Units

maximum: 32767

minimum: 0\]

created

string(\$date-time)

title: Created

readOnly: true

user\*

{

id

integer

title: ID

readOnly: true

username\*

string

title: Username

pattern: \^\[\\w.@+-\]+\$

maxLength: 150

Required. 150 characters or fewer. Letters,

digits and @/./+/-/\_ only.

}

tenant\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

description\*

string

title: Description

maxLength: 100

}

**PUT**

/dcim/rack-reservations/{id}/

dcim_rack-reservations_update

**Parameters**

**RackReservation**

**Rack**

**User**

**Tenant**
:::

[]{#205}

::: {#page205-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

205/543

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

rack\*

integer

title: Rack

units\*

\[integer

title: Units

maximum: 32767

minimum: 0\]

user\*

integer

title: User

tenant

integer

title: Tenant

description\*

string

title: Description

maxLength: 100

}

**id \*\
**integer\
(path)

A unique integer value identifying this rack reservation.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value

**WritableRackReservation**

**required**

Example Value
:::

[]{#206}

::: {#page206-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

206/543

Code

Description

{

id

integer

title: ID

readOnly: true

rack\*

integer

title: Rack

units\*

\[integer

title: Units

maximum: 32767

minimum: 0\]

user\*

integer

title: User

tenant

integer

title: Tenant

description\*

string

title: Description

maxLength: 100

}

**PATCH**

**PA**

/dcim/rack-reservations/{id}/

dcim_rack-reservations_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

rack\*

integer

title: Rack

units\*

\[integer

title: Units

maximum: 32767

minimum: 0\]

user\*

integer

title: User

tenant

integer

title: Tenant

description\*

string

title: Description

maxLength: 100

}

**id \*\
**integer\
(path)

A unique integer value identifying this rack reservation.

**Responses**

**WritableRackReservation**

**required**

Example Value

**WritableRackReservation**

**required**
:::

[]{#207}

::: {#page207-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

207/543

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

rack\*

integer

title: Rack

units\*

\[integer

title: Units

maximum: 32767

minimum: 0\]

user\*

integer

title: User

tenant

integer

title: Tenant

description\*

string

title: Description

maxLength: 100

}

**DELETE**

**DEL**

/dcim/rack-reservations/{id}/

dcim_rack-reservations_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this rack reservation.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/rack-roles/

dcim_rack-roles_list

**Parameters**

**Try it out**

Example Value

**WritableRackReservation**

**required**
:::

[]{#208}

::: {#page208-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

208/543

Name

Description

name\
string\
(query)

slug\
string\
(query)

color\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#209}

::: {#page209-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

209/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

}\]

}

**POST**

**P**

/dcim/rack-roles/

dcim_rack-roles_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

}

**Responses**

**Response content type**

**application/json**

**RackRole**

**required**

Example Value

**RackRole**
:::

[]{#210}

::: {#page210-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

210/543

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

}

**GET**

/dcim/rack-roles/{id}/

dcim_rack-roles_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this rack role.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**RackRole**

**required**

Example Value
:::

[]{#211}

::: {#page211-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

211/543

Code

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

}

**PUT**

/dcim/rack-roles/{id}/

dcim_rack-roles_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

}

**id \*\
**integer\
(path)

A unique integer value identifying this rack role.

**Responses**

**Response content type**

**application/json**

**RackRole**

**required**

Example Value

**RackRole**

**required**
:::

[]{#212}

::: {#page212-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

212/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

}

**PATCH**

**PA**

/dcim/rack-roles/{id}/

dcim_rack-roles_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

}

**id \*\
**integer\
(path)

A unique integer value identifying this rack role.

Example Value

**RackRole**

**required**

Example Value

**RackRole**

**required**
:::

[]{#213}

::: {#page213-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

213/543

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

color\*

string

title: Color

pattern: \^\[0-9a-f\]{6}\$

maxLength: 6

}

**DELETE**

**DEL**

/dcim/rack-roles/{id}/

dcim_rack-roles_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this rack role.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/racks/

dcim_racks_list

**Parameters**

**Try it out**

Example Value

**RackRole**

**required**
:::

[]{#214}

::: {#page214-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

214/543

Name

Description

name\
string\
(query)

serial\
string\
(query)

type\
string\
(query)

width\
string\
(query)

u_height\
number\
(query)

desc_units\
string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

facility_id\
string\
(query)

site_id\
string\
(query)

site\
string\
(query)

group_id\
string\
(query)

group\
string
:::

[]{#215}

::: {#page215-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

215/543

Name

Description

(query)

tenant_id\
string\
(query)

tenant\
string\
(query)

role_id\
string\
(query)

role\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#216}

::: {#page216-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

216/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

facility_id\*

string

title: Facility ID

maxLength: 50

display_name

string

title: Display name

readOnly: true

site\*

{\...}

group\*

{\...}

tenant\*

{\...}

role\*

{\...}

serial

string

title: Serial number

maxLength: 50

type\*

{\...}

width\*

{\...}

u_height

integer

title: Height (U)

maximum: 100

minimum: 1

desc_units

boolean

title: Descending units

Units are numbered top-to-bottom

comments

string

title: Comments

custom_fields

{\...}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}\]

}

**POST**

**P**

/dcim/racks/

dcim_racks_create

**Parameters**

**Try it out**

Name

Description

**data \***

**Rack**

**Site\
Group\
Tenant\
Role**

**Type\
Width**

**Custom fields**

**required**
:::

[]{#217}

::: {#page217-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

217/543

Name

Description

(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

facility_id

string

title: Facility ID

maxLength: 50

site\*

integer

title: Site

group

integer

title: Group

tenant

integer

title: Tenant

role

integer

title: Role

serial

string

title: Serial number

maxLength: 50

type

integer

title: Type

Enum:

Array \[ 5 \]

width

integer

title: Width

Rail-to-rail width

Enum:

Array \[ 2 \]

u_height

integer

title: Height (U)

maximum: 100

minimum: 1

desc_units

boolean

title: Descending units

Units are numbered top-to-bottom

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

Example Value

**WritableRack**

**Custom fields**
:::

[]{#218}

::: {#page218-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

218/543

Code

Description

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

facility_id

string

title: Facility ID

maxLength: 50

site\*

integer

title: Site

group

integer

title: Group

tenant

integer

title: Tenant

role

integer

title: Role

serial

string

title: Serial number

maxLength: 50

type

integer

title: Type

Enum:

Array \[ 5 \]

width

integer

title: Width

Rail-to-rail width

Enum:

Array \[ 2 \]

u_height

integer

title: Height (U)

maximum: 100

minimum: 1

desc_units

boolean

title: Descending units

Units are numbered top-to-bottom

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**GET**

/dcim/racks/{id}/

dcim_racks_read

**Parameters**

**Try it out**

Name

Description

**id \***

A unique integer value identifying this rack.

Example Value

**WritableRack**

**Custom fields**

**required**
:::

[]{#219}

::: {#page219-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

219/543

Name

Description

integer\
(path)

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#220}

::: {#page220-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

220/543

Code

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

facility_id\*

string

title: Facility ID

maxLength: 50

display_name

string

title: Display name

readOnly: true

site\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

group\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

tenant\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

role\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

**Rack**

**Site**

**Group**

**Tenant**

**Role**
:::

[]{#221}

::: {#page221-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

221/543

name

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

serial

string

title: Serial number

maxLength: 50

type\*

{

value\*

integer

label\*

string

}

width\*

{

value\*

integer

label\*

string

}

u_height

integer

title: Height (U)

maximum: 100

minimum: 1

desc_units

boolean

title: Descending units

Units are numbered top-to-bottom

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

Code

Description

**PUT**

/dcim/racks/{id}/

dcim_racks_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Type**

**Width**

**Custom fields**

**required**

Example Value
:::

[]{#222}

::: {#page222-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

222/543

Name

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

facility_id

string

title: Facility ID

maxLength: 50

site\*

integer

title: Site

group

integer

title: Group

tenant

integer

title: Tenant

role

integer

title: Role

serial

string

title: Serial number

maxLength: 50

type

integer

title: Type

Enum:

Array \[ 5 \]

width

integer

title: Width

Rail-to-rail width

Enum:

Array \[ 2 \]

u_height

integer

title: Height (U)

maximum: 100

minimum: 1

desc_units

boolean

title: Descending units

Units are numbered top-to-bottom

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**id \*\
**integer\
(path)

A unique integer value identifying this rack.

**Responses**

**Response content type**

**application/json**

**WritableRack**

**Custom fields**

**required**
:::

[]{#223}

::: {#page223-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

223/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

facility_id

string

title: Facility ID

maxLength: 50

site\*

integer

title: Site

group

integer

title: Group

tenant

integer

title: Tenant

role

integer

title: Role

serial

string

title: Serial number

maxLength: 50

type

integer

title: Type

Enum:

Array \[ 5 \]

width

integer

title: Width

Rail-to-rail width

Enum:

Array \[ 2 \]

u_height

integer

title: Height (U)

maximum: 100

minimum: 1

desc_units

boolean

title: Descending units

Units are numbered top-to-bottom

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**PATCH**

**PA**

/dcim/racks/{id}/

dcim_racks_partial_update

**Parameters**

**Try it out**

Example Value

**WritableRack**

**Custom fields**
:::

[]{#224}

::: {#page224-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

224/543

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

facility_id

string

title: Facility ID

maxLength: 50

site\*

integer

title: Site

group

integer

title: Group

tenant

integer

title: Tenant

role

integer

title: Role

serial

string

title: Serial number

maxLength: 50

type

integer

title: Type

Enum:

Array \[ 5 \]

width

integer

title: Width

Rail-to-rail width

Enum:

Array \[ 2 \]

u_height

integer

title: Height (U)

maximum: 100

minimum: 1

desc_units

boolean

title: Descending units

Units are numbered top-to-bottom

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**id \*\
**integer\
(path)

A unique integer value identifying this rack.

**Responses**

**required**

Example Value

**WritableRack**

**Custom fields**

**required**
:::

[]{#225}

::: {#page225-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

225/543

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

facility_id

string

title: Facility ID

maxLength: 50

site\*

integer

title: Site

group

integer

title: Group

tenant

integer

title: Tenant

role

integer

title: Role

serial

string

title: Serial number

maxLength: 50

type

integer

title: Type

Enum:

Array \[ 5 \]

width

integer

title: Width

Rail-to-rail width

Enum:

Array \[ 2 \]

u_height

integer

title: Height (U)

maximum: 100

minimum: 1

desc_units

boolean

title: Descending units

Units are numbered top-to-bottom

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**DELETE**

**DEL**

/dcim/racks/{id}/

dcim_racks_delete

**Parameters**

**Try it out**

Example Value

**WritableRack**

**Custom fields**
:::

[]{#226}

::: {#page226-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

226/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this rack.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/racks/{id}/units/

dcim_racks_units

List rack units (by rack)

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this rack.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

**required**

Example Value
:::

[]{#227}

::: {#page227-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

227/543

Code

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

facility_id\*

string

title: Facility ID

maxLength: 50

display_name

string

title: Display name

readOnly: true

site\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

group\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

tenant\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

role\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

**Rack**

**Site**

**Group**

**Tenant**

**Role**
:::

[]{#228}

::: {#page228-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

228/543

name

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

serial

string

title: Serial number

maxLength: 50

type\*

{

value\*

integer

label\*

string

}

width\*

{

value\*

integer

label\*

string

}

u_height

integer

title: Height (U)

maximum: 100

minimum: 1

desc_units

boolean

title: Descending units

Units are numbered top-to-bottom

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

Code

Description

**GET**

/dcim/regions/

dcim_regions_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

slug\
string\
(query)

q\
string\
(query)

**Type**

**Width**

**Custom fields**
:::

[]{#229}

::: {#page229-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

229/543

Name

Description

parent_id\
string\
(query)

parent\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

parent\*

{\...}

}\]

}

**POST**

**P**

/dcim/regions/

dcim_regions_create

**Parameters**

**Try it out**

Example Value

**Region**

**Parent**
:::

[]{#230}

::: {#page230-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

230/543

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

parent

integer

title: Parent

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

parent

integer

title: Parent

}

**GET**

/dcim/regions/{id}/

dcim_regions_read

**Parameters**

**Try it out**

Name

Description

**id \***

A unique integer value identifying this region.

**required**

Example Value

**WritableRegion**

Example Value

**WritableRegion**

**required**
:::

[]{#231}

::: {#page231-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

231/543

Name

Description

integer\
(path)

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

parent\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

}

**PUT**

/dcim/regions/{id}/

dcim_regions_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**Region**

**Parent**

**required**

Example Value
:::

[]{#232}

::: {#page232-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

232/543

Name

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

parent

integer

title: Parent

}

**id \*\
**integer\
(path)

A unique integer value identifying this region.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

parent

integer

title: Parent

}

**PATCH**

**PA**

/dcim/regions/{id}/

dcim_regions_partial_update

**Parameters**

**Try it out**

Name

Description

**data \***

**WritableRegion**

**required**

Example Value

**WritableRegion**

**required**
:::

[]{#233}

::: {#page233-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

233/543

Name

Description

(body)

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

parent

integer

title: Parent

}

**id \*\
**integer\
(path)

A unique integer value identifying this region.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

parent

integer

title: Parent

}

**DELETE**

**DEL**

/dcim/regions/{id}/

dcim_regions_delete

**Parameters**

**Try it out**

Example Value

**WritableRegion**

**required**

Example Value

**WritableRegion**
:::

[]{#234}

::: {#page234-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

234/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this region.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/sites/

dcim_sites_list

**Parameters**

**Try it out**

Name

Description

q\
string\
(query)

name\
string\
(query)

slug\
string\
(query)

facility\
string\
(query)

asn\
number\
(query)

contact_name\
string\
(query)

contact_phone\
string\
(query)

**required**
:::

[]{#235}

::: {#page235-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

235/543

Name

Description

contact_email\
string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

status\
string\
(query)

region_id\
string\
(query)

region\
string\
(query)

tenant_id\
string\
(query)

tenant\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#236}

::: {#page236-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

236/543

Code

Description

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

status\*

{\...}

region\*

{\...}

tenant\*

{\...}

facility

string

title: Facility

maxLength: 50

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

time_zone

string

title: Time zone

description

string

title: Description

maxLength: 100

physical_address

string

title: Physical address

maxLength: 200

shipping_address

string

title: Shipping address

maxLength: 200

contact_name

string

title: Contact name

maxLength: 50

contact_phone

string

title: Contact phone

maxLength: 20

contact_email

string(\$email)

title: Contact E-mail

maxLength: 254

comments

string

title: Comments

custom_fields

{\...}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

count_prefixes

string

title: Count prefixes

readOnly: true

count_vlans

string

title: Count vlans

readOnly: true

count_racks

string

title: Count racks

readOnly: true

count_devices

string

title: Count devices

readOnly: true

**Site**

**Status\
Parent\
Tenant**

**Custom fields**
:::

[]{#237}

::: {#page237-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

237/543

count_circuits

string

title: Count circuits

readOnly: true

}\]

}

Code

Description

**POST**

**P**

/dcim/sites/

dcim_sites_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**required**

Example Value
:::

[]{#238}

::: {#page238-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

238/543

Name

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

status

integer

title: Status

Enum:

Array \[ 3 \]

region

integer

title: Region

tenant

integer

title: Tenant

facility

string

title: Facility

maxLength: 50

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

time_zone

string

title: Time zone

description

string

title: Description

maxLength: 100

physical_address

string

title: Physical address

maxLength: 200

shipping_address

string

title: Shipping address

maxLength: 200

contact_name

string

title: Contact name

maxLength: 50

contact_phone

string

title: Contact phone

maxLength: 20

contact_email

string(\$email)

title: Contact E-mail

maxLength: 254

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**Responses**

**Response content type**

**application/json**

**WritableSite**

**Custom fields**
:::

[]{#239}

::: {#page239-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

239/543

Code

Description

201

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

status

integer

title: Status

Enum:

Array \[ 3 \]

region

integer

title: Region

tenant

integer

title: Tenant

facility

string

title: Facility

maxLength: 50

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

time_zone

string

title: Time zone

description

string

title: Description

maxLength: 100

physical_address

string

title: Physical address

maxLength: 200

shipping_address

string

title: Shipping address

maxLength: 200

contact_name

string

title: Contact name

maxLength: 50

contact_phone

string

title: Contact phone

maxLength: 20

contact_email

string(\$email)

title: Contact E-mail

maxLength: 254

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

Example Value

**WritableSite**

**Custom fields**
:::

[]{#240}

::: {#page240-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

240/543

**GET**

/dcim/sites/{id}/

dcim_sites_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this site.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value
:::

[]{#241}

::: {#page241-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

241/543

Code

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

status\*

{

value\*

integer

label\*

string

}

region\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

tenant\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

facility

string

title: Facility

maxLength: 50

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

time_zone

string

title: Time zone

description

string

title: Description

maxLength: 100

physical_address

string

title: Physical address

maxLength: 200

shipping_address

string

title: Shipping address

maxLength: 200

contact_name

string

title: Contact name

maxLength: 50

contact phone

string

**Site**

**Status**

**Parent**

**Tenant**
:::

[]{#242}

::: {#page242-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

242/543

contact_phone

string

title: Contact phone

maxLength: 20

contact_email

string(\$email)

title: Contact E-mail

maxLength: 254

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

count_prefixes

string

title: Count prefixes

readOnly: true

count_vlans

string

title: Count vlans

readOnly: true

count_racks

string

title: Count racks

readOnly: true

count_devices

string

title: Count devices

readOnly: true

count_circuits

string

title: Count circuits

readOnly: true

}

Code

Description

**PUT**

/dcim/sites/{id}/

dcim_sites_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Custom fields**

**required**

Example Value
:::

[]{#243}

::: {#page243-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

243/543

Name

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

status

integer

title: Status

Enum:

Array \[ 3 \]

region

integer

title: Region

tenant

integer

title: Tenant

facility

string

title: Facility

maxLength: 50

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

time_zone

string

title: Time zone

description

string

title: Description

maxLength: 100

physical_address

string

title: Physical address

maxLength: 200

shipping_address

string

title: Shipping address

maxLength: 200

contact_name

string

title: Contact name

maxLength: 50

contact_phone

string

title: Contact phone

maxLength: 20

contact_email

string(\$email)

title: Contact E-mail

maxLength: 254

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**id \*\
**integer\
(path)

A unique integer value identifying this site.

**WritableSite**

**Custom fields**

**required**
:::

[]{#244}

::: {#page244-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

244/543

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

status

integer

title: Status

Enum:

Array \[ 3 \]

region

integer

title: Region

tenant

integer

title: Tenant

facility

string

title: Facility

maxLength: 50

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

time_zone

string

title: Time zone

description

string

title: Description

maxLength: 100

physical_address

string

title: Physical address

maxLength: 200

shipping_address

string

title: Shipping address

maxLength: 200

contact_name

string

title: Contact name

maxLength: 50

contact_phone

string

title: Contact phone

maxLength: 20

contact_email

string(\$email)

title: Contact E-mail

maxLength: 254

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

Example Value

**WritableSite**

**Custom fields**
:::

[]{#245}

::: {#page245-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

245/543

**PATCH**

**PA**

/dcim/sites/{id}/

dcim_sites_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**required**

Example Value
:::

[]{#246}

::: {#page246-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

246/543

Name

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

status

integer

title: Status

Enum:

Array \[ 3 \]

region

integer

title: Region

tenant

integer

title: Tenant

facility

string

title: Facility

maxLength: 50

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

time_zone

string

title: Time zone

description

string

title: Description

maxLength: 100

physical_address

string

title: Physical address

maxLength: 200

shipping_address

string

title: Shipping address

maxLength: 200

contact_name

string

title: Contact name

maxLength: 50

contact_phone

string

title: Contact phone

maxLength: 20

contact_email

string(\$email)

title: Contact E-mail

maxLength: 254

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**id \*\
**integer\
(path)

A unique integer value identifying this site.

**WritableSite**

**Custom fields**

**required**
:::

[]{#247}

::: {#page247-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

247/543

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

status

integer

title: Status

Enum:

Array \[ 3 \]

region

integer

title: Region

tenant

integer

title: Tenant

facility

string

title: Facility

maxLength: 50

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

time_zone

string

title: Time zone

description

string

title: Description

maxLength: 100

physical_address

string

title: Physical address

maxLength: 200

shipping_address

string

title: Shipping address

maxLength: 200

contact_name

string

title: Contact name

maxLength: 50

contact_phone

string

title: Contact phone

maxLength: 20

contact_email

string(\$email)

title: Contact E-mail

maxLength: 254

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

Example Value

**WritableSite**

**Custom fields**
:::

[]{#248}

::: {#page248-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

248/543

**DELETE**

**DEL**

/dcim/sites/{id}/

dcim_sites_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this site.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/dcim/sites/{id}/graphs/

dcim_sites_graphs

A convenience method for rendering graphs for a particular site.

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this site.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

**required**

Example Value
:::

[]{#249}

::: {#page249-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

249/543

Code

Description

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

status\*

{

value\*

integer

label\*

string

}

region\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

tenant\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name\*

string

title: Name

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

facility

string

title: Facility

maxLength: 50

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

time_zone

string

title: Time zone

description

string

title: Description

maxLength: 100

physical_address

string

title: Physical address

maxLength: 200

shipping_address

string

title: Shipping address

maxLength: 200

contact_name

string

title: Contact name

maxLength: 50

contact phone

string

**Site**

**Status**

**Parent**

**Tenant**
:::

[]{#250}

::: {#page250-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

250/543

contact_phone

string

title: Contact phone

maxLength: 20

contact_email

string(\$email)

title: Contact E-mail

maxLength: 254

comments

string

title: Comments

custom_fields

{

}

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

count_prefixes

string

title: Count prefixes

readOnly: true

count_vlans

string

title: Count vlans

readOnly: true

count_racks

string

title: Count racks

readOnly: true

count_devices

string

title: Count devices

readOnly: true

count_circuits

string

title: Count circuits

readOnly: true

}

Code

Description

**GET**

/dcim/virtual-chassis/

dcim_virtual-chassis_list

**Parameters**

**Try it out**

Name

Description

limit\
integer\
(query)

Number of results to return per page.

offset\
integer\
(query)

The initial index from which to return the results.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Custom fields**
:::

[]{#251}

::: {#page251-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

251/543

Code

Description

**Model**

{

count\*

integer

next

string(\$uri)

x-nullable: true

previous

string(\$uri)

x-nullable: true

results\*

\[

{

id

integer

title: ID

readOnly: true

master\*

{\...}

domain

string

title: Domain

maxLength: 30

}\]

}

**POST**

**P**

/dcim/virtual-chassis/

dcim_virtual-chassis_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

master\*

integer

title: Master

domain

string

title: Domain

maxLength: 30

}

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

Example Value

**VirtualChassis**

**Device**

**required**

Example Value

**WritableVirtualChassis**

Example Value
:::

[]{#252}

::: {#page252-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

252/543

Code

Description

{

id

integer

title: ID

readOnly: true

master\*

integer

title: Master

domain

string

title: Domain

maxLength: 30

}

**GET**

/dcim/virtual-chassis/{id}/

dcim_virtual-chassis_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this virtual chassis.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableVirtualChassis**

**required**

Example Value
:::

[]{#253}

::: {#page253-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

253/543

Code

Description

{

id

integer

title: ID

readOnly: true

master\*

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

domain

string

title: Domain

maxLength: 30

}

**PUT**

/dcim/virtual-chassis/{id}/

dcim_virtual-chassis_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

master\*

integer

title: Master

domain

string

title: Domain

maxLength: 30

}

**id \*\
**integer\
(path)

A unique integer value identifying this virtual chassis.

**Responses**

**Response content type**

**application/json**

**VirtualChassis**

**Device**

**required**

Example Value

**WritableVirtualChassis**

**required**
:::

[]{#254}

::: {#page254-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

254/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

master\*

integer

title: Master

domain

string

title: Domain

maxLength: 30

}

**PATCH**

**PA**

/dcim/virtual-chassis/{id}/

dcim_virtual-chassis_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

{

id

integer

title: ID

readOnly: true

master\*

integer

title: Master

domain

string

title: Domain

maxLength: 30

}

**id \*\
**integer\
(path)

A unique integer value identifying this virtual chassis.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**WritableVirtualChassis**

**required**

Example Value

**WritableVirtualChassis**

**required**

Example Value
:::

[]{#255}

::: {#page255-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

255/543

Code

Description

{

id

integer

title: ID

readOnly: true

master\*

integer

title: Master

domain

string

title: Domain

maxLength: 30

}

**DELETE**

**DEL**

/dcim/virtual-chassis/{id}/

dcim_virtual-chassis_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this virtual chassis.

**Responses**

**Response content type**

**application/json**

Code

Description

204
