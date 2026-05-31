# OpenAPI Documentation

> The OpenAPI Specification (OAS) defines a standard, language-agnostic interface to HTTP APIs which allows both humans and computers to discover and understand the capabilities of the service without access to source code, documentation, or through network traffic inspection. When properly defined, a consumer can understand and interact with the remote service with a minimal amount of implementation logic. (Swagger, 2024)

## Rationale
Describing the API endpoints using OpenAPI documents
- allows clarity in the specifications and requirements of the HTTP API which allows communication between the frontend mobile application and the backend.
- provides a machine and human readable format, which allows the automatic generation of server-side and client SDK stubs for API endpoints using tools such as [Swagger Codegen](https://swagger.io/tools/swagger-codegen/)
- API documentation is easily generated from the documents using tools such as [Swagger UI](https://swagger.io/tools/swagger-ui/)

## Format
The OpenAPI documents are commonly written in either JSON or YAML. For this project, the documents will be written in YAML since it provides a much cleaner and human-readable syntax for a negligible performance hit.

The documents are stored in the current `api/` directory
```
api 
├── README.md   
├── openapi.yaml        # The root OpenAPI document which imports all other YAML documents
├── paths               # Each YAML file in a subdirectory corresponds to the definition of a specific API endpoint path
│   └── ...
└── schema              # Each YAML file consists of a reusable OpenAPI schema model (e.g. a User model)
    ├── components            # Contains the building block models (users, etc.)
    │   └── ...
    ├── errors                # Contains the models for error responses
    │   └── ...
    ├── requests              # Contains the models for request bodies
    │   └── ...
    └── responses             # Contains the models for successful response bodies
        └── ...
    
```

CI/CD infrastructure to automatically lint OpenAPI documentation on push events using [Spectral](https://github.com/stoplightio/spectral), as well as automatically build and deploy documentation is also present. 

A Swagger UI deployment is present [here](https://thewatchmasters.github.io/specs/api/specs)
