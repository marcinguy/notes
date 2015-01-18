# Auto layout

An _attribute_ is one of

1. left
2. leading
3. right
4. trailing
5. top
6. bottom
7. width
8. height
9. centerX
10. centerY
11. baseline

* trailing and leading do the right thing when the language direction changes (unlike left and right)

## Anatomy of a constraint

* Type (one of the attributes above)
    * seems to be akin to "algorithm"
* First item
* Relation
* Second item
    * Not on all constraints have a second item e.g. "Width constraint" does not have one
* Constant
* Priority
    * Higher priority constraints are satisfied first
* Mutliplier
* Placeholder
* installed
    * yes|no


* Examples of types

* Horizontal space
* Vertical space
* Equal widths
* Equal heights
* Top alignment


Things that can be an "item" in a constraint

* View width
* View horizontal center
* View vertical center
* View height
* Layout guide bottom

* Note that the item is not the "view" itself - it is an attribute of the view
* The page has to be able to solve the equation for the width, height, x, y of
  every box on the page.
* Xcode has ways to make constraints for multiple things at the same time but
  each constraint is between exactly two things
Constraints are cumulative, and do not override each other.
* Constraints can cross the view heirarchy but there can be "barriers" e.g. ???
* _Leaf views_ like buttons have an "instrinsic size"
    * tells the layout system that the view contians some content that it does
      not "understand" so it has to go off the intrinsic dimensions
* You can add/remove/edit constraints at run-time using the controller

When you first drag an element onto the storyboard it has no constraints. When
you build, Xcode will fix the element's width, height and pin its posistion
relative to the top left corner of the superview.