## Available Data
The statistics table shows both namespaces/classes and methods. Because a namespace or class cannot have any direct calls to it, it shows the sum of all its children.

Currently we have the following data sets in order that they appear:
- Formatted Name, the name of the namespace, class or method.
- Active Calls, the amount of function being called in this item.
- Active Threads, the amount of active threads in this item.
- Total Calls, the total amount of calls made in this item.
- Exclusive Call, the total amount of [measured time](#time-measurement) spend in this item, excluding the duration of calls made in this item.
- Inclusive Call, the total amount of [measured time](#time-measurement) spend in this item, including the duration of calls made in this item.
- AVG, the average amount of [measured time](#time-measurement) spend in this item.
- Longest Call, the longest [measured time](#time-measurement) spend in this item.
- Shortest Call, the shortest [measured time](#time-measurement) spend int this item.
- Δ Calls, the amount of calls that were made to this item in the last second.
- Δ Duration, the amount of [measured time](#time-measurement) spend in this item in the last second.

- Self Allocations, the amount of allocations that were made in this item.
- Self Deallocations, the amount of deallocations that were made in this item.
- Δ Self Allocations, the difference between the amount of self allocations and self deallocations that were made in this item.
- Callee Allocations, the amount of allocations that happened in items called by this one.
- Self Bytes Allocated, the amount of bytes allocated in this item.
- Self Bytes Deallocated, the amount of bytes deallocated in this item.
- Δ Self Allocated Bytes, the difference between the amount of self allocated bytes and self deallocated bytes that were made in this item.
- Callee Bytes Allocated, the amount of bytes allocated in items called by this one.

When you double click an item in the tree view it will open the [object details view](ObjectDetailsView) or [function details view](CodeMemberDetailsView) of the selected item.

## Time Measurement
To get more information on how we measure time, see [Feature - Time Measurement](../../features/TimeMessurement)