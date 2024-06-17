# Commits

## Commits on Jun 13, 2024

### Debug with fmt::print.
Three debug functions added.
In the sawtoothCallback function to output the memory address and the vector data.
In the configureWebSocketRoutes function to indicate when the WebSocket is started.
In the ROUTE .onmessage to display the clients address and its message.

### Refactoring of the DLL handling.
Improved logging for sawtooth callback and WebSocket initialization.
Replaced  in the  structure with  map for better path management.
Unnecessary debug output in  has been cleaned up.
Improved the  function to map DLL handles to their paths and added logging to check the contents of the mapping.
