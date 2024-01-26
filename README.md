# svg

The general idea here is to streamline the process of taking a photograph and
converting to an SVG file that is appropriate for a laser or vinyl cutting machine.

The software:

    * IrFan View
    * Inkscape

Obviously there's lots of other tools to edit photographs and trace vector
graphics. ymmv &c &c

Your average phone produces photographs that are megabytes in size. These
are enormous! The key idea is that we are reducing resolution, ruthlessly
stripping away information that can't possibly be rendered in the form we
want.

## IrFan View

IrFan View is a bit limited, but it does run under windows easily. The key process
is "Decrease Color Depth..." which can convert your silhouette into a proper two-
color black-and-white image. Unfortunately, it's not very adjustable.

Make sure to "Show Paint Dialog (F12)" Erase as much of the background garbage as possible.



## Inkscape

### Configuration

_Display_units_ is under the menu _Document Properties_. Switch between _inches_, _millimeters_, & as desired.

### Layers

I have been assigning different types of images to different layers [shift-ctrl-l].
The initial import is in a layer named "bitmap". Once traced, the outline is in a
layer called "trace". All the subsequent work, simplifying and framing, is in the
default layer. The "trace" and "bitmap" layers can be hidden by default, but returned
to as source material.


### Tracing an outline

* _Import_ ... png as bitmap.
* _Path -> Trace Bitmap_  Use "Speckles" to remove the background static
* _Object -> Transform_ to resize
* _Object -> Fill and Stroke_ to remove fill, add stroke color
* Use the _Edit Path_ tool to select
* _Path -> Simplify_ to reduce the number of points
* _Path -> Break Apart_ to separate the components (and delete the ones you don't want)


### Joining a pattern inside a frame.

For the fern project, I'm making 8 inch square tiles. The outer edge of the cut is
an 8 inch square, and the inner edge is a 7 3/4 inch square, so that the frame is
1/8 inch wide all around. These squares are made with the rectangle tool, which,
when the shape is created, offers a dimension box where you can enter the height
and width desired. The fern pattern must be joined with and connected to the inner
frame line.

To join the fern pattern with the inner square edge,use _Path -> Difference_.  Make sure
that the pattern is raised above the frame, _Object -> Raise to Top_. That way,
everything outside the frame is removed.

To make side-by-side panels, take two frames and group the *insides* of the two frames together
with _Path -> Combine Paths_. Group the *outsides* of the frames and move them aside.Then lay the pattern over it, selecting the pattern path plus the two insides, and again use _Difference_. Now move the outside frames back and align everything vertically or horizontally using _Align and Distribute_.

