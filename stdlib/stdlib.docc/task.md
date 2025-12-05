# ``Swift/Task``

## Topics

### Creating a Task

- ``Swift/Task/init(priority:operation:)-7f0zv``
- ``Swift/Task/init(priority:operation:)-ntwf``
- ``Swift/Task/init(name:priority:operation:)-2dll5``
- ``Swift/Task/init(name:priority:operation:)-43wmk``
- ``Swift/Task/init(name:executorPreference:priority:operation:)-59bfi``
- ``Swift/Task/init(name:executorPreference:priority:operation:)-81pay``
- ``Swift/Task/init(executorPreference:priority:operation:)-7zpzv``
- ``Swift/Task/init(executorPreference:priority:operation:)-6o27o``
- ``Swift/Task/detached(priority:operation:)-d24l``
- ``Swift/Task/detached(priority:operation:)-1g00u``
- ``Swift/Task/detached(executorPreference:priority:operation:)-1y7ms``
- ``Swift/Task/detached(executorPreference:priority:operation:)-7vnfx``
- ``Swift/Task/currentPriority``
- ``Swift/Task/basePriority``
- ``Swift/withTaskPriorityEscalationHandler(operation:onPriorityEscalated:isolation:)``

### Creating a Detached Task

- ``Swift/Task/detached(name:priority:operation:)-795w1``
- ``Swift/Task/detached(name:priority:operation:)-9xki7``
- ``Swift/Task/detached(name:executorPreference:priority:operation:)-6r16s``
- ``Swift/Task/detached(name:executorPreference:priority:operation:)-75ffe``

### Creating a Task that Starts Immediately

- ``Swift/Task/immediate(name:priority:executorPreference:operation:)-88o80``
- ``Swift/Task/immediate(name:priority:executorPreference:operation:)-9bghc``
- ``Swift/Task/immediateDetached(name:priority:executorPreference:operation:)-52ipd``
- ``Swift/Task/immediateDetached(name:priority:executorPreference:operation:)-7h41b``

### Accessing Results

- ``Swift/Task/value-60t02``
- ``Swift/Task/value-40dtq``
- ``Swift/Task/result``

### Accessing the Current Task's Name

- ``Swift/Task/name``

### Canceling Tasks

- ``Swift/CancellationError``
- ``Swift/Task/cancel()``
- ``Swift/Task/isCancelled-swift.property``
- ``Swift/Task/isCancelled-swift.type.property``
- ``Swift/Task/checkCancellation()``
- ``Swift/withTaskCancellationHandler(handler:operation:)``
- ``Swift/withTaskCancellationHandler(operation:onCancel:isolation:)``

### Suspending Execution

- ``Swift/Task/yield()``
- ``Swift/Task/sleep(nanoseconds:)``
- ``Swift/Task/sleep(for:tolerance:clock:)``
- ``Swift/Task/sleep(until:tolerance:clock:)``

### Escalating Tasks

- ``Swift/Task/escalatePriority(to:)``

### Comparing Tasks

- ``Swift/Task/==(_:_:)``
- ``Swift/Task/!=(_:_:)``
- ``Swift/Task/hashValue``
- ``Swift/Task/hash(into:)``

### Deprecated

- ``Swift/Task/Group``
- ``Swift/Task/Handle``
- ``Swift/Task/Priority``
- ``Swift/Task/CancellationError()``
- ``Swift/Task/getResult()``
- ``Swift/Task/get()-4i2gt``
- ``Swift/Task/get()-4ohks``
- ``Swift/Task/sleep(_:)``
- ``Swift/Task/suspend()``
- ``Swift/Task/runDetached(priority:operation:)-88zf5``
- ``Swift/Task/runDetached(priority:operation:)-8s8lh``
- ``Swift/Task/startSynchronously(name:priority:_:)-38jhc``
- ``Swift/Task/startSynchronously(name:priority:_:)-47sar``
- ``Swift/Task/withCancellationHandler(handler:operation:)``
- ``Swift/Task/withGroup(resultType:returning:body:)``
