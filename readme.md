## 2017-05-11  v8
* new feature: copy estilos
* informe oe

## 2017-05-03  v7
* frm OE
	* para copiar add:  frame, btn, cBox
	* code not in list cbEstilo, add newRec/controls enable/move next field

## 2017-04-26  V6
* frm cortes, sirvió solo para discutir en la planta y darme una idea mejor

## 2017-04-19  V5
* campos tiempo/precio se movieron de la tabla "oe" a la table "operaciones"
* los campos tiempo y precio ahora son "currency" para no tener problemas de redondeo en los calculos posteriores
* se formatearon tiempo/precio en sub form: operaciones/oe.
* form "oe" tiempo/precio se bloquearon (enabled: no)
* form "oe" data: agregar tabla "operaciones" y relacionar.
* form "oe" data:  left join, para que al insertar aparezca el nuevo registro
* form "oe" sort por sec.

## 2017-04-12  V4
* OE - operaciones por estilo
	* icono "+" inserta operaciones
	* icono "-" elimina operacion
	* fix: al cambiar una operacion, ya no le cambia la secuencia

## 2017-04-05  V3
* OE
  * tabla ( estiloID y operacionID - DataType LOOKUP WIZARD )
  * form ( cbEstilo AfterUpdate filtra regs, operacionID cBox AfterUpdate numera secuencia y asigna estilo )
  * textbox como var auxiliar usando "FUNCION SQL AGREGATE" para obtener MAX(estiloID)

## 2017-03-29  V2
* fix: ya no tengo que dar enter + down para capturar en any catalog
* fix: form clientes rehacer

## 2017-03-22  V1
* Menu principal con ui en base a tabs
* estilos, operaciones, tallas, clientes

# Sistema de tickets para COBYTEX