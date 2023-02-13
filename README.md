## Css 

# ref mdn docs, frontend mentor, code pen

Descendence selector
.mainclass li {
    This mainclass is the preselector and li is the selector, the one with the right is always the actual elem we wana style
}
Child selector 
.mainclass > p {} --> will only target the child 

sibbling selector
ul ~ p {} will look for all the ul and the direct sibling (para) and style em

if diff tags shares the same class name and we wwana style only one then
p[class = "mainclass"]{} now this will apply only to the para, its kinda of and op

in the end.. tag, class, and id are totally sufficient for styling .

 common prop:
 if we wana give the same props vals b/w 2 class then we can separate em by comma
 .main1, .main2 {} this will avoid dry -- shared styles

or we can also provide diff class names and also give same class name for the shared props

<div class= "main1 shared"> this space b/w em is considered as the diff class 
.shared{}

# pseudo class 

we can use this to btn and based on the state the pseudo class will styled differenty, such as hovering
button:hover {} target the elem and in hover state apply styling

the concept of cascading is put all the style sheets together and the one with the more precedence win the rule and the remaining rule will not apply or strike out, this happens when we ve our local style sheet and the external style sheet come together.

there are 2 factors for determing the precedent of the css 
1. location of the css file  -- since the css reads from top to bottom the recent one wins 
2. the specificity of the css rule -- mostly the id prop wins, despite of its position/ location...least-tags , 2nd least classes, most- ids
3. mostly it will counts for the no.of id selectors and class selectors and then finally the no. of tag selectors .. this is the math 
4. Then the inline styles takes the precedence over anything else 
   <p styles = "color: blue">
5. finally the important kw will take more precedence, we can use this only if we wana overide the predefined css
   p {
    color : orage !important;
   }

## box model 

the main display prop are block, inline block, flex, and grid

 - the default type of most of the elem is block
 - unlike block elem, the inline elems only occupy the content of the div, and it does not respect the height and width
 - but the inline block elem will respect the height and width props

box 
 - the default type of box is content box
 - the border box we don't ve to calculate all the width or heighe we can just give the h and w valus -- if we add padding or border to the elem it ensures that the final width wont be change if we add 200px the padding and border 10 each and the final elem will still be 200 not included the padding and border
  box-sizing : border-box;  
- this box ssizing is very imp when we working with the grids, how much size we can give to the child elems to fit within the parent container etc..
- * -- is wildcard char basically saying we wana target every elem in the doc
  

  - the box model describes how much space an html elems occupy 
  - the space is heavily influenced by the box sizing prop
  - the space nd layout is heavily influenced by the display prop
  - all the other css props are supplementry to the box model concept

# position prop

this position prop are very handy when working with nav bar

position : fixed or static or sticky or absolute or relative;
width : 100 vw - view port width, and vh viewport height
- finally if we set relative position to the parent elem, then we can set absolute position to the child elems. if it don't ve relative positioin to the parent then it will position itself relative to the view port 

## css measurement units 

1. REM (font units) - if we set the font-size : 1rem; means its gon be 100% to the relative of the root elems font size - html{font-size : 16px;}, means 100% to the 16px which is 16px
2. Em (font units) - its almost as same as rem instead its relative to parent elem not to the root elem
3. pixel
4. percentage (for responsive designs) - instead of placing px for the width or height which can shrink as the display size changes, we can make % for them so they can stay as per the display changes ex - height :80% insted of 600px 
   - the percentages are relative to their container not relative to their entire web pages

# custom fonts 

when we re dealing with fonts there are 4 props we wana follow
1. font-family - takes 2 props 1st font fam, 2nd (sans-serif) is fallback font.. we can download from gogle fonts <link rel="stylesheet" href="./styles.css">
2. font-size : 16px;
3. font-weight : 900; for the thickness
4. line-height : 20px; space b/w each line in the para 
5. font-color : red; can define as hex, rgb and rgba .the a defines opacity val rgba(255, 255, 255, 1) 1- for 100% opacity sim 0.5 for 50% .. we can refer ADOBE color for diff option

# BG prop

the BG image ve couple of props - background-img : url(""); .. background-size: cover; will cover the whole container with the img
- background-repeat: no-repeat; the img wont be repeat
- backgroun-position: t, r, d, l

## systematic way to write css and html

1. how do we wana arrange these elems on page
2. how does the arrangement looks in the form of html
3. how can i use css to achieve the layout i imagined 
4. how should each elems be styled

"Inline-block" - when we make the inline block they respect within the white space with in the doc if we re bring two divs next to each other then the white space wont be happen becaz by default the div below the div considered as the white space. soln--- </div><div id="next div">
- the best practice would be when we use grid layout we won't be having this weird quirks
- when we ve inline elems they follow diff rule than the block elem. for ex prop like vertical-alingn: top; -- snap that to top
- we can use Box shadow generator tool (bunch of sites) to generate the cust box shadow effect
- overflow: hidden; --> when apply this prop to the parent container, its basically saying, if there is the child containers ve overflow border edges just hide it..it will give the nice border edge instead of squared one.
- For the relative elems .. sometimes the elems wont be fit next to each other one on top and one slightly bottom to fix this-- position: relative; top: -3px; will put the elem inline perfectly
- to remove the bulletins of ul ... ul{list-style: none}
- in the hower pseudoclass there is trans prop which will change the button size in hower state... button:hower{transform: scale(1.1);}

## Resposive web design

1. mobile first vs desktop first design

 - Break pts .. when we apply 700px and the screen gets smaller or bigger than the px of 700 width we wana apply diff css rule -- we can see our window width by >window.innerwidth
 - in general mobile devices ve widht of 320 to 480 px wide and tablets of 600 and 800 px 
 - Avaialable break pts -- xs: <576px, sm: >576, md: >768, lg: >992, xl: >1200, xxl : >1400..
 - ex - @media: (min-width: 576px){}.. there are diff media typs 1. all, 2. print, 3. screen, 4.speech -- we can use em like @media and screen (min-width: 576px)
 - the css have logical operators we can use in @media query ex - @media only screen (min-width: 500px) and (max-width: 700px){} -- means only screens with the size of these the rules apply.. and for this media quries the order is important as we know the css interpret from top to bottom..
 - the best practice is to use mobile first design rather than desktop first
  
  # REsponsive checklist 
  <img src="./responsive-checklist.png">

  ## FlexBox designs 

  The FlexBox is  a layout model for displaying items in a sigle dimension, either in a row or column.

  The Flexbox alon with css grid will provide a better model for doing css

  - The FlexBox will eleminate lot of frustrations in the layout and css .
  - As we re writing css there are 2 main comps 1. layout related props, 2. style related props 
  - Flexbox will help us out in the layout related props 
  - The relation b/w parent and child is imp bcoz the second we enable flexbox on a container all the child elems(direct child) in the container will become flex item.
  - ex - .class {display: flex}
  - flex container vs flex item - we can make a flex item a flex container which is inside the flex container(parent)
  
# Flex container props

1. diplay
2. flex-direction (by default its row and the props main axis (horizontal) and the cross axis(vertical))
3. justify-content
4. allign-items {has flex-start, flex-end, center, baseline, stretch etc}
5. align-content
6. flex-wrap (when we enable this the overflw items will properly alligned and wrped in the container) if the flex wrap is set to anything other than no wrap then we ve to use allign-content instead of allign-item -- this will tel the flexbox how to arrange the group of wrapped items with in the container

# Flex item props

1. align-self
2. order
3. flex-basis (by default its set to auto ) what that means is basically saying flexbox go ahead and look for the height and width prop, if it finds them respect the props.. if it don't find em go and set the flex items based on the inner content
4. flex-grow (by default its 0) and 1 will occupy the free space of the container
5. flex-shrink (by default its 1) so the each item will be equal overflow

sometimes we ll be dealing with both so we ve to use the combinations of this both for the sigle elem .

Refer the cheat sheet [flex cheat sheet](https://yoksel.github.io/flex-cheatsheet/).

when dealing with flex box we ve to be aware of the default props.

shorthand - {flex: 0 1 auto;} is eq of flex-grow, shrink, and basis. 

To influence the size of the individual flex item .flexitem1{align-self: start;}

# Flex item size

when there is unocuppoid space along the main axis of the flex container, the flex grow prop is come into play.

- By default if we wana allign things along the main axis (H), we wana use justify-content and if we wana align things along the cross axis we use align-item,
  
- similar to how we allocate empty space for the flex item we can also reduce the size of flex item by the amt of overflow that we ve...by using flex-shrink: 

"Flex-Basis" prop - we can also assign the px and % units to overide the width and height of our flex items, and its the reliable way to go with flex containers

# Grid 

[Grid Prop]("./../Grid_prop.png")

# order of the item

lets see the order of the items along the main axis of the flex container
- we can set the order on all the flex item and determine the order they re coming
- this will comes in handy when working with the media query
- Tne border radius --> trick to make a pics rounded -- border-radius: 50%;


### UI UX Design, wireframe mockup and design in figma

# Wireframing 

If we re planning to design something its a good idea to do wireframing, so that we and the client knows exactly what we re building, and how it works.\

- The wireFraming is a visual blueprint for how the website works and also the pages as themselves and it also works as a schema for the functionality of the s/m.
- we can use paper to sketch it out or some third party tools to achieve this.
  

### SASS, BEM Responsive design

Syntactically awesome style sheet and its a css preprocessor.. the file extn is .sass and its sim to the css w/o the braces just indentation and .scss is sim to the css
- in order to write our style we need a way to compile the sass to css  PP
  
<h1> sass partials </h1>
- for splitiing up the larger css and put them in subfolder

- in the index.scss file add @forward 'boilerplate'; -- this will load the style rules from boilerplate.scss

- and in our style.css file add @forward 'globals'; this will look for the index.scss file which is in our globals dir

"Variables" -- when we wana create a cust prop (var) it should start with double hypens -> .root{--bg-color: black;} 
- and to load this var in our css --> body {background-color: var(--background-color)}
- in addition to the sass cust var (in which css dont ve) we can use the js to change the css val after the website is loaded, ex color theme toggle dark 
- The default sass var will starts with $dollar sign
- to load the other sass partial as modules we ve to use @use followed by the file path

## Sass and Bem

The naming conv of the class name ex class = "grid__sidebar" this double uderscore is part of Bem (Block elem Modifier) approach to write the sass files..
- and to use that inside the parent nesting class ex - .grid {&__main {}} 

The BEM -- Block are the standalone elem and the Elems are the child items contained in the block.. and the modifiers are versions of either the block or the elems and we denote em with double --(hypen)

- The benefit of using bem is we dont ve style conflicts, it will helps to keep the class naem unique
- and if we ve to change the name of block from grid to something else we only need to change in one place 
- and finally bem is also used for the code organizatioin. ( means in our ex the class file and the block name is similar which will comes in handy when we re doing debugging)
- 
  

