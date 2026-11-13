# Navbar

## Alighn links to right

to get all links to far right use

 <ul class="navbar-nav ms-auto">

 ## Images

 make sure to have correct directory so it is pointing to the right direction e.g. 

 STATIC_URL = '/static/'

STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
STATICFILES_DIRS = [os.path.join(BASE_DIR, 'new_portfolio', 'static')]


## cards 

make all cards same length on all sizes  set also height 100%

``` bash
    min-height: 280px;
    height: 100%;
    min-width: 200px;
```

## Navbar

To make navigation stick add:

```bash
fixed-top
```

## making a vertical timeline:

# create the timeline container 

```bash

    <div class="timeline">
        <div class="timeline-content>
            <h4>lorem impsum</h4>
            <p>lorem impsum</p>
        </div>
    </div>

```

- CSS	Meaning::

.timeline:  Main container and positioning reference
.timeline-content: Holds the heading and paragraph
h4: heading of milestone
p: text in each milestome

# position and style the timeline (example)

```bash
.timeline {
    position: relative;
    max-width: 850px;
    margin: 50px auto;}

```
CSS	Meaning:

position: relative	Establishes a positioning reference for absolute elements inside it

max-width: 850px	Prevents the timeline becoming too wide

margin: 50px auto	Adds 50px vertical spacing and centres the container horizontally

* position: relative does not automatically move container. It establishes a reference point for positioned descendants


# draw vertical line using ::before

```bash

.timeline::before {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    width: 2px;
    background-color: #c9b8aa;}

```
CSS	Meaning:

::before	Creates a pseudo-element before the container's content

content: ""	Generates an empty decorative element

position: absolute	Allows precise positioning

left: 0	Places it at the left edge

top: 0	Starts at the top

bottom: 0	Extends to the bottom

width: 2px	Makes it 2px thick

background-color	Gives it a colour

* ::before and ::after are pseudo-elements. They let CSS create decorative elements without adding extra HTML

# create space between the line and text
```bash

.timeline-content {
    padding-left: 35px;}

```
* We need it because without it the text could sit too close to it and overlap it

# add timeline points
We want a dot besides each milestone heading

First, make each heading a positioning reference:
```bash
.timeline-content h4 {
    position: relative;}
```

Then create circle or any other shape using ::after:

```bash

.timeline-content h4::after {
    content: "";
    position: absolute;
    left: -42px;
    top: 5px;
    width: 14px;
    height: 14px;
    border-radius: 50%;
    background-color: #c9b8aa;}

```
CSS	Meaning:

position: relative	Makes the heading the reference point

::after	Creates the decorative dot

position: absolute	Allows us to position the dot

left: -42px	Moves the dot to the left of the heading

top: 5px	Adjusts its vertical position

width: 14px	Sets its width

height: 14px	Sets its height

border-radius: 50%	Turns the square into a circle

The negative value in left means we move the dot outside the heading's left edge.

# Add some space between Milestones

```bash

.timeline-content h4 {
    margin-bottom: 12px;
}

.timeline-content p {
    margin-bottom: 35px;
}

```
Also can style the headings:
```bash

.timeline-content h4 {
    font-family: var(--secondary-font);
    font-size: 1.2rem;
    font-weight: 700;
}

```

# Complete timeline CSS:

```bash

# /* Main timeline container */
.timeline {
    position: relative;
    max-width: 850px;
    margin: 50px auto;
}

# /* Vertical line */
.timeline::before {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    width: 2px;
    background-color: #c9b8aa;
}

# /* Timeline text area */
.timeline-content {
    padding-left: 35px;
}

# /* Milestone headings */
.timeline-content h4 {
    position: relative;
    font-family: var(--secondary-font);
    font-size: 1.2rem;
    font-weight: 700;
    margin-bottom: 12px;
}

# /* Circular timeline points */
.timeline-content h4::after {
    content: "";
    position: absolute;
    left: -42px;
    top: 5px;
    width: 14px;
    height: 14px;
    border-radius: 50%;
    background-color: #c9b8aa;
}

# /* Paragraph spacing */
.timeline-content p {
    margin-bottom: 35px;
}
```
# Things to remember:

position:   relative	Establishes a reference point

position:   absolute	Positions an element relative to its nearest positioned ancestor

::before	Creates a pseudo-element before content

::after	Creates a pseudo-element after content
content: ""	Generates an empty decorative pseudo-element

padding	Space inside an element

margin	Space outside an element

transform	Rotates, scales or moves an element

border-radius	Rounds corners or creates circles

Negative positioning	Moves an element beyond its normal reference edge

## making shapes with transform

# transform:

```bash
transform: rotate(45deg);
transform: rotate(98deg);
transform: scale(1.2);
transform: translateX(10px);
transform: translateY(10px);
```

rotate()    turns element
scale()     makes it larger or smaller
translateX  moves horizontally
translateY  moves vertically


# shapes:

Circle: border-radius: 50%

Square: width + height

Diamond: rotate(45deg)

Triangle: clip-path

Pill: border-radius

Star: polygon

# creating star

```bash 
.star {
    width: 50px;
    height: 50px;
    background-color: #c9b8aa;
    clip-path: polygon(
        50% 0%,
        61% 35%,
        98% 35%,
        68% 57%,
        79% 91%,
        50% 70%,
        21% 91%,
        32% 57%,
        2% 35%,
        39% 35%
    );
}
```
What does clip-path mean?

- polygon() creates a shape from a list of points.
- Each percentage represents a position inside the element.
- 50% 0% means halfway across and right at the top.
- 98% 35% means almost all the way across and 35% down.

* the star is made from 10 points joined together