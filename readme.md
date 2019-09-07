<section>

# FUNDAMENTOS DE PHP PARA DESARROLLO DE THEMES EN WORDPRESS

![Landing More Themes](screenshot_landing.png)

PHP (acrónimo recursivo de PHP: Hypertext Preprocessor) es un lenguaje de código abierto muy popular especialmente adecuado para el desarrollo web y que puede ser incrustado en HTML.


## PARA ESCRIBIR PHP
~~~html
<?php ?>
~~~

## USO DE COMENTARIOS
~~~html
<?php
//Comentarios en Line
/*Comentarios en Bloque/*
;?>
~~~

## SALIDA POR PANTALLA PHP
~~~html
<?php
	print 'Hola';
	echo  'Hola', 'Hola de nuevo';
?>
~~~

## VARIABLES TIPO CADENAS O STRING
~~~html
<?php
	$nombre 	= 'Roberto';
	$apellido   = 'Rojas';
	echo "$nombre, $apellido"; // imprime "Roberto, Rojas"

	$4nombre    = 'aun no';   // inválido; comienza con un número
	$_4nombre   = 'aun no';  // válido; comienza con un carácter de subrayado
?>
~~~

## VARIABLES TIPO NUMEROS INT
~~~html
<?php
	$x = 5985;
	var_dump(is_int($x));//Imprime bool(true)
	echo '</br>';
	$x = 59.85;//Imprime bool(false)
	var_dump(is_int($x));
?>
~~~

## VARIABLES TIPO NUMEROS FLOAT
~~~html
<?php
	$x = 10.365;
	var_dump(is_float($x));
?>
~~~

## ARRAYS
~~~html
<?php
	$cars = array("Volvo", "BMW", "Toyota");
	echo "I like " . $cars[0] . ", " . $cars[1] . " and " . $cars[2] . ".";
?>
~~~

## OPERADORES DE COMPARACIÓN
~~~html
==	Igual			$x == $y 
===	Identico		$x === $y 
!=	Distinto		$x != $y
<>	Distinto  		$x <> $y
!==	No es identico	$x !== $y
>	Mayor que		$x > $y
<	Menor que		$x < $y
>=	Mayor igual		$x >= $y
<=	Menor Igual 	$x <= $y
~~~

## OPERADORES DE INCREMENTO Y DECREMENTO
~~~html
++$x	Pre-incrementa
$x++	Post-incrementa
--$x	Pre-decrementa
$x--	Post-decrementa
~~~

## CONCATENAR VARIABLES
~~~html
<?php 
	$numeroUno = 18;
	$numeroDos = ' de Septiembre'
	echo '<h1>'.$numeroUno.$numeroDos.'</h1>';
?>
~~~

## ESTRUCTURA DE CONTROL MÁS UTILIZADAS EN WORDPRESS

### Condicional IF
~~~html
<?php
	$a = 100;
	$b = 0;
	if($a > $b){
	   echo "a es mayor que b";
	}
?>
~~~

### Bucle o Loop While
~~~html
<?php
	$a = 0;
	while($a <= 10){
	   $a++;
	   echo '<h1>'.$a.'</h1>';
	}
?>
~~~

### Bucle o Loop For
~~~html
<?php  
	for ($x = 0; $x <= 10; $x++) {
	  echo "The number is: $x <br>";
	}
?> 
~~~


# INICIO DE UN THEME BASICO

Descargar la plantilla del siguiente enlace:

[Bajar Themes themes-01-html5-Rocks](https://drive.google.com/file/d/1UXLah6ijtf2zys-NtgUpkCELisH6xth4/view?usp=sharing)

### Para crear un Theme desde cero, se necesita minimo:
~~~
	-wp-content/themes/themes_lab01
	|
	|– index.php  
	|– style.css
	|– screenshot.png
	|– function.php
~~~

### Taxonomía de un theme.
~~~
-wp-content/themes/themes_lab02
	|--img/
	|	|--img.jpg
	|	|--img.png
	|	|--img.gif
	|
	|--js/
	|	|--___.js--Archivos js que se requieren según la necesidad del proyecto
	|	|--___.js
	|	|--___.js
	|
	|--css/
	|	|--___.css--Archivos css que se requieren según la necesidad del proyecto
	|	|--___.css
	|	|--___.css
	|
	|– index.php--Pagina de inicio o de partida de un themes.
	|
	|– function.php--Guarda todas las funciones de worpdress. 
	|
	|– style.css--Hoja de estilo de la raiz del themes.
	|
	|– screenshot.png--Imagen 1200px de ancho por 900px de alto.
	|
	|– page.php--Muestra el detalle de la información de las páginas (page).
	|		|--page-nombre.php--Distintas plantillas de page,requieren comentario.
	|		|--page-nombre-de-la-plantilla.php
	|		|--page-nombre-de-la-plantilla.php
	|
	|– single.php--Muestra el detalle de la información de las publicaciones (post).
	|		|--single-nombre.php--Distintas plantillas de single,requieren comentario.
	|		|--single-nombre.php
	|		|--single-nombre.php
	|
	|– header.php--Contiene la información superior de head de mis páginas.
	|
	|– footer.php--Contiene la información del footer de mis páginas.
	|
	|– footer.php--Contiene la información del footer de mis páginas.
~~~

### COMETARIOS PLANTILLAS
#### page-nosotros.php
~~~html
/**
 * Template Name: Page Nosotros
 * Template Post Type: page
*/
~~~
#### single.php
~~~html
/*
 * Template Name: Single Default
 * Template Post Type: post
 */
~~~

#### single-servicios.php
~~~html
/*
 * Template Name: Single Servicios
 * Template Post Type: post
 */
~~~


# PARA LLAMAR AL HEAD (TIPO INCLUDE)
## URL DE REFERENCIA
`https://developer.wordpress.org/reference/functions/get_header/`

~~~html
<?php get_header();?>
~~~

# PARA LLAMAR AL SIDEBAR (TIPO INCLUDE)
## URL DE REFERENCIA
`https://developer.wordpress.org/reference/functions/get_sidebar/`

~~~html
<?php get_sidebar();?>
~~~

# PARA LLAMAR AL FOOTER (TIPO INCLUDE)
## URL DE REFERENCIA
`https://developer.wordpress.org/reference/functions/get_footer/`

~~~html
<?php get_footer();?>
~~~

# HEADER Y FOOTER HOOK

## URL DE REFERENCIA
`https://codex.wordpress.org/Function_Reference/wp_head`

~~~html
<?php 
 ...
    /* Siempre inserte wp_head() justo antes de cerrar el </head>
     * wp_head(), ayuda a que complementos como plugins inserten
     * sus estilos, jquey, script, complementos necesarios para su correcto funcionamiento.
     * También es importante para insertar correctamente los CSS JQURY y complemnetos del Themes,
     * desde una funcion desde el archivo function.php
     */
    wp_head();
 ?>
~~~

## URL DE REFERENCIA
`https://codex.wordpress.org/Function_Reference/wp_footer`

~~~html
<?php 
 ...
    /* Siempre inserte wp_footer() justo antes de cerrar el </body>
     * wp_head(), ayuda a que complementos como plugins inserten
     * sus estilos, jquey, script, complementos necesarios para su correcto funcionamiento.
     * También es importante para insertar correctamente los CSS JQURY y complemnetos del Themes,
     * desde una funcion desde el archivo function.php
     */
    wp_footer();
 ?>
~~~

## LOOP BASE DE WORDPRESS
~~~html
<?php 
// Si existe publicación.
if(have_posts()){
	//Muestra las publicaciones.
	while (have_posts()):the_post(); 
	{
		//get_the_title(), recupera el título de la publicación
		echo '<h1>'.get_the_title().'</h1>';

		//the_post_thumbnails(), recupera la imagen destacada.
		echo the_post_thumbnail('thumbnail','class=img');

		//Recupera la fecha de la publicación
		echo '<h5>'.get_the_date().'</h5>';

		// the_content(), recupera el contenido de la publicación.
		echo the_content();

		//the_excerpt(), recupera el resumen de la publicación.
		echo the_content();

		// get_the_permalink(), recupera el enlace permanente
		echo '<a href="'.get_the_permalink().'" target="_self" title="'.get_the_title().'">Ver publicación</a>';     
	}
	endwhile;
}else{
      echo '<h3>Lo sentimos no existe publicacion</h3>';
   }
?>
~~~

## POST_TYPE DE WORDPRESS CONDICIONADO A UNA CATEGORÍA
~~~html
<?php 

    $argsXXXX = array(
      'post_type'=>'xxxx',
       'category_name'  => 'xxxx'
       'posts_per_page' => -1,
       'orderby'        => 'title',
       'order'          => 'DEC',
    );

    $the_queryXXXX = new WP_Query($argsXXXX);
        while($the_queryXXXX->have_posts()) : $the_queryXXXX->the_post();
	        $category = get_the_category();
	        if(in_category('xxxx')){

	             echo $the_queryXXX->post->ID;
	             echo $the_queryXXX->post->post_title;
	             echo $the_queryXXX->post->ID;
	             echo $category[0]->cat_name;
	             echo get_the_date('j F, Y');

	        }
        endwhile;
        wp_reset_postdata();
?>

~~~

## LLAMADAS PARA OBTENER INFORMACIÓN GENERAL DEL SITIO
### URL DE REFERENCIA
`https://developer.wordpress.org/reference/functions/bloginfo/`
~~~html
- Título del Sitio

	<?php bloginfo('name');?>

- Descripción de la página

	<?php bloginfo('description');?>

- Para recuperar la ruta hacia la hoja de estilo "style.css", de la Raíz.

  <?php bloginfo('stylesheet_url');?> 
  Esto devuelve la sigiente dirección: http://localhost/wp_inicio/content/themes/themes_query_01/style.css

- Para recuperar la ruta hacia cualquier carpeta.

  <?php bloginfo('template_url');?>
  Esto devuelve la ruta hacia un recurso que se aloja en una carpeta
  
  #Ejemplos:
  <img src="<?php bloginfo('template_url');?>/img/logo.png" alt="Logo">
  http://localhost/wp_inicio/content/themes/themes_01/img/logo.png
  
  <script src="<?php bloginfo('template_url');?>/js/jquery.js"></script>
  http://localhost/wp_inicio/content/themes/themes_query_01/js/jquery.js

~~~


## CREAR UN POST_TYPE
~~~html

add_action( 'init', 'codex_book_init' );

function codex_book_init() {
    $labels = array(
        'name'               => _x( 'Books', 'post type general name', 'your-plugin-textdomain' ),
        'singular_name'      => _x( 'Book', 'post type singular name', 'your-plugin-textdomain' ),
        'menu_name'          => _x( 'Books', 'admin menu', 'your-plugin-textdomain' ),
        'name_admin_bar'     => _x( 'Book', 'add new on admin bar', 'your-plugin-textdomain' ),
        'add_new'            => _x( 'Add New', 'book', 'your-plugin-textdomain' ),
        'add_new_item'       => __( 'Add New Book', 'your-plugin-textdomain' ),
        'new_item'           => __( 'New Book', 'your-plugin-textdomain' ),
        'edit_item'          => __( 'Edit Book', 'your-plugin-textdomain' ),
        'view_item'          => __( 'View Book', 'your-plugin-textdomain' ),
        'all_items'          => __( 'All Books', 'your-plugin-textdomain' ),
        'search_items'       => __( 'Search Books', 'your-plugin-textdomain' ),
        'parent_item_colon'  => __( 'Parent Books:', 'your-plugin-textdomain' ),
        'not_found'          => __( 'No books found.', 'your-plugin-textdomain' ),
        'not_found_in_trash' => __( 'No books found in Trash.', 'your-plugin-textdomain' )
    );

    $args = array(
        'labels'             => $labels,
        'description'        => __( 'Description.', 'your-plugin-textdomain' ),
        'public'             => true,
        'publicly_queryable' => true,
        'show_ui'            => true,
        'show_in_menu'       => true,
        'query_var'          => true,
        'rewrite'            => array( 'slug' => 'book' ),
        'capability_type'    => 'page',
        'has_archive'        => true,
        'hierarchical'       => false,
        'menu_position'      => null,
        'supports'           => array('title','editor','author','thumbnail','excerpt','category'),
        'taxonomies'         => array( 'category' ),
    );

    register_post_type( 'book', $args );
}
~~~

## RECUPERAR LOS PAGE EN EL MENU DE NAVEGACION
~~~html

<?php wp_page_menu(
	array(
	// 0 (predeterminado) Muestra las páginas a cualquier profundidad y las organiza jerárquicamente en listas
anidadas
		'depth' => 0,
		// Ordena páginas por orden de páginas.
		'sort_column' => 'menu_order, post_title',
		//( cadena ) La clase div en la que se muestra la lista. Por defecto está en el menú .
		'menu_class' => 'menu',
		// Incluye los id ejemplo 3,7,31
		'include' => ' ',
		// Excluye los id ejemplo 3,7,31
		'exclude' => ' ',
		//( booleano ) Alterna la visualización de la lista generada de enlaces o devuelve la lista como
		    una cadena de texto HTML para usar en PHP. El valor predeterminado es 1 (Mostrar los elementos de la lista
		    generados). Valores válidos:
		'echo' => true,
		// ( booleano ) Agregue "Inicio" como primer elemento en la lista de "Páginas".
	    'show_home' => true,
		'link_before' => '',
		'link_after' => ''
	)
)
;?>
~~~


</section>
