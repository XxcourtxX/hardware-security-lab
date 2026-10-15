# Original DuckyScript Exercises — Comparison

These two files were supplied by Cristian Luna as scripts he worked on. Both are retained because they are **different implementations of the same typed-text exercise**, not duplicates.

- [My own Rick Roll.txt](My%20own%20Rick%20Roll.txt) — configurable timing and a boolean switch.
- [payload.txt](payload.txt) — fixed progressive timing and a delay alias.
- [Repository overview](../README.md) · [Short original-text demo](../examples/timing-demo.duck)

## Static comparison
| Feature | My own Rick Roll.txt | payload.txt |
| --- | --- | --- |
| Initial device mode | HID | HID + STORAGE |
| Button definition | Switches to STORAGE | Switches to STORAGE |
| Text output | 59 STRINGLN statements | Same 59 statements, in the same order |
| Delay configuration | DELAY_TIME, TIME, STEP_TIME | TIME starts at 100; increment is a literal 100 |
| Toggle | DELAY_LYRICS = FALSE | No toggle |
| Delay instruction | DELAY directly | DEFINE SLW DELAY, then SLW |
| Current timing behavior | Branch sets TIME and STEP_TIME to zero | Wait increases by 100 ms after each output line |
| Wait before first output | Extra DELAY TIME; currently zero | No explicit pre-output delay |
| Explicit delays | 60 delay statements | 59 alias invocations |

### Timing analysis
- **My own Rick Roll.txt as supplied:** all explicit waits evaluate to zero because the boolean switch is FALSE. Device enumeration and keystroke delivery still take time.
- **payload.txt:** waits of 100, 200, and so on through 5,900 milliseconds sum to **177,000 ms (177 seconds)**. This includes the wait after the final line and excludes typing and device overhead.
- If the configurable version's toggle were changed to TRUE, its 59 post-line waits would also sum to 177 seconds, plus its extra 100 ms initial wait: **177.1 seconds** of explicit waits.

## What the source does
Both scripts configure a programmable keyboard and type lines of text. Both define a button action that changes to storage mode. The supplied source contains no shell-launch shortcut, credential collection, network request, or system-configuration command. It sends text to whichever application has focus, so a blank text editor must be focused manually for a typing demonstration.

## Review observations
- The two output sequences match exactly; this includes the same incomplete text line in both originals.
- The configurable version uses consistently named variables in these supplied files; the historical DELAY_TIME_TIME typo is not present.
- The progressive version requires support for its DEFINE alias and variable arithmetic; device/firmware compatibility still needs compilation and testing.
- Neither version provides a positive startup settling delay as currently supplied. A separate initial delay can improve reliability in a future revised demo.
- These are user-supplied originals. Their logic and output were not edited in this import. GitHub's web editor may normalize line endings; byte-level hashes below identify the **source attachments**, not a guarantee of repository-byte identity.

## Source attachment identification
SHA-256:

~~~text
My own Rick Roll.txt
19ada769512c81c70e7ebdd33abe5b49b067cb2aef89f9c607e661e47363c7f2

payload.txt
264deb15c9927253ba09ba747ac6c1b14fefb78d4e07f8d5715b47532790703b
~~~

## Validation status
Static comparison only: file hashes, control-flow inspection, and exact equality of the 59 STRINGLN lines. Neither original was executed, compiled, or tested on hardware during this review. No successful device run or security compromise is inferred.
