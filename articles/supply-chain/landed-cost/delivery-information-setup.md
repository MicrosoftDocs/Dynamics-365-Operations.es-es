---
title: Configuración de la información de entrega
description: Este tema describe cómo configurar la información de entrega para el módulo de costo de entrega.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMPortTable, ITMLeadTimeTable, ITMLegTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 5d20f732f02140204d67e5602acaf42f9d9df424
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021597"
---
# <a name="delivery-information-setup"></a>Configuración de la información de entrega

[!include [banner](../../includes/banner.md)]

Este tema describe cómo configurar la información de entrega para el módulo de **costo de entrega**.

## <a name="shipping-ports"></a>Puertos de envío

Los puertos de envío identifican desde y hacia dónde se envían las mercancías. Para cada viaje, se definen un puerto "a" y un puerto "de", en función del viaje que se selecciona para el barco de viaje. Los puertos de envío se utilizan para construir los tramos de un viaje y también las actividades del viaje. Por lo general, se definen mediante el nombre de la ciudad y el país o región donde se encuentra el puerto de envío físico.

Para trabajar con puertos de envío, vaya a **Coste de aterrizaje \> Configuración de la información de entrega \> Puertos de envío**. Allí, puede ver, agregar y eliminar registros para sus puertos de envío. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Puerto de envío | Escriba un nombre/número de identificador único para el puerto de envío. |
| Descripción | Permite especificar una descripción del puerto de envío. |

## <a name="tracking-control-center"></a><a name="tracking-control-center"></a>Centro de control de seguimiento

Utilice el centro de control de seguimiento para configurar los plazos de entrega, las actualizaciones de estado y el flujo de información asociado con un viaje a medida que los contenedores de envío se mueven de un tramo al siguiente. Cuando crea un registro de control de seguimiento, se asocia con un tramo específico de un viaje para un viaje. Cuando un viaje actualiza un tramo, el registro asociado se actualizará y completará como se define. Puede actualizar la información de seguimiento para viajes individuales desde la página **Todos los viajes**.

Para abrir el centro de control de seguimiento, vaya a **Coste de aterrizaje \> Configuración de la información de entrega \> Centro de control de seguimiento**.

El centro de control de seguimiento muestra una de las tres vistas de página, según el valor seleccionado en el campo **Crear tipo** en el panel de lista: *Blanco*, *Tiempo de espera* o *Actualización de estado*. Cada tipo de creación actualiza un conjunto diferente de información que se asocia con el progreso de un viaje desde el punto de origen hasta el destino final.

### <a name="common-rule-settings"></a>Configuración común de las reglas

La siguiente tabla muestra los campos que están disponibles para los tres tipos de creación en el Centro de control de seguimiento.

| Campo | Descripción |
|---|---|
| Tabla de origen, campo de origen | Estos campos identifican una tabla de origen y un campo en la base de datos. La regla cargará el valor en el campo y luego lo usará de la manera que se define en otras configuraciones de la regla. |
| Tabla de destino, campo de destino | Estos campos identifican una tabla de destino y un campo en la base de datos. La regla cargará el valor en el campo y luego lo usará (o sobrescribirá) de la manera que se define en otras configuraciones de la regla. |
| Actividad | Este campo identifica el tipo de actividad que se debe aplicar a un contenedor de envío que coincide con una regla. |
| Criterios de coincidencia | Este campo determina cómo el sistema identifica una coincidencia para una regla. En cada caso, el sistema revisa los datos en las tablas de origen y destino para determinar si un campo debe actualizarse en la tabla de destino y cuándo.<p>Por ejemplo, la tabla de origen es *Viajes* y la tabla de destino es *Encabezado de compra* o *Líneas de compra*. La tabla *Viajes* tiene un valor **Desde el puerto** de *Hong Kong* y la tabla *Encabezado de compra* tiene un valor **Desde el puerto** de *Shanghai*. Luego se crea una regla que tiene *Hong Kong* como el puerto de origen. En este caso, los valores del campo **Criterios coincidentes** funcionarán de la siguiente manera:</p><ul><li>**Ambos** - El campo de destino no se actualizará porque uno de los dos puertos no coincide.</li><li>**Fuente** - El campo de destino se actualizará, porque el puerto "desde" de la tabla de origen es *Hong Kong*.</li><li>**Objetivo** - El campo de destino no se actualizará, porque el puerto "desde" de la tabla de destino es *Shanghai* (no *Hong Kong*).</li></ul> |
| Copiar acción | Los valores disponibles son *Copiar* y *Predeterminado*. Seleccione *Copiar* para copiar el valor del campo de origen al campo de destino. Seleccione *Predeterminado* para establecer un valor estático para el campo de destino. |
| Predeterminada | Cuando el campo **Acción de copia** está configurado en *Predeterminado*, el campo **Predeterminado** define el valor predeterminado del campo de destino. Por ejemplo, si la acción está relacionada con una actualización de puerto y el campo **Acción de copia** está configurado en *Predeterminado*, el campo **Predeterminado** identifica un puerto. |
| Escala | Este campo identifica el tramo del viaje para el que ocurre la acción especificada, como carga o aduana. |
| Proveedor de servicio | Si se utiliza un proveedor de servicios específico para la actualización del estado actual / tramo del viaje, este campo identifica al proveedor de servicios. Los proveedores de servicios se definen en la cuenta del proveedor. |

### <a name="lead-time-rules"></a>Reglas de plazo

El tiempo de espera es el tiempo estimado que requerirá un viaje para completar un tramo definido de un viaje para un viaje. El tiempo de espera de cada tramo de un viaje se utiliza para calcular la fecha de entrega estimada del viaje. Luego, esa fecha se ingresa en el campo **Fecha de entrega confirmada** en cada línea de compra en el viaje.

Utiliza reglas de tiempo de entrega para administrar las actualizaciones de fechas. Las actividades se generan automáticamente cuando se utiliza una plantilla de viaje para un viaje.

Para agregar una regla de tiempo de entrega al centro de control de seguimiento, siga estos pasos.

1. Siga uno de estos pasos:

    - Ir **Coste de aterrizaje \> Configuración de viaje de varios tramos \> Tramos**. Seleccione el tramo para el que desea configurar los plazos de entrega y luego, en el Panel de acciones, seleccione **Centro de control de seguimiento**. El centro de control de seguimiento está precargado con información sobre el tramo seleccionado.
    - Ir **Coste de aterrizaje \> Configuración de la información de entrega \> Centro de control de seguimiento**. A continuación, debe seleccionar manualmente un tramo en el paso 4 de este procedimiento.

1. En el panel de lista, configure el campo **Crear tipo** en *Tiempo de espera*.
1. En el panel de acciones, haga clic en **Nueva**.
1. Si comenzó desde el centro de control de seguimiento en el paso 1, configure el campo **Tramo** como el tramo para el que desea crear una regla de tiempo de entrega. Si comenzó en la página **Tramos**, el campo **Tramo** está preestablecido en el tramo que seleccionó antes de abrir el Centro de control de seguimiento.

    Basado en el valor del campo **Tramo**, varios campos se establecen automáticamente, como se muestra aquí:

    - **Tabla de origen:** *Actividades de contenedores*
    - **Campo fuente:** *Fecha de inicio*
    - **Tabla de destino:** *Actividades de contenedores*
    - **Campo de destino:** *Fecha de finalización estimada*

1. En el campo **Actividad**, seleccione la actividad a la que se debe aplicar la regla actual.
1. En el campo **Tiempo de espera**, ingrese el tiempo de espera (en días) que se debe aplicar cuando se activa la regla actual.

### <a name="status-update-rules"></a>Reglas de actualización de estado

Los registros donde el campo **Crear tipo** esté configurado como *Actualización de estado* actualizarán el estado de las líneas de la orden de compra, o el estado a nivel de viaje, contenedor de envío o folio. Los estados se pueden configurar de forma independiente. Úselos para informar al usuario o al departamento sobre la etapa de un viaje (como documentos recibidos o mercancías en tránsito).

Cuando el campo **Crear tipo** está configurado en *Actualización de estado*, el centro de control de seguimiento incluye una ficha desplegable **Líneas** donde puede definir un área de costo y el estado actualizado del viaje. Por ejemplo, tiene una línea donde el campo **Área de costo** está configurado en *Envase* y el campo **Estado del viaje** está configurado en *Las mercancías en tránsito*. En este caso, cuando un pedido completa el tramo especificado, el campo **Estado del viaje** del contenedor de envío se actualizará a *Mercancías en tránsito*.

Las actualizaciones de estado proporcionan el estado de un viaje a lo largo de las líneas de viaje y las líneas de orden de compra que están asociadas con ese viaje. A medida que un viaje avanza a través de su viaje desde el puerto, la navegación y la aduana, hasta el almacén de destino, el campo **Estado del viaje** del registro de viaje proporciona una vista rápida de la etapa en la que se encuentran los elementos.

Para agregar una regla de actualización de estado al centro de control de seguimiento, siga estos pasos.

1. Siga uno de estos pasos:

    - Ir **Coste de aterrizaje \> Configuración de viaje de varios tramos \> Tramos**. Seleccione el tramo para el que desea configurar una actualización de estado y luego, en el Panel de acciones, seleccione **Centro de control de seguimiento**. El centro de control de seguimiento está precargado con información sobre el tramo seleccionado.
    - Ir **Coste de aterrizaje \> Configuración de la información de entrega \> Centro de control de seguimiento**. A continuación, debe seleccionar manualmente un tramo en el paso 4 de este procedimiento.

1. En el panel de lista, configure el campo **Crear tipo** en *Actualización de estado*.
1. En el panel de acciones, haga clic en **Nueva**.
1. Si comenzó desde el centro de control de seguimiento en el paso 1, configure el campo **Tramo** como el tramo para el que desea crear una regla de actualización de estaod. Si comenzó en la página **Tramos**, el campo **Tramo** está preestablecido en el tramo que seleccionó antes de abrir el Centro de control de seguimiento.

    Basado en el valor del campo **Tramo**, varios campos se establecen automáticamente, como se muestra aquí:

    - **Tabla de origen:** *Actividades de contenedores*
    - **Campo fuente:** *Fecha de finalización real*
    - **Tabla de destino:** Este campo se deja en blanco.
    - **Campo de destino:** Este campo se deja en blanco.

1. En el campo **Actividad**, seleccione la actividad a la que se debe aplicar su regla.
1. En la ficha despelgable **Líneas**, ingrese las actualizaciones de estado para cada área de costo.

### <a name="blank-type-rules"></a>Reglas de tipo en blanco

Utiliza los registros que tienen un valor **Crear tipo** de *En blanco* para anular o ingresar un valor de campo, según los datos de otro campo. Un campo de Landed cost sobrescribirá los datos en otras áreas de Microsoft Dynamics 365 Supply Chain Management, según las reglas que se configuran en el centro de control de seguimiento.

1. Ir **Coste de aterrizaje \> Configuración de la información de entrega \> Centro de control de seguimiento**.
1. En el panel de lista, configure el campo **Crear tipo** como *En blanco*.
1. En el panel de acciones, haga clic en **Nueva**.
1. Defina los valores de origen y destino, los criterios de coincidencia, la acción de copia y otros parámetros relevantes, según sea necesario para su regla.

### <a name="required-tracking-control-setup"></a>Configuración de control de seguimiento requerida

Para cada plantilla de viaje, se deben configurar dos registros en el centro de control de seguimiento. Ambos registros tienen un valor **Crear tipo** de *En blanco* y se utilizan en todas las implementaciones de costos de aterrizaje. Ayudan a garantizar que la fecha de compra confirmada y las fechas esperadas de las mercancías en tránsito se actualicen para los viajes y en las líneas de órdenes de compra relacionadas de la forma esperada.

Se requiere el primer registro para actualizar las líneas de compra. Debe tener la siguiente configuración:

- **Tabla de origen:** *Actividades de contenedores*
- **Campo de origen:** *Fecha de finalización estimada*
- **Tabla de destino:** *Líneas de compra*
- **Campo de destino:** *Fecha confirmada o de entrega*

El segundo registro es necesario para actualizar las transacciones de mercancías en tránsito. Debe tener la siguiente configuración:

- **Tabla de origen:** *Actividades de contenedores*
- **Campo de origen:** *Fecha de finalización estimada*
- **Tabla de destino:** *Mercancías en orden de tránsito*
- **Campo de destino:** *Fecha esperada*
