# Cheat Sheet - Sass

# Set Up


 - ordenar la estructura de archivos -> sass/main.scss - css/main.css

 - Link css to html

 - Tengo que usar un modulo de npm entonces nesacito hacer primero ---> npm init 

 - Ahora puedo instalar node-sass por npm

 - añadir el comando al script
 `"scripts": {
  "scss": "node-sass --watch scss -o css"
}`
 

 -- node sass is the module, -- watch is the optional key to recompile every time there is a change. Scss is the folder with our sass code, -o and css is the output folder


- npm run sass

# Nesting

- Podemos poner clases dentro de clases, se llama nesting.
 - `.parent{
    height: 100%;
    .child{
      background: black;
    }`  

Background(main): podemos nest properties de shorthands como asi

`main{
  height: 100vh;
  background: {
    color: green
  }`
 
 # Variables
 
`$main: grey;
$border: 2px solid white;`

`main{
  border: $border
  background: {
    color: $main
  }`
 
 # Mixins
 
- Como variables pero por estilos más grandes .
- Los aceptan parámetros como funciones en JS
- tu puedes pasar parámetros por default con : 

`@mixin flex-center($direction: row) {
  display: flex;
  flex-direction: $direction;
  justify-content: space-around;
  align-items: center;
}`

# Extending

- como inheritance en js podemos tomar las propiedades de otras clases

`.lemon{
      border: {
        radius: 50px 15px 50px 15px;
        width: 2px;
      }
    }
    .lime{
      @extend .lemon;
      background: yellowgreen;
    }
`
# & keyword - ampersand

- El & siempre se refiere al selector principal cuando se anida. Piense en el & como eliminado y reemplazado con el selector padre
![alt text](https://css-tricks.com/wp-content/uploads/2016/01/scss-to-css.gif)
- Normalmente, lo usamos para psuedo-selectores.

`.lemon{
      transition-duration: 2s;
      &:hover{
        transform: rotate(360deg) scale(3);
        transition-duration: 2s;
        }
 }`
# Structura de carpetas


- Components e.g _buttons.scss, carasoul.scss

- Helpers e.g _variables.scss, _functions.scss

- Layout e.g _grid.scss, _header.scss, _footer.scss

 - Pages e.g _home.scss, _contact.scss

- Main

# Tips

 - Create mixins that take an argument 
- Otherwise extend
- always check the css output to see what your getting


 


  
  
