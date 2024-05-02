#network 
[[Network MOC]]
- - - 

The Open Systems Interconnection (OSI) is a theoretical model for network  communication.

# OSI Layers

Each layer transforms data from highest level into electrical signals at physical level. Receiving data is received at the lowest level and works up to the application layer for the user.

1. **Physical**: Converts packets into electrical signals
2. **Data Link**: Encodes and decodes packets into bits, adds [[MAC Addresses]]
3. **Network**: Routes packet over network, adds [[IP addresses]]
4. **Transport**: Create end-to-end connection, adds [[TCP Protocol]] or [[UDP Protocol]] header
5. **Session**: Managing connections
6. **Presentation**: Formats data for recipient, encrypts data, XML, JSON, binary...
7. **Application**: The application, [[HTTP Protocol]], [[FTP Protocol]]

# TCP IP Model

The TCP/IP model is an adaption of the OSI model.

1. **Network Access**: OSI Data Link and Physical layer
2. **Internet**: Same as OSI Network layer
3. **Transport**: Same as OSI Transportation layer
4. **Application**: Includes OSI Application, Presentation, and Session layers