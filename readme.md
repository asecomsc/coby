## 2017-09-27  v15
* integrar OE en tab

## 2017-09-13  v14
* chage: ui final
  * dos columnas: secLectura y ticketID
  * hide tbMaxSec
  * no edit ( lock-yes ) fields: secLectura y ticketID
  
## 2017-09-13  v13
* FORM-TAB: Leer Tick 
  * operarID filter by ( fecha, operarioID )
  * barcode sqlUpdate ( fecha, operarioID, secLectura) en tabla-TICKETS

## 2017-08-16  v12
* fix code imprime_Tickets + qry PRINT_TICKETS, ahora ambos usan parametros

## 2017-08-09  v11b
* v11a, oe fix renumeracion de secuencia ( antes partir del 11, ponia 10,10,10...)
* print tickets manual 1,2 y todo el corte de prueba A101 ( 15 tickets )
* form Cortes, new boton Imprimir Tickets
* actualizar tb-parametros en sub generaTickets, para que siga progresiva la numeracion de bultos y tickets* 

## 2017-07-26  V11
* se canceló restructura de tb-tickets 
* la bd está en access 16

## 2017-07-19  v10d, v10e
* restructura tb tickets ( 1 x 6 ) [cortes_detID] x [corteID/estiloID/color/tallaID/piezas/bultoID]
* copy code autonumber
* copy qry GEN_TICKETS y GEN_BULTOS
* modif qry GEN_TICKETS por restructura tb-tickets
* planta, relink tables via nework
* gen layout2, ticket2.txt y test print via network
  * copy ticket2.txt \\prod1-pc\zebra
  * ( no se necesita instalar driver en pc local )
* copy tb-parametros
* modif qry PRINT_TICKETS por restructura tb-tickets

## 2017-07-12  v10c
* qry select genTickets  
* BE db - change structure

## 2017-07-05  v10b
* genBultos  
  * GOO access query row numbering, http://www.lebans.com/rownumber.htm 
  * qry select
    * rownumber marca err desde docmd.openqry
  * qry update
    * row number si funciona con currentdb.Execute
* code: openqry genBultos
  * err: incrementar row, no funciona

## 2017-06-21  v10, v10a
* Generar Tickets
  * qry genTicket: corteNom, nomEstilo, piezas, sec, nomOperacion, tiempo, precio, nomTalla
  * module1
    * function rowNum ( usa var row public )
  * <COPY> table param: ticketID, bultoID
  * funciones: 
    * getParam ["ticketID", "bultoID"], updateParam y rowNumber
  
## 2017-06-07  v9a
* form/sub cortes

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