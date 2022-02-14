//Variables utiles 
//Precio base de la cotización, en quetzales, lo puede cambiar
var precio_base = 2000

//Valores de los recargos 
var edad_18 = 0.1; // 10%
var edad_25 = 0.2; // 20%
var edad_50 = 0.3; // 30%

var casado_18 = 0.1; // 10%
var casado_25 = 0.2; // 20%
var casado_50 = 0.3; // 30%

var hijos_recargo = 0.2; // 20%


//Recargo
var recargo = 0
var recargo_conyugue = 0
var recargo_hijos = 0
var recargo_total = 0

//Precio final 
var precio_final = 0


//Mensajes de alerta para ingresar datos 
nombre = prompt("Ingrese su nombre, por favor (Si desea salir ingrese la palabra Salir)")

var edad = prompt("¿Cuantos años tiene? Ingrese solamente números ")
//convirtiendo edad a numero
var edad_numero = parseInt(edad)

var casado = prompt("¿Está casado actualmente?")
//Comprobamos la edad del cónyuge, solamente si se está casado/a
var edad_conyugue
if("SI" == casado.toUpperCase()){
  edad_conyugue = prompt("¿Que edad tiene su esposo/a?", "si/no")
  //convirtiendo edad de conyugue a numero
  var edad_conyugue_numero = (parseInt(edad_conyugue))
}

var hijos = prompt("¿Tiene hijos o hijas?")
//Comprobamos la cantidad de hijos solamente si los tienen
if ("SI" == hijos.toUpperCase()){
var cantidad_hijos = prompt ("Cuantos hijos tiene?")
//convirtiendo el numero de hijos a numero
var cantidad_hijos_numero = parseInt(cantidad_hijos)
}

//1. Aquí debe calcular el recargo total basado en las respuestas ingresadas
//Aquí es donde debe de calcular los recargos y el valor final
//Ejemplo (Debe completar los condicionales): Recargo por edad del asegurado 
if(edad_numero>=18 && edad_numero<25){
  //Calculamos el recargo en base a la edad 
  recargo = precio_base * edad_18
  /*Sumamos todos los recargos que hemos obtenido
  recargo_total = recargo_total + recargo
  */
}
//aqui puede colocar un else if() con el siguiente rango
if(edad_numero>=25 && edad_numero<50){
  recargo = precio_base * edad_25
}
if(edad_numero>=50){
  recargo = precio_base * edad_50
}

// 2. recargo por la edad del conyugue
if(edad_conyugue_numero>=18 && edad_conyugue_numero<25){
  recargo_conyugue = precio_base * casado_18
}

if(edad_conyugue_numero>=25 && edad_conyugue_numero <50){
  recargo_conyugue = precio_base * casado_25
}

if(edad_conyugue_numero>=50){
  recargo_conyugue = precio_base * casado_50
}

// 3. Recargo por la cantidad de hijos 
if (cantidad_hijos_numero > 0 ){
recargo_hijos = precio_base * hijos_recargo * cantidad_hijos_numero
}

// Calculo de recargos y de precio final
recargo_total = recargo + recargo_conyugue + recargo_hijos
precio_final = precio_base + recargo_total

//Resultado
alert ("Para el asegurado "+nombre)

if (recargo_total > 0){
  alert ("El recargo total sera de:"+
       "\nRecargo por edad del solicitante: "+recargo+
       "\nRecargo por conyugue: "+recargo_conyugue+
       "\nRecargo por hijos: "+recargo_hijos)
} else {
  alert ("No hay recargos extras")
}

alert ("El precio total sera de: "+precio_final)

