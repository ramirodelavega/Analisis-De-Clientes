# Analisis de Clientes en Empresa de Telecomunicaciones
El siguiente proyecto se desarrollo en el marco del Curso de Data Analytics de CoderHouse.

<img align="right" width="1000" height = "600" alt="Inicio" src="https://github.com/ramirodelavega/Analisis-De-Clientes/assets/140906094/9c2ff713-cfb7-4b32-84ef-b1bbcc19cc1e">

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






