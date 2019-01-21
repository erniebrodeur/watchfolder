# Watchfolder

Watch a folder or file for changes, and do something about it.

## Imports
- External imports, not stdlib stuff

### Runtime
- fsnotify

### Testing
- ginkgo
- gomega

## Packages

### cmd/watchfolder
- contains main loop

### internal/target
- contains target types and functions

### internal/actions
- things that can be done

### internal/event
- types of events

### internal/watch
- watch
- watched

### internal/server
- the internal server/daemon

### internal/server/configuration
- the server configuration (as a buildable object)

### internal/listening
- listening types

## Types

### Event Listener

### Watched
- slice of all files being watched
- only watches files

### Watch
- combo of []targets, []events, and []actions

### Targets
- slice of all active targets

### Target
- generic that can be file or directory

### TargetFile
- file

### TargetDirectory
- directory

### Action
- thing to do to a target

### Event
- trigger for target
- calls action

### Server
- contains runtime server information
- waits for events in `[]targets`
- calls `action` when `event` triggers in `[]targets`

### ServerConfiguration
- server related settings

### Listener
-

## Threads

### ListenerManager
- controls listeners

### Listener
- individual listener for each target
