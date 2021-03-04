---
title: Motores de administración del transporte
description: Los motores de administración del transporte definen la lógica que se usa para generar y procesar tasas de transporte en Administración de transporte.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSGenericEngine, TMSMileageEngine, TMSRateEngine, TMSTransitTimeEngine, TMSZoneEngine, TMSFreightBillTypeAssignment, TMSZoneMaster, TMSEngineParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ab6667ac02ca55eeb093fa5854a962ac4357aaac
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437222"
---
# <a name="transportation-management-engines"></a>Motores de administración del transporte

[!include [banner](../includes/banner.md)]

Los motores de administración del transporte definen la lógica que se usa para generar y procesar tasas de transporte en Administración de transporte. 

Un motor de administración del transporte calcula tareas como, por ejemplo, la tasa de transporte del transportista. El sistema del motor le permite cambiar las estrategias de cálculo en tiempo de ejecución, basándose en los datos de Supply Chain Management. Un motor de administración del transporte se asemeja a un complemento relacionado con un contrato concreto del transportista.

## <a name="what-engines-are-available"></a>¿Qué motores están disponibles?
En la siguiente tabla se muestran los motores de administración del transporte disponibles.

| Motor de administración del transporte | Descripción                                                                                                                                                                                                                                                                                                                 |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motor de tasas**                  | Calcula las tasas.                                                                                                                                                                                                                                                                                                           |
| **Motor genérico**               | Motores auxiliares simples que usan otros motores que no necesitan datos de Supply Chain Management, por ejemplo, un motor de reparto. Los motores de reparto se usan para reducir los costes finales de transporte en determinados pedidos y líneas, basándose en dimensiones, como el volumen y el peso. |
| **Motor de kilometraje**               | Calcula la distancia de transporte.                                                                                                                                                                                                                                                                                     |
| **Motor de tiempo de tránsito**          | Calcula el tiempo necesario para desplazarse desde el inicio hasta el destino final.                                                                                                                                                                                                                                       |
| **Motor de zona**                  | Calcula la zona basada en la dirección actual y calcula el número de zonas que se deben cruzar para desplazarse de la dirección A a la dirección B.                                                                                                                                                                    |
| **Tipo de albarán de flete**            | Estandariza la factura de flete y las líneas de albarán de flete y se usa para conciliar automáticamente albaranes de flete.                                                                                                                                                                                                                |


<a name="what-engines-must-be-configured-to-rate-a-shipment"></a>¿Qué motores se deben configurar para clasificar un envío?
---------------------------------------------------

Para clasificar un envío mediante un transportista específico, debe configurar varios motores de administración del transporte. El **Motor de tarifas** es necesario, pero es posible que también sean necesarios otros motores de administración del transporte para ofrecer soporte al **Motor de tarifas**. Por ejemplo, el **Motor de tarifas** se puede usar para recuperar los datos del **Motor de cálculo de kilometraje** con el fin de calcular la tasa basándose en el kilometraje entre el origen y el destino.

## <a name="whats-required-to-initialize-a-transportation-management-engine"></a>¿Qué se necesita para inicializar un motor de administración del transporte?
Un motor de administración del transporte necesita que configure los datos de inicialización para que funcionen de una manera específica. La configuración puede incluir los siguientes tipos de datos:
-   Referencias a otros motores de administración del transporte. Para obtener detalles, vea el ejemplo de configuración de esta sección.
-   Referencias a los tipos de .NET que usa el motor de administración del transporte.
-   Datos de configuración simple.

En la mayoría de los casos, puede hacer clic en el botón **Parámetros** de los formularios de configuración del motor de administración del transporte para configurar los datos de inicialización. **Ejemplo de la configuración de un motor de tarifas que hace referencia a un motor de cálculo de kilometraje** En el siguiente ejemplo se muestra la configuración necesaria para un motor de tarifas basado en tipo de motor .NET Microsoft.Dynamics.Ax.Tms.Bll.MileageRateEngine y hace referencia a un motor de cálculo de kilometraje.

|          Parámetro           |                                                                                  Descripción                                                                                  |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <em>RateBaseAssigner</em>   | El tipo de .NET que interpreta los datos de asignación base de la tasa para un esquema concreto. La sintaxis del valor del parámetro consta de dos segmentos delimitados por una barra vertical ( |
|  <em>MileageEngineCode</em>  |                       Código del motor de cálculo de kilometraje que identifica el registro del motor de cálculo de kilometraje en la base de datos.                        |
| <em>ApportionmentEngine</em> |                        Código de motor genérico que identifica el motor de reparto en la base de datos.                        |

<a name="how-is-metadata-used-in-transportation-management-engines"></a>¿Cómo se usan los metadatos en los motores de administración del transporte?
----------------------------------------------------------

Los motores de administración del transporte que se basan en datos definidos en Supply Chain Management pueden usar diferentes esquemas de datos. El sistema de administración del transporte permite que distintos motores de administración del transporte usen las mismas tablas de base de datos física genéricas. Para garantizar que la interpretación en tiempo ejecución de los datos del motor sea correcta, puede definir los metadatos de las tablas de base de datos. Esto reduce el coste de crear nuevos motores de administración del transporte porque las estructuras adicionales de tabla y formulario no son necesarias en Operaciones.

## <a name="what-can-be-used-as-search-data-in-rate-calculations"></a>¿Qué se puede usar como datos de la búsqueda en los cálculos de tasas?
Los datos que se usan al calcular tasas se controlan mediante la configuración de metadatos. Por ejemplo, si desea buscar tasas basadas en códigos postales debe configurar los metadatos según el tipo de búsqueda de un código postal.

## <a name="do-all-engine-configurations-require-metadata"></a>¿Todas las configuraciones de motores requieren metadatos?
No, los motores de administración del transporte que se usan para recuperar los datos necesarios para el cálculo de tasas de sistemas externos no necesitan metadatos. Los datos de tasas para estos motores se pueden recuperar a partir de sistemas de transportistas externos, generalmente mediante un servicio web. Por ejemplo, puede usar un motor de cálculo de kilometraje que recupera datos directamente de Mapas de Bing de modo que no necesite metadatos para este motor.

| **Nota**                                                                                                                                                                                                                                                                                                                                                                     |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Los motores de administración del transporte que se entregan con Supply Chain Management se basan en datos recuperados de la aplicación. Los motores que se conectan a sistemas externos no se incluyen con Operaciones. Sin embargo, el modelo de extensibilidad basado en motores le permite crear extensiones mediante Visual Studio Tools. |

## <a name="how-do-i-configure-metadata-for-a-transportation-management-engine"></a>¿Cómo se configuran los metadatos para un motor de administración del transporte?
Los metadatos para motores de administración del transporte se configuran de forma diferente para cada tipo de motor.

| Motor de administración del transporte               | Configuración de metadatos                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motor de tasas**                                | Requiere un **Tipo de base de tasa**. El tipo de base de tasa contiene metadatos para los datos base de tasa y los datos de asignación de base de tasa. La estructura de los metadatos de base de tasa viene determinada por el tipo de motor de tarifas. La estructura de los metadatos de asignación de base de tasa viene determinada por el tipo de asignador de base de tasa asociado a ese motor de tarifas. Debe configurar el tipo de base de tasa de un motor de tarifas en la página **Motor de tarifas** y en la página **Tasa maestra**. |
| **Motor de zona**                                | Necesita que los metadatos se configuren directamente en la zona maestra.                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Motor de cálculo de tiempo de tránsito** y **Motor de cálculo de kilometraje** | Recupera los metadatos directamente del formulario de configuración del motor de cálculo de kilometraje.                                                                                                                                                                                                                                                                                                                                                                                  |

  **Ejemplo de metadatos para un motor de tarifas** El motor de administración del transporte requiere la identificación de la dirección de origen, el estado y el país o la región de destino, así como el punto de envío inicial y final. Una vez cumplidos estos requisitos, los metadatos aparecerán como los datos de la tabla siguiente. La tabla también incluye información acerca del tipo de datos de entrada necesario.
-   Defina esta información en **Administración de transporte** &gt; **Configurar** en la página **Tipo de base de tasa**.

| Secuencia | Nombre                          | Tipo de campo | Tipo de datos | Tipo de búsqueda    | Obligatorio |
|----------|-------------------------------|------------|-----------|----------------|-----------|
| 1        | Código postal de origen            | Asignación | Cadena    | Código postal    | Seleccionado  |
| 2        | Estado o comunidad autónoma de destino             | Asignación | Cadena    | Estatal          |           |
| 3        | Código postal inicial de destino | Asignación | Cadena    | Código postal    | Seleccionado  |
| 4        | Código postal final de destino   | Asignación | Cadena    | Código postal    | Seleccionado  |
| 5        | País de destino           | Asignación | Cadena    | País o región |           |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]