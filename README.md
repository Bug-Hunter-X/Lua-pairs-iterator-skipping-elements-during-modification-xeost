# Lua pairs iterator skipping elements during modification

This repository demonstrates a subtle bug in Lua where the `pairs` iterator might skip elements if the table being iterated over is modified during iteration.  The provided code sample showcases this behavior. The solution offers a safer approach to iterating over tables while potentially modifying them.

## Bug Description
The `pairs` iterator in Lua does not guarantee the order of iteration, and if the table structure is changed (elements added or removed) during iteration, it can lead to elements being skipped. This is particularly problematic when recursively traversing nested tables.

## Solution
The solution avoids modifying the table during iteration.  Alternatively,  it provides a safer way to iterate, preserving the behavior even when the table is modified during iteration. This can be done by iterating over a copy of the table or maintaining a separate list of keys to iterate over.