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
