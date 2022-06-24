---
title: Aplicación Visibilidad de inventario
description: Este artículo describe cómo usar la aplicación Visibilidad de inventario.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: db158e3b6ae76f69149db04096f99d3dc4251146
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895768"
---
# <a name="use-the-inventory-visibility-app"></a>Usar la aplicación Inventory Visibility

[!include [banner](../includes/banner.md)]


Este artículo describe cómo usar la aplicación Visibilidad de inventario.

Visibilidad de inventario proporciona una aplicación basada en modelo para la visualización. La aplicación contiene tres páginas: **Configuración**, **Visibilidad operativa** y **Resumen de inventario**. Tiene las siguientes características:

- Proporciona una interfaz de usuario (IU) para la configuración disponible y la configuración de reserva flexible.
- Admite consultas de inventario disponible en tiempo real en varias combinaciones de dimensiones.
- Proporciona una interfaz de usuario para publicar solicitudes de reserva.
- Proporciona una vista personalizada del inventario disponible para productos junto con todas las dimensiones.

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

Cuando selecciona la ficha **Consulta de inventario disponible**, el sistema solicita sus credenciales para poder obtener el token de portador que se requiere para consultar el servicio de visibilidad de inventario. Puede pegar el token de portador en el campo **BearerToken** campo y cerrar el cuadro de diálogo. A continuación, puede registrar una solicitud de consulta de inventario disponible.

Si el token de portador no es válido, o si ha caducado, debe pegar uno nuevo en el campo **BearerToken**. Introduzca los valores correctos de **Id. de cliente**, **Id. de inquilino**, **Secreto de cliente** y luego seleccione **Actualizar**. El sistema obtendrá automáticamente un token de portador nuevo y válido.

Para registrar una consulta de inventario disponible, introduzca la consulta en el cuerpo de la solicitud. Utilice el patrón que se describe en [Consultar mediante el método de registro](inventory-visibility-api.md#query-with-post-method).

![Configuración de consulta de inventario disponible](media/inventory-visibility-query-settings.png "Configuración de consulta de inventario disponible")

### <a name="reservation-posting"></a>Registro de reservas

Utilice la ficha **Registro de reserva** para registrar una solicitud de reserva. Antes de poder registrar una solicitud de reserva, debe activar la función *OnHandReservation*. Para obtener más información sobre esta función, consulte [Reservas de visibilidad de inventario ](inventory-visibility-reservations.md).

Para registrar una solicitud de reserva, debe introducir un valor en el cuerpo de la solicitud. Utilice el patrón que se describe en [Crear un evento de reserva](inventory-visibility-api.md#create-one-reservation-event). A continuación, seleccione **Registrar**. Para ver los detalles de la respuesta a la solicitud, seleccione **Mostrar detalles**. También puede obtener el valor de `reservationId` de los detalles de la respuesta.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Resumen de inventario

**Resumen de inventario** es una vista personalizada para la entidad *Suma de inventario disponible*. Proporciona un resumen de inventario de productos junto con todas las dimensiones. Los datos de resumen de inventario se sincronizarán periódicamente desde Inventory Visibility cada 15 minutos. Para ver datos en la pestaña **Resumen de inventario**, debe activar la característica *OnHandMostSpecificBackgroundService* en la pestaña **Gestión de funciones** y seleccionar **Configuración de actualización**.

> [!NOTE]
> La característica *OnHandMostSpecificBackgroundService* solo rastrea los cambios de productos disponibles que ocurrieron después de activar la característica. Los datos de los productos que no han cambiado desde que activó la característica no se sincronizarán desde la caché del servicio de inventario al entorno de Dataverse. Si la página **Resumen de inventario** no muestra toda la información disponible que espera, vaya a **Gestión del inventario > Tareas periódicas > Integración de Visibilidad de inventario**, deshabilite el trabajo por lotes y vuelva a habilitarlo. Esto hará la inserción inicial y todos los datos se sincronizarán con la entidad *Suma de disponibilidad de inventario* en los próximos 15 minutos. Si desea utilizar esta característica, le recomendamos que la active antes de crear cualquier cambio disponible y habilite el trabajo por lotes **Integración de Visibilidad de inventario**.

Usando el **filtro Avanzado** que proporciona Dataverse, puede crear una vista personal que muestre las filas que son importantes para usted. Las opciones de filtro avanzadas le permiten crear una amplia gama de vistas, desde simples hasta complejas. También le permiten agregar condiciones agrupadas y anidadas a los filtros. Para obtener más información sobre cómo utilizar el **filtro Avanzado**, consulte [Editar o crear vistas personales utilizando filtros de cuadrícula avanzados](/powerapps/user/grid-filters-advanced).

La parte superior de la vista personalizada proporciona tres campos : **Dimensión predeterminada**, **Dimensión personalizada** y **Medida**. Puede utilizar estos campos para controlar qué columnas están visibles.

Puede seleccionar el encabezado de la columna para filtrar u ordenar el resultado actual.

La parte inferior de la vista personalizada muestra información como "50 registros (29 seleccionados)" o "50 registros". Esta información se refiere a los registros cargados actualmente del resultado del **filtro avanzado**. El texto "29 seleccionados" se refiere al número de registros que se han seleccionado mediante el filtro de encabezado de columna para los registros cargados.

En la parte inferior de la vista hay un botón **Cargar más** que puede utilizar para cargar más registros desde Dataverse. El número predeterminado de registros que se cargan es 50. Cuando selecciona **Cargar más**, los siguientes 1000 registros disponibles se cargan en la vista. El número en el botón **Cargar más** indica los registros cargados actualmente y el número total de registros para el resultado de **Filtro avanzado**.

![Resumen de inventario](media/inventory-visibility-onhand-list.png "Resumen de inventario")
