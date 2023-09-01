# Netbox Circuits API Documentation

## Introduction

The Netbox Circuits API provides a set of endpoints to manage and retrieve information related to circuits in the Netbox system. This documentation covers all the functions, data types, fields, and possible results for the API.

## Endpoints

### 1. `/api/circuits/circuit-types/`

#### Description:
This endpoint provides functions to manage circuit types.

#### Methods:
- **GET**: Retrieve a list of circuit types.
- **POST**: Create a new circuit type.

#### Input Parameters:
- `limit`: (integer) The maximum number of results to return.
- `offset`: (integer) The starting position within the query results from which to return data.

#### Input JSON Structure:
- `name`: (string) Name of the circuit type.
- `slug`: (string) A URL-friendly representation of the name.
- `description`: (string, optional) A brief description of the circuit type.

#### Output JSON Fields:
- `id`: (integer) Unique identifier for the circuit type.
- `name`: (string) Name of the circuit type.
- `slug`: (string) A URL-friendly representation of the name.
- `description`: (string, optional) A brief description of the circuit type.

### 2. `/api/circuits/circuits/`

#### Description:
This endpoint provides functions to manage circuits.

#### Methods:
- **GET**: Retrieve a list of circuits.
- **POST**: Create a new circuit.

#### Input Parameters:
- `limit`: (integer) The maximum number of results to return.
- `offset`: (integer) The starting position within the query results from which to return data.

#### Input JSON Structure:
- `cid`: (string) Circuit ID.
- `type`: (integer) ID of the associated circuit type.
- `provider`: (integer) ID of the associated provider.
- `status`: (string) Operational status of the circuit.
- `install_date`: (date, optional) Date the circuit was installed.
- `commit_rate`: (integer, optional) Committed data rate in kbps.
- `description`: (string, optional) A brief description of the circuit.

#### Output JSON Fields:
- `id`: (integer) Unique identifier for the circuit.
- `cid`: (string) Circuit ID.
- `type`: (object) Associated circuit type details.
  - `id`: (integer) Unique identifier for the circuit type.
  - `name`: (string) Name of the circuit type.
  - `slug`: (string) A URL-friendly representation of the name.
- `provider`: (object) Associated provider details.
  - `id`: (integer) Unique identifier for the provider.
  - `name`: (string) Name of the provider.
  - `slug`: (string) A URL-friendly representation of the name.
- `status`: (string) Operational status of the circuit.
- `install_date`: (date, optional) Date the circuit was installed.
- `commit_rate`: (integer, optional) Committed data rate in kbps.
- `description`: (string, optional) A brief description of the circuit.
