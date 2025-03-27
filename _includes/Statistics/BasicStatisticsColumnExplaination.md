## Available Data
Currently we have the following data sets in order they appear in the screenshot:
- Active Calls, The amount of active calls under one item
- Active Threads, The amount of active threads under one item <br/>
- Total Calls, The amount of total calls made while profiling under one item.
- Self Time, the total amount of [measured time](#time-measurement) spend in one item
- Time, the total amount of [measured time](#time-measurement) spend under one item
- AVG, the average amount of [measured time](#time-measurement) spend under one item
- Longest Call, the longest [measured time](#time-measurement) spend under one item
- Shortest Call, the shortest [measured time](#time-measurement) spend under one item
- Δ Calls, amount of calls last second under one item
- Δ Duration, the amount of [measured time](#time-measurement) spend last second under one item

- Self Allocations, the amount of allocations in one item
- Self Deallocations, the amount of deallocations in one item
- Callee Allocations, the amount of allocations that happened in items called by this one
- Self Bytes Allocated, the amount of bytes allocated in one item
- Self Bytes Deallocated, the amount of bytes deallocated in one item
- Callee Bytes Allocated, the amount of bytes allocated in items called by this one

When you double click an item in the tree view it will open the [object details view](ObjectDetailsView) or [function details view](CodeMemberDetailsView) of the selected item.

## Time Measurement
To get more information on how we measure time, see [Feature - Time Measurement](../../features/TimeMessurement)