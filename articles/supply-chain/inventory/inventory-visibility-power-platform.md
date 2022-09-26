---
title: Aplicación Visibilidad de inventario
description: Este artículo describe cómo usar la aplicación Visibilidad de inventario.
author: yufeihuang
ms.date: 09/15/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 674adb70cc4372a8c5ca8c75ed3ef840d8ec7b79
ms.sourcegitcommit: d2046cad5de570e6302a4390b41881a7ecb12e26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "9520874"
---
# <a name="use-the-inventory-visibility-app"></a>Usar la aplicación Inventory Visibility

[!include [banner](../includes/banner.md)]

Este artículo describe cómo usar la aplicación Visibilidad de inventario.

Visibilidad de inventario proporciona una aplicación basada en modelo para la visualización. La aplicación contiene tres páginas: **Configuración**, **Visibilidad operativa** y **Resumen de inventario**. Tiene las siguientes características:

- Proporciona una interfaz de usuario (IU) para la configuración disponible y la configuración de reserva flexible.
- Admite consultas de inventario disponible en tiempo real en varias combinaciones de dimensiones.
- Proporciona una interfaz de usuario para publicar solicitudes de reserva.
- Proporciona una vista del inventario disponible para productos junto con todas las dimensiones.
- Proporciona una vista de la lista de inventario disponible para productos junto con todas las dimensiones predefinidas.


## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, instale y configure el complemento de visibilidad de inventario como se describe en [Instalar y configurar la visibilidad del inventario](inventory-visibility-setup.md).

## <a name="open-the-inventory-visibility-app"></a>Abrir la aplicación Visibilidad de inventario

Para abrir la aplicación Inventory Visibility, inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.

## <a name="configuration"></a><a name="configuration"></a>Configuración

La página **Configuración** de la aplicación Visibilidad de inventario le ayuda a configurar la configuración disponible y la configuración de reserva flexible. Una vez instalado el complemento, la configuración predeterminada incluye una configuración predeterminada para Microsoft Dynamics 365 Supply Chain Management (el origen de datos `fno`). Puede revisar la configuración predeterminada. A partir de ahí, según sus requisitos comerciales y los requisitos de registro de inventario de su sistema externo, puede modificar la configuración para estandarizar la forma en que los cambios de inventario se pueden publicar, organizar y consultar en los múltiples sistemas.

Para obtener detalles completos sobre cómo configurar la solución, consulte [Configurar la visibilidad del inventario](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Visibilidad operativa

La página **Visibilidad operativa** proporciona los resultados de una consulta de inventario disponible en tiempo real, basada en varias combinaciones de dimensiones. Cuando la función *OnHandReservation* está activada, también puede registrar solicitudes de reserva desde la página **Visibilidad operativa**.

### <a name="on-hand-query"></a>Consulta de inventario disponible

La ficha **Consulta de inventario disponible** muestra los resultados de una consulta de inventario disponible en tiempo real.

Cuando abre la pestaña **Consulta disponible** de la página **Visibilidad operativa**, el sistema solicita sus credenciales para poder obtener el token de portador que se requiere para consultar el servicio de visibilidad de inventario. Puede pegar el token de portador en el campo **BearerToken** campo y cerrar el cuadro de diálogo. A continuación, puede registrar una solicitud de consulta de inventario disponible.

Si el token de portador no es válido, o si ha caducado, debe pegar uno nuevo en el campo **BearerToken**. Introduzca los valores correctos de **Id. de cliente**, **Id. de inquilino**, **Secreto de cliente** y luego seleccione **Actualizar**. El sistema obtendrá automáticamente un token de portador nuevo y válido.

Para registrar una consulta de inventario disponible, introduzca la consulta en el cuerpo de la solicitud. Utilice el patrón que se describe en [Consultar mediante el método de registro](inventory-visibility-api.md#query-with-post-method).

![Configuración de consulta de inventario disponible](media/inventory-visibility-query-settings.png "Configuración de consulta de inventario disponible")

### <a name="reservation-posting"></a>Registro de reservas

Utilice la pestaña **Registro de reserva** de la página **Visibilidad operativa** para registrar una solicitud de reserva.. Antes de poder registrar una solicitud de reserva, debe activar la función *OnHandReservation*. Para obtener más información sobre esta característica y sobre cómo activarla, consulte [Reservas de visibilidad de inventario](inventory-visibility-reservations.md).

Para registrar una solicitud de reserva, debe introducir un valor en el cuerpo de la solicitud. Utilice el patrón que se describe en [Crear un evento de reserva](inventory-visibility-api.md#create-one-reservation-event). A continuación, seleccione **Registrar**. Para ver los detalles de la respuesta a la solicitud, seleccione **Mostrar detalles**. También puede obtener el valor de `reservationId` de los detalles de la respuesta.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Resumen de inventario

La página **Resumen de inventario** proporciona un resumen de inventario de productos, junto con todas las dimensiones. Es una vista personalizada para la entidad *Suma de inventario disponible*. Los datos de resumen de inventario se sincronizan periódicamente desde Inventory Visibility.

Para habilitar la página **Resumen de inventario** y establecer la frecuencia de sincronización, siga estos pasos:

1. Abra la página **Configuración**.
1. Abra la pestaña **Administración y configuración de características**.
1. Ajuste el interruptor de palanca para la característica **OnHandMostSpecificBackgroundService** en *Sí*.
1. Cuando la función está habilitada, la sección **Configuración del servicio** está disponible e incluye una fila para configurar la característica **OnHandMostSpecificBackgroundService**. Esta configuración le permite elegir la frecuencia con la que se sincronizan los datos de resumen de inventario. Utilizar los botones **Arriba** y **Abajo** en la columna **Valor** para cambiar el tiempo entre sincronizaciones (que puede ser tan bajo como 5 minutos). A continuación, seleccione **Guardar**.

    ![La configuración OnHandMostSpecificBackgroundService](media/inventory-visibility-ohms-freq.png "La configuración OnHandMostSpecificBackgroundService")

1. Seleccione **Actualizar configuración** para guardar todos los cambios.


> [!NOTE]
> La característica *OnHandMostSpecificBackgroundService* solo rastrea los cambios de inventario disponibles que ocurrieron después de activar la característica. Los datos de los productos que no han cambiado desde que activó la característica no se sincronizarán desde la caché del servicio de inventario al entorno de Dataverse. Si la página **Resumen de inventario** no muestra toda la información disponible que espera, abra Supply Chain Management, vaya a **Gestión del inventario > Tareas periódicas > Integración de Visibilidad de inventario**, deshabilite el trabajo por lotes y vuelva a habilitarlo. Esto hará la inserción inicial y todos los datos se sincronizarán con la entidad *Suma de disponibilidad de inventario* en los próximos 15 minutos. Si desea utilizar la característica *OnHandMostSpecificBackgroundService*, le recomendamos que la active antes de crear cualquier cambio disponible y habilite el trabajo por lotes **Integración de Visibilidad de inventario**.

## <a name="preload-a-streamlined-on-hand-query"></a><a name="preload-the-inventory-visibility-onhand-query"></a>Precargar una consulta disponible optimizada

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until further notice -->

Supply Chain Management almacena una gran cantidad de información sobre su inventario disponible actual y la pone a disposición para una amplia variedad de propósitos. Sin embargo, muchas operaciones diarias e integraciones de terceros requieren solo un pequeño subconjunto de estos detalles, y consultar el sistema por todos ellos puede generar grandes conjuntos de datos que toman tiempo para ensamblar y transferir. Por lo tanto, el servicio de visibilidad de inventario puede obtener y almacenar periódicamente un conjunto simplificado de datos de inventario disponibles para que esa información optimizada esté disponible continuamente. Los detalles del inventario disponible almacenado se filtran en función de criterios comerciales configurables para garantizar que solo se incluya la información más relevante. Debido a que las listas de inventario disponibles filtradas se almacenan localmente en el servicio de visibilidad de inventario y se actualizan regularmente, admiten un acceso rápido, exportaciones de datos bajo demanda y una integración optimizada con sistemas externos.

> [!NOTE]
> La versión preliminar actual de esta característica solo puede proporcionar resultados precargados que incluyen el sitio y la ubicación. Se espera que la versión final de la característica le permita seleccionar otras dimensiones para precargar los resultados.

La página **Precargar el resumen de visibilidad del inventario** proporciona una vista para la entidad *Resultados de precarga de consultas de índice disponibles*. A diferencia de la entidad *Resumen de inventario*, la entidad *Resultados de precarga de consultas de índice disponibles* proporciona una lista de inventario disponible para productos junto con dimensiones seleccionadas. La visibilidad de inventario sincroniza los datos de resumen precargados cada 15 minutos.

Para ver los datos en la pestaña **Precargar el resumen de visibilidad del inventario**, debe activar la característica *OnHandIndexQueryPreloadBackgroundService* en la pestaña **Gestión de características** de la página **Configuración** y luego seleccione **Actualizar configuración** (ver también [Configurar visibilidad de inventario](inventory-visibility-configuration.md)).

> [!NOTE]
> Al igual que con la característica *OnhandMostSpecificBackgroudService*, la característica *OnHandIndexQueryPreloadBackgroundService* solo realiza un seguimiento de los cambios en el inventario disponible que ocurrieron después de activar la característica. Los datos de los productos que no han cambiado desde que activó la característica no se sincronizarán desde la caché del servicio de inventario al entorno de Dataverse. Si la página **Resumen de inventario** no muestra toda la información disponible que espera, vaya a **Gestión del inventario > Tareas periódicas > Integración de Visibilidad de inventario**, deshabilite el trabajo por lotes y vuelva a habilitarlo. Esto hará la inserción inicial y todos los datos se sincronizarán con la entidad *Resultados de precarga de consulta de índice disponibles* en los próximos 15 minutos. Si desea utilizar esta característica, le recomendamos que la active antes de crear cualquier cambio disponible y habilite el trabajo por lotes **Integración de Visibilidad de inventario**.

## <a name="filter-and-browse-the-inventory-summaries"></a><a name="additional-tip-for-viewing-data"></a>Filtre y explore los resúmenes de inventario

Usando el **filtro Avanzado** que proporciona Dataverse, puede crear una vista personal que muestre las filas que son importantes para usted. Las opciones de filtro avanzadas le permiten crear una amplia gama de vistas, desde simples hasta complejas. También le permiten agregar condiciones agrupadas y anidadas a los filtros. Para obtener más información sobre cómo utilizar el filtro avanzado, consulte [Editar o crear vistas personales utilizando filtros de cuadrícula avanzados](/powerapps/user/grid-filters-advanced).

La página **Resumen de inventario** proporciona tres campos encima de la cuadrícula (**Dimensión predeterminada**, **Dimensión personalizada** y **Medida**) que puede usar para controlar qué columnas están visibles. También puede seleccionar cualquier encabezado de columna para filtrar u ordenar el resultado actual por dicho columna La siguiente captura de pantalla destaca los campos de dimensión, filtrado, conteo de resultados y "cargar más" disponibles en la página **Resumen de inventario**.

![La página de resumen del inventario.](media/inventory-visibility-onhand-list.png "La página de resumen del inventario.")

Debido a que habrá predefinido las dimensiones utilizadas para cargar datos de resumen, la página **Precargar el resumen de visibilidad del inventario** muestra columnas relacionadas con la dimensión. *Las dimensiones no son personalizables&mdash;el sistema solo admite dimensiones de sitio y ubicación para listas disponibles precargadas.* La página **Precargar el resumen de visibilidad del inventario** proporciona filtros que son similares a los de la página **Resumen de inventario**, excepto que las dimensiones ya están seleccionadas. La siguiente captura de pantalla destaca los campos de filtrado disponibles en la página **Precargar el resumen de la visibilidad del inventario**.

![La página Precargar resumen de la visibilidad del inventario.](media/inventory-visibility-preload-onhand-list.png "La página Precargar resumen de la visibilidad del inventario.")

En la parte inferior de las páginas **Precargar resumen de visibilidad del inventario** y **Resumen de inventario**, encontrará información como "50 registros (29 seleccionados)" o "50 registros". Esta información se refiere a los registros cargados actualmente del resultado del **filtro avanzado**. El texto "29 seleccionados" se refiere al número de registros que se han seleccionado mediante el filtro de encabezado de columna para los registros cargados. También hay un botón **Cargar más** que puede utilizar para cargar más registros desde Dataverse. El número predeterminado de registros que se cargan es 50. Cuando selecciona **Cargar más**, los siguientes 1000 registros disponibles se cargarán en la vista. El número en el botón **Cargar más** indica los registros cargados actualmente y el número total de registros para el resultado de **Filtro avanzado**.
