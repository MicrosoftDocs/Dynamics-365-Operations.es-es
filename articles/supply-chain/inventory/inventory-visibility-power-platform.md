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
ms.openlocfilehash: 0a4e436cc1af6b71049f75fb66bdfb89ca38df9f
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831784"
---
# <a name="use-the-inventory-visibility-app"></a>Usar la aplicación Inventory Visibility

[!include [banner](../includes/banner.md)]

Este artículo describe cómo usar la aplicación Visibilidad de inventario.

Visibilidad de inventario proporciona una aplicación basada en modelo para la visualización. La aplicación contiene tres páginas: **Configuración**, **Visibilidad operativa** y **Resumen de inventario**. Tiene las siguientes características:

- Proporciona una interfaz de usuario (IU) para la configuración disponible y la configuración de reserva flexible.
- Admite consultas de inventario disponible en tiempo real en varias combinaciones de dimensiones.
- Proporciona una interfaz de usuario para publicar solicitudes de reserva.
- Proporciona una vista del inventario disponible para productos junto con todas las dimensiones.
- Proporciona una vista de la lista de inventario disponible para productos junto con todas las dimensiones predefinidas. La vista de lista disponible puede ser un resumen completo o un resultado precargado de una consulta disponible.

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, instale y configure el complemento de visibilidad de inventario como se describe en [Instalar y configurar la visibilidad del inventario](inventory-visibility-setup.md).

## <a name="open-and-authenticate-the-inventory-visibility-app"></a><a name="open-authenticate"></a>Abra y autentique la aplicación Inventory Visibility

Para abrir y autenticar la aplicación de Visibilidad de inventario, siga estos pasos.

1. Inicie sesión en su entorno de Power Apps.
1. Abra la aplicación **Visibilidad de inventario**.
1. Abra la página **Visibilidad operativa** en el panel izquierdo.
1. Seleccione el botón **Configurar** (símbolo del engranaje) en la parte superior de la página.
1. En el cuadro de diálogo **Ajustes**, introduzca los valores de **Id. del cliente**, **Id. de inquilino** y **Secreto del cliente** que anotó cuando [instaló y configuró Visibilidad de inventario](inventory-visibility-setup.md).
1. Seleccione el botón **Actualizar** al lado del campo **Ficha de portador**. El sistema genera un nuevo token de portador, basado en la información que ingresó.

    ![Configuración de consulta de inventario disponible.](media/inventory-visibility-query-settings.png "Configuración de consulta de inventario disponible")

1. Cuando reciba un token de portador válido, cierre el cuadro de diálogo. El token del portador caducará después de un tiempo. Por lo tanto, debe actualizarlo ocasionalmente cuando tenga que actualizar la configuración, publicar datos o consultar datos.

## <a name="configure-the-inventory-visibility-app"></a><a name="configuration"></a>Configurar la aplicación Visibilidad de inventario

La página **Configuración** de la aplicación Visibilidad de inventario le ayuda a definir la configuración disponible de administración de datos general y la configuración de características. Una vez instalado el complemento, la configuración predeterminada incluye una configuración predeterminada para Microsoft Dynamics 365 Supply Chain Management (el origen de datos `fno`). Puede revisar la configuración predeterminada. Luego, según sus requisitos comerciales y los requisitos de registro de inventario de su sistema externo, puede modificar la configuración para estandarizar la forma en que los cambios de inventario se pueden publicar, organizar y consultar en los múltiples sistemas.

Para obtener detalles completos sobre cómo configurar la solución, consulte [Configurar la visibilidad del inventario](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Visibilidad operativa

La página **Visibilidad operativa** proporciona los resultados de una consulta de inventario disponible en tiempo real, registro de reservas y asignación, según varias combinaciones de dimensiones. Cuando la función *OnHandReservation* está [activada](inventory-visibility-configuration.md), también puede registrar solicitudes de reserva desde la página **Visibilidad operativa**.

### <a name="on-hand-query"></a>Consulta de inventario disponible

La ficha **Consulta de inventario disponible** de la página **Visibilidad operativa** permite consultar el inventario disponible en tiempo real. Siga esos pasos para configurar y ejecutar una consulta.

1. Abra la aplicación **Visibilidad de inventario**.
1. Abra la página **Visibilidad operativa** en el panel izquierdo.
1. En la pestaña **Consulta disponible**, introduzca los valores de **Id. de la organización**, **Id. de sitio** e **Id. de ubicación** que desea consultar.
1. En el campo **Id. de producto**, ingrese uno o más id. de producto para obtener una coincidencia exacta para su consulta. Si deja el campo **Id. de producto** en blanco, los resultados incluirán todos los productos en el sitio y la ubicación especificados.
1. Para obtener un resultado más granular (por ejemplo, una vista por valores de dimensión como color y tamaño), seleccione agrupar por dimensiones en el campo **Resultado del grupo por**.
1. Para buscar elementos que tengan un valor de dimensión específico (como color = rojo), seleccione la dimensión en el campo **Dimensiones del filtro** y, a continuación, introduzca un valor de dimensión.
1. Seleccione **Consulta**. Recibirá un mensaje de éxito (verde) o un mensaje de error (rojo). Si la consulta falla, verifique sus criterios de consulta y asegúrese de que su [ficha al portador](#open-authenticate) no ha caducado.

Otra forma de realizar una consulta disponible es realizar solicitudes API directas. Puede usar `/api/environment/{environmentId}/onhand/indexquery` o `/api/environment/{environmentId}/onhand`. Para obtener más información, consulte [API públicas de Visibilidad de inventario](inventory-visibility-api.md).

### <a name="reservation-posting"></a>Registro de reservas

Utilice la pestaña **Registro de reserva** de la página **Visibilidad operativa** para registrar una solicitud de reserva.. Antes de poder registrar una solicitud de reserva, debe activar la función *OnHandReservation*. Para obtener más información sobre esta característica y sobre cómo activarla, consulte [Reservas de visibilidad de inventario](inventory-visibility-reservations.md).

> [!NOTE]
> La capacidad de hacer una reserva suave a través de la interfaz de usuario tiene como objetivo permitirle probar la función. Cada solicitud de reserva flexible debe asociarse con un cambio de línea de orden de transacción (creación, modificación, eliminación, etc.). Por lo tanto, le recomendamos que haga solo reservas blandas que estén vinculadas a un pedido final. Para obtener más información, consulte [Reservas de Visibilidad de inventario](inventory-visibility-reservations.md).

Siga estos pasos para publicar una solicitud de reserva flexible mediante la interfaz de usuario.

1. Abra la aplicación **Visibilidad de inventario**.
1. Abra la página **Visibilidad operativa** en el panel izquierdo.
1. En la pestaña **Publicación de reserva**, en el campo **Cantidad**, especifique la cantidad que desea reservar temporalmente.
1. Desactive la casilla **Habilitar el inventario negativo para respaldar la sobreventa** para evitar que el stock se sobrevenda o se sobre-reserve.
1. En el campo **Operador**, seleccione el origen de datos y la medida física que se aplican a la cantidad de reserva temporal.
1. Introduzca los valores de **Id. de la organización**, **Id. de sitio**, **Id. de ubicación** e **Id. de producto** que desea consultar.
1. Para obtener un resultado más granular, seleccione una fuente de datos, dimensiones y valores de dimensión.

Otra forma de publicar una reserva flexible es realizar solicitudes API directas. Utilice el patrón que se describe en [Crear un evento de reserva](inventory-visibility-api.md#create-one-reservation-event). A continuación, seleccione **Registrar**. Para ver los detalles de la respuesta a la solicitud, seleccione **Mostrar detalles**. También puede obtener el valor de `reservationId` de los detalles de la respuesta.

### <a name="allocation"></a>Asignación

Para obtener información sobre cómo administrar las asignaciones desde la interfaz de usuario y las API, consulte [Asignación de inventario de visibilidad de inventario](inventory-visibility-allocation.md).

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Resumen de inventario

La página **Resumen de inventario** proporciona un resumen de inventario de productos, junto con todas las dimensiones. Es una vista personalizada para la entidad *Suma de inventario disponible*. Los datos de resumen de inventario se sincronizan periódicamente desde Inventory Visibility.

Para habilitar la página **Resumen de inventario** y establecer la frecuencia de sincronización, siga estos pasos:

1. Abra la página **Configuración**.
1. Abra la pestaña **Administración y configuración de características**.
1. Ajuste el interruptor de palanca para la característica *OnHandMostSpecificBackgroundService* en *Sí*.
1. Cuando la función está habilitada, la sección **Configuración del servicio** está disponible e incluye una fila para configurar la característica **OnHandMostSpecificBackgroundService**. Esta configuración le permite elegir la frecuencia con la que se sincronizan los datos de resumen de inventario. Utilizar los botones **Arriba** y **Abajo** en la columna **Valor** para cambiar el tiempo entre sincronizaciones (que puede ser tan bajo como 5 minutos). A continuación, seleccione **Guardar**.

    ![La configuración OnHandMostSpecificBackgroundService](media/inventory-visibility-ohms-freq.png "La configuración OnHandMostSpecificBackgroundService")

1. Seleccione **Actualizar configuración** para guardar todos los cambios.

> [!NOTE]
> La característica *OnHandMostSpecificBackgroundService* solo rastrea los cambios de inventario disponibles que ocurrieron después de activar la característica. Los datos de los productos que no han cambiado desde que activó la característica no se sincronizarán desde la caché del servicio de inventario al entorno de Dataverse. Si la página **Resumen de inventario** no muestra toda la información disponible que espera, abra Supply Chain Management, vaya a **Gestión del inventario > Tareas periódicas > Integración de Visibilidad de inventario**, deshabilite el trabajo por lotes y vuelva a habilitarlo. Esto hará la inserción inicial y todos los datos se sincronizarán con la entidad *Suma de disponibilidad de inventario* en los próximos 15 minutos. Si desea utilizar la característica *OnHandMostSpecificBackgroundService*, le recomendamos que la active antes de crear cualquier cambio disponible y habilite el trabajo por lotes **Integración de Visibilidad de inventario**.

## <a name="preload-a-streamlined-on-hand-query"></a><a name="preload-streamlined-onhand-query"></a>Precargar una consulta disponible optimizada

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until further notice -->

Supply Chain Management almacena una gran cantidad de información sobre su inventario disponible actual y la pone a disposición para una amplia variedad de propósitos. Sin embargo, muchas operaciones diarias e integraciones de terceros requieren solo un pequeño subconjunto de estos detalles, y consultar el sistema por todos ellos puede generar grandes conjuntos de datos que toman tiempo para ensamblar y transferir. Por lo tanto, el servicio de visibilidad de inventario puede obtener y almacenar periódicamente un conjunto simplificado de datos de inventario disponibles para que esa información optimizada esté disponible continuamente. Los detalles del inventario disponible almacenado se filtran en función de criterios comerciales configurables para garantizar que solo se incluya la información más relevante. Debido a que las listas de inventario disponibles filtradas se almacenan localmente en el servicio de visibilidad de inventario y se actualizan regularmente, admiten un acceso rápido, exportaciones de datos bajo demanda y una integración optimizada con sistemas externos.

La página **Precargar el resumen de visibilidad del inventario** proporciona una vista para la entidad *Resultados de precarga de consultas de índice disponibles*. A diferencia de la entidad *Resumen de inventario*, la entidad *Resultados de precarga de consultas de índice disponibles* proporciona una lista de inventario disponible para productos junto con dimensiones seleccionadas. La visibilidad de inventario sincroniza los datos de resumen precargados cada 15 minutos.

Para ver los datos en la pestaña **Precarga del resumen de visibilidad de inventario**, debe activar y configurar la característica *OnHandIndexQueryPreloadBackgroundService*. Consulte [Activar y configurar consultas disponibles precargadas](inventory-visibility-configuration.md#query-preload-configuration) para obtener instrucciones.

> [!NOTE]
> Al igual que con la característica *OnHandMostSpecificBackgroundService*, la característica *OnHandIndexQueryPreloadBackgroundService* solo realiza un seguimiento de los cambios en el inventario disponible que ocurrieron después de activar la característica. Los datos de los productos que no han cambiado desde que activó la característica no se sincronizarán desde la caché del servicio de inventario al entorno de Dataverse. Si la página **Resumen de inventario** no muestra toda la información disponible que espera, vaya a **Gestión del inventario > Tareas periódicas > Integración de Visibilidad de inventario**, deshabilite el trabajo por lotes y vuelva a habilitarlo. Esto hará la inserción inicial y todos los datos se sincronizarán con la entidad *Resultados de precarga de consulta de índice disponibles* en los próximos 15 minutos. Si desea utilizar esta característica, le recomendamos que la active antes de crear cualquier cambio disponible y habilite el trabajo por lotes **Integración de Visibilidad de inventario**.

## <a name="filter-and-browse-the-inventory-summaries"></a><a name="additional-tip-for-viewing-data"></a>Filtre y explore los resúmenes de inventario

Usando el **filtro Avanzado** que proporciona Dataverse, puede crear una vista personal que muestre las filas que son importantes para usted. Las opciones de filtro avanzadas le permiten crear una amplia gama de vistas, desde simples hasta complejas. También le permiten agregar condiciones agrupadas y anidadas a los filtros. Para obtener más información sobre cómo utilizar el filtro avanzado, consulte [Editar o crear vistas personales utilizando filtros de cuadrícula avanzados](/powerapps/user/grid-filters-advanced).

La página **Resumen de inventario** proporciona tres campos encima de la cuadrícula (**Dimensión predeterminada**, **Dimensión personalizada** y **Medida**) que puede usar para controlar qué columnas están visibles. También puede seleccionar cualquier encabezado de columna para filtrar u ordenar el resultado actual por dicho columna La siguiente captura de pantalla destaca los campos de dimensión, filtrado, conteo de resultados y "cargar más" disponibles en la página **Resumen de inventario**.

![La página de resumen del inventario.](media/inventory-visibility-onhand-list.png "La página de resumen del inventario.")

Debido a que habrá predefinido las dimensiones utilizadas para cargar datos de resumen, la página **Precargar el resumen de visibilidad del inventario** muestra columnas relacionadas con la dimensión. *Las dimensiones no son personalizables&mdash;el sistema solo admite dimensiones de sitio y ubicación para listas disponibles precargadas.* La página **Precargar el resumen de visibilidad del inventario** proporciona filtros que son similares a los de la página **Resumen de inventario**, excepto que las dimensiones ya están seleccionadas. La siguiente captura de pantalla destaca los campos de filtrado disponibles en la página **Precargar el resumen de la visibilidad del inventario**.

![La página Precargar resumen de la visibilidad del inventario.](media/inventory-visibility-preload-onhand-list.png "La página Precargar resumen de la visibilidad del inventario.")

En la parte inferior de las páginas **Precargar resumen de visibilidad del inventario** y **Resumen de inventario**, encontrará información como "50 registros (29 seleccionados)" o "50 registros". Esta información se refiere a los registros cargados actualmente del resultado del **filtro avanzado**. El texto "29 seleccionados" se refiere al número de registros que se han seleccionado mediante el filtro de encabezado de columna para los registros cargados. También hay un botón **Cargar más** que puede utilizar para cargar más registros desde Dataverse. El número predeterminado de registros que se cargan es 50. Cuando selecciona **Cargar más**, los siguientes 1000 registros disponibles se cargarán en la vista. El número en el botón **Cargar más** indica los registros cargados actualmente y el número total de registros para el resultado de **Filtro avanzado**.
