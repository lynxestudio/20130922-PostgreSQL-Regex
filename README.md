# Regular Expressions (expresiones regulares) en PostgreSQL

<p align="justify">
Cuando las búsquedas con el operador <b>Like</b> no son lo suficientemente flexibles para localizar los registros que necesitamos, PostgreSQL permite las búsquedas de registos mediante el uso de regular expressions (expresiones regulares).
</p>
<p align="justify">
En este par de posts: Regular Expressions en PL/SQL Oracle, parte I y parte II  coloque unos ejemplos de la utilización de expresiones regulares en Oracle.</p>
<p align="justify">
Ahora utilizaré los mismos ejercicios de esas entradas, pero ahora para mostrar las regular expressions en PostgreSQL.
</p>
<p>
Creamos una tabla llamada <i>membership</i>:
</p>
<div>
<IMG src="images/">
</div>
<p>Ahora insertamos algunos registros con el script:</p>
<div>
<IMG src="images/fig1.png">
</div>
<p><b>El operador ~</b></p>
<p align="justify">Como primer ejemplo utilizamos el operador <b>~</b> (LIKE versión regular expression) en la consulta para buscar en la columna MEMBERSHIP_LASTNAME aquellos registros que empiecen con la letra
<i>D.</i></p>
<div>
<IMG src="images/query1.png">
</div>
<div>
<IMG src="images/fig2.png">
</div>
<p align="justify">
Aquí un segundo ejemplo en donde buscamos en la columna MEMBERSHIP_LASTNAME aquellos registros que comiencen con las letras de la <i>A</i> a la <i>F</i>.</p>
<div>
<IMG src="images/query2.png">
</div>
<div>
<IMG src="images/fig3.png">
</div>
<p><b>El operador inverso !</b></p>
<p>Ahora mostraré los ejemplos anteriores utilizando el operador inverso <b>!</b> o la negación del operador <b>~</b> para el primer ejemplo, esta consulta busca en la columna MEMBERSHIP_LASTNAME aquellos registros que no empiecen con la letra <i>D</i>.</p>
<div>
<IMG src="images/query3.png">
</div>
<div>
<IMG src="images/fig4.png">
</div>
<p>El mismo operador de negación para el segundo ejemplo, esta consulta busca en la columna MEMBERSHIP_LASTNAME aquellos registros que no empiecen con las letras de la <i>A</i> a la <i>F</i>.</p>
<div>
<IMG src="images/query4.png">
</div>
<div>
<IMG src="images/fig5.png">
</div>
<p><b>El operador case-insensitive *</b></p>
<p align="jusstify">Tanto <b>~</b> como <b>!</b> son case-sensitive, si necesitas que ambos operadores sean 
case-insensitive se combinan con el operador <b>*</b> , como en el ejemplo siguiente donde buscamos en la columna MEMBERSHIP_LASTNAME aquellos registros que después del primer caracter tenga la letra <i>O</i> mayúscula repetida una o más veces.
</p>
<div>
<IMG src="images/query5.png">
</div>
<div>
<IMG src="images/fig6.png">
</div>
<p align="justify">
Esta búsqueda no dio resultados porque excepto la primera letra de los registros en la columna MEMBERSHIP_LASTNAME el resto se encuentran en letras minúsculas, entonces para que la consulta encuentre resultados utilizamos el operador <b>*</b>.</p>
<div>
<IMG src="images/query6.png">
</div>
<div>
<IMG src="images/fig7.png">
</div>
<p>Ahora si la consulta anterior mostro los resultados.</p>
