spec
====

spec es una extensión de jQuery que te permite designar zonas de especificidad en un texto. De esa forma, se le puede dar control al usuario sobre qué tan corto y resumido o qué tan extenso y específico prefiere que sea el texto, sin pérdidas de cohesión ni coherencia.

El truco está en marcar el texto asignando niveles de especificidad. De esa manera, cuanto más texto pide el usuario, mostramos los fragmentos más específicos, y cuanto menos texto pide el usuario, vamos escondiendo del más específico al menos específico, hasta que sólo queda una noción vaga del artículo.

Esto se hace mediante etiquetas html5. Así se ve un texto html con spec:

  <spec>
  <spec0>
  
  <h1>Oso panda</h1>
  
  <spec10><big>Panda gigante</big></spec10>
  
  <p>
  
  	El <i>oso panda</i><spec3> o <i>panda gigante</i></spec3><spec9> ('Ailuropoda melanoleuca')</spec9> es una especie <spec3>de mamífero del orden de los carnívoros <spec10>y, aunque hay una gran controversia al respecto, los últimos estudios de su ADN lo engloban entre los</spec10> miembros </spec3>de la familia de los osos<spec5> (<i>Ursidae</i>)</spec5><spec15>, siendo el oso de anteojos su pariente más cercano<spec18>, si bien este pertenece a la subfamilia de los tremarctinos</spec18></spec15>. <spec7>Por otro lado, el panda rojo pertenece a una familia propia e independiente: <i>Ailuridae</i>. </spec7>Nativo de China central<spec5>, el panda gigante habita en regiones montañosas como Sichuan y el Tíbet<spec9>, hasta una altura de 3500m</spec9></spec5>. 
  
  </p>
  
  <spec5>
  <p>
  
  	Está en peligro de extinción; la especie está muy localizada. <spec10>Con 1600 viviendo en las selvas y 188 en cautiverio <spec20>(estadísticas 2004 - 2005)</spec20>, informes demuestran que la cifra de pandas viviendo en libertad va en aumento.</spec10> El oso panda es el símbolo de WWF <spec15>(Fondo mundial para la protección de la naturaleza) </spec15>desde 1961. 
  
  </p>
  </spec5>
  
  <spec9>
  <p>
  	El principal alimento del panda es el bambú<spec15> (en torno al 99% de su dieta)</spec15>, aunque también se alimenta de frutos, pequeños mamíferos, peces, e insectos. Es un buen trepador<spec5>, aunque rara vez se le ve en los árboles</spec5>.<spec10> Se adapta a la cautividad y gracias a su pelaje soporta fácilmente las condiciones invernales de su hábitat.</spec10>
  
  </p>
  </spec9>
  
  </spec0>
  </spec>



Uso avanzado
------------

spec también admite cláusulas negativas. Es decir, etiquetas para un contenido que se debe mostrar debajo de un nivel de especificidad. Esto se puede lograr así:

  <spec>
  <spec0>
  <p>
  	El <i>oso panda</i> es <spec-1>un oso</spec-1><spec1>una especie <spec3>de mamífero del orden de los carnívoros <spec10>y, aunque hay una gran controversia al respecto, los últimos estudios de su ADN lo engloban entre los</spec10> miembros </spec3>de la familia de los osos</spec1>.
  </p>
  </spec0>
  </spec>

spec se inicia automáticamente sobre todos los elementos <spec>, pero si se desea, se lo puede llamar sobre cualquier elemento:

  <script>
      $('.spec').spec();
  </script>



Instalación
-----------

spec funciona sobre jQuery . Para implementarlo, basta incluir las librerías en este orden:

<head>
    <script src="jquery-1.8.2.js"></script>
    <script src="spec.js"></script>
</head>
