Blueprint is a document language like HTML. it's pretty basic

Glint is a styling language like CSS. also pretty basic

Sparks for reactive stuff maybe but just a name I'm throwing out there

---

so, Glint...

# basic properties

### `color`

sets the color of the target element; can be `red`, `green`, `blue`, `black`, `white`, `grey`, `magenta`, `yellow`, or `cyan`

if multiple color keywords are within this property, they will be averaged together

for example, `color: red blue` will color the selected element halfway between `red` and `blue`

---

### `align`

aligns the target element within its parent; can be `left`, `bottom-left`, `bottom`, `bottom-right`, `right`, `top-right`, `top`, or `top-left`

if multiple alignment keywords are within this property, they will be averaged together

for example, `align: bottom-left left` will align the selected element halfway between `bottom-left` and `left`

---

here's a basic document (document.bp):

```blueprint
!styles styles.glnt

document

    text "text element showcase" end
    
    block (red) -- block with class "red" and "left"
        text (left)
            "text inside block"
        end
    end

end
```

and styles (styles.glnt):

```Glint

-- here's a comment

?red: -- select all elements of type "red"
    color: red
end

?left: -- select all elements of type "left"
    align: left   
end

-- "block block" will select all blocks inside of another block
-- "*" will select everything

```


