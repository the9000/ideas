# Issue tracker right on an Eisenhower square chart

Visually arranges tickets. People are good at seeing geometric patterns.

Seeing issues cropping up in "urgent and important" quadrant is a clear call
to action. Seeing issues dangerously creeping to the edges is a visual clue, too.

Every ticket has `importance` and `due` as required parameters;
the very geometry of the chart shows / sets them.

A task may (and generally should) specify an `expiration` date, later than the `due` date. 
A task past expiration date silently drop off the square into the archive.
This shows the opportunity window closing beyond user's control.

## Visual design

Four quadrants, each divided into its own four (nine?) quadrants.
(One more level of subrivision / zoom to be considered.)

Most urgent are on the left, most important are on the top.

The horizontal sequence:

    Past due but not expired | Due today | Due tomorrow | Due later.

Possibly each subdivision has its own user-settable division line, into
`hot zone` and `cold zone`. E.g. in due today, hot zone may be within 1
hour of due time, and in due later, hot zone may be those tasks with narrow
opportunity windows.

The vertical sequence:

    Most important (maybe come up with nicer level names)
    ---
    ...
    ---
    Least important
    
### Colors

The vertical sequence and the horizontal sequence each change background
color in a predictable way. E.g. left is 100% red, 0% green and right is
100% green, 0% red, while top to bottom is transparent to 50% blue.

There's no smooth gradient; color levels jump to show quadrant borders.

### Archived tasks
**TBD.**
Gutter on the left goes to the band / list of archived tasks, all past due.

Separate / split view of completed and failed tasks.

Some analysis tools (e.g. how much past due).

## Internals

