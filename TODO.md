
To Do List
==========

### Defects

* TBC

### New features

* IB Controller launcher (TWS and Gateway). Test IB Gateway app
* Add a cfgConnectionTimeOut setting?
* Command terminal (e.g. use Haskeline)
* Monadic interface
* Remaining IB requests and responses (summarise here from list in Enum.hs)

### Design

* Refactor Edge to ListT
* Async housekeeping audit
* Config read only (vs in 'mutable' state at present)?
* Some data unncecessary in IB connection state vs app service state (e.g. accounts, next valid id, etc?) 
* BASE currency (in AccountValue msg) solution - was in currency enum in hq.data.currency

### Test suite 

* Unit tests
* Property tests
* Benchmarks

### Data 

* More typing (enum,utctime,etc.) instead of strings/bytestrings (e.g. in contract)
* IBOrder: into multiple data types
* IBOrder: maybe's for bools
* IBOrder: decomposition may allow a single maybe for related fields
* Consistent use of IB prefix for data type names (e.g. IBRequest and IBResponse constructors and fields)

### Event Processor

* Auto-start option
* Debug option
* ServiceCommand: implement start, pause, resume
* ibsNextRequestId: add? if so, implment update logic
* ibsNextOrderId: retain? if so, implement remaining update logic
* Check client server version <= server version
* Error handler for error responses from IB (see IB API docs for error codes)
* Error response messages - see EClientSocket.java e.g. not connected, cannot send (also cannot create which currently only logs a message)

### Requests

* Create message functions to return Either with failure reason?

### Parsing

* FromIB class for parsing?
* Review fields for possible signed / blank / default parsing requirement
* IBContract: complete refactoring to use field level parsers
* TickPrice: parse also generates a TickSize but latter seems to also stream separately - confirm/remove duplication? Have commented out TickSize generation from TickPrice parser.
* Add error message to fail "" statements

### Socket service

* Move to another library (e.g mvc-service)
* Complete model (e.g. checking and updating state)
* Tidy up Connection code, consistent use of STM vs IO
* Streamline verbose code e.g. atomically
* Tests and benchmarks























