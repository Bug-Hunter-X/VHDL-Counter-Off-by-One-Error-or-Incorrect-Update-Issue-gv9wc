# VHDL Counter Bug

This repository demonstrates a subtle bug in a VHDL counter implementation.
The `buggy_counter.vhdl` file contains the buggy code.  The counter is designed to count from 0 to 15 and wrap around. However, under certain circumstances, it will exhibit unexpected behavior such as not incrementing or producing incorrect values, particularly if the assignment isn't done in a clocked process.
The `fixed_counter.vhdl` file shows the corrected version of the counter.

## Bug Description
The primary issue is related to how the internal counter state is updated.  Without a process correctly reacting to the clock's rising edge, the assignment `internal_count <= internal_count + 1;` might not be properly synchronized with the clock, potentially leading to unexpected behavior.  The correct approach is to use a `process` sensitive to the clock and reset signals.
