---


---

<h1 id="prueba-linuxbash">Prueba Linux/Bash</h1>
<ol>
<li>
<p><strong>Crear una carpeta llamada “Scripts”:</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">mkdir</span> Scripts <span class="token operator">&amp;&amp;</span> <span class="token function">cd</span> Scripts 
</code></pre>
</li>
<li>
<p><strong>Crear un archivo txt dentro de la carpeta “Scripts”:</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">touch</span> archivo.txt
</code></pre>
</li>
<li>
<p><strong>Asignarle permisos de solo lectura al archivo:</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">chmod</span> 444 archivo.txt
</code></pre>
</li>
<li>
<p><strong>Copiar el archivo y modificar el nombre:</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">cp</span> archivo.txt archivo_copia.txt
</code></pre>
</li>
<li>
<p><strong>Asignarle al nuevo archivo permisos de escritura:</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">chmod</span> 644 archivo_copia.txt
</code></pre>
</li>
<li>
<p><strong>-Ingesta el siguiente texto dentro del primer archivo que se creo</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token keyword">echo</span> <span class="token string">"Apple Inc. es una empresa estadounidense que diseña y produce equipos electrónicos, software y..."</span> <span class="token operator">&gt;</span> archivo.txt
</code></pre>
</li>
<li>
<p><strong>Sacar el número de líneas que contiene el archivo</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">wc</span> -l archivo.txt
</code></pre>
</li>
<li>
<p><strong>Escribe el comando para buscar la palabra “Apple”</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">grep</span> <span class="token string">"Apple"</span> archivo.txt
</code></pre>
</li>
<li>
<p><strong>¿En qué extensión se almacenan los programas Shell y como se ejecutan?</strong></p>
<ul>
<li>Los scripts de shell suelen almacenarse con la extensión <code>.sh</code>.</li>
<li>Se ejecutan con el comando <code>bash script.sh</code> o asignándole permisos ejecutables <code>chmod +x script.sh</code> y luego <code>./script.sh</code>.</li>
</ul>
</li>
<li>
<p><strong>¿Se requiere un compilador separado para ejecutar un programa de shell?</strong></p>
<ul>
<li>No, los scripts de shell son interpretados, <strong>NO compilados</strong>, por lo que no se requiere un compilador.</li>
</ul>
</li>
<li>
<p><strong>¿Cuáles son los permisos predeterminados de un archivo cuando se crea?</strong></p>
<ul>
<li>Los permisos predeterminados son <code>rw-r--r--</code> o <code>644</code>, pero pueden variar según la configuración <code>umask</code></li>
</ul>
</li>
<li>
<p><strong>¿Qué son las variables de shell?</strong></p>
<ul>
<li>Son variables utilizadas en scripts de shell para almacenar valores temporales que pueden ser usados en el script.</li>
</ul>
</li>
<li>
<p><strong>¿Cómo se almacenan las variables de shell? Ejemplo sencillo:</strong><br>
Las variables shell se almacenan en la <strong>memoria RAM</strong> durante la ejecución del script</p>
<pre class=" language-bash"><code class="prism  language-bash">nombre<span class="token operator">=</span><span class="token string">"Juan"</span>
<span class="token keyword">echo</span> <span class="token string">"Hola, <span class="token variable">$nombre</span>"</span>
</code></pre>
</li>
<li>
<p><strong>¿Cuál es la vida útil de una variable dentro de un script de shell?</strong></p>
<ul>
<li>Una variable en un script de shell dura solo mientras se está ejecutando el script, a menos que sea exportada como <strong>variable de entorno</strong>.</li>
</ul>
</li>
<li>
<p><strong>Explicación breve de permisos en archivos y directorios:</strong></p>
<ul>
<li>Los permisos se dividen en lectura ( r ), escritura (w) y ejecución (x) y pueden aplicarse a propietarios, grupos y otros.</li>
</ul>
</li>
<li>
<p><strong>¿Qué son los bucles y explica brevemente tres métodos diferentes de bucles?</strong></p>
<ul>
<li>Los bucles permiten repetir una serie de comandos.
<ul>
<li><code>for</code>: Itera sobre una lista.</li>
<li><code>while</code>: Se ejecuta mientras una condición sea verdadera.</li>
<li><code>until</code>: Se ejecuta hasta que una condición se cumpla.</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>¿Que comando se utiliza para validar si un shell script se encuentra en ejecución?</strong></p>
<pre class=" language-bash"><code class="prism  language-bash">pgrep -f script.sh
</code></pre>
</li>
<li>
<p><strong>Explicación breve del comando <code>sed</code> con un ejemplo:</strong></p>
<ul>
<li><code>sed</code> es un editor de texto para buscar y reemplazar.</li>
</ul>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">sed</span> <span class="token string">'s/Apple/Microsoft/g'</span> archivo.txt
</code></pre>
</li>
<li>
<p><strong>Explicación breve del comando <code>awk</code> con un ejemplo:</strong></p>
<ul>
<li><code>awk</code> procesa y analiza texto.</li>
</ul>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">awk</span> <span class="token string">'{print <span class="token variable">$1</span>}'</span> archivo.txt
</code></pre>
</li>
<li>
<p><strong>Explique cuál es el resultado del siguiente comando cat script1 &gt; script2</strong></p>
<ul>
<li>Sobreescribe <code>script2</code> con el contenido de <code>script1</code>.</li>
</ul>
</li>
<li>
<p><strong>Explique cuál es el resultado del siguiente comando cat script3 &gt;&gt; script4:</strong></p>
<ul>
<li>Añade el contenido de <code>script3</code> al final de <code>script4</code>. <strong>Sin sobreescribir</strong> <code>script4</code></li>
</ul>
</li>
<li>
<p><strong>Comando para borrar el primer archivo creado:</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">rm</span> archivo.txt
</code></pre>
</li>
<li>
<p><strong>Comando para borrar todos los archivos y el directorio creado:</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">rm</span> -r Scripts
</code></pre>
</li>
<li>
<p><strong>Escriba el comando para buscar una cadena de texto dentro de un árbol de directorios y<br>
archivos</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">grep</span> -r <span class="token string">"cadena de texto"</span> /
</code></pre>
</li>
<li>
<p><strong>Escriba el comando para imprimir las primeras 50 líneas de un archivo</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">head</span> -n 50 archivo.txt
</code></pre>
</li>
<li>
<p><strong>Escriba el comando para imprimir las últimas 50 líneas de un archivo</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">tail</span> -n 50 archivo.txt
</code></pre>
</li>
<li>
<p><strong>Ciclo for que imprime de 10 en 10 hasta 100:</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token keyword">for</span> i <span class="token keyword">in</span> <span class="token punctuation">{</span>10<span class="token punctuation">..</span>100<span class="token punctuation">..</span>10<span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token keyword">do</span> <span class="token keyword">echo</span> <span class="token variable">$i</span><span class="token punctuation">;</span> <span class="token keyword">done</span>
</code></pre>
</li>
<li>
<p><strong>Escriba el comando para mandar a segundo plano o a background el siguiente Shell<br>
“Compras_brio.sh” con salida al log “Compras_brio.log”</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">touch</span> Compras_brio.sh <span class="token operator">&amp;&amp;</span> <span class="token function">chmod</span> +x Compras_brio.sh
./Compras_brio.sh <span class="token operator">&gt;</span> Compras_brio.log <span class="token operator">&amp;</span>
</code></pre>
</li>
<li>
<p><strong>Escribir el comando para eliminar/suprimir/terminar la ejecución de “Compras_brio.sh”</strong></p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">pkill</span> -f Compras_brio.sh
</code></pre>
</li>
<li>
<p><strong>Crear una aplicación que tome como variable 1 nombre 1 edad y esta me la mueste 10 veces<br>
en la pantalla , Escriba el comando para ejecutar la aplicación y mandarla a segundo plano con su<br>
respectivo log.</strong></p>
<ul>
<li>Código del script <code>vim mostrar.sh</code>:<pre class=" language-bash"><code class="prism  language-bash"><span class="token shebang important">#!/bin/bash</span>
<span class="token comment"># Este es el "shebang" - indica qué intérprete usar</span>

<span class="token comment"># Recibimos los parámetros</span>
nombre<span class="token operator">=</span><span class="token variable">$1</span>  <span class="token comment"># $1 recibe el primer argumento (nombre)</span>
edad<span class="token operator">=</span><span class="token variable">$2</span>  <span class="token comment"># $2 recibe el segundo argumento (edad)</span>

<span class="token keyword">for</span> i <span class="token keyword">in</span> <span class="token punctuation">{</span>1<span class="token punctuation">..</span>10<span class="token punctuation">}</span><span class="token punctuation">;</span> <span class="token keyword">do</span>
    <span class="token keyword">echo</span> <span class="token string">"Nombre: <span class="token variable">$nombre</span>, Edad: <span class="token variable">$edad</span>"</span>
<span class="token keyword">done</span>
</code></pre>
</li>
<li>Comando para ejecutar y mandar al background:<pre class=" language-bash"><code class="prism  language-bash">  ./mostrar.sh <span class="token string">"Nombre"</span> <span class="token string">"Edad"</span> <span class="token operator">&gt;</span> mostrar.log <span class="token operator">&amp;</span>
  <span class="token function">cat</span> mostrar.log  
</code></pre>
</li>
</ul>
</li>
</ol>
<h1 id="prueba-sql">Prueba SQL</h1>
<h2 id="parte-1">PARTE 1</h2>
<ol>
<li>
<p><strong>¿Qué es un inner join?</strong></p>
<ul>
<li>Combina filas de dos tablas donde hay coincidencia en ambas.</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> empleados<span class="token punctuation">.</span>nombre<span class="token punctuation">,</span> departamentos<span class="token punctuation">.</span>nombre
<span class="token keyword">FROM</span> empleados
<span class="token keyword">INNER</span> <span class="token keyword">JOIN</span> departamentos <span class="token keyword">ON</span> empleados<span class="token punctuation">.</span>departamento_id <span class="token operator">=</span> departamentos<span class="token punctuation">.</span>id<span class="token punctuation">;</span>
</code></pre>
</li>
<li>
<p><strong>¿Cuál es la diferencia entre un inner join y un left join?</strong></p>
<ul>
<li><code>INNER JOIN</code>: Solo filas con coincidencia en ambas tablas.</li>
<li><code>LEFT JOIN</code>: Todas las filas de la izquierda y coincidencias de la derecha (los no coincidentes serán <code>NULL</code>).</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> empleados<span class="token punctuation">.</span>nombre<span class="token punctuation">,</span> departamentos<span class="token punctuation">.</span>nombre
<span class="token keyword">FROM</span> empleados
<span class="token keyword">LEFT</span> <span class="token keyword">JOIN</span> departamentos <span class="token keyword">ON</span> empleados<span class="token punctuation">.</span>departamento_id <span class="token operator">=</span> departamentos<span class="token punctuation">.</span>id<span class="token punctuation">;</span>
</code></pre>
</li>
<li>
<p><strong>¿Cuál es la diferencia entre un right join y un left join?</strong></p>
<ul>
<li><code>LEFT JOIN</code>: Todo de la izquierda y coincidencias de la derecha.</li>
<li><code>RIGHT JOIN</code>: Todo de la derecha y coincidencias de la izquierda.</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> empleados<span class="token punctuation">.</span>nombre<span class="token punctuation">,</span> departamentos<span class="token punctuation">.</span>nombre
<span class="token keyword">FROM</span> empleados
<span class="token keyword">RIGHT</span> <span class="token keyword">JOIN</span> departamentos <span class="token keyword">ON</span> empleados<span class="token punctuation">.</span>departamento_id <span class="token operator">=</span> departamentos<span class="token punctuation">.</span>id<span class="token punctuation">;</span>
</code></pre>
</li>
<li>
<p><strong>¿Qué es un cross join?</strong></p>
<ul>
<li>Genera el producto cartesiano de ambas tablas (cada fila de una con cada fila de la otra).</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> empleados<span class="token punctuation">.</span>nombre<span class="token punctuation">,</span> proyectos<span class="token punctuation">.</span>nombre
<span class="token keyword">FROM</span> empleados
<span class="token keyword">CROSS</span> <span class="token keyword">JOIN</span> proyectos<span class="token punctuation">;</span>
</code></pre>
</li>
<li>
<p><strong>¿Cuál es la estructura de un CASE?</strong></p>
<ul>
<li>Evalúa condiciones y devuelve valores según el caso.</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> nombre<span class="token punctuation">,</span>
<span class="token keyword">CASE</span>
    <span class="token keyword">WHEN</span> salario <span class="token operator">&gt;</span> <span class="token number">5000</span> <span class="token keyword">THEN</span> <span class="token string">'Alto'</span>
    <span class="token keyword">ELSE</span> <span class="token string">'Bajo'</span>
<span class="token keyword">END</span> <span class="token keyword">AS</span> rango_salarial
<span class="token keyword">FROM</span> empleados<span class="token punctuation">;</span>
</code></pre>
</li>
</ol>
<h3 id="tabla-1">Tabla 1</h3>

<table>
<thead>
<tr>
<th>execution_id</th>
<th>organizacion_pais_id</th>
<th>planta_id</th>
<th>lineas_id</th>
<th>turno_id</th>
<th>producto_id</th>
<th>rubro_id</th>
<th>tipo_costo</th>
<th>value</th>
<th>tmoneda_id</th>
<th>storeday</th>
<th>entidadlegal_id</th>
<th>periodo</th>
</tr>
</thead>
<tbody>
<tr>
<td>44142</td>
<td>Iberia</td>
<td>724</td>
<td>1706</td>
<td>49053</td>
<td>1</td>
<td>78462</td>
<td>2_costo_operat</td>
<td>2098.8935</td>
<td>USD</td>
<td>2020-11-12</td>
<td>211</td>
<td>2020-09</td>
</tr>
<tr>
<td>44142</td>
<td>Iberia</td>
<td>724</td>
<td>1706</td>
<td>49053</td>
<td>1</td>
<td>78462</td>
<td>2_costo_estand</td>
<td>1807.7285</td>
<td>USD</td>
<td>2020-11-12</td>
<td>211</td>
<td>2020-09</td>
</tr>
<tr>
<td>44142</td>
<td>Iberia</td>
<td>724</td>
<td>1706</td>
<td>49053</td>
<td>1</td>
<td>78462</td>
<td>3_costo_estand</td>
<td>256.46685</td>
<td>USD</td>
<td>2020-11-12</td>
<td>211</td>
<td>2020-09</td>
</tr>
<tr>
<td>44142</td>
<td>Iberia</td>
<td>724</td>
<td>1706</td>
<td>49053</td>
<td>1</td>
<td>78462</td>
<td>4_costo_estand</td>
<td>120.11863</td>
<td>USD</td>
<td>2020-11-12</td>
<td>211</td>
<td>2020-09</td>
</tr>
<tr>
<td>44142</td>
<td>Iberia</td>
<td>724</td>
<td>1706</td>
<td>49053</td>
<td>1</td>
<td>78462</td>
<td>4_costo_operat</td>
<td>39.966181</td>
<td>EUR</td>
<td>2020-11-12</td>
<td>211</td>
<td>2020-09</td>
</tr>
<tr>
<td>44142</td>
<td>Iberia</td>
<td>724</td>
<td>1706</td>
<td>49053</td>
<td>1</td>
<td>78462</td>
<td>4_costo_estand</td>
<td>146.778108</td>
<td>USD</td>
<td>2020-11-12</td>
<td>211</td>
<td>2020-09</td>
</tr>
<tr>
<td>44142</td>
<td>Iberia</td>
<td>724</td>
<td>1706</td>
<td>49053</td>
<td>1</td>
<td>78462</td>
<td>5_costo_estand</td>
<td>325.426707</td>
<td>EUR</td>
<td>2020-11-12</td>
<td>211</td>
<td>2020-09</td>
</tr>
<tr>
<td>44142</td>
<td>Iberia</td>
<td>724</td>
<td>1706</td>
<td>49053</td>
<td>1</td>
<td>78462</td>
<td>5_costo_operat</td>
<td>837.137463</td>
<td>EUR</td>
<td>2020-11-12</td>
<td>211</td>
<td>2020-09</td>
</tr>
</tbody>
</table><ol start="6">
<li><strong>Escriba el query que me muestre únicamente los datos planta, producto_id, periodo y sumarizar el value con<br>
los filtros tmoneda_id USD y que entren en el rubro_id numero 3</strong></li>
</ol>
<pre class=" language-bash"><code class="prism  language-bash">SELECT 
    planta_id, 
    producto_id, 
    periodo, 
    SUM<span class="token punctuation">(</span>value<span class="token punctuation">)</span> AS total_value
FROM 
    tabla
WHERE 
    tmoneda_id <span class="token operator">=</span> <span class="token string">'USD'</span> 
    AND rubro_id <span class="token operator">=</span> 3
GROUP BY 
    planta_id, 
    producto_id, 
    periodo<span class="token punctuation">;</span>
</code></pre>
<ol start="7">
<li><strong>Escribe el query donde si la moneda es EUR en tipo costo me aparezca null</strong></li>
</ol>
<pre class=" language-bash"><code class="prism  language-bash">SELECT 
    planta_id, 
    producto_id, 
    periodo, 
    value, 
    CASE 
        WHEN tmoneda_id <span class="token operator">=</span> <span class="token string">'EUR'</span> THEN NULL 
        ELSE tipo_costo 
    END AS tipo_costo
FROM 
    tabla<span class="token punctuation">;</span>
</code></pre>
<ol start="8">
<li><strong>Escribe el query donde si mi value es null me ponga un 0</strong></li>
</ol>
<pre class=" language-bash"><code class="prism  language-bash">SELECT 
    planta_id, 
    producto_id, 
    periodo, 
    COALESCE<span class="token punctuation">(</span>value, 0<span class="token punctuation">)</span> AS value
FROM 
    tabla<span class="token punctuation">;</span>

</code></pre>
<h2 id="parte-2">PARTE 2</h2>
<p>Se tienen las siguientes tablas que contienen información referente hacia los vuelos que se realizan<br>
en México</p>
<h2 id="parte-3">PARTE 3</h2>
<p>Escribir las sentencias completas para los siguientes incisos</p>
<p>a) <strong>Castear la columna <code>value</code> a <code>FLOAT</code>:</strong></p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> 
    CAST<span class="token punctuation">(</span><span class="token keyword">value</span> <span class="token keyword">AS</span> <span class="token keyword">FLOAT</span><span class="token punctuation">)</span> <span class="token keyword">AS</span> value_float
<span class="token keyword">FROM</span> 
    tabla<span class="token punctuation">;</span>
</code></pre>
<p>b) <strong>Castear la columna <code>fecha</code> al formato <code>YYYY-MM-DD</code>:</strong></p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> 
    TO_CHAR<span class="token punctuation">(</span>fecha<span class="token punctuation">,</span> <span class="token string">'YYYY-MM-DD'</span><span class="token punctuation">)</span> <span class="token keyword">AS</span> fecha_formato
<span class="token keyword">FROM</span> 
    tabla<span class="token punctuation">;</span>
</code></pre>
<p>c) <strong>Obtener únicamente el mes de la columna <code>fecha</code>:</strong></p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> 
    EXTRACT<span class="token punctuation">(</span>MONTH <span class="token keyword">FROM</span> fecha<span class="token punctuation">)</span> <span class="token keyword">AS</span> mes
<span class="token keyword">FROM</span> 
    tabla<span class="token punctuation">;</span>
</code></pre>
<p>d) <strong>Dividir la cadena y mostrar solo los números en <code>ADGO-1974-G&amp;HF</code>:</strong></p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> 
    REGEXP_SUBSTR<span class="token punctuation">(</span><span class="token string">'ADGO-1974-G&amp;HF'</span><span class="token punctuation">,</span> <span class="token string">'[0-9]+'</span><span class="token punctuation">)</span> <span class="token keyword">AS</span> numeros
<span class="token keyword">FROM</span> 
    tabla<span class="token punctuation">;</span>
</code></pre>
<p>e) <strong>Obtener todos los resultados de la columna <code>transaccion</code> que contengan la palabra “ADGO”:</strong></p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> 
    transaccion
<span class="token keyword">FROM</span> 
    tabla
<span class="token keyword">WHERE</span> 
    transaccion <span class="token operator">LIKE</span> <span class="token string">'%ADGO%'</span><span class="token punctuation">;</span>
</code></pre>
<p>f) <strong>Concatenar las cadenas “tu nombre”, “tu edad” y “tus apellidos”:</strong></p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> 
    CONCAT<span class="token punctuation">(</span><span class="token string">'tu nombre'</span><span class="token punctuation">,</span> <span class="token string">' '</span><span class="token punctuation">,</span> <span class="token string">'tu edad'</span><span class="token punctuation">,</span> <span class="token string">' '</span><span class="token punctuation">,</span> <span class="token string">'tus apellidos'</span><span class="token punctuation">)</span> <span class="token keyword">AS</span> informacion
<span class="token keyword">FROM</span> 
    tabla<span class="token punctuation">;</span>
</code></pre>
<p>g) <strong>Pasar a mayúsculas todos los datos de la columna <code>producto</code>:</strong></p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> 
    UPPER<span class="token punctuation">(</span>producto<span class="token punctuation">)</span> <span class="token keyword">AS</span> producto_mayusculas
<span class="token keyword">FROM</span> 
    tabla<span class="token punctuation">;</span>
</code></pre>

