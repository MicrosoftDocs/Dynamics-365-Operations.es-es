---
title: Configurar la integración de nóminas entre Talent y Dayforce
description: Este tema explica cómo configurar la integración entre Microsoft Dynamics 365 for Talent y Ceridian Dayforce de modo que pueda procesar un período de pago.
author: andreabichsel
manager: AnnBe
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9a88bf61dbb12520b555ceb7363b1c646d95386e
ms.sourcegitcommit: 204e4554e409c39fbbf7b273ad138ce2809931a8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "898453"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a>Configurar la integración de nóminas entre Talent y Dayforce

[!include [banner](includes/banner.md)]

La integración entre Microsoft Dynamics 365 for Talent y Ceridian Dayforce se basa en varios pasos de configuración que se describen en este tema. Debe configurar la integración en Talent y Dayforce para poder procesar un período de pago.

Cuando se utiliza un servicio como Dayforce para completar períodos de pago, debe habilitar la integración en Talent. La integración necesita los datos específicos de Talent. Por lo tanto, debe comprobar que los datos que se asignen a Dayforce se hayan configurado en Talent de una forma que admita la integración. La integración utiliza las amplias categorías de datos siguientes:

- Datos de recursos humanos
- Catos de compensación
- Datos de nómina, como ciclos de pago, períodos de sueldo, y códigos de ganancias
- Datos de trabajadores

Este tema describe los pasos que debe seguir para habilitar la integración. También explica los tipos de datos y los detalles de configuración que requiere la integración.

## <a name="enable-the-integration"></a>Habilitar la integración

En Talent, debe activar la integración y especificar información de configuración para conectarse a Dayforce. Si desea que la transacción de contabilidad general que se genera se importe en Microsoft Dynamics 365 for Finance and Operations, también debe configurar una cuenta de almacenamiento de Microsoft Azure y especificar la cadena de conexión Azure Storage en Finance and Operations.

Para activar la integración en Talent, siga estos pasos.

1. En la página **Administración del sistema** , seleccione **Configuración de la integración**.
2. Permite especificar el extremo del Protocolo de transferencia de archivos (FTP) y la ruta de carpeta de FTP seguro.
3. Escriba el nombre de usuario y contraseña del usuario que accederá al extremo y la ruta de carpeta de FTP seguro.
4. Pruebe la conexión, como sea necesario, y establezca la opción **Habilitar la integración de nómina** en **Sí**.

Cuando está activada la integración, se crean el paquete y los archivos de exportación de datos, y se establece la frecuencia. Puede cambiar esta frecuencia como sea necesario.

Para obtener más información acerca de las cuentas de almacenamiento de Azure y las cadenas de conexión de Azure Storage, consulte los temas de Azure siguientes:

- [Acerca de las cuentas de almacenamiento de Azure](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [Configurar las cadenas de conexión de Azure Storage](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a>Configurar los datos 

Para procesar las nóminas, debe configurar los datos de recursos humanos en Talent. Debe configurar datos de organización, como los trabajos y los puestos, así como las prestaciones y la información de compensación. Esta información proporciona la información de empleo, pago y deducciones que se necesita para producir el sueldo del empleado.

### <a name="human-resource-data"></a>Datos de recursos humanos

#### <a name="benefits"></a>Beneficios 

Recursos humanos ofrece herramientas para la configuración y el mantenimiento de prestaciones, deducciones y los planes de compensación de los trabajadores que una organización ofrece o procesa para sus trabajadores.

Al crear las prestaciones, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.

##### <a name="benefit-plans"></a>Planes de prestaciones

- Plan (obligatorio)
- Tipo (obligatorio)
- Impacto de nómina (obligatorio)
- Recuperar atrasos
- Método de deducción
- Prioridad de deducción
- Período de límite
- Importe límite

##### <a name="benefits"></a>Beneficios

- Plan (obligatorio)
- Tipo (obligatorio)
- Opción (obligatorio)
- Identificador de prestación (obligatorio)
- Frecuencia
- Base
- Importe o índice
- Código de ganancias

##### <a name="supported-frequencies"></a>Frecuencias admitidas 

- Semanalmente
- Quincenal
- Bimensual
- Mensualmente

##### <a name="supported-bases"></a>Bases admitidas 

- Importe fijo
- Porcentaje de ganancias
- Horas productivas

Dayforce crea las deducciones siguientes, según el impacto de nómina que hay definido en el plan de prestaciones.

| Selección en Talent        | Resultado en Dayforce                            |
|----------------------------|-----------------------------------------------|
| Sin ordenar                       | No se crea ninguna deducción.                      |
| Solo deducción             | Se crea una deducción del empleado.             |
| Solo contribución          | Se crea una deducción del empresario.             |
| Deducción y contribución | Se crean las deducciones del empleado y del empresario. |

Para obtener más información sobre cómo definir y administrar un programa de prestaciones, consulte los siguientes temas:

- [Proporcionar un programa de prestaciones de empleado](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [Crear una nueva prestación](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [Definir reglas y directivas de idoneidad para prestaciones](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [Inscribir y quitar prestaciones para trabajadores](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a>Compensación 

La gestión de compensaciones se usa para controlar la entrega de salarios base y primas. El sueldo base fijo de un empleado y los aumentos por méritos se controlan mediante planes de compensación fijos. El pago de incentivos, como los pagos de bonificación, las primas por rendimiento, las acciones y las concesiones, así como también las primas ocasionales, se controlan a través de planes de compensación variable.

Dayforce utiliza la información de compensación para calcular la tarifa por hora o anual de un empleado. Se requieren planes de compensación fija y conversiones de índice salarial. Los empleados deben estar asociados a un plan de compensación fija.

Para obtener más información acerca de los panes de compensación, consulte los siguientes temas:

- [Crear planes de compensación fija](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [Crear planes de compensación variable](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [Desarrollar planes y estructura de salarios o compensaciones](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [Procesar compensaciones](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [Definición del proceso de compensación y el cálculo de resultados](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [Inscribir a un empleado en un plan de compensación fija](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [Inscribir a un empleado en un plan de compensación variable](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a>Trabajos 

Un trabajo es un conjunto de las tareas y responsabilidades que deberá cumplir la persona que realiza un trabajo. Para obtener más información, consulte los siguientes temas:

- [Configurar los componentes de un trabajo](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [Definir nuevos trabajos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a>Puestos

Un puesto es un caso individual de un trabajo. Por ejemplo, el puesto "Director de ventas (Este)" es uno de los puestos asociados al trabajo "Director de ventas". Un puesto existe en un departamento. Solo un trabajador puede asociarse solo a cada puesto.

Tenga en cuenta los siguientes datos y configuración al configurar los puestos:

- Puesto (obligatorio)
- Descripción (obligatorio)
- Trabajo (obligatorio)
- Departamento (obligatorio)
- Tipo de puesto (obligatorio)
- Equivalente de jornada completa
- Horas ordinarias anuales (obligatorio)
- Pagado por la entidad jurídica (obligatorio)
- Ciclo de pago (obligatorio)
- Dimensión financiera predeterminada – Centro de coste (obligatorio)
- Asignación de trabajador – Trabajador, inicio de la asignación, final de la asignación, código de motivo

Si varios puestos en el mismo departamento están asociados al mismo trabajo, se consolidan en un solo puesto en Dayforce.

Para obtener más información, consulte los siguientes temas:

- [Organizar los recursos mediante departamentos, trabajos y puestos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [Configurar puestos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a>Departamentos

Un departamneto es una unidad operativa que representa una categoría o un área funcional de la organización. Un departamento es responsable de un área específica de la organización, como ventas, contabilidad o recursos humanos. Puede usar departamentos para informar sobre las áreas funcionales. Los departamentos pueden tener responsabilidad de pérdidas y ganancias.

Para obtener más información, consulte los siguientes temas:

- [Crear un departamento y asociarlo a la jerarquía de departamentos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [Definir nuevos departamentos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a>Ciclos y períodos de pago

Un ciclo de pago determina la frecuencia con la que se ejecuta el cálculo de nómina y los días específicos en los que se paga a los trabajadores. Por ejemplo, un ciclo de pago puede ser mensual y a los empleados se les podría pagar el último día del mes. De forma alternativa, un ciclo de pago puede ser semanal y a los empleados se les podría pagar el martes después del final del período de pago. Los ciclos de pago se asignan a los puestos para controlar cuándo se paga a los trabajadores en esos puestos.

Después de crear ciclos de pago, puede generar los períodos de pago para cada ciclo. Cada período de pago incluye una fecha de pago predeterminada basada en la información que proporcione. Sin embargo, puede modificar la fecha de pago predeterminada en un período de pago para permitir excepciones, por ejemplo, cuando la fecha de pago se encuentra en un día festivo.

La siguiente información se usa en Dayforce:

- Ciclo de pago (obligatorio)
- Frecuencia del ciclo de pago (obligatorio)
- Fecha de inicio del período (primer período de pago obligatorio)
- Fecha de pago predeterminado (primer período de pago obligatorio)

Esta información se integra con Dayforce como grupos salariales y se separa por país o región para cada ciclo de pago. Al menos se debe generar un período de sueldo antes de la integración. Dayforce genera los calendarios de grupo salarial y las fechas de pago, en función de la fecha inicial del primer período de pago y la fecha de pago predeterminada que se configuran en Talent.

#### <a name="earning-codes"></a>Códigos de ganancia

Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores. Los códigos tienen distintos parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.

La siguiente información se usa en Dayforce:

- Código de ganancias (obligatorio)
- Descripción
- Unidad de medida
- Productivo

### <a name="worker-data"></a>Datos de trabajadores

Los registros para los diferentes tipos de trabajadores que tiene son importantes para los sistemas de recursos humanos y nómina. La información que se indique se puede utilizar para efectuar un seguimiento de los trabajadores y su información personal.

Puede mantener la información siguiente para los trabajadores:

- **Básica**: permite mantener la información básica de un trabajador, como la información de contacto, información demográfica, información de identificación, información de familia, estado del servicio militar, información de expatriado y contactos personales y de emergencia.
- **Empleo**: permite mantener la información sobre el empleo de un trabajador, como afiliación de la empresa u organización, asignación de puesto, fecha de inicio y finalización, idoneidad para el trabajo, condiciones de empleo, pensión, vacaciones y la información de reubicación.
- **Bajas y ausencias**: permite mantener información sobre las ausencias de un trabajador, como calendarios de trabajo, transacciones de ausencia y configuración de ausencias.
- **Compensación y nómina**: permite mantener la información sobre los planes de compensación y la información de nómina de un trabajador, como inscripción del plan, concesiones, desempeño, comisión, información fiscal, retiro y deducciones de sueldo.

Al introducir la información del trabajador, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.

#### <a name="general-information"></a>Información general

- Número de personal (obligatorio)
- Nombre (obligatorio)
- Apellido (obligatorio)
- Segundo nombre
- Antigüedad
- Conocido como

#### <a name="personal-information"></a>Información personal

- Estado civil (obligatorio)
- Fecha de nacimiento (obligatorio)
- Sexo (obligatorio)
- Persona con discapacidades
- País o región, nacionalidad (solo para México)

#### <a name="address-information"></a>Información de dirección

- Principal (obligatorio)
- País o región (obligatorio)
- Código postal (obligatorio)
- Número de calle (obligatorio) (solo para México)
- Complemento de edificio (solo para México)
- Ciudad (obligatorio)
- Estado (obligatorio)
- Provincia (obligatorio)

#### <a name="contact-information"></a>Información de contacto 

- Principal (obligatorio)
- Número de contacto (obligatorio)
- Extensión

#### <a name="payroll-information-and-earning-codes"></a>Información de nómina y códigos de ganancias

A los empleados se les pueden asignar ganancias específicas de una frecuencia determinada de pago y tener un método de pago preferido. Los siguientes campos se utilizan en Dayforce para ayudar a garantizar que se usen las preferencias y valores.

##### <a name="earning-codes"></a>Códigos de ganancia

- Puesto (obligatorio)
- Código de ganancias (obligatorio)
- Frecuencia (obligatorio)
- Importe (obligatorio)

##### <a name="payroll-information"></a>Información de nómina

- Método de pago
- Región económica (obligatorio)
- Id. de prestaciones de empleado
- Número de id. nacional (obligatorio)
- Número de servicio militar
- Id. de turno (obligatorio)
- Número de identificación fiscal (obligatorio)
- Id. de sindicato (obligatorio)
- Id. de día laborable (obligatorio)
- Número de permiso de trabajo

> [!NOTE]
> Para el método de pago, México admite **Efectivo**, **Cheque** (cheque físico de la empresa) y **Pago electrónico**. Si no se especifica ningún método de pago, **Cheque** se usa de forma predeterminada.

#### <a name="employment-details"></a>Detalles del empleo

El historial de detalles de empleo se utiliza como información clave para derivar los estados de contratación, despido y recontratación de un empleado en Dayforce. Dayforce solo admite un registro de empleo activo a la vez.

- Fecha de inicio de empleo (obligatorio)
- Fecha final del empleo
- Fecha de inicio
- Fecha inicial ajustada
- Fecha de finalización (obligatorio en el momento de la finalización)
- Razón de la finalización (obligatorio en el momento de la finalización)

Las fechas clave de un empleado se obtienen utilizando la siguiente información.

| Talent                | Dayforce                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| Fecha de contratación más reciente | Inicio de empleo del registro actual de historial de empleo no finalizado                                 |
| Fecha de finalización      | Fecha de finalización del registro actual de historial de empleo no finalizado                                 |
| Fecha de inicio            | Fecha de inicio ajustada, fecha de inicio o inicio de empleo del registro de historial de empleo inactivo actual |
| Fecha de contratación original    | Inicio del empleo del registro del historial de empleo más temprano                                               |

#### <a name="compensation"></a>Compensación

Un plan de compensación fija se debe asociar al puesto principal de cada empleado durante un período de empleo. Este período comienza en la fecha de contratación del empleado (o la fecha de inicio del empleo) y continúa hasta la finalización.

- Fecha de vigencia (obligatorio)
- Fecha de expiración
- Índice salarial (obligatorio)
- Conversiones de índice salarial (obligatorio)
- Equivalente anual (obligatorio)
- Equivalente por hora (obligatorio)

Si un empleado por hora tiene varios puestos, se importa la compensación fija del puesto principal en Dayforce como índice/salario base de nivel de empleado. En el caso de los puestos no principales, el índice por hora se guarda en el puesto correspondiente en Dayforce.

Si un empleado a sueldo tiene varios puestos, se derivan el índice por hora acumulativa y el sueldo anual en todos los puestos activos y se utilizan como índice/salario base de nivel de empleado.

#### <a name="identification-numbers"></a>Números de identificación

##### <a name="social-security-identifier"></a>Identificador de seguridad social 

Cada empleado debe tener un identificador principal. Este identificador debe ser de tipo de identificación **Nº de SS**. En Dayforce, se deriva automáticamente como el identificador de seguridad social del empleado que se requiere para ser contratado.

- Principal (obligatorio)
- Tipo de identificación = "Nº de SS"
- Fecha de emisión
- Fecha de vencimiento

Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Nº de SS**. Sin embargo, solo el registro que está marcado como **Principal** está integrado en Dayforce, independientemente de si el número está activo o caducado.

#### <a name="bank-accounts-and-disbursements"></a>Cuentas bancarias y desembolsos

La información de cuenta bancaria válida se debe especificar para cualquier empleado que elija recibir el pago por transferencias de cuenta bancaria.

| Talent                         | Dayforce                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| Número de cuenta bancaria (obligatorio) |                                                                                                             |
| Código SWIFT (obligatorio)          | Campo **Identificador del banco** utilizado al procesar la nómina en México.                                                             |
| Número de sucursal (obligatorio)       |                                                                                                             |
| Tipo de cuenta bancaria (obligatorio)   | Campo **Tipo de cuenta** utilizado al procesar la nómina en México. Los valores admitidos incluyen **Comprobación** y **Nómina**. |

> [!NOTE]
> Los empleados que elijan que se les pague a través de transferencia bancaria deben proporcionar un vínculo a una cuenta de remanente que esté en una entidad legal que tenga su dirección principal en México y esté asociada con una cuenta bancaria válida de un banco mexicano. Todas las demás cuentas no remanentes se ignoran.

#### <a name="address-information"></a>Información de dirección

Cada empleado debe tener una ubicación principal. En Dayforce, esta ubicación se usa para determinar la residencia principal del empleado para impuestos.

- Principal (obligatorio)
- País o región (obligatorio)
- Código postal (obligatorio)
- Calle (obligatorio)
- Número de calle (obligatorio)
- Complemento de edificio
- Ciudad (obligatorio)
- Estado (obligatorio)
- Provincia (obligatorio)

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a>Configure los datos para generar nóminas en Estados Unidos y Canadá

Si va a generar el sueldo de los empleados en Estados Unidos y Canadá, los siguientes elementos deben estar configurados:

- Se requieren departamentos en los puestos.
- Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.

> [!NOTE] 
> Puede configurar Talent para requerir que los puestos especifiquen un departamento. Para ello, vaya a **Puestos compartidos de recursos humanos > Puestos > Requerir departamentos en puestos**. Recomendamos que este valor se aplique para la integración.

### <a name="job-types"></a>Tipos de trabajo

Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías. Los tipos de trabajo son obligatorios para procesar la nómina en Estados Unidos y Canadá. Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas. Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.

Los siguientes tipos de trabajo y descripciones son obligatorios.

| Tipo de trabajo   | Descripción |
|------------|-------------|
| Por hora     | Por hora      |
| Asalariado   | Asalariado    |

### <a name="position-types"></a>Tipos de puestos 

Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo. Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.

Los siguientes tipos de puesto y descripciones son obligatorios.

| Tipo de puesto   | Descripción        |
|-----------------|--------------------|
| Jornada completa       | Empleado a jornada completa |
| A tiempo parcial       | Empleado a tiempo parcial |

### <a name="reason-codes"></a>Códigos de motivos

Los códigos de motivos proporcionan información sobre el estado de un empleado. Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.

Los siguientes códigos de motivos y descripciones son obligatorios.

| Código de motivo    | Descripción      | Situaciones aplicables |
|----------------|------------------|----------------------|
| RESIGNATION    | Dimisión      | Dar de baja a trabajador     |
| TERMINATION    | Finalización      | Dar de baja a trabajador     |
| JUBILACIÓN     | Jubilación       | Dar de baja a trabajador     |
| OTHER          | Otros motivos    | Dar de baja a trabajador     |
| MUERTE          | Muerte            | Dar de baja a trabajador     |
| LEAVEOFABSENCE | Permiso para ausentarse | Dar de baja a trabajador     |
| CONTRACTEND    | Fin de contrato  | Dar de baja a trabajador     |
| SALARYCHANGE   | Cambio de salario | Compensación         |

### <a name="marital-status"></a>Estado civil

Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.

En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.

| Talent                 | Dayforce             |
|------------------------|----------------------|
| Casado/a                | Casado/a              |
| Soltero/a                 | Soltero/a               |
| Viudo/a                | Viudo/a              |
| Divorciado/a               | Divorciado/a             |
| Unión registrada | Sociedad doméstica |
| Sin ordenar                   | Sin ordenar                 |
| Cohabitando             | Cohabitando           |

### <a name="gender"></a>Género

Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.

En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.

| Talent       | Dayforce        |
|--------------|-----------------|
| Hombre         | Hombre            |
| Mujer       | Mujer          |
| No específico | *No admitido* |

### <a name="earning-codes"></a>Códigos de ganancia

Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores. Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto. Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.

#### <a name="supported-frequencies"></a>Frecuencias admitidas

- Todas
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>Direcciones

La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer. Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.

| Talent          | Dayforce              |
|-----------------|-----------------------|
| País/región  | Código de país          |
| Código postal | Código postal           |
| Comunidad autónoma           | Código de la comunidad autónoma            |
| Población            | Población                  |
| Comarca          | Condado (municipio) |
| Calle          | Línea de dirección 1        |

### <a name="tax-regions"></a>Regiones de impuestos

Las regiones de impuestos se usan para determinar los impuestos correspondientes que se deben aplicar durante la generación de nómina. Las regiones de impuestos se asignan a Dayforce como direcciones de ubicación. La región de impuestos predeterminada se debe asociar al puesto activo del trabajador. 

- Región de impuestos (obligatorio)
- País o región (obligatorio)
- Estado (obligatorio)
- Comarca 
- Ciudad (obligatorio)

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a>Configurar los datos para generar nóminas en México

Si va a generar el sueldo de los empleados en México, los siguientes elementos deben estar configurados:

- Se requieren departamentos en los puestos.
- Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.

### <a name="job-types"></a>Tipos de trabajo

Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías. Los tipos de trabajo son obligatorios para procesar la nómina en México. Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas. Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.

Los siguientes tipos de trabajo y descripciones son obligatorios.

| Tipo de trabajo   | Descripción |
|------------|-------------|
| Por hora     | MX Por hora   |
| Asalariado   | MX Asalariado |

### <a name="position-types"></a>Tipos de puestos 

Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo. Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.

Los siguientes tipos de puesto y descripciones son obligatorios.

| Tipo de puesto   | Descripción        |
|-----------------|--------------------|
| Jornada completa       | Empleado a jornada completa |
| A tiempo parcial       | Empleado a tiempo parcial |

### <a name="reason-codes"></a>Códigos de motivos

Los códigos de motivos proporcionan información sobre el estado de un empleado. Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.

Los siguientes códigos de motivos y descripciones son obligatorios.

| Código de motivo            | Descripción                    | Situaciones aplicables |
|------------------------|--------------------------------|----------------------|
| DEPARTUREBEFOREPAYMENT | Salida antes de la primera nómina | Dar de baja a trabajador     |
| RESIGNATION            | Dimisión                    | Dar de baja a trabajador     |
| PENSION                | Pensión                        | Dar de baja a trabajador     |
| TERMINATION            | Finalización                    | Dar de baja a trabajador     |
| JUBILACIÓN             | Jubilación                     | Dar de baja a trabajador     |
| ABSENTEE               | Ausente                       | Dar de baja a trabajador     |
| OTHER                  | Otros motivos                  | Dar de baja a trabajador     |
| CLOSURE                | Cierre de operaciones               | Dar de baja a trabajador     |
| MUERTE                  | Muerte                          | Dar de baja a trabajador     |
| LEAVEOFABSENCE         | Permiso para ausentarse               | Dar de baja a trabajador     |
| CONTRACTEND            | Fin de contrato                | Dar de baja a trabajador     |
| SALARYCHANGE           | Cambio de salario               | Compensación         |

### <a name="terms-of-employment"></a>Condiciones laborales

Las condiciones laborales se usan para crear categorías de condiciones laborales. Las condiciones se asignan a Dayforce como valores de indicador de empleo.

Las siguientes condiciones laborales y descripciones son obligatorias.

| Condiciones laborales   | Descripción |
|-----------------------|-------------|
| Normal               | Normal     |
| Directo                | Directo      |
| Prácticas            | Prácticas  |
| Permanente             | Permanente   |

### <a name="marital-status"></a>Estado civil

Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.

En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.

| Talent                 | Dayforce                  |
|------------------------|---------------------------|
| Casado/a                | Casado/a                   |
| Soltero/a                 | Soltero/a                    |
| Viudo/a                | Viudo/a                   |
| Divorciado/a               | Divorciado/a                  |
| Unión registrada | Sociedad doméstica      |
| Sin ordenar                   | *No se admite en México* |
| Cohabitando             | *No se admite en México* |

### <a name="gender"></a>Género

Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.

En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.

| Talent       | Dayforce                  |
|--------------|---------------------------|
| Hombre         | Hombre                      |
| Mujer       | Mujer                    |
| No específico | *No se admite en México* |

### <a name="payment-method"></a>Método de pago

Los métodos de pago ofrecen al empleado y la empresa una forma de describir cómo se pagará a los empleados. Los métodos de pago se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.

En la siguiente tabla se muestra cómo los métodos de pago se asignan a Dayforce.

| Talent             | Dayforce                  |
|--------------------|---------------------------|
| Efectivo               | Efectivo                      |
| Pago electrónico | Transferir                  |
| Comprobación              | Cheque                    |
| Efecto bancario         | *No se admite en México* |
| Otras              | *No se admite en México* |

### <a name="bank-account-type"></a>Tipo de cuenta bancaria

Los tipos de cuenta bancaria se usan para los pagos electrónicos a los empleados. Los tipos de cuenta bancaria se asignan a Dayforce como información de cuenta de transferencia. Los tipos de cuenta bancaria se convierten, según proceda, en los valores aceptados en la integración.

| Talent            | Dayforce                  |
|-------------------|---------------------------|
| Cuenta corriente  | CheckingAccount           |
| Cuenta de nómina   | PayrollAccount            |
| Cuenta de ahorros   | *No se admite en México* |
| Cuenta de BankGirot | *No se admite en México* |
| Cuenta de PlusGirot | *No se admite en México* |

### <a name="earning-codes"></a>Códigos de ganancia

Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores. Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto. Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.

#### <a name="supported-frequencies"></a>Frecuencias admitidas

- Todas
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>Direcciones

La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer. Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.

| Talent              | Dayforce              |
|---------------------|-----------------------|
| País/región      | Código de país          |
| Código postal     | Código postal           |
| Comunidad autónoma               | Código de la comunidad autónoma            |
| Población                | Población                  |
| Comarca              | Condado (municipio) |
| Calle              | Línea de dirección 1        |
| Número de calle       | Línea de dirección 2        |
| Complemento de edificio | Línea de dirección 5        |

### <a name="passport-number"></a>Número de pasaporte

Los empleados pueden declarar la información del pasaporte. Esta información es del tipo de identificación **Pasaporte** y se integra en Dayforce como parte de la información específica de México de un empleado.

- Tipo de identificación = "Pasaporte"
- Fecha de emisión
- Fecha de vencimiento

Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Pasaporte**. Sin embargo, solo la entrada de pasaporte activa actual se integra en Dayforce. Si todas las entradas de pasaporte han caducado, el pasaporte que se emitió más recientemente se integra en Dayforce.
