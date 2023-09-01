**Netbox Circuits API Documentation**

**Introduction**
The Netbox Circuits API provides a set of endpoints to manage and retrieve information related to circuits in the Netbox system. This documentation covers all the functions, data types, fields, and possible results for the API.

**Endpoints**

- **GET /circuits/_choices/**
  - **Description**: Retrieve choices for circuits.
  - **Parameters**: None
  - **Response**: JSON

- **GET /circuits/_choices/{id}/**
  - **Description**: Read choices for circuits based on ID.
  - **Parameters**:
    - `id`: string (path)
  - **Response**: JSON

- **GET /circuits/circuit-terminations/**
  - **Description**: List circuit terminations.
  - **Parameters**:
    - `term_side`: Side of the termination (A or Z).
    - `port_speed`: Speed of the port in kbps.
    - `upstream_speed`: Upstream speed in kbps.
    - `xconnect_id`: Cross-connect ID.
    - `q`: string (query)
    - `circuit_id`: ID of the associated circuit.
    - `site_id`: ID of the associated site.
    - `site`: Name of the associated site.
    - `limit`: integer (query) - Number of results to return per page.
    - `offset`: integer (query) - The initial index from which to return the results.
  - **Response**: JSON
    - `count`: integer
    - `next`: string (nullable)
    - `previous`: string (nullable)
    - `results`: Array of CircuitTermination objects.
- **POST /circuits/circuit-terminations/**
  - **Description**: Create circuit terminations.
  - **Parameters**:
    - `data`: JSON body with fields like `id`, `term_side`, `port_speed`, `upstream_speed`, `xconnect_id`, `circuit_id`, `site_id`, and `site`.
  - **Response**: JSON

- **GET /circuits/circuit-terminations/{id}/**
  - **Description**: Read circuit terminations based on ID.
  - **Parameters**:
    - `id`: integer (path) - A unique integer value identifying this circuit termination.
  - **Response**: JSON

- **PUT /circuits/circuit-terminations/{id}/**
  - **Description**: Update circuit terminations based on ID.
  - **Parameters**:
    - `data`: JSON body with fields like `id`, `term_side`, `port_speed`, `upstream_speed`, `xconnect_id`, `circuit_id`, `site_id`, and `site`.
    - `id`: integer (path) - A unique integer value identifying this circuit termination.
  - **Response**: JSON

- **PATCH /circuits/circuit-terminations/{id}/**
  - **Description**: Partially update circuit terminations based on ID.
  - **Parameters**:
    - `data`: JSON body with fields like `id`, `term_side`, `port_speed`, `upstream_speed`, `xconnect_id`, `circuit_id`, `site_id`, and `site`.
    - `id`: integer (path) - A unique integer value identifying this circuit termination.
  - **Response**: JSON

- **DELETE /circuits/circuit-terminations/{id}/**
  - **Description**: Delete circuit terminations based on ID.
  - **Parameters**:
    - `id`: integer (path) - A unique integer value identifying this circuit termination.
  - **Response**: JSON

- **GET /circuits/circuit-types/**
  - **Description**: List circuit types.
  - **Parameters**:
    - `name`: Name of the circuit type.
    - `slug`: URL-friendly representation of the circuit type.
    - `limit`: integer (query) - Number of results to return per page.
    - `offset`: integer (query) - The initial index from which to return the results.
  - **Response**: JSON

- **POST /circuits/circuit-types/**
  - **Description**: Create circuit types.
  - **Parameters**:
    - `data`: JSON body with fields like `id`, `name`, and `slug`.
  - **Response**: JSON

- **GET /circuits/circuit-types/{id}/**
  - **Description**: Read circuit types based on ID.
  - **Parameters**:
    - `id`: integer (path) - A unique integer value identifying this circuit type.
  - **Response**: JSON

- **PUT /circuits/circuit-types/{id}/**
  - **Description**: Update circuit types based on ID.
  - **Parameters**:
    - `data`: JSON body with fields like `id`, `name`, and `slug`.
    - `id`: integer (path) - A unique integer value identifying this circuit type.
  - **Response**: JSON

- **PATCH /circuits/circuit-types/{id}/**
  - **Description**: Partially update circuit types based on ID.
  - **Parameters**:
    - `data`: JSON body with fields like `id`, `name`, and `slug`.
    - `id`: integer (path) - A unique integer value identifying this circuit type.
  - **Response**: JSON

- **DELETE /circuits/circuit-types/{id}/**
  - **Description**: Delete circuit types based on ID.
  - **Parameters**:
    - `id`: integer (path) - A unique integer value identifying this circuit type.
  - **Response**: JSON

- **GET /circuits/circuits/**
  - **Description**: List circuits.
  - **Parameters**:
    - `cid`: Circuit ID.
    - `provider_id`: ID of the associated provider.
    - `type_id`: ID of the associated circuit type.
    - `status`: Status of the circuit.
    - `limit`: integer (query) - Number of results to return per page.
    - `offset`: integer (query) - The initial index from which to return the results.
  - **Response**: JSON

- **POST /circuits/circuits/**
  - **Description**: Create circuits.
  - **Parameters**:
    - `data`: JSON body with fields like `id`, `cid`, `provider_id`, `type_id`, and `status`.
  - **Response**: JSON

- **GET /circuits/providers/**
  - **Description**: List circuit providers.
  - **Parameters**:
    - `name`: Name of the provider.
    - `slug`: URL-friendly representation of the provider.
    - `limit`: integer (query) - Number of results to return per page.
    - `offset`: integer (query) - The initial index from which to return the results.
  - **Response**: JSON

- **POST /circuits/providers/**
  - **Description**: Create circuit providers.
  - **Parameters**:
    - `data`: JSON body with fields like `id`, `name`, and `slug`.
  - **Response**: JSON

- **GET /circuits/providers/{id}/**
  - **Description**: Read circuit providers based on ID.
  - **Parameters**:
    - `id`: integer (path) - A unique integer value identifying this circuit provider.
  - **Response**: JSON

- **PUT /circuits/providers/{id}/**
  - **Description**: Update circuit providers based on ID.
  - **Parameters**:
    - `data`: JSON body with fields like `id`, `name`, and `slug`.
    - `id`: integer (path) - A unique integer value identifying this circuit provider.
  - **Response**: JSON

- **PATCH /circuits/providers/{id}/**
  - **Description**: Partially update circuit providers based on ID.
  - **Parameters**:
    - `data`: JSON body with fields like `id`, `name`, and `slug`.
    - `id`: integer (path) - A unique integer value identifying this circuit provider.
  - **Response**: JSON

- **DELETE /circuits/providers/{id}/**
  - **Description**: Delete circuit providers based on ID.
  - **Parameters**:
    - `id`: integer (path) - A unique integer value identifying this circuit provider.
  - **Response**: JSON

### JSON Structures Reference

1. **CircuitTermination**
   - `id`: Unique identifier for the circuit termination.
   - `term_side`: Side of the termination (A or Z).
   - `port_speed`: Speed of the port in kbps.
   - `upstream_speed`: Upstream speed in kbps.
   - `xconnect_id`: Cross-connect ID.
   - `circuit_id`: ID of the associated circuit.
   - `site_id`: ID of the associated site.
   - `site`: Name of the associated site.

2. **CircuitType**
   - `id`: Unique identifier for the circuit type.
   - `name`: Name of the circuit type.
   - `slug`: URL-friendly representation of the circuit type.

3. **Circuit**
   - `id`: Unique identifier for the circuit.
   - `cid`: Circuit ID.
   - `provider_id`: ID of the associated provider.
   - `type_id`: ID of the associated circuit type.
   - `status`: Status of the circuit.

4. **Provider**
   - `id`: Unique identifier for the provider.
   - `name`: Name of the provider.
   - `slug`: URL-friendly representation of the provider.

