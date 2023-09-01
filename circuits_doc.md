# Netbox Circuits API Documentation

## Introduction

The Netbox Circuits API provides a set of endpoints to manage and retrieve information related to circuits in the Netbox system. This documentation covers all the functions, data types, fields, and possible results for the API.

### Endpoints

1. **GET /circuits/_choices/**
   - **Description**: Retrieve choices for circuits.
   - **Parameters**: None
   - **Response**: JSON

2. **GET /circuits/_choices/{id}/**
   - **Description**: Read choices for circuits based on ID.
   - **Parameters**: 
     - **id**: string (path)
   - **Response**: JSON

3. **GET /circuits/circuit-terminations/**
   - **Description**: List circuit terminations.
   - **Parameters**: 
     - **term_side**: string (query)
     - **port_speed**: number (query)
     - **upstream_speed**: number (query)
     - **xconnect_id**: string (query)
     - **q**: string (query)
     - **circuit_id**: string (query)
     - **site_id**: string (query)
     - **site**: string (query)
     - **limit**: integer (query) - Number of results to return per page.
     - **offset**: integer (query) - The initial index from which to return the results.
   - **Response**: JSON
     - **count**: integer
     - **next**: string (nullable)
     - **previous**: string (nullable)
     - **results**: Array of objects with fields like `id`, `term_side`, `port_speed`, `upstream_speed`, `xconnect_id`, etc.

4. **POST /circuits/circuit-terminations/**
   - **Description**: Create circuit terminations.
   - **Parameters**: 
     - **data**: JSON body with fields like `id`, `term_side`, `port_speed`, `upstream_speed`, `xconnect_id`, etc.
   - **Response**: JSON

5. **GET /circuits/circuit-terminations/{id}/**
   - **Description**: Read circuit terminations based on ID.
   - **Parameters**: 
     - **id**: integer (path) - A unique integer value identifying this circuit termination.
   - **Response**: JSON

6. **PUT /circuits/circuit-terminations/{id}/**
   - **Description**: Update circuit terminations based on ID.
   - **Parameters**: 
     - **data**: JSON body with fields like `id`, `term_side`, `port_speed`, `upstream_speed`, `xconnect_id`, etc.
     - **id**: integer (path) - A unique integer value identifying this circuit termination.
   - **Response**: JSON

7. **PATCH /circuits/circuit-terminations/{id}/**
   - **Description**: Partially update circuit terminations based on ID.
   - **Parameters**: 
     - **data**: JSON body with fields like `id`, `term_side`, `port_speed`, `upstream_speed`, `xconnect_id`, etc.
     - **id**: integer (path) - A unique integer value identifying this circuit termination.
   - **Response**: JSON

8. **DELETE /circuits/circuit-terminations/{id}/**
   - **Description**: Delete circuit terminations based on ID.
   - **Parameters**: 
     - **id**: integer (path) - A unique integer value identifying this circuit termination.
   - **Response**: JSON

9. **GET /circuits/circuit-types/**
   - **Description**: List circuit types.
   - **Parameters**: 
     - **name**: string (query)
     - **slug**: string (query)
     - **limit**: integer (query) - Number of results to return per page.
     - **offset**: integer (query) - The initial index from which to return the results.
   - **Response**: JSON

10. **POST /circuits/circuit-types/**
    - **Description**: Create circuit types.
    - **Parameters**: 
      - **data**: JSON body with fields like `id`, `name`, `slug`, etc.
    - **Response**: JSON

11. **GET /circuits/circuit-types/{id}/**
    - **Description**: Read circuit types based on ID.
    - **Parameters**: 
      - **id**: integer (path) - A unique integer value identifying this circuit type.
    - **Response**: JSON

12. **PUT /circuits/circuit-types/{id}/**
    - **Description**: Update circuit types based on ID.
    - **Parameters**: 
      - **data**: JSON body with fields like `id`, `name`, `slug`, etc.
      - **id**: integer (path) - A unique integer value identifying this circuit type.
    - **Response**: JSON

13. **PATCH /circuits/circuit-types/{id}/**
    - **Description**: Partially update circuit types based on ID.
    - **Parameters**: 
      - **data**: JSON body with fields like `id`, `name`, `slug`, etc.
      - **id**: integer (path) - A unique integer value identifying this circuit type.
    - **Response**:

 JSON

14. **DELETE /circuits/circuit-types/{id}/**
    - **Description**: Delete circuit types based on ID.
    - **Parameters**: 
      - **id**: integer (path) - A unique integer value identifying this circuit type.
    - **Response**: JSON

15. **GET /circuits/circuits/**
    - **Description**: List circuits.
    - **Parameters**: 
      - **cid**: string (query)
      - **provider_id**: string (query)
      - **type_id**: string (query)
      - **status**: string (query)
      - **limit**: integer (query) - Number of results to return per page.
      - **offset**: integer (query) - The initial index from which to return the results.
    - **Response**: JSON

16. **POST /circuits/circuits/**
    - **Description**: Create circuits.
    - **Parameters**: 
      - **data**: JSON body with fields like `id`, `cid`, `provider_id`, `type_id`, `status`, etc.
    - **Response**: JSON

17. **GET /circuits/circuits/{id}/**
    - **Description**: Read circuits based on ID.
    - **Parameters**: 
      - **id**: integer (path) - A unique integer value identifying this circuit.
    - **Response**: JSON

18. **PUT /circuits/circuits/{id}/**
    - **Description**: Update circuits based on ID.
    - **Parameters**: 
      - **data**: JSON body with fields like `id`, `cid`, `provider_id`, `type_id`, `status`, etc.
      - **id**: integer (path) - A unique integer value identifying this circuit.
    - **Response**: JSON

19. **PATCH /circuits/circuits/{id}/**
    - **Description**: Partially update circuits based on ID.
    - **Parameters**: 
      - **data**: JSON body with fields like `id`, `cid`, `provider_id`, `type_id`, `status`, etc.
      - **id**: integer (path) - A unique integer value identifying this circuit.
    - **Response**: JSON

20. **DELETE /circuits/circuits/{id}/**
    - **Description**: Delete circuits based on ID.
    - **Parameters**: 
      - **id**: integer (path) - A unique integer value identifying this circuit.
    - **Response**: JSON

21. **GET /circuits/providers/**
    - **Description**: List circuit providers.
    - **Parameters**: 
      - **name**: string (query)
      - **slug**: string (query)
      - **limit**: integer (query) - Number of results to return per page.
      - **offset**: integer (query) - The initial index from which to return the results.
    - **Response**: JSON

22. **POST /circuits/providers/**
    - **Description**: Create circuit providers.
    - **Parameters**: 
      - **data**: JSON body with fields like `id`, `name`, `slug`, etc.
    - **Response**: JSON

23. **GET /circuits/providers/{id}/**
    - **Description**: Read circuit providers based on ID.
    - **Parameters**: 
      - **id**: integer (path) - A unique integer value identifying this circuit provider.
    - **Response**: JSON

24. **PUT /circuits/providers/{id}/**
    - **Description**: Update circuit providers based on ID.
    - **Parameters**: 
      - **data**: JSON body with fields like `id`, `name`, `slug`, etc.
      - **id**: integer (path) - A unique integer value identifying this circuit provider.
    - **Response**: JSON

25. **PATCH /circuits/providers/{id}/**
    - **Description**: Partially update circuit providers based on ID.
    - **Parameters**: 
      - **data**: JSON body with fields like `id`, `name`, `slug`, etc.
      - **id**: integer (path) - A unique integer value identifying this circuit provider.
    - **Response**: JSON

26. **DELETE /circuits/providers/{id}/**
    - **Description**: Delete circuit providers based on ID.
    - **Parameters**: 
      - **id**: integer (path) - A unique integer value identifying this circuit provider.
    - **Response**: JSON
