# Commits

## Commits on Jun 13, 2024

### Debug with fmt::print.
- Three debug functions added.
- In the sawtoothCallback function to output the memory address and the vector data.
- In the configureWebSocketRoutes function to indicate when the WebSocket is started.
- In the ROUTE .onmessage to display the clients address and its message.

### Refactoring of the DLL handling.
- Improved logging for sawtooth callback and WebSocket initialization.
- Replaced  in the  structure with  map for better path management.
- Unnecessary debug output in  has been cleaned up.
- Improved the  function to map DLL handles to their paths and added logging to check the contents of the mapping.

### Refactor ConfigWebSocket usage.
- Removed the global instance of ConfigWebSocket.
- Updated the function signatures of handleClientMessage and configureWebSocketRoutes to pass ConfigWebSocket as a parameter.
- Changed the main function to create an instance of ConfigWebSocket and pass it to configureWebSocketRoutes.
- Removed redundant mutex lock in sawtoothCallback.

### Revision of the ConfigDLL destructor.
- Improvement of the debug output
- Updated the ConfigDLL destructor to iterate over the  map instead of the  vector. Deleted  instead of  in the destructor.
- Added debug output to display the address of  before closing it.
- Combined debug print statements in the  function

### Start and stop callback.
- Addition of callback control.
- Introduction of a new atomic variable  to control the status of the callback function. The callback will not process data if the status is false.
- The function  has been extended to parse incoming JSON messages and process the commands start and stop.
- The client.py file has been adapted to the new requirements.

### Revision of the callback control.
- Added  to the  structure for individual client callback control.
- The global variable  has been removed.
- Updated the  function to check the callback status for each individual client.

[zurück](../Unterlagen/Commits-and-Pull-Requests.md)
