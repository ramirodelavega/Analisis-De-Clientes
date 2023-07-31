# Analisis de Clientes en Empresa de Telecomunicaciones
El siguiente proyecto se desarrollo en el marco del Curso de Data Analytics de CoderHouse.

<img width="1000" alt="Inicio 1" src="https://github.com/ramirodelavega/Analisis-De-Clientes/assets/140906094/cf57dceb-4239-416d-b729-00f9a7427d5b">

---


# Tabla de Contenidos

1. [Descripción](https://github.com/ramirodelavega/Analisis-De-Clientes#Descripción)
2. [Hipótesis](https://github.com/ramirodelavega/Analisis-De-Clientes#Hipótesis)
3. [Dataset](https://github.com/ramirodelavega/Analisis-De-Clientes#Dataset)
4. [Usuario final y nivel de aplicación](https://github.com/ramirodelavega/Analisis-De-Clientes#Usuario-final-y-nivel-de-aplicacion)
5. [Diagrama Entidad Relación Inicial](https://github.com/ramirodelavega/Analisis-De-Clientes#Diagrama-Entidad-Relación-Inicial)
6. [Diagrama Entidad Relación Final](https://github.com/ramirodelavega/Analisis-De-Clientes#Diagrama-Entidad-Relación-Final)
7. [Listado de Tablas](https://github.com/ramirodelavega/Analisis-De-Clientes#Listado-de-Tablas)
8. [Campos](https://github.com/ramirodelavega/Analisis-De-Clientes#Campos)
9. [Transformación de datos](https://github.com/ramirodelavega/Analisis-De-Clientes#Transformación-de-datos)
10. [Medidas](https://github.com/ramirodelavega/Analisis-De-Clientes#Medidas)
11. [Dashboard](https://github.com/ramirodelavega/Analisis-De-Clientes#Dashboard)
12. [Futuras Líneas](https://github.com/ramirodelavega/Analisis-De-Clientes#Futuras-Líneas)



---

# Descripción 

Para el siguiente proyecto se extrajo información de la página web Kaggle en donde se descargo el presente dataset sobre los clientes de una compañía de Telecomunicaciones.
En el mismo se detallan algunas características de los clientes (género, pareja, dependencias, tenencia), servicios que utilizan (streaming, internet, línea móvil, etc), cuanto abonan, de qué forma y qué tipo de contrato tienen. Además también se indica si tienen riesgo de cancelar los servicios o no. Todas estas variablas se analizaran y presentaran en un dashboard de Power Bi.

---


# Hipótesis 

A partir del siguiente dataset se buscara realizar varios trabajos de análisis. En primera instacia un trabajo de segmentación, analizando qué servicios se consumen más, y a su vez analizandolos segun las características de los clientes. A partir de esos datos también se puede llegar a un análisis de venta de paquetes de telefonia, a partir de la identificación del servicio o conjunto de servicios que más se venden o los que menos. Por último también se identificara a los clientes que tienen riesgo de abandono, con que servicios cuentan y si generaron o no algún ticket de consulta o reclamo.

---

# Dataset

El dataset usado para este analisis fue presentado por [PWC Switzerland](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) y disponible en:

- SUBIR DATASET

---

# Usuario final y nivel de aplicación

Se presenta este análisis para un nivel táctico (mandos medios) en donde pueden analizar y segmentar a sus clientes así pudiendo enfocar su fuerza de ventas a los servicios más falibles y/o potenciar los más contratados. También puede llevar a decisiones sobre la facturación y tipos de contrato teniendo en cuenta también a los clientes que corren riesgo de abandono.

---

# Diagrama entidad relación inicial

![image](https://github.com/ramirodelavega/Analisis-De-Clientes/assets/140906094/83743c58-31bf-4c38-8673-2f2971a75afb)

---

# Diagrama entidad relación final

![image](https://github.com/ramirodelavega/Analisis-De-Clientes/assets/140906094/89fc064d-4363-4a28-9c86-380effd92650)

---

# Listado de Tablas


Tabla Clientes: contiene las características de los clientes.
- PK: ClienteID: representa el número único del cliente en el conjunto de datos.
- Género: describe el género del cliente
- CiudadanoMayor: Describe si el cliente es una persona mayor
- Pareja: Describe si el cliente tiene pareja
- Dependientes: Describe si el cliente tiene dependientes
- Tenencia: Describe cuánto tiempo ha sido cliente de la empresa
- Suscripción: Segmentación de tenencia, de 1 a 5 años.


Tabla Servicios: contiene los servicios contratados por los clientes y datos relevantes sobre facturación y reclamos.
- FK: ClienteID
- ServicioTelefonico: Describe si el cliente ha registrado un servicio telefónico
- LineasMultiples: Describe si el cliente ha registrado múltiples líneas.
- InternetID: Describe si el cliente se ha registrado para el servicio a internet
- SeguridadOnline: Describe si el cliente se ha registrado para la seguridad en línea
- BackupOnline: Describe si el cliente se ha registrado para la copia de seguridad en línea
- ProteccionDispositivo: Describe si el cliente se ha registrado para la protección del dispositivo
- SoporteTecnico: Describe si el cliente se ha registrado para soporte técnico
- StreamingTv: Describe si el cliente se ha registrado para la transmisión de televisión
- StreamingMovies: Describe si el cliente se ha registrado para la transmisión películas


Tabla Facturación: Contiene los datos de facturación de los clientes.
- FK: ClienteID
- FK: ContratoID
- FacturacionSinPapel: Describe si el cliente se ha registrado para la facturación electrónica
- FK: MetodoPagoID
- CargoMensual: Representa el cargo mensual incurrido por el cliente
- CargoTotal: Representa el cargo total incurrido por el cliente


Tabla Reclamos: contiene los datos de tickets abiertos por clientes, y riesgo de abandono (riesgo de dejar de ser clientes)
- FK: ClienteID
- AdminTickets:Representa el número de tickets de administración abiertos por el cliente
- TechTickets: Representa el número de tickets técnicos abiertos por el cliente
- FK: RiesgoAbandonoID
- FK:Admin Tickets ID
- FK: Tech Tickets ID


Tabla Contrato: Contiene los tipos de contratos y su ID
- ContratoID: Id del tipo de contrato
- TipoContrato: Describe el tipo del contrato del cliente (duración)


Tabla RiesgoAbandono:
- PK: RiesgoAbandonoID: ID del riesgo abandono
- RiesgoAbandono: Describe si el cliente está en riesgo de abandono o no


Tabla MetodoPago: contiene los tipos de pagos y su ID
- MetodoPagoID: ID del tipo de pago
- TipoPago: Describe el método de pago del cliente.


Tabla Internet: contiene los tipos de internet y su ID
- InternetID: ID del tipo de internet
- TipoInternet: Describe si el cliente se ha registrado para el servicio de Internet y que servicio tiene

Tabla Admin Tickets: contiene si hay tickets administrativos o no y su ID
- PK: Admin Tickets ID: segmentación de Admin Tickets, representa si hay o no tickets de administración con valores numéricos (1 o 2)
- Admin Tickets General: representa en palabras el significado de los valores numéricos de Admin Tickets ID.


Tabla Tech Tickets: contiene si hay tickets administrativos o no y su ID
- PK: Tech Tickets ID: segmentación de Tech Tickets, representa si hay tickets técnicos, o no, con valores numéricos (1 o 2).
- Tech Tickets General: representa en palabras el significado de los valores numéricos de Tech Tickets ID.


# Campos

Tabla Clientes
|Campo|Tipo de Campo|Clave|
|-----|--------------|-----|
|ClienteID| Int, Varchar|	PK|
|Género|	Varchar|	-|
|CiudadanoMayor|	Int|	-|
|Pareja|	Varchar|	-|
|Dependientes|	Varchar|	-|
|Tenencia|	Int|	-|
|Suscripcion|	Int|	-|

Tabla Servicios
|Campo|Tipo de Campo|Clave|
|-----|-------------|-----|
|ClienteID|	Int, Varchar|	FK|
|ServicioTelefonico|	Varchar|	-|
|LineasMultiples|	Varchar|	-|
|InternetID|	Varchar|	FK|
|SeguridadOnline|	Varchar|	-|
|BackupOnline|	Varchar|	-|
|ProteccionDispositivo|	Varchar|	-|
|SoporteTecnico|	Varchar|	-|
|StreamingTv|	Varchar|	-|
|StreamingMovies|	Varchar|	-|
|RiesgoAbandono|	Varchar|	FK|


Tabla Facturación
|Campo|Tipo de Campo|Clave|
|-----|-------------|-----|
|ClienteID|	Int, Varhcar|	FK|
|ContratoID|	Int|	FK|
|FacturacionSinPapel|	Varchar|	-|
|MetodoPagoID|	Int|	FK|
|CargoMensual|	Decimal|	PK|
|CargoTotal|	Decimal|	PK|

Tabla Reclamos
|Campo|Tipo de Campo|Clave|
|-----|-------------|-----|
|ClienteID|	Int, Varchar|	FK|
|AdminTickets|	Int|	-|
|TechTickets|	Int|	-|
|AdminTicketsID|	Int|	FK|
|AdminTicketsID|	Int|	FK|


Tabla Contrato		
|Campo|Tipo de Campo|Clave|
|-----|-------------|-----|
|ContratoID|	Int|	PK|
|TipoContrato|	Varchar|	-|
		
Tabla MetodoPago		
|Campo|Tipo de Campo|Clave|
|-----|-------------|-----|
|MetodoPagoID|	Int|	PK|
|TipoContrato|	Varchar|	-|
		
Tabla Internet	
|Campo|Tipo de Campo|Clave|
|-----|-------------|-----|
|InternetID|	Int|	PK|
|TipoInternet|	Varchar|	-|

Tabla TechTickets		
|Campo|Tipo de Campo|Clave|
|-----|-------------|-----|
|TechTicketsID|	Int|	PK|
|Tech Tickets General|	Varchar|	-| 
		
Tabla AdminTickets		
|Campo|Tipo de Campo|Clave|
|-----|-------------|-----|
|AdminticketsID|	Int|	PK|
|Admin Tickets General|	Varchar|	-| 


# Transformación de datos
En Power Bi se realizó una transformación de datos y reorganización del DER para mejorar su funcionamiento. Cabe destacar que la organización y división en tablas de la base de datos ya se realizó previamente en excel de acuerdo al primer DER presentado.
- Se normalizo las tablas Internet, MetodoPago y Contrato eliminando duplicados.
- Se eliminó de la tabla Servicios las columnas CargoMensual, CargoTotal y RiesgoAbandono ya que implicaba una relación de muchos a muchos con datos repetidos en otras tablas.
- En la tabla Reclamos, columna RiesgoAbandono se reemplazó los valores “Yes” y “No” por “1” y “2” y se modificó el nombre de la tabla a RiesgoAbandonoID(FK). Así mismo, se creó otra tabla llamada RiesgoAbandono en donde se encuentran las columnas RiesgoAbandonoID (PK) y RiesgoAbandono.
`=Table.ReplaceValue(#"Tipocambiado","Yes","1",Replacer.ReplaceText,{"RiesgoAbandono"})`
`=Table.ReplaceValue(#"Valorreemplazado","No","2",Replacer.ReplaceText,{"RiesgoAbandono"})` 
- Dentro de la Tabla Clientes se agregó una nueva columna llamada Suscripción, en la cual se buscó agrupar los valores de la columna Tenencia expresada en meses a esta nueva columna expresa en años.
`Suscripción = SWITCH(TRUE(),
[tenencia] < 12, "<1 año",
[tenencia] < 24, "<2 años",
[tenencia] < 48, "<3 años",
[tenencia] < 60, "<4 años",
[tenencia] < 72, "<5 años",
"Más de 5 años")`
- Se creó la Tabla medidas para agregar todas las medidas calculadas dentro de la misma.
- En la tabla Clientes, columna Género, se reemplazó los valores “Female” y “Male” por “Femenino” y “Masculino” respectivamente.
- Se reemplazaron todos los valores en inglés por su traducción en español.
- Con el objetivo de diferenciar los clientes que tienen Admin Tickets y los que no, en la tabla Reclamos, se duplicó la columna Admin Tickets, generando una nueva columna llamada Admin Tickets ID (FK). Luego se reemplazaron los valores distintos de cero por el valor 1. Además se creó una nueva tabla, llamada Admin Tickets, en donde se duplicó la columna Admin Tickets ID de la tabla Reclamos, luego se elimino los duplicados, para poder identificarla como PK. Además, se creó una segunda columna llamada Admin Tickets General, en donde se especifica “Sin Admin Tickets” o “Con Admin Tickets”.
- Con el objetivo de diferenciar los clientes que tienen TechTickets y los que no, en la tabla Reclamos, se duplicó la columna TechTickets, generando una nueva columna llamada Tech Tickets ID (FK). Luego se reemplazaron los valores distintos de cero por el valor 1. Además se creó una nueva tabla, llamada Tech Tickets, en donde se duplicó la columna Tech Tickets ID de la tabla Reclamos, luego se elimino los duplicados, para poder identificarla como PK. Además, se creó una segunda columna llamada Tech Tickets General, en donde se especifica “Sin Tech Tickets” o “Con Tech Tickets”.

---

# Medidas

- Total Clientes: total de clientes
`Total Clientes = CALCULATE(COUNT(Clientes[ClienteID]))`
- Suma Cargo Total: suma del cargo total de todos los clientes.
`Suma Cargo Total = CALCULATE(SUM(Facturacion[CargoTotal]))`
- Suma Cargo Mensual: suma del cargo mensual de todos los clientes.
`Suma Cargo Mensual = CALCULATE(SUM(Facturacion[CargoMensual]))`
- Contador Riesgo Abandono: cantidad de clientes que están en riesgo de rescindir de los servicios de la compañía.
`Contador Riesgo Abandono = CALCULATE(COUNTROWS(FILTER(Reclamos,Reclamos[RiesgoAbandonoID] =1)))`
- % Riesgo Abandono: porcentaje que representa la cantidad de clientes que están en riesgo de rescindir de los servicios de la compañía con respecto del total.
`% Riesgo Abandono = DIVIDE(Medidas[Contador Riesgo Abandono], Medidas[TotalClientes])`
- Hombres: Cantidad de clientes que son hombres
`Hombres = CALCULATE(COUNTROWS(FILTER(Clientes, Clientes[Genero] ="Masculino")))`
- Mujeres: Cantidad de clientes que son mujeres
`Mujeres = CALCULATE(COUNTROWS(FILTER(Clientes, Clientes[Genero] ="Femenino")))`
- Total Ciudadano Mayor: total de ciudadanos mayores
`Total Ciudadano Mayor = CALCULATE(COUNTROWS(FILTER(Clientes,Clientes[CiudadanoMayor] = 1)))`
- % Ciudadano Mayor: porcentaje que representa la cantidad de clientes que son ciudadanos mayores con respecto del total de clientes.
`% Ciudadano Mayor = DIVIDE(Medidas[Total Ciudadano Mayor], Medidas[TotalClientes])`
- Con Pareja: cantidad de clientes que estan en pareja
`Con Pareja = CALCULATE(COUNTROWS(FILTER(Clientes, Clientes[Pareja] ="Yes")))`
- Con dependientes: cantidad de clientes que tienen a cargo otras personas.
`Con Dependientes = CALCULATE(COUNTROWS(FILTER(Clientes,Clientes[Dependientes] = "Yes")))`
- % Con Pareja: porcentaje que representa la cantidad de clientes que están en pareja con respecto del total de clientes.
`% Con Pareja = DIVIDE(Medidas[Con Pareja],[Total Clientes])`
- % Con dependientes: porcentaje que representa la cantidad de clientes que tienen a cargo otras personas (ej. hijos) con respecto del total de clientes.
`% Con Dependientes = CALCULATE(DIVIDE(Medidas[Con Dependientes], [TotalClientes]))`
- <1 año: clientes que reciben los servicios de la compañía por menos de un año.
`<1 año = CALCULATE(COUNTROWS(FILTER(Clientes, Clientes[Suscripción] = "<1año")))`
- <2 años: clientes que reciben los servicios de la compañía desde hace más de un año y menos de dos.
`<2 años = CALCULATE(COUNTROWS(FILTER(Clientes, Clientes[Suscripción] = "<2años")))`
- <3 años: clientes que reciben los servicios de la compañía desde hace más de dos años y menos de tres..
`<3 años = CALCULATE(COUNTROWS(FILTER(Clientes, Clientes[Suscripción] = "<3años")))`
<4 años: clientes que reciben los servicios de la compañía desde hace más de tres
años y menos de cuatro.
<4 años = CALCULATE(COUNTROWS(FILTER(Clientes, Clientes[Suscripción] = "<4
años")))
- <5 años: clientes que reciben los servicios de la compañía desde hace más de cuatro años y menos de cinco..
`<5 años = CALCULATE(COUNTROWS(FILTER(Clientes, Clientes[Suscripción] = "<5años")))`
- Más de 5 años: clientes que reciben los servicios de la compañía desde hace más de 5 años.
`Más de 5 años = CALCULATE(COUNTROWS(FILTER(Clientes, Clientes[Suscripción]= "Más de 5 años")))`
- Promedio Cargo Mensual: promedio del cargo mensual
`Promedio Cargo Mensual = CALCULATE(DIVIDE([Suma Cargo Mensual], [TotalClientes]))`
- Promedio Cargo Total: promedio del cargo total
`Promedio Cargo Total = CALCULATE(DIVIDE([Suma Cargo Total], [Total Clientes])`
- Mes a Mes: cantidad de clientes que tienen contrato mensual.
`Mes a Mes = CALCULATE(COUNTROWS(FILTER(Facturacion,Facturacion[ContratoID] = 1)))`
- Un año: cantidad de clientes que tienen contrato por un año.
`Un año = CALCULATE(COUNTROWS(FILTER(Facturacion, Facturacion[ContratoID] =2)))`
- Dos años: cantidad de clientes que tienen contrato por dos años.
`Dos Años = CALCULATE(COUNTROWS(FILTER(Facturacion,Facturacion[ContratoID] = 3)))`
- Credit Card: clientes que pagan su factura con tarjeta de crédito
`Credit Card = CALCULATE(COUNTROWS(FILTER(Facturacion,Facturacion[MetodoPagoID] = 4)))`
- Electronic Check: Clientes que pagan su factura con cheque electrónico.
`Electronic Check = CALCULATE(COUNTROWS(FILTER(Facturacion,Facturacion[MetodoPagoID] = 1)))`
- Bank Transfer: clientes que pagan su factura con transferencia bancaria
BankTransfer = CALCULATE(COUNTROWS(FILTER(Facturacion,
Facturacion[MetodoPagoID] = 3)))
- Mailed check: clientes que pagan su factura con cheque enviado por correo.
`Mailed Check = CALCULATE(COUNTROWS(FILTER(Facturacion,Facturacion[MetodoPagoID] = 2)))`
- FC Con Papel: factura impresa en papel
`FC Con Papel = CALCULATE(COUNTROWS(FILTER(Facturacion,Facturacion[FacturacionSinPapel] = "No")))`
- FC Sin Papel: factura no impresa en papel, enviada por otros medios electrónicos
`FC Sin Papel = CALCULATE(COUNTROWS(FILTER(Facturacion,Facturacion[FacturacionSinPapel] = "Yes")))`
- Con Serv. Telefónico: clientes suscriptos al servicio telefónico.
`Con Serv. Telefonico = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[ServicioTelefonico] = "Yes")))`
- No Serv. Telefonico: clientes que no estan suscriptos al servicio telefónico.
`No Serv. Telefonico = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[LineasMultiples] = "No phone service")))`
- Si Lin. Multiples: clientes que cuentan con líneas múltiples.
`Si Lineas Multiples = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[LineasMultiples] = "Yes")))`
- No Lin. Múltiples: Clientes que no cuentan con líneas multiples
`No Lin. Multiples = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[LineasMultiples] = "No")))`
- DSL: clientes que cuentan con servicio de internet mediante DSL
`DSL = COUNTROWS(FILTER(Servicios, Servicios[InternetID] = 1))
- Fiber Optic: clientes que cuentan con servicio de internet mediante fibra óptica
`Fiber Optic = COUNTROWS(FILTER(Servicios, Servicios[InternetID] = 2))`
- Con Streaming Movies: Clientes que cuentan con el servicio de streaming movies.
Con Streaming Movies = CALCULATE(COUNTROWS(FILTER(Servicios,
Servicios[StreamingMovies] = "Yes")))
- Con Streaming TV: Clientes que cuentan con el servicio de streaming TV
`Con Streaming TV = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[StreamingTV] = "Yes")))`
- No Internet: Clientes que no cuentan con el servicio de internet contratado.
`No Internet = COUNTROWS(FILTER(Servicios, Servicios[InternetID] = 3))`
- Sin Streaming Movies: Clientes que no cuentan con el servicio de streaming movies.
`Sin Streaming Movies = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[StreamingMovies] = "No")))`
- Sin Streaming Tv: Clientes que no cuentan con el servicio de streaming TV
`Sin Streaming TV = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[StreamingTV] = "No")))`
- Con Soporte Tecnico: clientes que cuentan con el servicio de soporte técnico
`Con Soporte Tecnico = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[SoporteTecnico] = "Yes")))`
- Sin Soporte Técnico: clientes que no cuentan con el servicio de soporte técnico
`Sin Soporte Tecnico = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[SoporteTecnico] = "No")))`
- Con Protección del Dispositivo: clientes que cuentan con protección para sus dispositivos móviles.
`Con Proteccion del Dispositivo = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[ProteccionDispositivo] = "Yes")))`
- Sin Protección del Dispositivo: clientes que no cuentan con protección para sus dispositivos móviles.
`Sin Proteccion del Dispositivo = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[ProteccionDispositivo] = "No")))`
- Con Seguridad Online: clientes que cuentan con el servicio de seguridad online
`Con Seguridad Online = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[SeguridadOnline] = "Yes")))`
- Sin Seguridad Online: clientes que no cuentan con el servicio de seguridad online
`Sin Seguridad Online = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[SeguridadOnline] = "No")))`
- Con Backup Online: clientes que cuentan con el servicio de backup online.
`Con Backup Online = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[BackupOnline] = "Yes")))`
- Sin Backup Online: clientes que no cuentan con el servicio de backup online.
`Sin Backup Online = CALCULATE(COUNTROWS(FILTER(Servicios,Servicios[BackupOnline] = "No")))`
- Total Tickets: suma de la cantidad de tickets abiertos de administración y sistemas.
`Total Tickets = SUMX(Reclamos, Reclamos[Admin Tickets ID]+Reclamos[TechTickets ID])`

---

# Dashboard

El dashboard creado en Power Bi para la representación y análisis de los datos cuenta con cinco solapas, Inicio, Glosario, Clientes, Facturación y Análisis de Servicios.. La primera,solapa Inicio, consta de el título del proyecto, un navegador de páginas o solapas y una breve descripción de lo que se busca representar en el tablero.

<img width="685" alt="Inicio 1" src="https://github.com/ramirodelavega/Analisis-De-Clientes/assets/140906094/5fd86c9f-ee5f-493b-b5b3-5962f8f03033">

En la solapa Glosario se definen algunas variables o medidas que pueden prestarse a confusión.

<img width="685" alt="Glosario 1" src="https://github.com/ramirodelavega/Analisis-De-Clientes/assets/140906094/0af0ced8-0e09-4cf1-b280-8182ffd2db0c">


En la solapa Clientes se busca analizar las características de los clientes de la empresa. Al igual que la solapa Facturación, cuenta en la parte superior con un análisis general con diferentes indicadores que muestran Clientes Totales, Suma de Cargos Totales y Mensuales de todos los clientes, y Riesgo Abandono, en cantidad de clientes y de manera porcentual. La parte inferior se divide en dos recuadros. Uno en donde se representan lascaracterísticas de los clientes y otro recuadro en donde se muestran los reclamos realizados por los mismos, con opción de aplicar filtros. Además en la parte lateral derecha se encuentran la sección de filtros generales, que se repite también en los apartados Facturación y Análisis de servicios.

<img width="685" alt="Clientes 1" src="https://github.com/ramirodelavega/Analisis-De-Clientes/assets/140906094/4a18d881-27d5-41bb-b83e-5c8f070093e8">

Por su parte en la solapa Facturacion, ademas de los elementos ya descriptos anteriormente, se puede observar un analisis detallado de los tipos de contrato, metodos de pago, promedios de cargos y cargos segun el tipo de contrato. Siempre con posible interaccion con los filtros o segmentadores. 

<img width="685" alt="Facturacion" src="https://github.com/ramirodelavega/Analisis-De-Clientes/assets/140906094/cdc742b6-036f-4f13-a53f-c9e407b1d0c7">

Por último en la solapa, llamada Análisis de Servicios, se muestra una representación de los servicios que tienen contratados los clientes, con la opción de filtrarlos mediante tres segmentadores de datos.

<img width="685" alt="servicios 1" src="https://github.com/ramirodelavega/Analisis-De-Clientes/assets/140906094/99905e92-0c8c-4a3f-87cf-a66731065697">

---

# Futuras Líneas
Algunas iniciativas o mejoras que pueden llevarse a cabo sobre este proyecto son, la incorporación de mayor cantidad de filtros para un análisis más exhaustivo y minucioso de la información, claramente dependiendo de la información que se quiera obtener.











