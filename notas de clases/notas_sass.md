# Instalar SASS

1. Principal tener intalado NODE.JS
2. Crear un carpeta "SCSS" y dentro un archivo ".scss"
3. En la terminal ejecutamos el comando "npm init" para que crear el archivo .json
4. Ejecutamos el comando "npm install -g sass"
5. Y por ultimo para iniciar la compilación ejecutamos el comando "sass --watch scss:css"

6. Al ejecutar el comando del punto .5 tienen que estar en la carpeta donde esta creado las carpetas scss y css. Del caso contrario tira error

## Escritura de scss

    ul {
        list-style: none;
            
            li {
                padding: 15px;
                display: inline-block;
                
                a {
                    text-decoration: none;
                    font-size: 16px;
                    color: #444;
                }
            }
        }

## Escritrua en css

    ul {
        list-style: none;
        }

    ul li {
            padding: 15px;
            display: inline-block;
        }

    ul li a {
            text-decoration: none;
            font-size: 16px;
            color: #444;
        }

# El &, es un selector especial 
>Agregar una pseudoclase o agregar un selector antes del padre.

>SCSS:

    li {
    color:blue;

        &:hover{
        color:red;
            }
        }

>CSS:

    li {
    olor:blue;
        }
        li:hover {
                color:red;
            }

# Variables en SCSS
>Las variables son una manera de guardar información que necesites reutilizar en tus hojas de estilos: colores, dimensiones, fuentes o cualquier otro valor.

>SCSS: 

    /* Variables */
    $title-font: normal 24px/1.5 'Open Sans', sans-serif;
    $cool-red: #F44336;
    $box-shadow-bottom-only: 0 2px 1px 0 rgba(0,0, 0, 0.2);
    
    /* SCSS*/
    h1.title {
            font: $title-font; /* Uso la variable*/
            color: $cool-red;
            }
    div.container {
            color: $cool-red;
            background: #fff;
            width: 100%;
            box-shadow: $box-shadow-bottom-only;
            }

>CSS:

    h1.title {
        font: normal 24px/1.5 "Open Sans", sans-serif;
        color: #F44336;
    }
    div.container {
        color: #F44336;
        background: #fff;
        width: 100%;
        box-shadow: 0 2px 1px 0 rgba(0, 0, 0,0.2);
       }

# Operaciones numericas
>Puedes hacer calculos matematicos en las variables
>SCSS
    $ancho: 720px;
    $blue: #4285F4;
    $green: #33D374;

    .box_uno {
    background-color: $blue;
    width: $ancho/2;    ---->   /* Ancho de 360*/
    }

    .box_dos {
    background-color: $green;
    width: ($ancho/2)-50;
    }

>CSS: 
    .box_uno {
        background-color:
        #4285f4;
        width: 360px;  ----> /* La divicion anterior */
        }
    .box_dos {
        background-color: #33d374;
        width: 310px;
    }

# Import
>puedes usar @import para incluir la fuente de tus archivos individuales en una hoja de estilo maestra.

    @import "estructura";
    @import "colores";
    @import "tipografia";

>¡importante! cada archivo scss debe tener “_” (guión bajo) al principio del nombre. Ej: _colores.scss.
>Con esto puedes llevar tu otros scss al scss principal donde se unen todos los css en un solo archivo