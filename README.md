# sass-demo
- This is a simple demo of a responsive web using Sass for styling.
- Sass is a CSS pre-processor with syntax advancements. Style sheets in the advanced syntax are processed by the program, and turned into regular CSS style sheets. However, they do not extend the CSS standard itself.
CSS variables are supported and can be utilized but not as well as pre-processor variables.
- Tutorial: https://www.youtube.com/watch?v=roywYSEPSvc


## In this demo I've used
### variables
``` scss
$colors: (
    primary: blue,
    primary-light: lighten(blue, 40%),
    primary-dark: darken(blue, 40%),
    accent: yellow
);

$padding: (
    1rem
);
``` 

&nbsp;
### functions
``` scss
@function color($color-name){
    @return map-get($colors, $color-name)
};

background-color: color(primary);
```

&nbsp;
### nesting
``` scss
body {
    font-family: 'Monserrat';

    header a {
        padding: $padding;
    }
}
```

&nbsp;
### mixins
``` scss
@mixin dvesktop {
    @media(min-width: #{$desktop-screen-size}) {
        @content;
    }   
}

            @include desktop {
                display: inline-block;
                padding: $padding $padding * 4;
            }
```

&nbsp;
### layout

``` scss
    @include desktop {
        display: grid;
        grid-template-columns: 50% auto;
        grid-template-areas: "primary card";
    }
    
        @include desktop {
            grid-area: card;
            height: fit-content;
            align-self: center;
            margin-left: 1rem;
        }
        
        @include desktop {
            grid-area: primary;
            text-align: left;
            margin: 4rem 0 0 4rem;
        }
```
