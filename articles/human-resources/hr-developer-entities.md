---
title: Entidades de Common Data Service
description: Microsoft Dynamics 365 Human Resources usa Common Data Service para habilitar escenarios de extensibilidad e integración.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85dd95e8209fff28f214986f7960372db200351b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010515"
---
# <a name="common-data-service-entities"></a>Entidades de Common Data Service

Microsoft Dynamics 365 Human Resources usa Common Data Service para habilitar escenarios de extensibilidad e integración.

Para obtener más información acerca de Common Data Service, consulte [¿Qué es Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Las siguientes entidades de Recursos Humanos están disponibles en Common Data Service.

## <a name="benefit-entities"></a>Entidades de prestación

**Frecuencia de cálculo de la prestación**

| **Campos**        | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-------------------|---------------|--------------|----------------|
| Descripción       | Text          |              | X              |
| Control de frecuencia | Conjunto de opciones    | X            | X              |
| Es inmutable      | Dos opciones   |              | X              |
| Nombre              | Text          | X            | X              |


**Índice de cálculo de la prestación**

| **Campos**  | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-------------|---------------|--------------|----------------|
| Descripción | Text          |              | X              |
| Nombre        | Text          | X            | X              |
| TierType    | Conjunto de opciones    | X            | X              |


**Detalle de índice de cálculo de la prestación**

| **Campos**                             | **Tipo de datos**  | **Requerido** | **Se puede buscar** |
|----------------------------------------|----------------|--------------|----------------|
| Número de detalle de índice de cálculo de la prestación | Text           | X            | X              |
| Id. de índice de cálculo                    | Buscar         | X            | X              |
| Método de contribución                    | Conjunto de opciones     | X            | X              |
| Vigente                              | Solo fecha      | X            | X              |
| Contribución del empresario                  | Número decimal |              | X              |
| Caducidad                             | Solo fecha      | X            | X              |
| WorkerDeduction                        | Número decimal |              | X              |


**Tipo de beneficio**

| **Campos**           | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|----------------------|---------------|--------------|----------------|
| ConcurrentEnrollment | Conjunto de opciones    |              | X              |
| Descripción          | Text          |              | X              |
| Nombre                 | Text          | X            | X              |
| PayrollCategory      | Conjunto de opciones    |              | X              |


**Plan de prestaciones**

| **Campos**                               | **Tipo de datos**  | **Requerido** | **Se puede buscar** |
|------------------------------------------|----------------|--------------|----------------|
| Método de límite de atrasos                      | Conjunto de opciones     |              | X              |
| Tipo de prestación                             | Buscar         | X            | X              |
| Método de límite de contribución                | Conjunto de opciones     |              | X              |
| Método de contribución                      | Conjunto de opciones     |              | X              |
| Divisa                                 | Buscar         |              | X              |
| Prioridad de deducción                       | Número entero   |              | X              |
| Importe límite de contribución predeterminado        | Divisa       |              | X              |
| Importe de límite de contribución predeterminado (base) | Divisa       |              | X              |
| Periodo límite de contribución predeterminado        | Conjunto de opciones     |              | X              |
| Importe límite de deducción predeterminado           | Divisa       |              | X              |
| Importe de límite de deducción predeterminado (base)    | Divisa       |              | X              |
| Periodo límite de deducción predeterminado           | Conjunto de opciones     |              | X              |
| Descripción                              | Text           |              | X              |
| Tipo de cambio                            | Número decimal |              | X              |
| Es ejecución de nómina adicional                | Dos opciones    |              | X              |
| Se informa para Ley de Cuidado de Salud Asequible        | Dos opciones    |              | X              |
| Se genera con atrasos                      | Dos opciones    |              | X              |
| Valor bruto                              | Dos opciones    |              | X              |
| Es principal                               | Dos opciones    |              | X              |
| Nombre                                     | Text           | X            | X              |
| Impacto de nómina                           | Conjunto de opciones     |              | X              |
| Tipo de jubilación                          | Conjunto de opciones     |              | X              |


**Entidad de empleo**

| **Campos**                     | **Tipo de datos**  | **Requerido** | **Se puede buscar** |
|--------------------------------|----------------|--------------|----------------|
| Fecha inicial del trabajador ajustada     | Fecha y hora  |              | X              |
| Compañía                        | Buscar         | X            | X              |
| Importe de unidad de aviso del trabajador | Número decimal |              | X              |
| Unidad de aviso del trabajador        | Conjunto de opciones     |              | X              |
| Fecha final del empleo            | Fecha y hora  |              | X              |
| Número de empleo              | Text           | X            | X              |
| Fecha inicial del empleo          | Fecha y hora  |              | X              |
| Último día trabajado              | Fecha y hora  |              | X              |
| Fecha de transición                | Fecha y hora  |              | X              |
| Válido desde                     | Fecha y hora  | X            | X              |
| Válido hasta                       | Fecha y hora  |              | X              |
| Trabajador                         | Buscar         | X            | X              |
| Número de avisos del trabajador           | Número decimal |              | X              |
| Fecha de inicio del trabajador             | Fecha y hora  |              | X              |
| Tipo de trabajador                    | Conjunto de opciones     | X            | X              |
| Unidad de aviso del trabajador          | Conjunto de opciones     |              | X              |

## <a name="worker-entities"></a>Entidades del trabajador

**Origen étnico**

| **Campos**         | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|--------------------|---------------|--------------|----------------|
| Descripción        | Text          |              | X              |
| Nombre de origen étnico | Text          | X            | X              |


**Idioma**

| **Campos**    | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|---------------|---------------|--------------|----------------|
| Descripción   | Text          |              | X              |
| Nombre de idioma | Text          | X            | X              |


**Estado de excombatiente**

| **Campos**           | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|----------------------|---------------|--------------|----------------|
| Descripción          | Text          |              | X              |
| Es excombatiente protegido | Dos opciones    |              | X              |
| Nombre de idioma        | Text          | X            | X              |


**Trabajador**

| **Campos**                | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|---------------------------|---------------|--------------|----------------|
| Fecha de nacimiento                 | Solo fecha     |              | X              |
| Descripción               | Text          |              | X              |
| Dirección de correo electrónico 1           | Correo electrónico         |              | X              |
| Dirección de correo electrónico 2           | Correo electrónico         |              | X              |
| Identidad de Facebook         | Text          |              | X              |
| Nombre                | Text          |              | X              |
| Nombre completo                 | Text          |              | X              |
| Género                    | Conjunto de opciones    |              | X              |
| Generación                | Text          |              | X              |
| Se le permite contacto de correo electrónico  | Dos opciones   |              | X              |
| Se le permite contacto de teléfono  | Dos opciones   |              | X              |
| Apellidos                 | Text          |              | X              |
| Identidad de LinkedIn         | Text          |              | X              |
| Administrador                   | Buscar        |              | X              |
| Segundo nombre               | Text          |              | X              |
| Teléfono móvil              | Teléfono         |              | X              |
| Identificador de Office Graph   | Text          |              | X              |
| Dirección de correo electrónico principal     | Correo electrónico         |              | X              |
| Teléfono principal         | Teléfono         |              | X              |
| Profesión                | Text          |              | X              |
| Red social 1          | Conjunto de opciones    |              | X              |
| Red social 2          | Conjunto de opciones    |              | X              |
| Identidad de red social 1 | Text          |              | X              |
| Identidad de red social 2 | Text          |              | X              |
| Origen                    | Conjunto de opciones    | X            | X              |
| Estado                    | Conjunto de opciones    | X            | X              |
| Teléfono 1               | Teléfono         |              | X              |
| Teléfono 2               | Teléfono         |              | X              |
| Teléfono 3               | Teléfono         |              | X              |
| Identidad de Twitter          | Text          |              | X              |
| Usuario                      | Buscar        |              | X              |
| Dirección URL del sitio web               | URL           |              | X              |
| Número del trabajador             | Text          | X            | X              |
| Tipo de trabajador               | Conjunto de opciones    | X            | X              |
| Nombre Yomi           | Text          |              | X              |
| Nombre completo Yomi            | Text          |              | X              |
| Apellido Yomi            | Text          |              | X              |
| Segundo nombre Yomi          | Text          |              | X              |


**Dirección de trabajador**

| **Campos**           | **Tipo de datos**  | **Requerido** | **Se puede buscar** |
|----------------------|----------------|--------------|----------------|
| Número de dirección       | Text           | X            | X              |
| Tipo de dirección         | Conjunto de opciones     | X            | X              |
| Ciudad                 | Text           |              | X              |
| Región o país    | Text           |              | X              |
| Provincia               | Text           |              | X              |
| Fax                  | Teléfono          |              | X              |
| Es preferido         | Dos opciones    |              | X              |
| Latitud             | Número decimal |              | X              |
| Línea 1               | Text           |              | X              |
| Línea 2               | Text           |              | X              |
| Línea 3               | Text           |              | X              |
| Longitud            | Número decimal |              | X              |
| Código postal          | Text           |              | X              |
| Apartado de correos      | Text           |              | X              |
| Código de método de envío | Número entero   |              | X              |
| Comunidad autónoma o provincia    | Text           |              | X              |
| Teléfono 1          | Teléfono          |              | X              |
| Teléfono 2          | Teléfono          |              | X              |
| Teléfono 3          | Teléfono          |              | X              |
| Zona de porte (UPS)             | Text           |              | X              |
| Contrapartida UTC           | Número entero   |              | X              |
| Trabajador               | Buscar         | X            | X              |


**Detalle personal del trabajador**

| Campos                             | Tipo de datos    | Requerido | Se puede buscar |
|------------------------------------|--------------|----------|------------|
| Ciudad de nacimiento                         | Text         |          | X          |
| País o región de nacimiento            | Conjunto de opciones   |          | X          |
| Fecha de nacimiento                          | Solo fecha    |          | X          |
| País o región de nacionalidad      | Conjunto de opciones   |          | X          |
| Fecha de fallecimiento                      | Solo fecha    |          | X          |
| Fecha de verificación de excombatiente discapacitado | Solo fecha    |          | X          |
| Formación                          | Text         |          | X          |
| Origen étnico                     | Buscar       |          | X          |
| ExpatriateEndDate                  | Solo fecha    |          | X          |
| ExpatriateStartDate                | Solo fecha    |          | X          |
| País o región de nacimiento del padre     | Conjunto de opciones   |          | X          |
| Género                             | Conjunto de opciones   |          | X          |
| Está deshabilitada                        | Dos opciones  |          | X          |
| Es excombatiente discapacitado                | Dos opciones  |          | X          |
| Se aplica la normativa de expatriados    | Dos opciones  |          | X          |
| Es estudiante a tiempo completo               | Dos opciones  |          | X          |
| Estado civil                     | Conjunto de opciones   |          | X          |
| Fecha final del servicio militar          | Solo fecha    |          | X          |
| Fecha inicial del servicio militar        | Solo fecha    |          | X          |
| País o región de nacimiento de la madre     | Conjunto de opciones   |          | X          |
| País o región de la nacionalidad      | Conjunto de opciones   |          | X          |
| Idioma materno                    | Buscar       |          | X          |
| Número de dependientes               | Número entero |          |            |
| Estado de veterano                     | Buscar       |          | X          |
| Trabajador                             | Buscar       | X        | X          |
| Número de detalle personal del trabajador      | Text         | X        | X          |


**Cuenta bancaria del trabajador**

| **Campos**                 | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|----------------------------|---------------|--------------|----------------|
| Titular de la cuenta             | Text          |              | X              |
| Identificación de la cuenta     | Text          |              | X              |
| Descripción de la dirección        | Text          |              | X              |
| Tipo de cuenta bancaria          | Conjunto de opciones    |              | X              |
| Código de ubicación del banco         | Text          |              | X              |
| Nombre de sucursal                | Text          |              | X              |
| Número de sucursal              | Text          |              | X              |
| Ciudad                       | Text          |              | X              |
| Región o país          | Text          |              | X              |
| Provincia                     | Text          |              | X              |
| Descripción                | Text          |              | X              |
| Nombre del distrito              | Text          |              | X              |
| Correo electrónico                      | Text          |              | X              |
| Extensión                  | Text          |              | X              |
| Fax                        | Text          |              | X              |
| IBAN                       | Text          |              | X              |
| Línea 1                     | Text          |              | X              |
| Línea 2                     | Text          |              | X              |
| Línea 3                     | Text          |              | X              |
| Teléfono móvil               | Text          |              | X              |
| Nombre de la persona             | Text          |              | X              |
| Código postal                | Text          |              | X              |
| Apartado de correos            | Text          |              |                |
| Número de ruta             | Text          |              | X              |
| Tipo de número de ruta        | Conjunto de opciones    |              | X              |
| Comunidad autónoma o provincia          | Text          |              | X              |
| Código SWIFT                 | Text          |              | X              |
| Teléfono                  | Text          |              | X              |
| Número de télex               | Text          |              | X              |
| Dirección URL del sitio web                | Text          |              | X              |
| Trabajador                     | Buscar        | X            | X              |
| Número de cuenta bancaria del trabajador | Text          |              | X              |
| Número de cuenta bancaria del trabajador | Text          | X            | X              |

**Compensación fija del trabajador**

| Campos                                | Tipo de datos      | Requerido | Se puede buscar |
|---------------------------------------|----------------|----------|------------|
| Compañía                               | Buscar         | X        | X          |
| Tipo de compensación                     | Conjunto de opciones     |          | X          |
| Divisa                              | Buscar         |          | X          |
| Fecha de vigencia                        | Solo fecha      |          | X          |
| Evento                                 | Buscar         | X        | X          |
| Tipo de cambio                         | Número decimal |          | X          |
| Fecha de vencimiento                       | Solo fecha      |          | X          |
| Número de línea                           | Número decimal |          | X          |
| Frecuencia de pago                         | Buscar         | X        | X          |
| Índice salarial                              | Divisa       |          | X          |
| Índice salarial (base)                       | Divisa       |          | X          |
| Plan                                  | Buscar         | X        | X          |
| Posición                              | Buscar         | X        | X          |
| Tipo de proceso                          | Conjunto de opciones     | X        | X          |
| Línea de configuración de punto de referencia            | Buscar         |          | X          |
| Trabajador                                | Buscar         | X        | X          |
| Número de compensación fija del trabajador      | Text           | X        | X          |

**Número de identificación de persona del trabajador**

| Campos                 | Tipo de datos   | Requerido | Se puede buscar |
|------------------------|-------------|----------|------------|
| Descripción            | Text        |          | X          |
| Tipo de entrada             | Text        |          | X          |
| Fecha de vencimiento        | Solo fecha   |          | X          |
| Número de identificación  | Text        | X        | X          |
| Tipo de identificación    | Buscar      | X        | X          |
| Es principal             | Dos opciones |          | X          |
| Fecha de emisión             | Solo fecha   |          | X          |
| Agencia emisora         | Buscar      | X        | X          |
| Trabajador                 | Buscar      | X        | X          |


## <a name="position-entities"></a>Entidades de puesto

**Puesto de trabajo**

| **Campos**               | **Tipo de datos**  | **Requerido** | **Se puede buscar** |
|--------------------------|----------------|--------------|----------------|
| Activación               | Fecha y hora  |              | X              |
| Disponible para la asignación | Fecha y hora  |              | X              |
| Departamento               | Buscar         |              | X              |
| Descripción              | Text           |              | X              |
| Equivalente de jornada completa     | Número decimal |              | X              |
| Puesto                      | Buscar         | X            | X              |
| Número del puesto      | Text           | X            | X              |
| Puesto principal      | Buscar         |              | X              |
| Tipo de puesto            | Buscar         |              | X              |
| Jubilación               | Fecha y hora  |              | X              |
| Cargo                    | Conjunto de opciones     |              | X              |
| Válido desde               | Fecha y hora  | X            | X              |
| Válido hasta                 | Fecha y hora  |              | X              |


**Tipo de puesto**

| **Campos**         | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|--------------------|---------------|--------------|----------------|
| Clasificación     | Conjunto de opciones    |              | X              |
| Descripción        | Text          |              | X              |
| Nombre de tipo de puesto | Text          | X            | X              |


**Asignación del trabajador del puesto**

| **Campos**                        | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-----------------------------------|---------------|--------------|----------------|
| Puesto de trabajo                      | Buscar        | X            | X              |
| Número de asignación del trabajador del puesto | Text          | X            | X              |
| Válido desde                        | Text          | X            | X              |
| Válido hasta                          |               |              | X              |
| Trabajador                            |               | X            | X              |

## <a name="job-entities"></a>Entidades de trabajo

**Trabajo**

| **Campos**                   | **Tipo de datos**  | **Requerido** | **Se puede buscar** |
|------------------------------|----------------|--------------|----------------|
| Permitir puestos ilimitados    | Dos opciones    |              | X              |
| Equivalente de jornada completa predeterminada | Número decimal |              | X              |
| Descripción                  | Text           |              | X              |
| Descripción del trabajo              | Text           |              | X              |
| Función de trabajo                 | Buscar         |              | X              |
| Tipo de trabajo                     | Buscar         |              | X              |
| Número máximo de puestos  | Número entero   |              | X              |
| Nombre                         | Text           | X            | X              |
| Cargo                        | Conjunto de opciones     |              | X              |
| Válido desde                   | Fecha y hora  | X            | X              |
| Válido hasta                     | Fecha y hora  |              | X              |


**Función de trabajo**

| **Campos**        | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-------------------|---------------|--------------|----------------|
| Descripción       | Text          | X            | X              |
| Nombre de la función de trabajo | Text          | X            | X              |


**Tipo de trabajo**

| **Campos**    | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|---------------|---------------|--------------|----------------|
| Descripción   | Text          | X            | X              |
| Estado de exento | Conjunto de opciones    | X            | X              |
| Nombre de tipo de trabajo | Text          | X            | X              |

## <a name="leave-and-absence-entities"></a>Entidades de permisos y ausencias

**Inscripción en baja**

| **Campos**            | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-----------------------|---------------|--------------|----------------|
| Base de fecha de acumulación    | Solo fecha     | X            | X              |
| Fecha inicial de acumulación    | Solo fecha     | X            | X              |
| Fecha personalizada           | Solo fecha     | X            | X              |
| Se ha suspendido la acumulación  | Dos opciones   |              | X              |
| LeaveEnrollmentNumber | Text          | X            | X              |
| Plan de bajas            | Buscar        | X            | X              |
| Fecha inicial            | Solo fecha     | X            | X              |
| Base de nivel            | Conjunto de opciones    | X            | X              |
| Trabajador                | Buscar        | X            | X              |


**Transacción bancaria de bajas**

| **Campos**                    | **Tipo de datos**  | **Requerido** | **Se puede buscar** |
|-------------------------------|----------------|--------------|----------------|
| Importe                        | Número decimal | X            | X              |
| Compañía                       | Buscar         | X            | X              |
| Número de transacción bancaria de bajas | Text           | X            | X              |
| Plan de bajas                    | Buscar         |              | X              |
| Tipo de baja                    | Buscar         | X            | X              |
| Fecha de la transacción              | Solo fecha      | X            | X              |
| Número de transacción            | Número decimal | X            | X              |
| Tipo de transacción              | Conjunto de opciones     | X            | X              |
| Trabajador                        | Buscar         | X            | X              |


**Plan de bajas**

| **Campos**        | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-------------------|---------------|--------------|----------------|
| Frecuencia de acumulación | Conjunto de opciones    | X            | X              |
| Compañía           | Buscar        | X            | X              |
| Descripción       | Text          |              | X              |
| Tipo de baja        | Buscar        | X            | X              |
| Nombre              | Text          | X            | X              |
| Fecha inicial        | Solo fecha     | X            | X              |


**Solicitud de baja**

| **Campos**           | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|----------------------|---------------|--------------|----------------|
| Comentar              | Text          | X            | X              |
| Compañía              | Buscar        | X            | X              |
| Número de solicitud de baja | Text          |              | X              |
| Fecha de solicitud         | Fecha y hora | X            | X              |
| Estado               | Conjunto de opciones    | X            | X              |
| Trabajador               | Buscar        | X            | X              |


**Detalle de solicitud de baja**

| **Campos**                  | **Tipo de datos**  | **Requerido** | **Se puede buscar** |
|-----------------------------|----------------|--------------|----------------|
| Importe                      | Número decimal | X            | X              |
| Fecha de baja                  | Fecha y hora  | X            | X              |
| Solicitud de baja               | Buscar         | X            | X              |
| Número de detalle de solicitud de baja | Text           | X            | X              |
| Tipo de baja                  | Buscar         | X            | X              |


**Tipo de baja**

| **Campos**      | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-----------------|---------------|--------------|----------------|
| Compañía         | Buscar        | X            | X              |
| Descripción     | Text          |              | X              |
| Código de ganancias    | Buscar        |              | X              |
| Nombre del tipo de baja | Text          | X            | X              |


**Calendario de trabajo**

| **Campos**  | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-------------|---------------|--------------|----------------|
| Compañía     | Buscar        | X            | X              |
| Descripción | Text          |              | X              |
| Nombre        | Text          | X            | X              |


**Día de calendario de trabajo**

| **Campos**               | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|--------------------------|---------------|--------------|----------------|
| Fecha del calendario            | Solo fecha     | X            | X              |
| Compañía                  | Buscar        |              | X              |
| Estado                   | Text          |              | X              |
| Calendario de trabajo            | Buscar        | X            | X              |
| Número de día de calendario de trabajo | Text          | X            | X              |


**Vacaciones calendario de trabajo**

| **Campos**  | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-------------|---------------|--------------|----------------|
| Nombre        | Text          |              | X              |
| Descripción | Text          | X            | X              |


**Línea de festivo del calendario de trabajo**

| **Campos**                        | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-----------------------------------|---------------|--------------|----------------|
| Fecha de vacaciones                      | Solo fecha     | X            | X              |
| Nombre                              | Text          |              | X              |
| Vacaciones calendario de trabajo             | Buscar        | X            | X              |
| Número de línea de festivo del calendario de trabajo | Text          | X            | X              |


**Intervalo de tiempo del calendario de trabajo**

| **Campos**                         | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|------------------------------------|---------------|--------------|----------------|
| Compañía                            | Buscar        |              | X              |
| Hora final                           | Número entero  |              | X              |
| Hora inicial                         | Número entero  |              | X              |
| Calendario de trabajo                      | Buscar        | X            | X              |
| Día de calendario de trabajo                  | Buscar        | X            | X              |
| Número de intervalo de tiempo del calendario de trabajo | Text          | X            | X              |

## <a name="organization-entities"></a>Entidades de la organización

**Empresa**

| **Campos**   | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|--------------|---------------|--------------|----------------|
| Código de empresa | Text          | X            | X              |
| Nombre         | Text          | X            | X              |


**Departamento**

| **Campos**        | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-------------------|---------------|--------------|----------------|
| Número del departamento | Text          | X            | X              |
| Descripción       | Text          |              | X              |
| Nombre              | Text          | X            | X              |
| Departamento principal | Buscar        |              | X              |


**Divisa**

| **Campos**         | **Tipo de datos**  | **Requerido** | **Se puede buscar** |
|--------------------|----------------|--------------|----------------|
| Código de divisa      | Text           | X            | X              |
| Nombre de divisa      | Text           | X            | X              |
| Precisión de divisa | Número entero   | X            | X              |
| Símbolo de divisa    | Text           | X            | X              |
| Imagen de entidad       | Imagen          |              |                |
| Tipo de cambio      | Número decimal | X            | X              |
| Organización       | Buscar         | X            | X              |
| Estado             | Conjunto de opciones     |              | X              |

## <a name="payroll-entities"></a>Entidades de nómina

**Ciclo de pago**

| **Campos**  | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-------------|---------------|--------------|----------------|
| Descripción | Text          | X            | X              |
| Frecuencia   | Conjunto de opciones    | X            | X              |
| Nombre        | Text          | X            | X              |


**Período de pago**

| **Campos**           | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|----------------------|---------------|--------------|----------------|
| Fecha de pago predeterminada | Solo fecha     |              | X              |
| Descripción          | Text          |              | X              |
| Ciclo de pago            | Mirar          | X            | X              |
| Número de período de pago    | Text          | X            | X              |
| Fecha final de período      | Solo fecha     | X            | X              |
| Fecha inicial del período    | Solo fecha     | X            | X              |
| Estado               | Conjunto de opciones    |              | X              |


**Código de ganancia de nómina**

| **Campos**              | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-------------------------|---------------|--------------|----------------|
| Descripción             | Text          | X            | X              |
| Incluir en tipo de pago | Conjunto de opciones    | X            | X              |
| Es productivo           | Dos opciones   | X            | X              |
| Nombre                    | Text          |              | X              |
| Unidad de cantidad           | Conjunto de opciones    |              | X              |
| Seguimiento de horas FMLA        | Dos opciones   |              | X              |


**Región de impuestos**

| **Campos**        | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-------------------|---------------|--------------|----------------|
| Ciudad              | Text          |              | X              |
| Región o país | Text          |              | X              |
| Provincia            | Text          |              | X              |
| Nombre              | Text          | X            | X              |
| Comunidad autónoma o provincia | Text          |              | X              |


**Período de pago de la frecuencia de cálculo de prestación**

| **Campos**                                      | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-------------------------------------------------|---------------|--------------|----------------|
| Frecuencia de cálculo de la prestación                   | Buscar        | X            | X              |
| Número de período de pago de la frecuencia de cálculo de prestación | Text          | X            | X              |
| Período de pago                                      | Buscar        | X            | X              |


**Desembolso de cuenta bancaria**

| **Campos**                       | **Tipo de datos**  | **Requerido** | **Se puede buscar** |
|----------------------------------|----------------|--------------|----------------|
| Importe                           | Divisa       |              | X              |
| Importe (base)                    | Divisa       |              | X              |
| Cuenta bancaria                     | Buscar         | X            | X              |
| Número de desembolso de cuenta bancaria | Text           | X            | X              |
| Compañía                          | Buscar         | X            | X              |
| Divisa                         | Buscar         |              | X              |
| Tipo de cambio                    | Número decimal |              | X              |
| Es restante                     | Dos opciones    |              | X              |
| Prioridad                         | Número entero   |              | X              |

**Agencia emisora de identificación de personas**

| **Campos**           | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|----------------------|---------------|--------------|----------------|
| Descripción de la dirección  | Text          |              | X              |
| Línea de dirección 1       | Text          |              | X              |
| Línea de dirección 2       | Text          |              | X              |
| Línea de dirección 3       | Text          |              | X              |
| Ciudad                 | Text          |              | X              |
| Región o país    | Conjunto de opciones    |              | X              |
| Provincia               | Text          |              | X              |
| Descripción          | Text          |              | X              |
| Correo electrónico                | Text          |              | X              |
| Extensión            | Text          |              | X              |
| Fax                  | Text          |              | X              |
| Nombre de agencia emisora  | Text          | X            | X              |
| Teléfono móvil         | Text          |              | X              |
| Página                 | Text          |              | X              |
| Código postal          | Text          |              | X              |
| Apartado de correos      | Text          |              | X              |
| SMS                  | Text          |              | X              |
| Comunidad autónoma o provincia    | Text          |              | X              |
| Teléfono            | Text          |              | X              |
| Télex                | Text          |              | X              |
| Dirección URL del sitio web          | Text          |              | X              |

**Tipo de identificación de persona del trabajador**

| **Campos**                        | **Tipo de datos**  | **Requerido** | **Se puede buscar** |
|-----------------------------------|----------------|--------------|----------------|
| Valores permitidos                    | Conjunto de opciones     |              | X              |
| Región o país                 | Text           |              | X              |
| Descripción                       | Text           |              | X              |
| Longitud fija                      | Número entero   |              | X              |
| Formato de número de identificación      | Text           |              | X              |
| Tipo                              | Conjunto de opciones     |              | X              |
| Tipo de identificación de persona del trabajador | Text           | X            | X              |

## <a name="fixed-compensation-entities"></a>Entidades de compensación fija

**Plan de compensación fija**

| **Campos**                  | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-----------------------------|---------------|--------------|----------------|
| Compañía                     | Buscar        | X            | X              |
| Cuadrícula de compensación           | Buscar        |              | X              |
| Divisa                    | Buscar        | X            | X              |
| Descripción                 | Text          | X            | X              |
| Fecha de vigencia              | Solo fecha     | X            | X              |
| Fecha de vencimiento             | Solo fecha     | X            | X              |
| Regla de contratación                   | Conjunto de opciones    | X            | X              |
| Nombre                        | Text          | X            | X              |
| Fuera del intervalo de tolerancia      | Conjunto de opciones    | X            | X              |
| Frecuencia de pago               | Buscar        | X            | X              |
| Recomendación permitida      | Dos opciones   | X            | X              |
| Configuración de línea de punto de referencia  | Buscar        |              | X              |
| Tipo                        | Conjunto de opciones    | X            | X              |

**Cuadrícula de compensación**

| **Campos**                  | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-----------------------------|---------------|--------------|----------------|
| Compañía                     | Buscar        | X            | X              |
| Divisa                    | Buscar        |              | X              |
| Descripción                 | Text          | X            | X              |
| Fecha de vigencia              | Solo fecha     |              | X              |
| Fecha de vencimiento             | Solo fecha     |              | X              |
| Nombre                        | Text          | X            | X              |
| Configuración de punto de referencia       | Buscar        | X            | X              |
| Tipo                        | Conjunto de opciones    | X            | X              |

**Nivel de compensación**

| **Campos**      | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-----------------|---------------|--------------|----------------|
| Descripción     | Text          |              | X              |
| Nombre            | Text          | X            | X              |
| Tipo            | Conjunto de opciones     | X            | X              |

**Frecuencia de pago de compensación**

| **Campos**                  | **Tipo de datos**   | **Requerido** | **Se puede buscar** |
|-----------------------------|-----------------|--------------|----------------|
| Factor de conversión anual    | Número decimal  |              | X              |
| Compañía                     | Buscar          | X            | X              |
| Descripción                 | Text            |              | X              |
| Factor de conversión de horas    | Número decimal  |              | X              |
| Factor de conversión mensual   | Número decimal  |              | X              |
| Nombre                        | Text            | X            | X              |
| Período                      | Conjunto de opciones      |              | X              |
| Factor de conversión semanal    | Conjunto de opciones      |              | X              |


**Configurar puntos de referencia de compensación**

| **Campos**          | **Tipo de datos**   | **Requerido** | **Se puede buscar** |
|---------------------|-----------------|--------------|----------------|
| Compañía             | Buscar          | X            | X              |
| Tipo de compensación   | Conjunto de opciones      | X            | X              |
| Descripción         | Text            | X            | X              |
| Nombre                | Text            | X            | X              |

**Línea de configuración de puntos de referencia de compensación**

| **Campos**            | **Tipo de datos**   | **Requerido** | **Se puede buscar** |
|-----------------------|-----------------|--------------|----------------|
| Compañía               | Buscar          | X            | X              |
| Descripción           | Text            | X            | X              |
| Número de línea           | Número decimal  | X            | X              |
| Nombre                  | Text            | X            | X              |
| Configuración de punto de referencia | Buscar          | X            | X              |

**Región de compensación**

| **Campos**      | **Tipo de datos** | **Requerido** | **Se puede buscar** |
|-----------------|---------------|--------------|----------------|
| Descripción     | Text          | X            | X              |
| Nombre            | Text          | X            | X              |

**Estructura de compensación**

| **Campos**                    | **Tipo de datos**   | **Requerido** | **Se puede buscar** |
|-------------------------------|---------------  |--------------|----------------|
| Importe                        | Divisa        |              | X              |
| Importe base                   | Divisa        |              | X              |
| Compañía                       | Buscar          | X            | X              |
| Número de estructura de compensación | Text            | X            | X              |
| Divisa                      | Buscar          |              | X              |
| Tipo de cambio                 | Número decimal  |              | X              |
| Cuadrícula                          | Buscar          | X            | X              |
| Nivel                         | Buscar          | X            | X              |
| Punto de referencia               | Buscar          | X            | X              |
| Configuración de línea de punto de referencia    | Buscar          | X            | X              |

**Evento de compensación fija**

| **Campos**            | **Tipo de datos**   | **Requerido** | **Se puede buscar** |
|-----------------------|-----------------|--------------|----------------|
| Compañía               | Buscar          | X            | X              |
| Descripción           | Text            | X            | X              |
| Tipo de evento            | Conjunto de opciones      | X            | X              |
| Está activo             | Dos opciones     | X            |                |
| Nombre                  | Text            | X            | X              |

## <a name="entity-relationship-models"></a>Modelos de relación de entidad

### <a name="worker"></a>Trabajador
![Trabajador](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Trabajo y puesto de trabajo
![Trabajo y puesto de trabajo](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Prestaciones
![Prestaciones](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Compensación
![Compensación](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Dejar
![Dejar](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Calendario de trabajo
![Calendario de trabajo](./media/HCMCommon-work-calendar-entity-diagram.png)
