# Asctuces CSS

- ## Footer qui reste en bas et 

 ```css
body {
    min-height: 100vh;
    margin: 0;
    display: grid;
    grid-template-rows: auto 1fr auto;
}

header {
    min-height: 50px;
}

footer {
    min-height: 50px;
}
 ```

- ## Unitées

 1. On peut modifier les CSS units en faisant des calculs EX:
 
 ```css
 height: calc(100vh - 50px); 
 ```
 
  