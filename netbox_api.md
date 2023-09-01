link to page 418 []{#1}

::: {#page1-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

1/543

[**swagger**](NetBox%20API.html#418)

https://netbox.satspee

**Explore**

NetBox API\
\[ Base URL: netbox.satspeed.com/api \]\
<https://netbox.satspeed.com/api/docs/?format=openapi>

API to access NetBox\
[Terms of service\
](https://github.com/digitalocean/netbox)[Contact the developer\
](mailto:netbox@digitalocean.com)Apache v2 License

**Schemes**

**HTTPS**

[**Django Login**](https://netbox.satspeed.com/login/?next=/api/docs/)

**Authorize**

Filter by tag

**circuits**

**GET**

/circuits/\_choices/

circuits\_\_choices_list

**Parameters**

**Try it out**

No parameters

**Responses**

**Response content type**

**application/json**

Code

Description

200

**GET**

/circuits/\_choices/{id}/

circuits\_\_choices_read

**Parameters**

**Try it out**

** 2.3 **
:::

[]{#2}

::: {#page2-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

2/543

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

/circuits/circuit-terminations/

circuits_circuit-terminations_list

**Parameters**

**Try it out**

Name

Description

term_side\
string\
(query)

port_speed\
number\
(query)

upstream_speed\
number\
(query)

xconnect_id\
string\
(query)

q\
string\
(query)

circuit_id\
string\
(query)

site_id\
string\
(query)

**required**
:::

[]{#3}

::: {#page3-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

3/543

Name

Description

site\
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

[]{#4}

::: {#page4-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

4/543

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

circuit\*

{\...}

term_side\*

string

title: Termination

Enum:

Array \[ 2 \]

site\*

{\...}

interface\*

{\...}

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

}\]

}

**POST**

**P**

/circuits/circuit-terminations/

circuits_circuit-terminations_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**CircuitTermination**

**Circuit**

**Site\
Interface**

**required**

Example Value
:::

[]{#5}

::: {#page5-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

5/543

Name

Description

{

id

integer

title: ID

readOnly: true

circuit\*

integer

title: Circuit

term_side\*

string

title: Termination

Enum:

Array \[ 2 \]

site\*

integer

title: Site

interface

integer

title: Interface

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

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

**WritableCircuitTermination**

Example Value
:::

[]{#6}

::: {#page6-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

6/543

Code

Description

{

id

integer

title: ID

readOnly: true

circuit\*

integer

title: Circuit

term_side\*

string

title: Termination

Enum:

Array \[ 2 \]

site\*

integer

title: Site

interface

integer

title: Interface

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

**GET**

/circuits/circuit-terminations/{id}/

circuits_circuit-terminations_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this circuit termination.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableCircuitTermination**

**required**

Example Value
:::

[]{#7}

::: {#page7-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

7/543

Code

Description

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

interface\*

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

**CircuitTermination**

**Circuit**

**Site**

**Interface**

**Device**

**Form factor**

**Lag**
:::

[]{#8}

::: {#page8-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

8/543

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

{\...}

term_side\*

string

title: Termination

Enum:

Array \[ 2 \]

port_speed\*

integer

title: Port speed

(Kbps)

maximum: 2147483647

minimum: 0

upstream_speed

integer

title: Upstream speed

(Kbps)

maximum: 2147483647

minimum: 0

Upstream speed, if

different from port

speed

xconnect_id

string

title: Cross-connect

ID

maxLength: 50

pp_info

string

title: Patch

panel/port(s)

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

Code

Description

**Circuit termination**

**Circuit**

**Mode**

**Untagged vlan**
:::

[]{#9}

::: {#page9-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

9/543

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

{\...}\]

}

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

**PUT**

/circuits/circuit-terminations/{id}/

circuits_circuit-terminations_update

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

circuit\*

integer

title: Circuit

term_side\*

string

title: Termination

Enum:

Array \[ 2 \]

site\*

integer

title: Site

interface

integer

title: Interface

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

**id \*\
**integer\
(path)

A unique integer value identifying this circuit termination.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**Untagged vlan**

**required**

Example Value

**WritableCircuitTermination**

**required**

Example Value
:::

[]{#10}

::: {#page10-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

10/543

Code

Description

{

id

integer

title: ID

readOnly: true

circuit\*

integer

title: Circuit

term_side\*

string

title: Termination

Enum:

Array \[ 2 \]

site\*

integer

title: Site

interface

integer

title: Interface

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

**PATCH**

**PA**

/circuits/circuit-terminations/{id}/

circuits_circuit-terminations_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableCircuitTermination**

**required**

Example Value
:::

[]{#11}

::: {#page11-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

11/543

Name

Description

{

id

integer

title: ID

readOnly: true

circuit\*

integer

title: Circuit

term_side\*

string

title: Termination

Enum:

Array \[ 2 \]

site\*

integer

title: Site

interface

integer

title: Interface

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

**id \*\
**integer\
(path)

A unique integer value identifying this circuit termination.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableCircuitTermination**

**required**

Example Value
:::

[]{#12}

::: {#page12-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

12/543

Code

Description

{

id

integer

title: ID

readOnly: true

circuit\*

integer

title: Circuit

term_side\*

string

title: Termination

Enum:

Array \[ 2 \]

site\*

integer

title: Site

interface

integer

title: Interface

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

**DELETE**

**DEL**

/circuits/circuit-terminations/{id}/

circuits_circuit-terminations_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this circuit termination.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/circuits/circuit-types/

circuits_circuit-types_list

**WritableCircuitTermination**

**required**
:::

[]{#13}

::: {#page13-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

13/543

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

Example Value

**CircuitType**
:::

[]{#14}

::: {#page14-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

14/543

**POST**

**P**

/circuits/circuit-types/

circuits_circuit-types_create

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

/circuits/circuit-types/{id}/

circuits_circuit-types_read

**Parameters**

**Try it out**

**required**

Example Value

**CircuitType**

Example Value

**CircuitType**
:::

[]{#15}

::: {#page15-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

15/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this circuit type.

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

/circuits/circuit-types/{id}/

circuits_circuit-types_update

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

**required**

Example Value

**CircuitType**

**required**

Example Value

**CircuitType**
:::

[]{#16}

::: {#page16-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

16/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this circuit type.

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

/circuits/circuit-types/{id}/

circuits_circuit-types_partial_update

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

**id \***

A unique integer value identifying this circuit type.

**required**

Example Value

**CircuitType**

**required**

Example Value

**CircuitType**

**required**
:::

[]{#17}

::: {#page17-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

17/543

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

}

**DELETE**

**DEL**

/circuits/circuit-types/{id}/

circuits_circuit-types_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this circuit type.

**Responses**

**Response content type**

**application/json**

Code

Description

204

Example Value

**CircuitType**

**required**
:::

[]{#18}

::: {#page18-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

18/543

**GET**

/circuits/circuits/

circuits_circuits_list

**Parameters**

**Try it out**

Name

Description

cid\
string\
(query)

install_date\
string\
(query)

commit_rate\
number\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

provider_id\
string\
(query)

provider\
string\
(query)

type_id\
string\
(query)

type\
string\
(query)

status\
string\
(query)

tenant_id\
string\
(query)

tenant\
string
:::

[]{#19}

::: {#page19-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

19/543

Name

Description

(query)

site_id\
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

[]{#20}

::: {#page20-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

20/543

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

cid\*

string

title: Circuit ID

maxLength: 50

provider\*

{\...}

type\*

{\...}

status\*

{\...}

tenant\*

{\...}

install_date

string(\$date)

title: Date installed

commit_rate

integer

title: Commit rate (Kbps)

maximum: 2147483647

minimum: 0

description

string

title: Description

maxLength: 100

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

/circuits/circuits/

circuits_circuits_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Circuit**

**Provider\
Type\
Status\
Tenant**

**Custom fields**

**required**

Example Value
:::

[]{#21}

::: {#page21-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

21/543

Name

Description

{

id

integer

title: ID

readOnly: true

cid\*

string

title: Circuit ID

maxLength: 50

provider\*

integer

title: Provider

type\*

integer

title: Type

status

integer

title: Status

Enum:

Array \[ 6 \]

tenant

integer

title: Tenant

install_date

string(\$date)

title: Date installed

commit_rate

integer

title: Commit rate (Kbps)

maximum: 2147483647

minimum: 0

description

string

title: Description

maxLength: 100

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

**Model**

**WritableCircuit**

**Custom fields**

Example Value
:::

[]{#22}

::: {#page22-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

22/543

Code

Description

{

id

integer

title: ID

readOnly: true

cid\*

string

title: Circuit ID

maxLength: 50

provider\*

integer

title: Provider

type\*

integer

title: Type

status

integer

title: Status

Enum:

Array \[ 6 \]

tenant

integer

title: Tenant

install_date

string(\$date)

title: Date installed

commit_rate

integer

title: Commit rate (Kbps)

maximum: 2147483647

minimum: 0

description

string

title: Description

maxLength: 100

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

/circuits/circuits/{id}/

circuits_circuits_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this circuit.

**Responses**

**Response content type**

**application/json**

**WritableCircuit**

**Custom fields**

**required**
:::

[]{#23}

::: {#page23-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

23/543

Code

Description

200

**Model**

Example Value
:::

[]{#24}

::: {#page24-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

24/543

Code

Description

{

id

integer

title: ID

readOnly: true

cid\*

string

title: Circuit ID

maxLength: 50

provider\*

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

type\*

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

status\*

{

value\*

integer

label\*

string

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

install_date

string(\$date)

title: Date installed

commit_rate

integer

title: Commit rate (Kbps)

maximum: 2147483647

minimum: 0

description

string

title: Description

maxLength: 100

**Circuit**

**Provider**

**Type**

**Status**

**Tenant**
:::

[]{#25}

::: {#page25-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

25/543

maxLength: 100

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

/circuits/circuits/{id}/

circuits_circuits_update

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

cid\*

string

title: Circuit ID

maxLength: 50

provider\*

integer

title: Provider

type\*

integer

title: Type

status

integer

title: Status

Enum:

Array \[ 6 \]

tenant

integer

title: Tenant

install_date

string(\$date)

title: Date installed

commit_rate

integer

title: Commit rate (Kbps)

maximum: 2147483647

minimum: 0

description

string

title: Description

maxLength: 100

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

**Custom fields**

**required**

Example Value

**WritableCircuit**

**Custom fields**
:::

[]{#26}

::: {#page26-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

26/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this circuit.

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

cid\*

string

title: Circuit ID

maxLength: 50

provider\*

integer

title: Provider

type\*

integer

title: Type

status

integer

title: Status

Enum:

Array \[ 6 \]

tenant

integer

title: Tenant

install_date

string(\$date)

title: Date installed

commit_rate

integer

title: Commit rate (Kbps)

maximum: 2147483647

minimum: 0

description

string

title: Description

maxLength: 100

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

/circuits/circuits/{id}/

circuits_circuits_partial_update

**Parameters**

**Try it out**

**required**

Example Value

**WritableCircuit**

**Custom fields**
:::

[]{#27}

::: {#page27-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

27/543

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

cid\*

string

title: Circuit ID

maxLength: 50

provider\*

integer

title: Provider

type\*

integer

title: Type

status

integer

title: Status

Enum:

Array \[ 6 \]

tenant

integer

title: Tenant

install_date

string(\$date)

title: Date installed

commit_rate

integer

title: Commit rate (Kbps)

maximum: 2147483647

minimum: 0

description

string

title: Description

maxLength: 100

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

A unique integer value identifying this circuit.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value

**WritableCircuit**

**Custom fields**

**required**

Example Value
:::

[]{#28}

::: {#page28-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

28/543

Code

Description

{

id

integer

title: ID

readOnly: true

cid\*

string

title: Circuit ID

maxLength: 50

provider\*

integer

title: Provider

type\*

integer

title: Type

status

integer

title: Status

Enum:

Array \[ 6 \]

tenant

integer

title: Tenant

install_date

string(\$date)

title: Date installed

commit_rate

integer

title: Commit rate (Kbps)

maximum: 2147483647

minimum: 0

description

string

title: Description

maxLength: 100

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

/circuits/circuits/{id}/

circuits_circuits_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this circuit.

**Responses**

**Response content type**

**application/json**

**WritableCircuit**

**Custom fields**

**required**
:::

[]{#29}

::: {#page29-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

29/543

Code

Description

204

**GET**

/circuits/providers/

circuits_providers_list

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

asn\
number\
(query)

account\
string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

site_id\
string\
(query)

site\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.
:::

[]{#30}

::: {#page30-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

30/543

Name

Description

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

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

account

string

title: Account number

maxLength: 30

portal_url

string(\$uri)

title: Portal

maxLength: 200

noc_contact

string

title: NOC contact

admin_contact

string

title: Admin contact

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

Example Value

**Provider**

**Custom fields**
:::

[]{#31}

::: {#page31-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

31/543

**POST**

**P**

/circuits/providers/

circuits_providers_create

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

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

account

string

title: Account number

maxLength: 30

portal_url

string(\$uri)

title: Portal

maxLength: 200

noc_contact

string

title: NOC contact

admin_contact

string

title: Admin contact

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

**Model**

**required**

Example Value

**WritableProvider**

**Custom fields**

Example Value
:::

[]{#32}

::: {#page32-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

32/543

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

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

account

string

title: Account number

maxLength: 30

portal_url

string(\$uri)

title: Portal

maxLength: 200

noc_contact

string

title: NOC contact

admin_contact

string

title: Admin contact

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

/circuits/providers/{id}/

circuits_providers_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this provider.

**Responses**

**Response content type**

**application/json**

**WritableProvider**

**Custom fields**

**required**
:::

[]{#33}

::: {#page33-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

33/543

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

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

account

string

title: Account number

maxLength: 30

portal_url

string(\$uri)

title: Portal

maxLength: 200

noc_contact

string

title: NOC contact

admin_contact

string

title: Admin contact

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

**PUT**

/circuits/providers/{id}/

circuits_providers_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**Provider**

**Custom fields**

**required**

Example Value
:::

[]{#34}

::: {#page34-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

34/543

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

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

account

string

title: Account number

maxLength: 30

portal_url

string(\$uri)

title: Portal

maxLength: 200

noc_contact

string

title: NOC contact

admin_contact

string

title: Admin contact

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

A unique integer value identifying this provider.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableProvider**

**Custom fields**

**required**

Example Value
:::

[]{#35}

::: {#page35-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

35/543

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

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

account

string

title: Account number

maxLength: 30

portal_url

string(\$uri)

title: Portal

maxLength: 200

noc_contact

string

title: NOC contact

admin_contact

string

title: Admin contact

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

/circuits/providers/{id}/

circuits_providers_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableProvider**

**Custom fields**

**required**

Example Value
:::

[]{#36}

::: {#page36-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

36/543

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

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

account

string

title: Account number

maxLength: 30

portal_url

string(\$uri)

title: Portal

maxLength: 200

noc_contact

string

title: NOC contact

admin_contact

string

title: Admin contact

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

A unique integer value identifying this provider.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableProvider**

**Custom fields**

**required**

Example Value
:::

[]{#37}

::: {#page37-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

37/543

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

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

account

string

title: Account number

maxLength: 30

portal_url

string(\$uri)

title: Portal

maxLength: 200

noc_contact

string

title: NOC contact

admin_contact

string

title: Admin contact

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

/circuits/providers/{id}/

circuits_providers_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this provider.

**Responses**

**Response content type**

**application/json**

**WritableProvider**

**Custom fields**

**required**
:::

[]{#38}

::: {#page38-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

38/543

Code

Description

204

**GET**

/circuits/providers/{id}/graphs/

circuits_providers_graphs

A convenience method for rendering graphs for a particular provider.

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this provider.

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

[]{#39}

::: {#page39-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

39/543

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

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

account

string

title: Account number

maxLength: 30

portal_url

string(\$uri)

title: Portal

maxLength: 200

noc_contact

string

title: NOC contact

admin_contact

string

title: Admin contact

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

**extras**

**GET**

/extras/\_choices/

extras\_\_choices_list

**Parameters**

**Try it out**

No parameters

**Responses**

**Response content type**

**application/json**

**WritableVirtualChassis**

**required**
:::

[]{#256}

::: {#page256-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

256/543

Code

Description

200

**GET**

/extras/\_choices/{id}/

extras\_\_choices_read

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

/extras/export-templates/

extras_export-templates_list

**Parameters**

**Try it out**

Name

Description

content_type\
string\
(query)

name\
string\
(query)

limit\
integer\
(query)

Number of results to return per page.

**required**
:::

[]{#257}

::: {#page257-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

257/543

Name

Description

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

content_type\*

integer

title: Content type

name\*

string

title: Name

maxLength: 100

description

string

title: Description

maxLength: 200

template_code\*

string

title: Template code

mime_type

string

title: Mime type

maxLength: 15

file_extension

string

title: File extension

maxLength: 15

}\]

}

**POST**

**P**

/extras/export-templates/

extras_export-templates_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**ExportTemplate**

**required**

Example Value
:::

[]{#258}

::: {#page258-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

258/543

Name

Description

{

id

integer

title: ID

readOnly: true

content_type\*

integer

title: Content type

name\*

string

title: Name

maxLength: 100

description

string

title: Description

maxLength: 200

template_code\*

string

title: Template code

mime_type

string

title: Mime type

maxLength: 15

file_extension

string

title: File extension

maxLength: 15

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

content_type\*

integer

title: Content type

name\*

string

title: Name

maxLength: 100

description

string

title: Description

maxLength: 200

template_code\*

string

title: Template code

mime_type

string

title: Mime type

maxLength: 15

file_extension

string

title: File extension

maxLength: 15

}

**GET**

/extras/export-templates/{id}/

extras_export-templates_read

**ExportTemplate**

Example Value

**ExportTemplate**
:::

[]{#259}

::: {#page259-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

259/543

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this export template.

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

content_type\*

integer

title: Content type

name\*

string

title: Name

maxLength: 100

description

string

title: Description

maxLength: 200

template_code\*

string

title: Template code

mime_type

string

title: Mime type

maxLength: 15

file_extension

string

title: File extension

maxLength: 15

}

**PUT**

/extras/export-templates/{id}/

extras_export-templates_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**required**

Example Value

**ExportTemplate**

**required**

Example Value
:::

[]{#260}

::: {#page260-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

260/543

Name

Description

{

id

integer

title: ID

readOnly: true

content_type\*

integer

title: Content type

name\*

string

title: Name

maxLength: 100

description

string

title: Description

maxLength: 200

template_code\*

string

title: Template code

mime_type

string

title: Mime type

maxLength: 15

file_extension

string

title: File extension

maxLength: 15

}

**id \*\
**integer\
(path)

A unique integer value identifying this export template.

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

content_type\*

integer

title: Content type

name\*

string

title: Name

maxLength: 100

description

string

title: Description

maxLength: 200

template_code\*

string

title: Template code

mime_type

string

title: Mime type

maxLength: 15

file_extension

string

title: File extension

maxLength: 15

}

**ExportTemplate**

**required**

Example Value

**ExportTemplate**
:::

[]{#261}

::: {#page261-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

261/543

**PATCH**

**PA**

/extras/export-templates/{id}/

extras_export-templates_partial_update

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

content_type\*

integer

title: Content type

name\*

string

title: Name

maxLength: 100

description

string

title: Description

maxLength: 200

template_code\*

string

title: Template code

mime_type

string

title: Mime type

maxLength: 15

file_extension

string

title: File extension

maxLength: 15

}

**id \*\
**integer\
(path)

A unique integer value identifying this export template.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value

**ExportTemplate**

**required**

Example Value
:::

[]{#262}

::: {#page262-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

262/543

Code

Description

{

id

integer

title: ID

readOnly: true

content_type\*

integer

title: Content type

name\*

string

title: Name

maxLength: 100

description

string

title: Description

maxLength: 200

template_code\*

string

title: Template code

mime_type

string

title: Mime type

maxLength: 15

file_extension

string

title: File extension

maxLength: 15

}

**DELETE**

**DEL**

/extras/export-templates/{id}/

extras_export-templates_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this export template.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/extras/graphs/

extras_graphs_list

**Parameters**

**Try it out**

Name

Description

type

**ExportTemplate**

**required**
:::

[]{#263}

::: {#page263-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

263/543

Name

Description

string\
(query)

name\
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

type\*

{\...}

weight

integer

title: Weight

maximum: 32767

minimum: 0

name\*

string

title: Name

maxLength: 100

source\*

string

title: Source URL

maxLength: 500

link

string(\$uri)

title: Link URL

maxLength: 200

}\]

}

Example Value

**Graph**

**Type**
:::

[]{#264}

::: {#page264-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

264/543

**POST**

**P**

/extras/graphs/

extras_graphs_create

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

type\*

integer

title: Type

Enum:

Array \[ 3 \]

weight

integer

title: Weight

maximum: 32767

minimum: 0

name\*

string

title: Name

maxLength: 100

source\*

string

title: Source URL

maxLength: 500

link

string(\$uri)

title: Link URL

maxLength: 200

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

**WritableGraph**

Example Value
:::

[]{#265}

::: {#page265-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

265/543

Code

Description

{

id

integer

title: ID

readOnly: true

type\*

integer

title: Type

Enum:

Array \[ 3 \]

weight

integer

title: Weight

maximum: 32767

minimum: 0

name\*

string

title: Name

maxLength: 100

source\*

string

title: Source URL

maxLength: 500

link

string(\$uri)

title: Link URL

maxLength: 200

}

**GET**

/extras/graphs/{id}/

extras_graphs_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this graph.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableGraph**

**required**

Example Value
:::

[]{#266}

::: {#page266-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

266/543

Code

Description

{

id

integer

title: ID

readOnly: true

type\*

{

value\*

integer

label\*

string

}

weight

integer

title: Weight

maximum: 32767

minimum: 0

name\*

string

title: Name

maxLength: 100

source\*

string

title: Source URL

maxLength: 500

link

string(\$uri)

title: Link URL

maxLength: 200

}

**PUT**

/extras/graphs/{id}/

extras_graphs_update

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

type\*

integer

title: Type

Enum:

Array \[ 3 \]

weight

integer

title: Weight

maximum: 32767

minimum: 0

name\*

string

title: Name

maxLength: 100

source\*

string

title: Source URL

maxLength: 500

link

string(\$uri)

title: Link URL

maxLength: 200

}

**id \***

A unique integer value identifying this graph.

**Graph**

**Type**

**required**

Example Value

**WritableGraph**

**required**
:::

[]{#267}

::: {#page267-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

267/543

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

type\*

integer

title: Type

Enum:

Array \[ 3 \]

weight

integer

title: Weight

maximum: 32767

minimum: 0

name\*

string

title: Name

maxLength: 100

source\*

string

title: Source URL

maxLength: 500

link

string(\$uri)

title: Link URL

maxLength: 200

}

**PATCH**

**PA**

/extras/graphs/{id}/

extras_graphs_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**WritableGraph**

**required**

Example Value
:::

[]{#268}

::: {#page268-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

268/543

Name

Description

{

id

integer

title: ID

readOnly: true

type\*

integer

title: Type

Enum:

Array \[ 3 \]

weight

integer

title: Weight

maximum: 32767

minimum: 0

name\*

string

title: Name

maxLength: 100

source\*

string

title: Source URL

maxLength: 500

link

string(\$uri)

title: Link URL

maxLength: 200

}

**id \*\
**integer\
(path)

A unique integer value identifying this graph.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableGraph**

**required**

Example Value
:::

[]{#269}

::: {#page269-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

269/543

Code

Description

{

id

integer

title: ID

readOnly: true

type\*

integer

title: Type

Enum:

Array \[ 3 \]

weight

integer

title: Weight

maximum: 32767

minimum: 0

name\*

string

title: Name

maxLength: 100

source\*

string

title: Source URL

maxLength: 500

link

string(\$uri)

title: Link URL

maxLength: 200

}

**DELETE**

**DEL**

/extras/graphs/{id}/

extras_graphs_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this graph.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/extras/image-attachments/

extras_image-attachments_list

**Parameters**

**Try it out**

**WritableGraph**

**required**
:::

[]{#270}

::: {#page270-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

270/543

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

parent

string

title: Parent

readOnly: true

name

string

title: Name

maxLength: 50

image\*

string(\$uri)

title: Image

readOnly: true

image_height\*

integer

title: Image height

maximum: 32767

minimum: 0

image_width\*

integer

title: Image width

maximum: 32767

minimum: 0

created

string(\$date-time)

title: Created

readOnly: true

}\]

}

**POST**

**P**

/extras/image-attachments/

extras_image-attachments_create

Example Value

**ImageAttachment**
:::

[]{#271}

::: {#page271-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

271/543

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

content_type\*

string

title: Content type

object_id\*

integer

title: Object id

maximum: 2147483647

minimum: 0

name

string

title: Name

maxLength: 50

image\*

string(\$uri)

title: Image

readOnly: true

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

content_type\*

string

title: Content type

object_id\*

integer

title: Object id

maximum: 2147483647

minimum: 0

name

string

title: Name

maxLength: 50

image\*

string(\$uri)

title: Image

readOnly: true

}

**GET**

/extras/image-attachments/{id}/

extras_image-attachments_read

**required**

Example Value

**WritableImageAttachment**

Example Value

**WritableImageAttachment**
:::

[]{#272}

::: {#page272-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

272/543

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this image attachment.

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

parent

string

title: Parent

readOnly: true

name

string

title: Name

maxLength: 50

image\*

string(\$uri)

title: Image

readOnly: true

image_height\*

integer

title: Image height

maximum: 32767

minimum: 0

image_width\*

integer

title: Image width

maximum: 32767

minimum: 0

created

string(\$date-time)

title: Created

readOnly: true

}

**PUT**

/extras/image-attachments/{id}/

extras_image-attachments_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**required**

Example Value

**ImageAttachment**

**required**

Example Value
:::

[]{#273}

::: {#page273-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

273/543

Name

Description

{

id

integer

title: ID

readOnly: true

content_type\*

string

title: Content type

object_id\*

integer

title: Object id

maximum: 2147483647

minimum: 0

name

string

title: Name

maxLength: 50

image\*

string(\$uri)

title: Image

readOnly: true

}

**id \*\
**integer\
(path)

A unique integer value identifying this image attachment.

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

content_type\*

string

title: Content type

object_id\*

integer

title: Object id

maximum: 2147483647

minimum: 0

name

string

title: Name

maxLength: 50

image\*

string(\$uri)

title: Image

readOnly: true

}

**PATCH**

**PA**

/extras/image-attachments/{id}/

extras_image-attachments_partial_update

**Parameters**

**Try it out**

**WritableImageAttachment**

**required**

Example Value

**WritableImageAttachment**
:::

[]{#274}

::: {#page274-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

274/543

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

content_type\*

string

title: Content type

object_id\*

integer

title: Object id

maximum: 2147483647

minimum: 0

name

string

title: Name

maxLength: 50

image\*

string(\$uri)

title: Image

readOnly: true

}

**id \*\
**integer\
(path)

A unique integer value identifying this image attachment.

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

content_type\*

string

title: Content type

object_id\*

integer

title: Object id

maximum: 2147483647

minimum: 0

name

string

title: Name

maxLength: 50

image\*

string(\$uri)

title: Image

readOnly: true

}

**required**

Example Value

**WritableImageAttachment**

**required**

Example Value

**WritableImageAttachment**
:::

[]{#275}

::: {#page275-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

275/543

**DELETE**

**DEL**

/extras/image-attachments/{id}/

extras_image-attachments_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this image attachment.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/extras/recent-activity/

extras_recent-activity_list

List all UserActions to provide a log of recent activity.

**Parameters**

**Try it out**

Name

Description

user\
string\
(query)

username\
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

[]{#276}

::: {#page276-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

276/543

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

time

string(\$date-time)

title: Time

readOnly: true

user\*

{\...}

action\*

{\...}

message

string

title: Message

}\]

}

**GET**

/extras/recent-activity/{id}/

extras_recent-activity_read

List all UserActions to provide a log of recent activity.

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this user action.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**UserAction**

**User\
Action**

**required**

Example Value
:::

[]{#277}

::: {#page277-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

277/543

Code

Description

{

id

integer

title: ID

readOnly: true

time

string(\$date-time)

title: Time

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

action\*

{

value\*

integer

label\*

string

}

message

string

title: Message

}

**GET**

/extras/topology-maps/

extras_topology-maps_list

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

site_id\
string\
(query)

site\
string\
(query)

limit\
integer

Number of results to return per page.

**UserAction**

**User**

**Action**
:::

[]{#278}

::: {#page278-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

278/543

Name

Description

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

device_patterns\*

string

title: Device patterns

Identify devices to include in the diagram

using regular expressions, one per line. Each

line will result in a new tier of the

drawing. Separate multiple regexes within a

line using semicolons. Devices will be

rendered in the order they are defined.

description

string

title: Description

maxLength: 100

}\]

}

**POST**

**P**

/extras/topology-maps/

extras_topology-maps_create

**Parameters**

**Try it out**

Example Value

**TopologyMap**

**Site**
:::

[]{#279}

::: {#page279-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

279/543

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

site

integer

title: Site

device_patterns\*

string

title: Device patterns

Identify devices to include in the diagram using regular

expressions, one per line. Each line will result in a new tier of

the drawing. Separate multiple regexes within a line using

semicolons. Devices will be rendered in the order they are defined.

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

**WritableTopologyMap**

Example Value
:::

[]{#280}

::: {#page280-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

280/543

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

site

integer

title: Site

device_patterns\*

string

title: Device patterns

Identify devices to include in the diagram using regular expressions,

one per line. Each line will result in a new tier of the drawing.

Separate multiple regexes within a line using semicolons. Devices

will be rendered in the order they are defined.

description

string

title: Description

maxLength: 100

}

**GET**

/extras/topology-maps/{id}/

extras_topology-maps_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this topology map.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableTopologyMap**

**required**

Example Value
:::

[]{#281}

::: {#page281-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

281/543

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

device_patterns\*

string

title: Device patterns

Identify devices to include in the diagram using regular expressions,

one per line. Each line will result in a new tier of the drawing.

Separate multiple regexes within a line using semicolons. Devices

will be rendered in the order they are defined.

description

string

title: Description

maxLength: 100

}

**PUT**

/extras/topology-maps/{id}/

extras_topology-maps_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**TopologyMap**

**Site**

**required**

Example Value
:::

[]{#282}

::: {#page282-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

282/543

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

site

integer

title: Site

device_patterns\*

string

title: Device patterns

Identify devices to include in the diagram using regular

expressions, one per line. Each line will result in a new tier of

the drawing. Separate multiple regexes within a line using

semicolons. Devices will be rendered in the order they are defined.

description

string

title: Description

maxLength: 100

}

**id \*\
**integer\
(path)

A unique integer value identifying this topology map.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableTopologyMap**

**required**

Example Value
:::

[]{#283}

::: {#page283-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

283/543

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

site

integer

title: Site

device_patterns\*

string

title: Device patterns

Identify devices to include in the diagram using regular expressions,

one per line. Each line will result in a new tier of the drawing.

Separate multiple regexes within a line using semicolons. Devices

will be rendered in the order they are defined.

description

string

title: Description

maxLength: 100

}

**PATCH**

**PA**

/extras/topology-maps/{id}/

extras_topology-maps_partial_update

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

site

integer

title: Site

device_patterns\*

string

title: Device patterns

Identify devices to include in the diagram using regular

expressions, one per line. Each line will result in a new tier of

the drawing. Separate multiple regexes within a line using

semicolons. Devices will be rendered in the order they are defined.

description

string

title: Description

maxLength: 100

}

**WritableTopologyMap**

**required**

Example Value

**WritableTopologyMap**
:::

[]{#284}

::: {#page284-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

284/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this topology map.

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

site

integer

title: Site

device_patterns\*

string

title: Device patterns

Identify devices to include in the diagram using regular expressions,

one per line. Each line will result in a new tier of the drawing.

Separate multiple regexes within a line using semicolons. Devices

will be rendered in the order they are defined.

description

string

title: Description

maxLength: 100

}

**DELETE**

**DEL**

/extras/topology-maps/{id}/

extras_topology-maps_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this topology map.

**required**

Example Value

**WritableTopologyMap**

**required**
:::

[]{#285}

::: {#page285-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

285/543

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/extras/topology-maps/{id}/render/

extras_topology-maps_render

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this topology map.

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

[]{#286}

::: {#page286-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

286/543

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

device_patterns\*

string

title: Device patterns

Identify devices to include in the diagram using regular expressions,

one per line. Each line will result in a new tier of the drawing.

Separate multiple regexes within a line using semicolons. Devices

will be rendered in the order they are defined.

description

string

title: Description

maxLength: 100

}

**ipam**

**GET**

/ipam/\_choices/

ipam\_\_choices_list

**Parameters**

**Try it out**

No parameters

**Responses**

**Response content type**

**application/json**

Code

Description

200

**TopologyMap**

**Site**
:::

[]{#287}

::: {#page287-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

287/543

**GET**

/ipam/\_choices/{id}/

ipam\_\_choices_read

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

/ipam/aggregates/

ipam_aggregates_list

**Parameters**

**Try it out**

Name

Description

family\
string\
(query)

date_added\
string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

rir_id\
string\
(query)

rir\
string

**required**
:::

[]{#288}

::: {#page288-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

288/543

Name

Description

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

family\*

integer

title: Family

Enum:

Array \[ 2 \]

prefix\*

string

title: Prefix

rir\*

{\...}

date_added

string(\$date)

title: Date added

description

string

title: Description

maxLength: 100

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

/ipam/aggregates/

ipam_aggregates_create

Example Value

**Aggregate**

**Rir**

**Custom fields**
:::

[]{#289}

::: {#page289-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

289/543

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

prefix\*

string

title: Prefix

rir\*

integer

title: RIR

date_added

string(\$date)

title: Date added

description

string

title: Description

maxLength: 100

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

**Model**

**required**

Example Value

**WritableAggregate**

**Custom fields**

Example Value
:::

[]{#290}

::: {#page290-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

290/543

Code

Description

{

id

integer

title: ID

readOnly: true

prefix\*

string

title: Prefix

rir\*

integer

title: RIR

date_added

string(\$date)

title: Date added

description

string

title: Description

maxLength: 100

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

/ipam/aggregates/{id}/

ipam_aggregates_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this aggregate.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableAggregate**

**Custom fields**

**required**

Example Value
:::

[]{#291}

::: {#page291-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

291/543

Code

Description

{

id

integer

title: ID

readOnly: true

family\*

integer

title: Family

Enum:

Array \[ 2 \]

prefix\*

string

title: Prefix

rir\*

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

date_added

string(\$date)

title: Date added

description

string

title: Description

maxLength: 100

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

**PUT**

/ipam/aggregates/{id}/

ipam_aggregates_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Aggregate**

**Rir**

**Custom fields**

**required**

Example Value
:::

[]{#292}

::: {#page292-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

292/543

Name

Description

{

id

integer

title: ID

readOnly: true

prefix\*

string

title: Prefix

rir\*

integer

title: RIR

date_added

string(\$date)

title: Date added

description

string

title: Description

maxLength: 100

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

A unique integer value identifying this aggregate.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableAggregate**

**Custom fields**

**required**

Example Value
:::

[]{#293}

::: {#page293-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

293/543

Code

Description

{

id

integer

title: ID

readOnly: true

prefix\*

string

title: Prefix

rir\*

integer

title: RIR

date_added

string(\$date)

title: Date added

description

string

title: Description

maxLength: 100

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

/ipam/aggregates/{id}/

ipam_aggregates_partial_update

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

prefix\*

string

title: Prefix

rir\*

integer

title: RIR

date_added

string(\$date)

title: Date added

description

string

title: Description

maxLength: 100

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

**WritableAggregate**

**Custom fields**

**required**

Example Value

**WritableAggregate**

**Custom fields**
:::

[]{#294}

::: {#page294-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

294/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this aggregate.

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

prefix\*

string

title: Prefix

rir\*

integer

title: RIR

date_added

string(\$date)

title: Date added

description

string

title: Description

maxLength: 100

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

/ipam/aggregates/{id}/

ipam_aggregates_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this aggregate.

**required**

Example Value

**WritableAggregate**

**Custom fields**

**required**
:::

[]{#295}

::: {#page295-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

295/543

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/ipam/ip-addresses/

ipam_ip-addresses_list

**Parameters**

**Try it out**

Name

Description

family\
string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

parent\
string\
(query)

address\
string\
(query)

mask_length\
number\
(query)

vrf_id\
string\
(query)

vrf\
string\
(query)

tenant_id\
string\
(query)

tenant
:::

[]{#296}

::: {#page296-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

296/543

Name

Description

string\
(query)

device\
string\
(query)

device_id\
number\
(query)

virtual_machine_id\
string\
(query)

virtual_machine\
string\
(query)

interface_id\
string\
(query)

status\
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

[]{#297}

::: {#page297-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

297/543

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

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

vrf\*

{\...}

tenant\*

{\...}

status\*

{\...}

role\*

{\...}

interface\*

{\...}

description

string

title: Description

maxLength: 100

nat_inside\*

{\...}

nat_outside\*

{\...}

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

/ipam/ip-addresses/

ipam_ip-addresses_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**IPAddress**

**Vrf\
Tenant\
Status\
Role\
Interface**

**Nat inside\
Nat inside\
Custom fields**

**required**

Example Value
:::

[]{#298}

::: {#page298-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

298/543

Name

Description

{

id

integer

title: ID

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

vrf

integer

title: VRF

tenant

integer

title: Tenant

status

integer

title: Status

The operational status of this IP

Enum:

Array \[ 4 \]

role

integer

title: Role

The functional role of this IP

Enum:

Array \[ 8 \]

interface

integer

title: Interface

description

string

title: Description

maxLength: 100

nat_inside

integer

title: NAT (Inside)

The IP for which this address is the "outside" IP

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

**Model**

**WritableIPAddress**

**Custom fields**

Example Value
:::

[]{#299}

::: {#page299-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

299/543

Code

Description

{

id

integer

title: ID

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

vrf

integer

title: VRF

tenant

integer

title: Tenant

status

integer

title: Status

The operational status of this IP

Enum:

Array \[ 4 \]

role

integer

title: Role

The functional role of this IP

Enum:

Array \[ 8 \]

interface

integer

title: Interface

description

string

title: Description

maxLength: 100

nat_inside

integer

title: NAT (Inside)

The IP for which this address is the "outside" IP

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

/ipam/ip-addresses/{id}/

ipam_ip-addresses_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this IP address.

**Responses**

**Response content type**

**application/json**

**WritableIPAddress**

**Custom fields**

**required**
:::

[]{#300}

::: {#page300-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

300/543

Code

Description

200

**Model**

Example Value
:::

[]{#301}

::: {#page301-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

301/543

Code

Description

{

id

integer

title: ID

readOnly: true

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

vrf\*

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

rd\*

string

title: Route distinguisher

maxLength: 21

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

status\*

{

value\*

integer

label\*

string

}

role\*

{

value\*

integer

label\*

string

}

interface\*

{

id

integer

title: ID

readOnly: true

url

string

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

**IPAddress**

**Vrf**

**Tenant**

**Status**

**Role**

**Interface**

**Device**
:::

[]{#302}

::: {#page302-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

302/543

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

virtual_machine\*

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

name\*

string

title: Name

maxLength: 64

}

description

string

title: Description

maxLength: 100

nat_inside\*

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

nat_outside\*

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

**Virtual machine**

**Nat inside**

**Nat inside**

**Custom fields**
:::

[]{#303}

::: {#page303-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

303/543

**PUT**

/ipam/ip-addresses/{id}/

ipam_ip-addresses_update

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

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

vrf

integer

title: VRF

tenant

integer

title: Tenant

status

integer

title: Status

The operational status of this IP

Enum:

Array \[ 4 \]

role

integer

title: Role

The functional role of this IP

Enum:

Array \[ 8 \]

interface

integer

title: Interface

description

string

title: Description

maxLength: 100

nat_inside

integer

title: NAT (Inside)

The IP for which this address is the "outside" IP

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

A unique integer value identifying this IP address.

**Responses**

**Response content type**

**application/json**

**required**

Example Value

**WritableIPAddress**

**Custom fields**

**required**
:::

[]{#304}

::: {#page304-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

304/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

vrf

integer

title: VRF

tenant

integer

title: Tenant

status

integer

title: Status

The operational status of this IP

Enum:

Array \[ 4 \]

role

integer

title: Role

The functional role of this IP

Enum:

Array \[ 8 \]

interface

integer

title: Interface

description

string

title: Description

maxLength: 100

nat_inside

integer

title: NAT (Inside)

The IP for which this address is the "outside" IP

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

/ipam/ip-addresses/{id}/

ipam_ip-addresses_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**WritableIPAddress**

**Custom fields**

**required**

Example Value
:::

[]{#305}

::: {#page305-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

305/543

Name

Description

{

id

integer

title: ID

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

vrf

integer

title: VRF

tenant

integer

title: Tenant

status

integer

title: Status

The operational status of this IP

Enum:

Array \[ 4 \]

role

integer

title: Role

The functional role of this IP

Enum:

Array \[ 8 \]

interface

integer

title: Interface

description

string

title: Description

maxLength: 100

nat_inside

integer

title: NAT (Inside)

The IP for which this address is the "outside" IP

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

A unique integer value identifying this IP address.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableIPAddress**

**Custom fields**

**required**

Example Value
:::

[]{#306}

::: {#page306-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

306/543

Code

Description

{

id

integer

title: ID

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

vrf

integer

title: VRF

tenant

integer

title: Tenant

status

integer

title: Status

The operational status of this IP

Enum:

Array \[ 4 \]

role

integer

title: Role

The functional role of this IP

Enum:

Array \[ 8 \]

interface

integer

title: Interface

description

string

title: Description

maxLength: 100

nat_inside

integer

title: NAT (Inside)

The IP for which this address is the "outside" IP

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

/ipam/ip-addresses/{id}/

ipam_ip-addresses_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this IP address.

**Responses**

**Response content type**

**application/json**

**WritableIPAddress**

**Custom fields**

**required**
:::

[]{#307}

::: {#page307-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

307/543

Code

Description

204

**GET**

/ipam/prefixes/

ipam_prefixes_list

**Parameters**

**Try it out**

Name

Description

family\
string\
(query)

is_pool\
string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

within\
string\
(query)

within_include\
string\
(query)

contains\
string\
(query)

mask_length\
number\
(query)

vrf_id\
string\
(query)

vrf\
string\
(query)
:::

[]{#308}

::: {#page308-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

308/543

Name

Description

tenant_id\
string\
(query)

tenant\
string\
(query)

site_id\
string\
(query)

site\
string\
(query)

vlan_id\
string\
(query)

vlan_vid\
number\
(query)

role_id\
string\
(query)

role\
string\
(query)

status\
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

[]{#309}

::: {#page309-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

309/543

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

family

integer

title: Family

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

site\*

{\...}

vrf\*

{\...}

tenant\*

{\...}

vlan\*

{\...}

status\*

{\...}

role\*

{\...}

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are

considered usable

description

string

title: Description

maxLength: 100

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

/ipam/prefixes/

ipam_prefixes_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**Prefix**

**Site\
Vrf\
Tenant\
Vlan\
Status\
Role**

**Custom fields**

**required**

Example Value
:::

[]{#310}

::: {#page310-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

310/543

Name

Description

{

id

integer

title: ID

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

site

integer

title: Site

vrf

integer

title: VRF

tenant

integer

title: Tenant

vlan

integer

title: VLAN

status

integer

title: Status

Operational status of this prefix

Enum:

Array \[ 4 \]

role

integer

title: Role

The primary function of this prefix

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

**Model**

**WritablePrefix**

**Custom fields**

Example Value
:::

[]{#311}

::: {#page311-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

311/543

Code

Description

{

id

integer

title: ID

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

site

integer

title: Site

vrf

integer

title: VRF

tenant

integer

title: Tenant

vlan

integer

title: VLAN

status

integer

title: Status

Operational status of this prefix

Enum:

Array \[ 4 \]

role

integer

title: Role

The primary function of this prefix

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

/ipam/prefixes/{id}/

ipam_prefixes_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this pre x.

**Responses**

**Response content type**

**application/json**

**WritablePrefix**

**Custom fields**

**required**
:::

[]{#312}

::: {#page312-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

312/543

Code

Description

200

**Model**

Example Value
:::

[]{#313}

::: {#page313-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

313/543

Code

Description

{

id

integer

title: ID

readOnly: true

family

integer

title: Family

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

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

vrf\*

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

rd\*

string

title: Route distinguisher

maxLength: 21

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

vlan\*

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

**Prefix**

**Site**

**Vrf**

**Tenant**

**Vlan**
:::

[]{#314}

::: {#page314-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

314/543

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

status\*

{

value\*

integer

label\*

string

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

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

/ipam/prefixes/{id}/

ipam_prefixes_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Status**

**Role**

**Custom fields**

**required**

Example Value
:::

[]{#315}

::: {#page315-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

315/543

Name

Description

{

id

integer

title: ID

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

site

integer

title: Site

vrf

integer

title: VRF

tenant

integer

title: Tenant

vlan

integer

title: VLAN

status

integer

title: Status

Operational status of this prefix

Enum:

Array \[ 4 \]

role

integer

title: Role

The primary function of this prefix

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

A unique integer value identifying this pre x.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritablePrefix**

**Custom fields**

**required**

Example Value
:::

[]{#316}

::: {#page316-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

316/543

Code

Description

{

id

integer

title: ID

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

site

integer

title: Site

vrf

integer

title: VRF

tenant

integer

title: Tenant

vlan

integer

title: VLAN

status

integer

title: Status

Operational status of this prefix

Enum:

Array \[ 4 \]

role

integer

title: Role

The primary function of this prefix

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

/ipam/prefixes/{id}/

ipam_prefixes_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritablePrefix**

**Custom fields**

**required**

Example Value
:::

[]{#317}

::: {#page317-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

317/543

Name

Description

{

id

integer

title: ID

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

site

integer

title: Site

vrf

integer

title: VRF

tenant

integer

title: Tenant

vlan

integer

title: VLAN

status

integer

title: Status

Operational status of this prefix

Enum:

Array \[ 4 \]

role

integer

title: Role

The primary function of this prefix

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

A unique integer value identifying this pre x.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritablePrefix**

**Custom fields**

**required**

Example Value
:::

[]{#318}

::: {#page318-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

318/543

Code

Description

{

id

integer

title: ID

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

site

integer

title: Site

vrf

integer

title: VRF

tenant

integer

title: Tenant

vlan

integer

title: VLAN

status

integer

title: Status

Operational status of this prefix

Enum:

Array \[ 4 \]

role

integer

title: Role

The primary function of this prefix

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

/ipam/prefixes/{id}/

ipam_prefixes_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this pre x.

**Responses**

**Response content type**

**application/json**

**WritablePrefix**

**Custom fields**

**required**
:::

[]{#319}

::: {#page319-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

319/543

Code

Description

204

**GET**

/ipam/prefixes/{id}/available-ips/

ipam_prefixes_available-ips_read

A convenience method for returning available IP addresses within a pre x. By default, the number of IPs\
returned will be equivalent to PAGINATE_COUNT. An arbitrary limit (up to MAX_PAGE_SIZE, if set) may be passed,\
however results will not be paginated.

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this pre x.

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

[]{#320}

::: {#page320-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

320/543

Code

Description

{

id

integer

title: ID

readOnly: true

family

integer

title: Family

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

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

vrf\*

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

rd\*

string

title: Route distinguisher

maxLength: 21

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

vlan\*

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

**Prefix**

**Site**

**Vrf**

**Tenant**

**Vlan**
:::

[]{#321}

::: {#page321-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

321/543

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

status\*

{

value\*

integer

label\*

string

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

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

**POST**

**P**

/ipam/prefixes/{id}/available-ips/

ipam_prefixes_available-ips_create

A convenience method for returning available IP addresses within a pre x. By default, the number of IPs\
returned will be equivalent to PAGINATE_COUNT. An arbitrary limit (up to MAX_PAGE_SIZE, if set) may be passed,\
however results will not be paginated.

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Status**

**Role**

**Custom fields**

**required**

Example Value
:::

[]{#322}

::: {#page322-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

322/543

Name

Description

{

id

integer

title: ID

readOnly: true

family

integer

title: Family

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

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

vrf\*

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

rd\*

string

title: Route distinguisher

maxLength: 21

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

vlan\*

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

**Prefix**

**Site**

**Vrf**

**Tenant**

**Vlan**
:::

[]{#323}

::: {#page323-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

323/543

g

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

status\*

{

value\*

integer

label\*

string

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

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

**id \*\
**integer\
(path)

A unique integer value identifying this pre x.

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

**Status**

**Role**

**Custom fields**

**required**

Example Value
:::

[]{#324}

::: {#page324-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

324/543

Code

Description

{

id

integer

title: ID

readOnly: true

family

integer

title: Family

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

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

vrf\*

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

rd\*

string

title: Route distinguisher

maxLength: 21

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

vlan\*

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

**Prefix**

**Site**

**Vrf**

**Tenant**

**Vlan**
:::

[]{#325}

::: {#page325-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

325/543

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

status\*

{

value\*

integer

label\*

string

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

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

/ipam/prefixes/{id}/available-prefixes/

ipam_prefixes_available-prefixes_read

A convenience method for returning available child pre xes within a parent.

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this pre x.

**Status**

**Role**

**Custom fields**

**required**
:::

[]{#326}

::: {#page326-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

326/543

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#327}

::: {#page327-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

327/543

Code

Description

{

id

integer

title: ID

readOnly: true

family

integer

title: Family

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

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

vrf\*

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

rd\*

string

title: Route distinguisher

maxLength: 21

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

vlan\*

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

**Prefix**

**Site**

**Vrf**

**Tenant**

**Vlan**
:::

[]{#328}

::: {#page328-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

328/543

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

status\*

{

value\*

integer

label\*

string

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

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

**POST**

**P**

/ipam/prefixes/{id}/available-prefixes/

ipam_prefixes_available-prefixes_create

A convenience method for returning available child pre xes within a parent.

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Status**

**Role**

**Custom fields**

**required**

Example Value
:::

[]{#329}

::: {#page329-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

329/543

Name

Description

{

id

integer

title: ID

readOnly: true

family

integer

title: Family

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

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

vrf\*

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

rd\*

string

title: Route distinguisher

maxLength: 21

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

vlan\*

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

**Prefix**

**Site**

**Vrf**

**Tenant**

**Vlan**
:::

[]{#330}

::: {#page330-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

330/543

g

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

status\*

{

value\*

integer

label\*

string

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

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

**id \*\
**integer\
(path)

A unique integer value identifying this pre x.

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

**Status**

**Role**

**Custom fields**

**required**

Example Value
:::

[]{#331}

::: {#page331-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

331/543

Code

Description

{

id

integer

title: ID

readOnly: true

family

integer

title: Family

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

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

vrf\*

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

rd\*

string

title: Route distinguisher

maxLength: 21

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

vlan\*

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

**Prefix**

**Site**

**Vrf**

**Tenant**

**Vlan**
:::

[]{#332}

::: {#page332-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

332/543

name

string

title: Name

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

status\*

{

value\*

integer

label\*

string

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

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

/ipam/rirs/

ipam_rirs_list

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

is_private

**Status**

**Role**

**Custom fields**
:::

[]{#333}

::: {#page333-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

333/543

Name

Description

string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

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

is_private

boolean

title: Private

IP space managed by this RIR is considered

private

}\]

}

**POST**

**P**

/ipam/rirs/

ipam_rirs_create

**Parameters**

**Try it out**

Example Value

**RIR**
:::

[]{#334}

::: {#page334-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

334/543

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

is_private

boolean

title: Private

IP space managed by this RIR is considered private

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

is_private

boolean

title: Private

IP space managed by this RIR is considered private

}

**GET**

/ipam/rirs/{id}/

ipam_rirs_read

**Parameters**

**Try it out**

**required**

Example Value

**RIR**

Example Value

**RIR**
:::

[]{#335}

::: {#page335-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

335/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this RIR.

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

is_private

boolean

title: Private

IP space managed by this RIR is considered private

}

**PUT**

/ipam/rirs/{id}/

ipam_rirs_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**required**

Example Value

**RIR**

**required**

Example Value
:::

[]{#336}

::: {#page336-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

336/543

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

is_private

boolean

title: Private

IP space managed by this RIR is considered private

}

**id \*\
**integer\
(path)

A unique integer value identifying this RIR.

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

is_private

boolean

title: Private

IP space managed by this RIR is considered private

}

**PATCH**

**PA**

/ipam/rirs/{id}/

ipam_rirs_partial_update

**Parameters**

**Try it out**

**RIR**

**required**

Example Value

**RIR**
:::

[]{#337}

::: {#page337-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

337/543

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

is_private

boolean

title: Private

IP space managed by this RIR is considered private

}

**id \*\
**integer\
(path)

A unique integer value identifying this RIR.

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

is_private

boolean

title: Private

IP space managed by this RIR is considered private

}

**DELETE**

**DEL**

/ipam/rirs/{id}/

ipam_rirs_delete

**Parameters**

**Try it out**

**required**

Example Value

**RIR**

**required**

Example Value

**RIR**
:::

[]{#338}

::: {#page338-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

338/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this RIR.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/ipam/roles/

ipam_roles_list

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

**required**

Example Value
:::

[]{#339}

::: {#page339-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

339/543

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

weight

integer

title: Weight

maximum: 32767

minimum: 0

}\]

}

**POST**

**P**

/ipam/roles/

ipam_roles_create

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

weight

integer

title: Weight

maximum: 32767

minimum: 0

}

**Responses**

**Response content type**

**application/json**

**Role**

**required**

Example Value

**Role**
:::

[]{#340}

::: {#page340-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

340/543

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

weight

integer

title: Weight

maximum: 32767

minimum: 0

}

**GET**

/ipam/roles/{id}/

ipam_roles_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this role.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**Role**

**required**

Example Value
:::

[]{#341}

::: {#page341-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

341/543

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

weight

integer

title: Weight

maximum: 32767

minimum: 0

}

**PUT**

/ipam/roles/{id}/

ipam_roles_update

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

weight

integer

title: Weight

maximum: 32767

minimum: 0

}

**id \*\
**integer\
(path)

A unique integer value identifying this role.

**Responses**

**Response content type**

**application/json**

**Role**

**required**

Example Value

**Role**

**required**
:::

[]{#342}

::: {#page342-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

342/543

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

weight

integer

title: Weight

maximum: 32767

minimum: 0

}

**PATCH**

**PA**

/ipam/roles/{id}/

ipam_roles_partial_update

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

weight

integer

title: Weight

maximum: 32767

minimum: 0

}

**id \*\
**integer\
(path)

A unique integer value identifying this role.

Example Value

**Role**

**required**

Example Value

**Role**

**required**
:::

[]{#343}

::: {#page343-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

343/543

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

weight

integer

title: Weight

maximum: 32767

minimum: 0

}

**DELETE**

**DEL**

/ipam/roles/{id}/

ipam_roles_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this role.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/ipam/services/

ipam_services_list

**Parameters**

**Try it out**

Example Value

**Role**

**required**
:::

[]{#344}

::: {#page344-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

344/543

Name

Description

name\
string\
(query)

protocol\
string\
(query)

port\
number\
(query)

device_id\
string\
(query)

device\
string\
(query)

virtual_machine_id\
string\
(query)

virtual_machine\
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

[]{#345}

::: {#page345-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

345/543

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

virtual_machine\*

{\...}

name\*

string

title: Name

maxLength: 30

port\*

integer

title: Port number

maximum: 65535

minimum: 1

protocol\*

{\...}

ipaddresses\*

\[\...\]

description

string

title: Description

maxLength: 100

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

/ipam/services/

ipam_services_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Service**

**Device\
Virtual machine**

**Protocol**

**required**

Example Value
:::

[]{#346}

::: {#page346-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

346/543

Name

Description

{

id

integer

title: ID

readOnly: true

device

integer

title: Device

virtual_machine

integer

title: Virtual machine

name\*

string

title: Name

maxLength: 30

port\*

integer

title: Port number

maximum: 65535

minimum: 1

protocol\*

integer

title: Protocol

Enum:

Array \[ 2 \]

ipaddresses

\[

uniqueItems: true

integer

title: IP addresses\]

description

string

title: Description

maxLength: 100

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

**Model**

**WritableService**

Example Value
:::

[]{#347}

::: {#page347-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

347/543

Code

Description

{

id

integer

title: ID

readOnly: true

device

integer

title: Device

virtual_machine

integer

title: Virtual machine

name\*

string

title: Name

maxLength: 30

port\*

integer

title: Port number

maximum: 65535

minimum: 1

protocol\*

integer

title: Protocol

Enum:

Array \[ 2 \]

ipaddresses

\[

uniqueItems: true

integer

title: IP addresses\]

description

string

title: Description

maxLength: 100

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

/ipam/services/{id}/

ipam_services_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this service.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableService**

**required**

Example Value
:::

[]{#348}

::: {#page348-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

348/543

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

virtual_machine\*

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

name\*

string

title: Name

maxLength: 30

port\*

integer

title: Port number

maximum: 65535

minimum: 1

protocol\*

{

value\*

integer

label\*

string

}

ipaddresses\*

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

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

}\]

description

string

title: Description

maxLength: 100

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

**Service**

**Device**

**Virtual machine**

**Protocol**

**Nat inside**
:::

[]{#349}

::: {#page349-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

349/543

}

Code

Description

**PUT**

/ipam/services/{id}/

ipam_services_update

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

device

integer

title: Device

virtual_machine

integer

title: Virtual machine

name\*

string

title: Name

maxLength: 30

port\*

integer

title: Port number

maximum: 65535

minimum: 1

protocol\*

integer

title: Protocol

Enum:

Array \[ 2 \]

ipaddresses

\[

uniqueItems: true

integer

title: IP addresses\]

description

string

title: Description

maxLength: 100

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

A unique integer value identifying this service.

**Responses**

**Response content type**

**application/json**

**required**

Example Value

**WritableService**

**required**
:::

[]{#350}

::: {#page350-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

350/543

Code

Description

200

**Model**

{

id

integer

title: ID

readOnly: true

device

integer

title: Device

virtual_machine

integer

title: Virtual machine

name\*

string

title: Name

maxLength: 30

port\*

integer

title: Port number

maximum: 65535

minimum: 1

protocol\*

integer

title: Protocol

Enum:

Array \[ 2 \]

ipaddresses

\[

uniqueItems: true

integer

title: IP addresses\]

description

string

title: Description

maxLength: 100

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

/ipam/services/{id}/

ipam_services_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**WritableService**

**required**

Example Value
:::

[]{#351}

::: {#page351-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

351/543

Name

Description

{

id

integer

title: ID

readOnly: true

device

integer

title: Device

virtual_machine

integer

title: Virtual machine

name\*

string

title: Name

maxLength: 30

port\*

integer

title: Port number

maximum: 65535

minimum: 1

protocol\*

integer

title: Protocol

Enum:

Array \[ 2 \]

ipaddresses

\[

uniqueItems: true

integer

title: IP addresses\]

description

string

title: Description

maxLength: 100

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

A unique integer value identifying this service.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableService**

**required**

Example Value
:::

[]{#352}

::: {#page352-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

352/543

Code

Description

{

id

integer

title: ID

readOnly: true

device

integer

title: Device

virtual_machine

integer

title: Virtual machine

name\*

string

title: Name

maxLength: 30

port\*

integer

title: Port number

maximum: 65535

minimum: 1

protocol\*

integer

title: Protocol

Enum:

Array \[ 2 \]

ipaddresses

\[

uniqueItems: true

integer

title: IP addresses\]

description

string

title: Description

maxLength: 100

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

/ipam/services/{id}/

ipam_services_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this service.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**WritableService**

**required**
:::

[]{#353}

::: {#page353-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

353/543

**GET**

/ipam/vlan-groups/

ipam_vlan-groups_list

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

site_id\
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

[]{#354}

::: {#page354-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

354/543

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

site\*

{\...}

}\]

}

**POST**

**P**

/ipam/vlan-groups/

ipam_vlan-groups_create

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

site

integer

title: Site

}

**Responses**

**Response content type**

**application/json**

**VLANGroup**

**Site**

**required**

Example Value

**WritableVLANGroup**
:::

[]{#355}

::: {#page355-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

355/543

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

site

integer

title: Site

}

**GET**

/ipam/vlan-groups/{id}/

ipam_vlan-groups_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this VLAN group.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value

**WritableVLANGroup**

**required**

Example Value
:::

[]{#356}

::: {#page356-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

356/543

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

/ipam/vlan-groups/{id}/

ipam_vlan-groups_update

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

site

integer

title: Site

}

**VLANGroup**

**Site**

**required**

Example Value

**WritableVLANGroup**
:::

[]{#357}

::: {#page357-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

357/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this VLAN group.

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

site

integer

title: Site

}

**PATCH**

**PA**

/ipam/vlan-groups/{id}/

ipam_vlan-groups_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**required**

Example Value

**WritableVLANGroup**

**required**

Example Value
:::

[]{#358}

::: {#page358-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

358/543

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

site

integer

title: Site

}

**id \*\
**integer\
(path)

A unique integer value identifying this VLAN group.

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

site

integer

title: Site

}

**DELETE**

**DEL**

/ipam/vlan-groups/{id}/

ipam_vlan-groups_delete

**Parameters**

**Try it out**

Name

Description

**id \***

A unique integer value identifying this VLAN group.

**WritableVLANGroup**

**required**

Example Value

**WritableVLANGroup**

**required**
:::

[]{#359}

::: {#page359-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

359/543

Name

Description

integer\
(path)

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/ipam/vlans/

ipam_vlans_list

**Parameters**

**Try it out**

Name

Description

vid\
number\
(query)

name\
string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
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

group
:::

[]{#360}

::: {#page360-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

360/543

Name

Description

string\
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

status\
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

[]{#361}

::: {#page361-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

361/543

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

site\*

{\...}

group\*

{\...}

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

tenant\*

{\...}

status\*

{\...}

role\*

{\...}

description

string

title: Description

maxLength: 100

display_name

string

title: Display name

readOnly: true

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

/ipam/vlans/

ipam_vlans_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**VLAN**

**Site\
Group**

**Tenant\
Status\
Role**

**Custom fields**

**required**

Example Value
:::

[]{#362}

::: {#page362-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

362/543

Name

Description

{

id

integer

title: ID

readOnly: true

site

integer

title: Site

group

integer

title: Group

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

tenant

integer

title: Tenant

status

integer

title: Status

Enum:

Array \[ 3 \]

role

integer

title: Role

description

string

title: Description

maxLength: 100

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

**Model**

**WritableVLAN**

**Custom fields**

Example Value
:::

[]{#363}

::: {#page363-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

363/543

Code

Description

{

id

integer

title: ID

readOnly: true

site

integer

title: Site

group

integer

title: Group

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

tenant

integer

title: Tenant

status

integer

title: Status

Enum:

Array \[ 3 \]

role

integer

title: Role

description

string

title: Description

maxLength: 100

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

/ipam/vlans/{id}/

ipam_vlans_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this VLAN.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**WritableVLAN**

**Custom fields**

**required**
:::

[]{#364}

::: {#page364-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

364/543

Code

Description

**Model**

Example Value
:::

[]{#365}

::: {#page365-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

365/543

Code

Description

{

id

integer

title: ID

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

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

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

status\*

{

value\*

integer

label\*

string

}

role\*

{

id

integer

title: ID

readOnly: true

**VLAN**

**Site**

**Group**

**Tenant**

**Status**

**Role**
:::

[]{#366}

::: {#page366-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

366/543

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

description

string

title: Description

maxLength: 100

display_name

string

title: Display name

readOnly: true

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

/ipam/vlans/{id}/

ipam_vlans_update

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

[]{#367}

::: {#page367-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

367/543

Name

Description

{

id

integer

title: ID

readOnly: true

site

integer

title: Site

group

integer

title: Group

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

tenant

integer

title: Tenant

status

integer

title: Status

Enum:

Array \[ 3 \]

role

integer

title: Role

description

string

title: Description

maxLength: 100

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

A unique integer value identifying this VLAN.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableVLAN**

**Custom fields**

**required**

Example Value
:::

[]{#368}

::: {#page368-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

368/543

Code

Description

{

id

integer

title: ID

readOnly: true

site

integer

title: Site

group

integer

title: Group

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

tenant

integer

title: Tenant

status

integer

title: Status

Enum:

Array \[ 3 \]

role

integer

title: Role

description

string

title: Description

maxLength: 100

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

/ipam/vlans/{id}/

ipam_vlans_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableVLAN**

**Custom fields**

**required**

Example Value
:::

[]{#369}

::: {#page369-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

369/543

Name

Description

{

id

integer

title: ID

readOnly: true

site

integer

title: Site

group

integer

title: Group

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

tenant

integer

title: Tenant

status

integer

title: Status

Enum:

Array \[ 3 \]

role

integer

title: Role

description

string

title: Description

maxLength: 100

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

A unique integer value identifying this VLAN.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableVLAN**

**Custom fields**

**required**

Example Value
:::

[]{#370}

::: {#page370-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

370/543

Code

Description

{

id

integer

title: ID

readOnly: true

site

integer

title: Site

group

integer

title: Group

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

tenant

integer

title: Tenant

status

integer

title: Status

Enum:

Array \[ 3 \]

role

integer

title: Role

description

string

title: Description

maxLength: 100

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

/ipam/vlans/{id}/

ipam_vlans_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this VLAN.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**WritableVLAN**

**Custom fields**

**required**
:::

[]{#371}

::: {#page371-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

371/543

Code

Description

**GET**

/ipam/vrfs/

ipam_vrfs_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

rd\
string\
(query)

enforce_unique\
string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
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
:::

[]{#372}

::: {#page372-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

372/543

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

rd\*

string

title: Route distinguisher

maxLength: 21

tenant\*

{\...}

enforce_unique

boolean

title: Enforce unique space

Prevent duplicate prefixes/IP addresses

within this VRF

description

string

title: Description

maxLength: 100

display_name

string

title: Display name

readOnly: true

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

/ipam/vrfs/

ipam_vrfs_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**VRF**

**Tenant**

**Custom fields**

**required**

Example Value
:::

[]{#373}

::: {#page373-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

373/543

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

rd\*

string

title: Route distinguisher

maxLength: 21

tenant

integer

title: Tenant

enforce_unique

boolean

title: Enforce unique space

Prevent duplicate prefixes/IP addresses within this VRF

description

string

title: Description

maxLength: 100

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

**Model**

**WritableVRF**

**Custom fields**

Example Value
:::

[]{#374}

::: {#page374-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

374/543

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

rd\*

string

title: Route distinguisher

maxLength: 21

tenant

integer

title: Tenant

enforce_unique

boolean

title: Enforce unique space

Prevent duplicate prefixes/IP addresses within this VRF

description

string

title: Description

maxLength: 100

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

/ipam/vrfs/{id}/

ipam_vrfs_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this VRF.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableVRF**

**Custom fields**

**required**

Example Value
:::

[]{#375}

::: {#page375-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

375/543

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

rd\*

string

title: Route distinguisher

maxLength: 21

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

enforce_unique

boolean

title: Enforce unique space

Prevent duplicate prefixes/IP addresses within this VRF

description

string

title: Description

maxLength: 100

display_name

string

title: Display name

readOnly: true

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

**PUT**

/ipam/vrfs/{id}/

ipam_vrfs_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**VRF**

**Tenant**

**Custom fields**

**required**

Example Value
:::

[]{#376}

::: {#page376-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

376/543

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

rd\*

string

title: Route distinguisher

maxLength: 21

tenant

integer

title: Tenant

enforce_unique

boolean

title: Enforce unique space

Prevent duplicate prefixes/IP addresses within this VRF

description

string

title: Description

maxLength: 100

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

A unique integer value identifying this VRF.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableVRF**

**Custom fields**

**required**

Example Value
:::

[]{#377}

::: {#page377-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

377/543

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

rd\*

string

title: Route distinguisher

maxLength: 21

tenant

integer

title: Tenant

enforce_unique

boolean

title: Enforce unique space

Prevent duplicate prefixes/IP addresses within this VRF

description

string

title: Description

maxLength: 100

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

/ipam/vrfs/{id}/

ipam_vrfs_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableVRF**

**Custom fields**

**required**

Example Value
:::

[]{#378}

::: {#page378-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

378/543

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

rd\*

string

title: Route distinguisher

maxLength: 21

tenant

integer

title: Tenant

enforce_unique

boolean

title: Enforce unique space

Prevent duplicate prefixes/IP addresses within this VRF

description

string

title: Description

maxLength: 100

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

A unique integer value identifying this VRF.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableVRF**

**Custom fields**

**required**

Example Value
:::

[]{#379}

::: {#page379-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

379/543

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

rd\*

string

title: Route distinguisher

maxLength: 21

tenant

integer

title: Tenant

enforce_unique

boolean

title: Enforce unique space

Prevent duplicate prefixes/IP addresses within this VRF

description

string

title: Description

maxLength: 100

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

/ipam/vrfs/{id}/

ipam_vrfs_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this VRF.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**secrets**

**WritableVRF**

**Custom fields**

**required**
:::

[]{#380}

::: {#page380-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

380/543

**GET**

/secrets/\_choices/

secrets\_\_choices_list

**Parameters**

**Try it out**

No parameters

**Responses**

**Response content type**

**application/json**

Code

Description

200

**GET**

/secrets/\_choices/{id}/

secrets\_\_choices_read

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

/secrets/generate-rsa-key-pair/

secrets_generate-rsa-key-pair_list

This endpoint can be used to generate a new RSA key pair. The keys are returned in PEM format.

**{\
    \"public_key\": \"\<public key\>\",\
    \"private_key\": \"\<private key\>\"\
}**

**Parameters**

**Try it out**

**required**
:::

[]{#381}

::: {#page381-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

381/543

No parameters

**Responses**

**Response content type**

**application/json**

Code

Description

200

**POST**

**P**

/secrets/get-session-key/

secrets_get-session-key_create

Retrieve a temporary session key to use for encrypting and decrypting secrets via the API. The user's private RSA\
key is POSTed with the name private_key. An example:

**curl -v -X POST -H \"Authorization: Token \<token\>\" -H \"Accept: application/json; indent=4\" \\\
\--data-urlencode \"private_key@\<filename\>\" https://netbox/api/secrets/get-session-key/**

This request will yield a base64-encoded session key to be included in an X-Session-Key header in future requests:

**{\
    \"session_key\": \"+8t4SI6XikgVmB5+/urhozx9O5qCQANyOk1MNe6taRf=\"\
}**

This endpoint accepts one optional parameter: preserve_key. If True and a session key exists, the existing session\
key will be returned instead of a new one.

**Parameters**

**Try it out**

No parameters

**Responses**

**Response content type**

**application/json**

Code

Description

201

**GET**

/secrets/secret-roles/

secrets_secret-roles_list

**Parameters**

**Try it out**

Name

Description

name\
string
:::

[]{#382}

::: {#page382-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

382/543

Name

Description

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

/secrets/secret-roles/

secrets_secret-roles_create

**Parameters**

**Try it out**

Example Value

**SecretRole**
:::

[]{#383}

::: {#page383-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

383/543

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

/secrets/secret-roles/{id}/

secrets_secret-roles_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this secret role.

**required**

Example Value

**SecretRole**

Example Value

**SecretRole**

**required**
:::

[]{#384}

::: {#page384-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

384/543

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

/secrets/secret-roles/{id}/

secrets_secret-roles_update

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

A unique integer value identifying this secret role.

**Responses**

**Response content type**

**application/json**

Example Value

**SecretRole**

**required**

Example Value

**SecretRole**

**required**
:::

[]{#385}

::: {#page385-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

385/543

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

/secrets/secret-roles/{id}/

secrets_secret-roles_partial_update

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

A unique integer value identifying this secret role.

**Responses**

**Response content type**

**application/json**

Example Value

**SecretRole**

**required**

Example Value

**SecretRole**

**required**
:::

[]{#386}

::: {#page386-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

386/543

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

/secrets/secret-roles/{id}/

secrets_secret-roles_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this secret role.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/secrets/secrets/

secrets_secrets_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

Example Value

**SecretRole**

**required**
:::

[]{#387}

::: {#page387-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

387/543

Name

Description

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

role_id\
string\
(query)

role\
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

[]{#388}

::: {#page388-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

388/543

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

role\*

{\...}

name\*

string

title: Name

maxLength: 100

plaintext

string

title: Plaintext

readOnly: true

hash

string

title: Hash

readOnly: true

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

/secrets/secrets/

secrets_secrets_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Secret**

**Device\
Role**

**required**

Example Value
:::

[]{#389}

::: {#page389-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

389/543

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

role\*

integer

title: Role

name

string

title: Name

maxLength: 100

plaintext\*

string

title: Plaintext

hash

string

title: Hash

readOnly: true

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

**Model**

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

role\*

integer

title: Role

name

string

title: Name

maxLength: 100

plaintext\*

string

title: Plaintext

hash

string

title: Hash

readOnly: true

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**WritableSecret**

Example Value

**WritableSecret**
:::

[]{#390}

::: {#page390-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

390/543

**GET**

/secrets/secrets/{id}/

secrets_secrets_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this secret.

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

[]{#391}

::: {#page391-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

391/543

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

title: Name

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

maxLength: 100

plaintext

string

title: Plaintext

readOnly: true

hash

string

title: Hash

readOnly: true

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**PUT**

/secrets/secrets/{id}/

secrets_secrets_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Secret**

**Device**

**Role**

**required**

Example Value
:::

[]{#392}

::: {#page392-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

392/543

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

role\*

integer

title: Role

name

string

title: Name

maxLength: 100

plaintext\*

string

title: Plaintext

hash

string

title: Hash

readOnly: true

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

A unique integer value identifying this secret.

**Responses**

**Response content type**

**application/json**

**WritableSecret**

**required**
:::

[]{#393}

::: {#page393-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

393/543

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

role\*

integer

title: Role

name

string

title: Name

maxLength: 100

plaintext\*

string

title: Plaintext

hash

string

title: Hash

readOnly: true

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

/secrets/secrets/{id}/

secrets_secrets_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**WritableSecret**

**required**

Example Value
:::

[]{#394}

::: {#page394-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

394/543

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

role\*

integer

title: Role

name

string

title: Name

maxLength: 100

plaintext\*

string

title: Plaintext

hash

string

title: Hash

readOnly: true

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

A unique integer value identifying this secret.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableSecret**

**required**

Example Value
:::

[]{#395}

::: {#page395-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

395/543

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

role\*

integer

title: Role

name

string

title: Name

maxLength: 100

plaintext\*

string

title: Plaintext

hash

string

title: Hash

readOnly: true

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

/secrets/secrets/{id}/

secrets_secrets_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this secret.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**tenancy**

**GET**

/tenancy/\_choices/

tenancy\_\_choices_list

**Parameters**

**Try it out**

**WritableSecret**

**required**
:::

[]{#396}

::: {#page396-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

396/543

No parameters

**Responses**

**Response content type**

**application/json**

Code

Description

200

**GET**

/tenancy/\_choices/{id}/

tenancy\_\_choices_read

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

/tenancy/tenant-groups/

tenancy_tenant-groups_list

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

limit

Number of results to return per page.

**required**
:::

[]{#397}

::: {#page397-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

397/543

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

/tenancy/tenant-groups/

tenancy_tenant-groups_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

Example Value

**TenantGroup**

**required**

Example Value
:::

[]{#398}

::: {#page398-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

398/543

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

/tenancy/tenant-groups/{id}/

tenancy_tenant-groups_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this tenant group.

**Responses**

**Response content type**

**application/json**

**TenantGroup**

Example Value

**TenantGroup**

**required**
:::

[]{#399}

::: {#page399-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

399/543

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

/tenancy/tenant-groups/{id}/

tenancy_tenant-groups_update

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

A unique integer value identifying this tenant group.

**Responses**

**Response content type**

**application/json**

Example Value

**TenantGroup**

**required**

Example Value

**TenantGroup**

**required**
:::

[]{#400}

::: {#page400-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

400/543

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

/tenancy/tenant-groups/{id}/

tenancy_tenant-groups_partial_update

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

A unique integer value identifying this tenant group.

**Responses**

**Response content type**

**application/json**

Example Value

**TenantGroup**

**required**

Example Value

**TenantGroup**

**required**
:::

[]{#401}

::: {#page401-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

401/543

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

/tenancy/tenant-groups/{id}/

tenancy_tenant-groups_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this tenant group.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/tenancy/tenants/

tenancy_tenants_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

Example Value

**TenantGroup**

**required**
:::

[]{#402}

::: {#page402-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

402/543

Name

Description

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

group_id\
string\
(query)

group\
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

[]{#403}

::: {#page403-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

403/543

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

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

group\*

{\...}

description

string

title: Description

maxLength: 100

Long-form name (optional)

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

/tenancy/tenants/

tenancy_tenants_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Tenant**

**Group**

**Custom fields**

**required**

Example Value
:::

[]{#404}

::: {#page404-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

404/543

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

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

group

integer

title: Group

description

string

title: Description

maxLength: 100

Long-form name (optional)

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

**Model**

**WritableTenant**

**Custom fields**

Example Value
:::

[]{#405}

::: {#page405-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

405/543

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

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

group

integer

title: Group

description

string

title: Description

maxLength: 100

Long-form name (optional)

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

/tenancy/tenants/{id}/

tenancy_tenants_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this tenant.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableTenant**

**Custom fields**

**required**

Example Value
:::

[]{#406}

::: {#page406-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

406/543

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

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

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

description

string

title: Description

maxLength: 100

Long-form name (optional)

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

**PUT**

/tenancy/tenants/{id}/

tenancy_tenants_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Tenant**

**Group**

**Custom fields**

**required**

Example Value
:::

[]{#407}

::: {#page407-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

407/543

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

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

group

integer

title: Group

description

string

title: Description

maxLength: 100

Long-form name (optional)

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

A unique integer value identifying this tenant.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableTenant**

**Custom fields**

**required**

Example Value
:::

[]{#408}

::: {#page408-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

408/543

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

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

group

integer

title: Group

description

string

title: Description

maxLength: 100

Long-form name (optional)

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

/tenancy/tenants/{id}/

tenancy_tenants_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableTenant**

**Custom fields**

**required**

Example Value
:::

[]{#409}

::: {#page409-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

409/543

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

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

group

integer

title: Group

description

string

title: Description

maxLength: 100

Long-form name (optional)

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

A unique integer value identifying this tenant.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableTenant**

**Custom fields**

**required**

Example Value
:::

[]{#410}

::: {#page410-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

410/543

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

maxLength: 30

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

group

integer

title: Group

description

string

title: Description

maxLength: 100

Long-form name (optional)

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

/tenancy/tenants/{id}/

tenancy_tenants_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this tenant.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**virtualization**

**WritableTenant**

**Custom fields**

**required**
:::

[]{#411}

::: {#page411-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

411/543

**GET**

/virtualization/\_choices/

virtualization\_\_choices_list

**Parameters**

**Try it out**

No parameters

**Responses**

**Response content type**

**application/json**

Code

Description

200

**GET**

/virtualization/\_choices/{id}/

virtualization\_\_choices_read

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

/virtualization/cluster-groups/

virtualization_cluster-groups_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

**required**
:::

[]{#412}

::: {#page412-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

412/543

Name

Description

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

/virtualization/cluster-groups/

virtualization_cluster-groups_create

**Parameters**

**Try it out**

Name

Description

**data \***

Example Value

**ClusterGroup**

**required**
:::

[]{#413}

::: {#page413-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

413/543

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

/virtualization/cluster-groups/{id}/

virtualization_cluster-groups_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this cluster group.

Example Value

**ClusterGroup**

Example Value

**ClusterGroup**

**required**
:::

[]{#414}

::: {#page414-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

414/543

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

/virtualization/cluster-groups/{id}/

virtualization_cluster-groups_update

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

A unique integer value identifying this cluster group.

**Responses**

**Response content type**

**application/json**

Example Value

**ClusterGroup**

**required**

Example Value

**ClusterGroup**

**required**
:::

[]{#415}

::: {#page415-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

415/543

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

/virtualization/cluster-groups/{id}/

virtualization_cluster-groups_partial_update

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

A unique integer value identifying this cluster group.

**Responses**

**Response content type**

**application/json**

Example Value

**ClusterGroup**

**required**

Example Value

**ClusterGroup**

**required**
:::

[]{#416}

::: {#page416-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

416/543

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

/virtualization/cluster-groups/{id}/

virtualization_cluster-groups_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this cluster group.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/virtualization/cluster-types/

virtualization_cluster-types_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

Example Value

**ClusterGroup**

**required**
:::

[]{#417}

::: {#page417-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

417/543

Name

Description

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

/virtualization/cluster-types/

virtualization_cluster-types_create

**Parameters**

**Try it out**

Name

Description

**data \***

Example Value

**ClusterType**

**required**
:::

[]{#418}

::: {#page418-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

418/543

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

/virtualization/cluster-types/{id}/

virtualization_cluster-types_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this cluster type.

Example Value

**ClusterType**

Example Value

**ClusterType**

**required**
:::

[]{#419}

::: {#page419-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

419/543

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

/virtualization/cluster-types/{id}/

virtualization_cluster-types_update

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

A unique integer value identifying this cluster type.

**Responses**

**Response content type**

**application/json**

Example Value

**ClusterType**

**required**

Example Value

**ClusterType**

**required**
:::

[]{#420}

::: {#page420-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

420/543

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

/virtualization/cluster-types/{id}/

virtualization_cluster-types_partial_update

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

A unique integer value identifying this cluster type.

**Responses**

**Response content type**

**application/json**

Example Value

**ClusterType**

**required**

Example Value

**ClusterType**

**required**
:::

[]{#421}

::: {#page421-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

421/543

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

/virtualization/cluster-types/{id}/

virtualization_cluster-types_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this cluster type.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/virtualization/clusters/

virtualization_clusters_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

Example Value

**ClusterType**

**required**
:::

[]{#422}

::: {#page422-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

422/543

Name

Description

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

group_id\
string\
(query)

group\
string\
(query)

type_id\
string\
(query)

type\
string\
(query)

site_id\
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

[]{#423}

::: {#page423-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

423/543

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

maxLength: 100

type\*

{\...}

group\*

{\...}

site\*

{\...}

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

/virtualization/clusters/

virtualization_clusters_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**Cluster**

**Type\
Group\
Site**

**Custom fields**

**required**

Example Value
:::

[]{#424}

::: {#page424-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

424/543

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

maxLength: 100

type\*

integer

title: Type

group

integer

title: Group

site

integer

title: Site

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

**Model**

**WritableCluster**

**Custom fields**

Example Value
:::

[]{#425}

::: {#page425-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

425/543

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

maxLength: 100

type\*

integer

title: Type

group

integer

title: Group

site

integer

title: Site

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

/virtualization/clusters/{id}/

virtualization_clusters_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this cluster.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableCluster**

**Custom fields**

**required**

Example Value
:::

[]{#426}

::: {#page426-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

426/543

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

maxLength: 100

type\*

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

**Cluster**

**Type**

**Group**

**Site**

**Custom fields**
:::

[]{#427}

::: {#page427-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

427/543

Code

Description

**PUT**

/virtualization/clusters/{id}/

virtualization_clusters_update

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

maxLength: 100

type\*

integer

title: Type

group

integer

title: Group

site

integer

title: Site

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

A unique integer value identifying this cluster.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**required**

Example Value

**WritableCluster**

**Custom fields**

**required**

Example Value
:::

[]{#428}

::: {#page428-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

428/543

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

maxLength: 100

type\*

integer

title: Type

group

integer

title: Group

site

integer

title: Site

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

/virtualization/clusters/{id}/

virtualization_clusters_partial_update

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableCluster**

**Custom fields**

**required**

Example Value
:::

[]{#429}

::: {#page429-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

429/543

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

maxLength: 100

type\*

integer

title: Type

group

integer

title: Group

site

integer

title: Site

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

A unique integer value identifying this cluster.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

**WritableCluster**

**Custom fields**

**required**

Example Value
:::

[]{#430}

::: {#page430-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

430/543

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

maxLength: 100

type\*

integer

title: Type

group

integer

title: Group

site

integer

title: Site

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

/virtualization/clusters/{id}/

virtualization_clusters_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this cluster.

**Responses**

**Response content type**

**application/json**

Code

Description

204

**GET**

/virtualization/interfaces/

virtualization_interfaces_list

**Parameters**

**Try it out**

**WritableCluster**

**Custom fields**

**required**
:::

[]{#431}

::: {#page431-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

431/543

Name

Description

name\
string\
(query)

enabled\
string\
(query)

mtu\
number\
(query)

virtual_machine_id\
string\
(query)

virtual_machine\
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

[]{#432}

::: {#page432-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

432/543

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

/virtualization/interfaces/

virtualization_interfaces_create

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

[]{#433}

::: {#page433-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

433/543

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

[]{#434}

::: {#page434-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

434/543

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

/virtualization/interfaces/{id}/

virtualization_interfaces_read

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

[]{#435}

::: {#page435-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

435/543

Code

Description

200

**Model**

Example Value
:::

[]{#436}

::: {#page436-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

436/543

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

[]{#437}

::: {#page437-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

437/543

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

[]{#438}

::: {#page438-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

438/543

}

**PUT**

/virtualization/interfaces/{id}/

virtualization_interfaces_update

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

[]{#439}

::: {#page439-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

439/543

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

/virtualization/interfaces/{id}/

virtualization_interfaces_partial_update

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

[]{#440}

::: {#page440-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

440/543

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

[]{#441}

::: {#page441-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

441/543

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

/virtualization/interfaces/{id}/

virtualization_interfaces_delete

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

[]{#442}

::: {#page442-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

442/543

Code

Description

204

**GET**

/virtualization/virtual-machines/

virtualization_virtual-machines_list

**Parameters**

**Try it out**

Name

Description

name\
string\
(query)

cluster\
string\
(query)

id\_\_in\
string\
(query)

Multiple values may be separated by commas.

q\
string\
(query)

status\
string\
(query)

cluster_group_id\
string\
(query)

cluster_group\
string\
(query)

cluster_type_id\
string\
(query)

cluster_type\
string\
(query)

cluster_id\
string\
(query)
:::

[]{#443}

::: {#page443-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

443/543

Name

Description

site_id\
string\
(query)

site\
string\
(query)

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

[]{#444}

::: {#page444-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

444/543

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

maxLength: 64

status\*

{\...}

cluster\*

{\...}

role\*

{\...}

tenant\*

{\...}

platform\*

{\...}

primary_ip\*

{\...}

primary_ip4\*

{\...}

primary_ip6\*

{\...}

vcpus

integer

title: VCPUs

maximum: 32767

minimum: 0

memory

integer

title: Memory (MB)

maximum: 2147483647

minimum: 0

disk

integer

title: Disk (GB)

maximum: 2147483647

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

title: Last updated

readOnly: true

}\]

}

**POST**

**P**

/virtualization/virtual-machines/

virtualization_virtual-machines_create

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**VirtualMachine**

**Status\
Cluster\
Device role\
Tenant\
Platform\
Primary ip\
Primary ip\
Primary ip**

**Custom fields**

**required**

Example Value
:::

[]{#445}

::: {#page445-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

445/543

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

maxLength: 64

status

integer

title: Status

Enum:

Array \[ 3 \]

cluster\*

integer

title: Cluster

role

integer

title: Role

tenant

integer

title: Tenant

platform

integer

title: Platform

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

vcpus

integer

title: VCPUs

maximum: 32767

minimum: 0

memory

integer

title: Memory (MB)

maximum: 2147483647

minimum: 0

disk

integer

title: Disk (GB)

maximum: 2147483647

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

**Responses**

**Response content type**

**application/json**

Code

Description

201

**Model**

**WritableVirtualMachine**

**Custom fields**

Example Value
:::

[]{#446}

::: {#page446-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

446/543

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

maxLength: 64

status

integer

title: Status

Enum:

Array \[ 3 \]

cluster\*

integer

title: Cluster

role

integer

title: Role

tenant

integer

title: Tenant

platform

integer

title: Platform

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

vcpus

integer

title: VCPUs

maximum: 32767

minimum: 0

memory

integer

title: Memory (MB)

maximum: 2147483647

minimum: 0

disk

integer

title: Disk (GB)

maximum: 2147483647

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

**GET**

/virtualization/virtual-machines/{id}/

virtualization_virtual-machines_read

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this virtual machine.

**WritableVirtualMachine**

**Custom fields**

**required**
:::

[]{#447}

::: {#page447-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

447/543

**Responses**

**Response content type**

**application/json**

Code

Description

200

**Model**

Example Value
:::

[]{#448}

::: {#page448-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

448/543

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

maxLength: 64

status\*

{

value\*

integer

label\*

string

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

**VirtualMachine**

**Status**

**Cluster**

**Device role**

**Tenant**

**Platform**
:::

[]{#449}

::: {#page449-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

449/543

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

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

vcpus

integer

title: VCPUs

maximum: 32767

minimum: 0

memory

integer

title: Memory (MB)

maximum: 2147483647

minimum: 0

disk

integer

title: Disk (GB)

maximum: 2147483647

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

Code

Description

**Primary ip**

**Primary ip**

**Primary ip**

**Custom fields**
:::

[]{#450}

::: {#page450-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

450/543

title: Last updated

readOnly: true

}

**PUT**

/virtualization/virtual-machines/{id}/

virtualization_virtual-machines_update

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

maxLength: 64

status

integer

title: Status

Enum:

Array \[ 3 \]

cluster\*

integer

title: Cluster

role

integer

title: Role

tenant

integer

title: Tenant

platform

integer

title: Platform

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

vcpus

integer

title: VCPUs

maximum: 32767

minimum: 0

memory

integer

title: Memory (MB)

maximum: 2147483647

minimum: 0

disk

integer

title: Disk (GB)

maximum: 2147483647

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

**required**

Example Value

**WritableVirtualMachine**

**Custom fields**
:::

[]{#451}

::: {#page451-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

451/543

Name

Description

**id \*\
**integer\
(path)

A unique integer value identifying this virtual machine.

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

[]{#452}

::: {#page452-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

452/543

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

maxLength: 64

status

integer

title: Status

Enum:

Array \[ 3 \]

cluster\*

integer

title: Cluster

role

integer

title: Role

tenant

integer

title: Tenant

platform

integer

title: Platform

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

vcpus

integer

title: VCPUs

maximum: 32767

minimum: 0

memory

integer

title: Memory (MB)

maximum: 2147483647

minimum: 0

disk

integer

title: Disk (GB)

maximum: 2147483647

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

**PATCH**

**PA**

/virtualization/virtual-machines/{i

d}/

virtualization_virtual-machines_partial_updat\
e

**Parameters**

**Try it out**

Name

Description

**data \*\
**(body)

**Model**

**WritableVirtualMachine**

**Custom fields**

**required**

Example Value
:::

[]{#453}

::: {#page453-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

453/543

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

maxLength: 64

status

integer

title: Status

Enum:

Array \[ 3 \]

cluster\*

integer

title: Cluster

role

integer

title: Role

tenant

integer

title: Tenant

platform

integer

title: Platform

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

vcpus

integer

title: VCPUs

maximum: 32767

minimum: 0

memory

integer

title: Memory (MB)

maximum: 2147483647

minimum: 0

disk

integer

title: Disk (GB)

maximum: 2147483647

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

**id \*\
**integer\
(path)

A unique integer value identifying this virtual machine.

**Responses**

**Response content type**

**application/json**

Code

Description

200

**WritableVirtualMachine**

**Custom fields**

**required**
:::

[]{#454}

::: {#page454-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

454/543

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

maxLength: 64

status

integer

title: Status

Enum:

Array \[ 3 \]

cluster\*

integer

title: Cluster

role

integer

title: Role

tenant

integer

title: Tenant

platform

integer

title: Platform

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

vcpus

integer

title: VCPUs

maximum: 32767

minimum: 0

memory

integer

title: Memory (MB)

maximum: 2147483647

minimum: 0

disk

integer

title: Disk (GB)

maximum: 2147483647

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

**DELETE**

**DEL**

/virtualization/virtual-machines/{id}/

virtualization_virtual-machines_delete

**Parameters**

**Try it out**

Name

Description

**id \*\
**integer

A unique integer value identifying this virtual machine.

Example Value

**WritableVirtualMachine**

**Custom fields**

**required**
:::

[]{#455}

::: {#page455-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

455/543

Name

Description

(path)

**Responses**

**Response content type**

**application/json**

Code

Description

204

**Models**

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

cid\*

string

title: Circuit ID

maxLength: 50

}

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

**Circuit**

**Site**
:::

[]{#456}

::: {#page456-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

456/543

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

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

title: Url

readOnly: true

cid\*

string

title: Circuit ID

maxLength: 50

}

**Device**

**Lag**

**Circuit**
:::

[]{#457}

::: {#page457-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

457/543

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

**Circuit termination**

**Circuit**

**Untagged vlan**
:::

[]{#458}

::: {#page458-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

458/543

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

url

string(\$uri)

title: Url

readOnly: true

**Interface**

**Device**

**Form factor**

**Lag**

**Circuit termination**

**Circuit**
:::

[]{#459}

::: {#page459-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

459/543

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

}

**Mode**

**Untagged vlan**

**Untagged vlan**
:::

[]{#460}

::: {#page460-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

460/543
:::

[]{#461}

::: {#page461-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

461/543

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

interface\*

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

**CircuitTermination**

**Circuit**

**Site**

**Interface**

**Device**

**Form factor**

**Lag**
:::

[]{#462}

::: {#page462-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

462/543

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

{\...}

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

Upstream speed, if different

from port speed

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

**Circuit termination**

**Circuit**

**Mode**

**Untagged vlan**
:::

[]{#463}

::: {#page463-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

463/543

maxLength: 64

display_name

string

title: Display name

readOnly: true

}

tagged_vlans\*

\[

{\...}\]

}

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

{

id

integer

title: ID

readOnly: true

circuit\*

integer

title: Circuit

term_side\*

string

title: Termination

Enum:

Array \[ 2 \]

site\*

integer

title: Site

interface

integer

title: Interface

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

**Untagged vlan**

**WritableCircuitTermination**
:::

[]{#464}

::: {#page464-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

464/543

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

**CircuitType**

**Provider**

**Type**
:::

[]{#465}

::: {#page465-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

465/543

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

**Tenant**
:::

[]{#466}

::: {#page466-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

466/543

{

id

integer

title: ID

readOnly: true

cid\*

string

title: Circuit ID

maxLength: 50

provider\*

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

type\*

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

status\*

{

value\*

integer

label\*

string

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

install_date

string(\$date)

title: Date installed

commit_rate

integer

title: Commit rate (Kbps)

maximum: 2147483647

minimum: 0

description

string

title: Description

maxLength: 100

comments

string

title: Comments

**Circuit**

**Provider**

**Type**

**Status**

**Tenant**
:::

[]{#467}

::: {#page467-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

467/543

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

{

id

integer

title: ID

readOnly: true

cid\*

string

title: Circuit ID

maxLength: 50

provider\*

integer

title: Provider

type\*

integer

title: Type

status

integer

title: Status

Enum:

Array \[ 6 \]

tenant

integer

title: Tenant

install_date

string(\$date)

title: Date installed

commit_rate

integer

title: Commit rate (Kbps)

maximum: 2147483647

minimum: 0

description

string

title: Description

maxLength: 100

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

**Custom fields**

**WritableCircuit**

**Custom fields**
:::

[]{#468}

::: {#page468-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

468/543

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

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

account

string

title: Account number

maxLength: 30

portal_url

string(\$uri)

title: Portal

maxLength: 200

noc_contact

string

title: NOC contact

admin_contact

string

title: Admin contact

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

**Provider**

**Custom fields**
:::

[]{#469}

::: {#page469-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

469/543

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

asn

integer

title: ASN

maximum: 4294967295

minimum: 1

account

string

title: Account number

maxLength: 30

portal_url

string(\$uri)

title: Portal

maxLength: 200

noc_contact

string

title: NOC contact

admin_contact

string

title: Admin contact

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

**WritableProvider**

**Custom fields**

**Manufacturer**
:::

[]{#470}

::: {#page470-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

470/543

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

}

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

**Device type**

**Manufacturer**

**Device role**
:::

[]{#471}

::: {#page471-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

471/543

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

**Platform**

**Rack**

**Primary ip**
:::

[]{#472}

::: {#page472-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

472/543

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

{

id

integer

title: ID

readOnly: true

url

string(\$uri)

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

**Cluster**

**Virtual chassis**

**Device**
:::

[]{#473}

::: {#page473-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

473/543

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

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

**Device**

**Device type**

**Manufacturer**

**Device role**

**Tenant**
:::

[]{#474}

::: {#page474-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

474/543

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

title: Parent device

readOnly: true

status\*

{

**Platform**

**Site**

**Rack**

**Face**

**Status**
:::

[]{#475}

::: {#page475-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

475/543

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

title: Url

readOnly: true

master\*

{

**Status**

**Primary ip**

**Primary ip**

**Primary ip**

**Cluster**

**Virtual chassis**

**Device**
:::

[]{#476}

::: {#page476-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

476/543

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

**Custom fields**

**Cs port**

**Device**
:::

[]{#477}

::: {#page477-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

477/543

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

**ConsolePort**

**Device**

**Cs port**

**Device**
:::

[]{#478}

::: {#page478-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

478/543

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

}

name\*

string

title: Name

maxLength: 50

}

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

**ConsolePortTemplate**

**Device type**

**Manufacturer**

**WritableConsolePortTemplate**
:::

[]{#479}

::: {#page479-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

479/543

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

}

name\*

string

title: Name

maxLength: 50

}

**WritableConsolePort**

**ConsoleServerPortTemplate**

**Device type**

**Manufacturer**
:::

[]{#480}

::: {#page480-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

480/543

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

**WritableConsoleServerPortTemplate**

**WritableConsoleServerPort**
:::

[]{#481}

::: {#page481-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

481/543

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

}

name\*

string

title: Name

maxLength: 50

}

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

**DeviceBayTemplate**

**Device type**

**Manufacturer**

**WritableDeviceBayTemplate**
:::

[]{#482}

::: {#page482-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

482/543

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

**DeviceBay**

**Device**

**Device**

**WritableDeviceBay**
:::

[]{#483}

::: {#page483-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

483/543

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
:::

[]{#484}

::: {#page484-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

484/543

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

[]{#485}

::: {#page485-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

485/543

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

Parent devices house child devices in device bays. Select "None" if this

device type is neither a parent nor a child.

Enum:

Array \[ 3 \]

comments

string

title: Comments

custom_fields

{

}

}

**WritableDeviceType**

**Custom fields**
:::

[]{#486}

::: {#page486-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

486/543

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

[]{#487}

::: {#page487-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

487/543

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

This interface is used only for out-of-band management

description

string

title: Description

maxLength: 100

}

**Interface a**

**Device**

**Form factor**

**Lag**
:::

[]{#488}

::: {#page488-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

488/543

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

This interface is used only for out-of-band management

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

url

string(\$uri)

title: Url

readOnly: true

device\*

**InterfaceConnection**

**Interface a**

**Device**

**Form factor**

**Lag**

**Interface a**
:::

[]{#489}

::: {#page489-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

489/543

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

**Device**

**Form factor**

**Lag**

**Connection status**
:::

[]{#490}

::: {#page490-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

490/543

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

**WritableInterfaceConnection**

**InterfaceTemplate**

**Device type**

**Manufacturer**

**Form factor**
:::

[]{#491}

::: {#page491-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

491/543

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

**WritableInterfaceTemplate**

**WritableInterface**
:::

[]{#492}

::: {#page492-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

492/543

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

**InventoryItem**

**Device**

**Manufacturer**
:::

[]{#493}

::: {#page493-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

493/543

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

**WritableInventoryItem**

**Manufacturer**
:::

[]{#494}

::: {#page494-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:39 PM

NetBox API

https://netbox.satspeed.com/api/docs/

494/543

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

**Platform**

**Manufacturer**

**WritablePlatform**
:::

[]{#495}

::: {#page495-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

495/543

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

**Power outlet**

**Device**
:::

[]{#496}

::: {#page496-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

496/543

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

**PowerPort**

**Device**

**Power outlet**

**Device**
:::

[]{#497}

::: {#page497-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

497/543

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

}

name\*

string

title: Name

maxLength: 50

}

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

**PowerOutletTemplate**

**Device type**

**Manufacturer**

**WritablePowerOutletTemplate**
:::

[]{#498}

::: {#page498-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

498/543

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

}

name\*

string

title: Name

maxLength: 50

}

**WritablePowerOutlet**

**PowerPortTemplate**

**Device type**

**Manufacturer**
:::

[]{#499}

::: {#page499-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

499/543

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

**WritablePowerPortTemplate**

**WritablePowerPort**

**RackGroup**

**Site**
:::

[]{#500}

::: {#page500-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

500/543

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

Required. 150 characters or fewer. Letters, digits and @/./+/-/\_ only.

}

**WritableRackGroup**

**User**
:::

[]{#501}

::: {#page501-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

501/543

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

Required. 150 characters or fewer. Letters, digits and

@/./+/-/\_ only.

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

**RackReservation**

**Rack**

**User**

**Tenant**
:::

[]{#502}

::: {#page502-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

502/543

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

**WritableRackReservation**

**RackRole**

**Group**
:::

[]{#503}

::: {#page503-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

503/543

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

**Role**
:::

[]{#504}

::: {#page504-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

504/543

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

title: Name

maxLength: 50

**Rack**

**Site**

**Group**

**Tenant**

**Role**
:::

[]{#505}

::: {#page505-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

505/543

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

**Type**

**Width**

**Custom fields**
:::

[]{#506}

::: {#page506-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

506/543

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

**WritableRack**

**Custom fields**
:::

[]{#507}

::: {#page507-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

507/543

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

**Parent**

**Region**

**Parent**

**WritableRegion**
:::

[]{#508}

::: {#page508-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

508/543

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

contact_phone

string

title: Contact phone

maxLength: 20

**Site**

**Status**

**Parent**

**Tenant**
:::

[]{#509}

::: {#page509-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

509/543

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

**Custom fields**
:::

[]{#510}

::: {#page510-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

510/543

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

**WritableSite**

**Custom fields**
:::

[]{#511}

::: {#page511-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

511/543

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

{

id

integer

title: ID

readOnly: true

content_type\*

integer

title: Content type

name\*

string

title: Name

maxLength: 100

description

string

title: Description

maxLength: 200

template_code\*

string

title: Template code

mime_type

string

title: Mime type

maxLength: 15

file_extension

string

title: File extension

maxLength: 15

}

**VirtualChassis**

**Device**

**WritableVirtualChassis**

**ExportTemplate**
:::

[]{#512}

::: {#page512-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

512/543

{

id

integer

title: ID

readOnly: true

type\*

{

value\*

integer

label\*

string

}

weight

integer

title: Weight

maximum: 32767

minimum: 0

name\*

string

title: Name

maxLength: 100

source\*

string

title: Source URL

maxLength: 500

link

string(\$uri)

title: Link URL

maxLength: 200

}

{

id

integer

title: ID

readOnly: true

type\*

integer

title: Type

Enum:

Array \[ 3 \]

weight

integer

title: Weight

maximum: 32767

minimum: 0

name\*

string

title: Name

maxLength: 100

source\*

string

title: Source URL

maxLength: 500

link

string(\$uri)

title: Link URL

maxLength: 200

}

**Graph**

**Type**

**WritableGraph**
:::

[]{#513}

::: {#page513-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

513/543

{

id

integer

title: ID

readOnly: true

parent

string

title: Parent

readOnly: true

name

string

title: Name

maxLength: 50

image\*

string(\$uri)

title: Image

readOnly: true

image_height\*

integer

title: Image height

maximum: 32767

minimum: 0

image_width\*

integer

title: Image width

maximum: 32767

minimum: 0

created

string(\$date-time)

title: Created

readOnly: true

}

{

id

integer

title: ID

readOnly: true

content_type\*

string

title: Content type

object_id\*

integer

title: Object id

maximum: 2147483647

minimum: 0

name

string

title: Name

maxLength: 50

image\*

string(\$uri)

title: Image

readOnly: true

}

**ImageAttachment**

**WritableImageAttachment**
:::

[]{#514}

::: {#page514-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

514/543

{

id

integer

title: ID

readOnly: true

time

string(\$date-time)

title: Time

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

Required. 150 characters or fewer. Letters, digits and

@/./+/-/\_ only.

}

action\*

{

value\*

integer

label\*

string

}

message

string

title: Message

}

**UserAction**

**User**

**Action**
:::

[]{#515}

::: {#page515-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

515/543

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

device_patterns\*

string

title: Device patterns

Identify devices to include in the diagram using regular expressions, one per

line. Each line will result in a new tier of the drawing. Separate multiple

regexes within a line using semicolons. Devices will be rendered in the order

they are defined.

description

string

title: Description

maxLength: 100

}

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

site

integer

title: Site

device_patterns\*

string

title: Device patterns

Identify devices to include in the diagram using regular expressions, one per

line. Each line will result in a new tier of the drawing. Separate multiple

regexes within a line using semicolons. Devices will be rendered in the order

they are defined.

description

string

title: Description

maxLength: 100

}

**TopologyMap**

**Site**

**WritableTopologyMap**
:::

[]{#516}

::: {#page516-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

516/543

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

{

id

integer

title: ID

readOnly: true

family\*

integer

title: Family

Enum:

Array \[ 2 \]

prefix\*

string

title: Prefix

rir\*

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

date_added

string(\$date)

title: Date added

description

string

title: Description

maxLength: 100

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

**Rir**

**Aggregate**

**Rir**

**Custom fields**
:::

[]{#517}

::: {#page517-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

517/543

{

id

integer

title: ID

readOnly: true

prefix\*

string

title: Prefix

rir\*

integer

title: RIR

date_added

string(\$date)

title: Date added

description

string

title: Description

maxLength: 100

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

rd\*

string

title: Route distinguisher

maxLength: 21

}

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

**WritableAggregate**

**Custom fields**

**Vrf**

**Virtual machine**
:::

[]{#518}

::: {#page518-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

518/543

{

id

integer

title: ID

readOnly: true

url

string

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

virtual_machine\*

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

name\*

string

title: Name

maxLength: 64

}

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

**Interface**

**Device**

**Virtual machine**

**Nat inside**
:::

[]{#519}

::: {#page519-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

519/543

{

id

integer

title: ID

readOnly: true

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

vrf\*

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

rd\*

string

title: Route distinguisher

maxLength: 21

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

status\*

{

value\*

integer

label\*

string

}

role\*

{

value\*

integer

label\*

string

}

interface\*

{

id

integer

title: ID

readOnly: true

url

string

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

display name

string

**IPAddress**

**Vrf**

**Tenant**

**Status**

**Role**

**Interface**

**Device**
:::

[]{#520}

::: {#page520-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

520/543

display_name

string

title: Display name

readOnly: true

}

virtual_machine\*

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

name\*

string

title: Name

maxLength: 64

}

description

string

title: Description

maxLength: 100

nat_inside\*

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

nat_outside\*

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

**Virtual machine**

**Nat inside**

**Nat inside**

**Custom fields**
:::

[]{#521}

::: {#page521-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

521/543

{

id

integer

title: ID

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

vrf

integer

title: VRF

tenant

integer

title: Tenant

status

integer

title: Status

The operational status of this IP

Enum:

Array \[ 4 \]

role

integer

title: Role

The functional role of this IP

Enum:

Array \[ 8 \]

interface

integer

title: Interface

description

string

title: Description

maxLength: 100

nat_inside

integer

title: NAT (Inside)

The IP for which this address is the "outside" IP

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

**WritableIPAddress**

**Custom fields**

**Vlan**
:::

[]{#522}

::: {#page522-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

522/543

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

**Role**
:::

[]{#523}

::: {#page523-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

523/543

{

id

integer

title: ID

readOnly: true

family

integer

title: Family

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

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

vrf\*

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

rd\*

string

title: Route distinguisher

maxLength: 21

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

vlan\*

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

**Prefix**

**Site**

**Vrf**

**Tenant**

**Vlan**
:::

[]{#524}

::: {#page524-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

524/543

display_name

string

title: Display name

readOnly: true

}

status\*

{

value\*

integer

label\*

string

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

title: Name

maxLength: 50

slug\*

string(\$slug)

title: Slug

pattern: \^\[-a-zA-Z0-9\_\]+\$

maxLength: 50

}

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

**Status**

**Role**

**Custom fields**
:::

[]{#525}

::: {#page525-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

525/543

{

id

integer

title: ID

readOnly: true

prefix\*

string

title: Prefix

IPv4 or IPv6 network with mask

site

integer

title: Site

vrf

integer

title: VRF

tenant

integer

title: Tenant

vlan

integer

title: VLAN

status

integer

title: Status

Operational status of this prefix

Enum:

Array \[ 4 \]

role

integer

title: Role

The primary function of this prefix

is_pool

boolean

title: Is a pool

All IP addresses within this prefix are considered usable

description

string

title: Description

maxLength: 100

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

is_private

boolean

title: Private

IP space managed by this RIR is considered private

}

**WritablePrefix**

**Custom fields**

**RIR**
:::

[]{#526}

::: {#page526-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

526/543

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

weight

integer

title: Weight

maximum: 32767

minimum: 0

}

**Role**
:::

[]{#527}

::: {#page527-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

527/543

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

virtual_machine\*

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

name\*

string

title: Name

maxLength: 30

port\*

integer

title: Port number

maximum: 65535

minimum: 1

protocol\*

{

value\*

integer

label\*

string

}

ipaddresses\*

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

family

integer

title: Family

readOnly: true

address\*

string

title: Address

IPv4 or IPv6 address (with mask)

}\]

description

string

title: Description

maxLength: 100

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**Service**

**Device**

**Virtual machine**

**Protocol**

**Nat inside**
:::

[]{#528}

::: {#page528-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

528/543

{

id

integer

title: ID

readOnly: true

device

integer

title: Device

virtual_machine

integer

title: Virtual machine

name\*

string

title: Name

maxLength: 30

port\*

integer

title: Port number

maximum: 65535

minimum: 1

protocol\*

integer

title: Protocol

Enum:

Array \[ 2 \]

ipaddresses

\[

uniqueItems: true

integer

title: IP addresses\]

description

string

title: Description

maxLength: 100

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

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

**WritableService**

**VLANGroup**

**Site**
:::

[]{#529}

::: {#page529-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

529/543

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

site

integer

title: Site

}

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

**WritableVLANGroup**

**Group**
:::

[]{#530}

::: {#page530-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

530/543

{

id

integer

title: ID

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

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

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

status\*

{

value\*

integer

label\*

string

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

d l

**VLAN**

**Site**

**Group**

**Tenant**

**Status**

**Role**
:::

[]{#531}

::: {#page531-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

531/543

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

description

string

title: Description

maxLength: 100

display_name

string

title: Display name

readOnly: true

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

{

id

integer

title: ID

readOnly: true

site

integer

title: Site

group

integer

title: Group

vid\*

integer

title: ID

maximum: 4094

minimum: 1

name\*

string

title: Name

maxLength: 64

tenant

integer

title: Tenant

status

integer

title: Status

Enum:

Array \[ 3 \]

role

integer

title: Role

description

string

title: Description

maxLength: 100

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

**Custom fields**

**WritableVLAN**

**Custom fields**
:::

[]{#532}

::: {#page532-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

532/543

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

rd\*

string

title: Route distinguisher

maxLength: 21

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

enforce_unique

boolean

title: Enforce unique space

Prevent duplicate prefixes/IP addresses within this VRF

description

string

title: Description

maxLength: 100

display_name

string

title: Display name

readOnly: true

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

**VRF**

**Tenant**

**Custom fields**
:::

[]{#533}

::: {#page533-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

533/543

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 50

rd\*

string

title: Route distinguisher

maxLength: 21

tenant

integer

title: Tenant

enforce_unique

boolean

title: Enforce unique space

Prevent duplicate prefixes/IP addresses within this VRF

description

string

title: Description

maxLength: 100

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

**WritableVRF**

**Custom fields**

**SecretRole**

**Role**
:::

[]{#534}

::: {#page534-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

534/543

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

title: Name

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

maxLength: 100

plaintext

string

title: Plaintext

readOnly: true

hash

string

title: Hash

readOnly: true

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

**Secret**

**Device**

**Role**
:::

[]{#535}

::: {#page535-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

535/543

{

id

integer

title: ID

readOnly: true

device\*

integer

title: Device

role\*

integer

title: Role

name

string

title: Name

maxLength: 100

plaintext\*

string

title: Plaintext

hash

string

title: Hash

readOnly: true

created

string(\$date)

title: Created

readOnly: true

last_updated

string(\$date-time)

title: Last updated

readOnly: true

}

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

**WritableSecret**

**TenantGroup**

**Group**
:::

[]{#536}

::: {#page536-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

536/543

{

id

integer

title: ID

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

description

string

title: Description

maxLength: 100

Long-form name (optional)

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

**Tenant**

**Group**

**Custom fields**
:::

[]{#537}

::: {#page537-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

537/543

{

id

integer

title: ID

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

group

integer

title: Group

description

string

title: Description

maxLength: 100

Long-form name (optional)

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

**WritableTenant**

**Custom fields**

**ClusterGroup**

**ClusterType**
:::

[]{#538}

::: {#page538-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

538/543

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

**Type**

**Group**
:::

[]{#539}

::: {#page539-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

539/543

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 100

type\*

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

**Cluster**

**Type**

**Group**

**Site**

**Custom fields**
:::

[]{#540}

::: {#page540-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

540/543

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 100

type\*

integer

title: Type

group

integer

title: Group

site

integer

title: Site

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

**WritableCluster**

**Custom fields**

**Primary ip**
:::

[]{#541}

::: {#page541-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

541/543

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 64

status\*

{

value\*

integer

label\*

string

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

**VirtualMachine**

**Status**

**Cluster**

**Device role**

**Tenant**

**Platform**
:::

[]{#542}

::: {#page542-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

542/543

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

vcpus

integer

title: VCPUs

maximum: 32767

minimum: 0

memory

integer

title: Memory (MB)

maximum: 2147483647

minimum: 0

disk

integer

title: Disk (GB)

maximum: 2147483647

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

**Primary ip**

**Primary ip**

**Primary ip**

**Custom fields**
:::

[]{#543}

::: {#page543-div style="position:relative;width:918px;height:1188px;"}
9/1/23, 1:40 PM

NetBox API

https://netbox.satspeed.com/api/docs/

543/543

}

{

id

integer

title: ID

readOnly: true

name\*

string

title: Name

maxLength: 64

status

integer

title: Status

Enum:

Array \[ 3 \]

cluster\*

integer

title: Cluster

role

integer

title: Role

tenant

integer

title: Tenant

platform

integer

title: Platform

primary_ip4

integer

title: Primary IPv4

primary_ip6

integer

title: Primary IPv6

vcpus

integer

title: VCPUs

maximum: 32767

minimum: 0

memory

integer

title: Memory (MB)

maximum: 2147483647

minimum: 0

disk

integer

title: Disk (GB)

maximum: 2147483647

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

**WritableVirtualMachine**

**Custom fields**
:::
