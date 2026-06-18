# Initial User Flows

## Flowcharts
### Main App Flow
```mermaid
flowchart TD

    A[App opens] --> B{Did a valid session persist over app installations?}

    B -->|Yes| C([Go to the home page])

    B -->|No| D[Show a language dropdown]
    
    D --> E([Go to the login page])
```

### Account Creation Flow
```mermaid
flowchart TD
    A[New account is being registered] -.-> B[Display the Crypto/Bank Account vault choice]

    B --> C[Set up goals]

    C --> D[Set up charity of choice]
    
    D --> E([Go to home page])
```

## Limitations
