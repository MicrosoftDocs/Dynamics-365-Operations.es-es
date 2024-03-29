---
title: Configurar campos promocionados para los pasos en la aplicación móvil Warehouse Management
description: Este artículo describe cómo promocionar y resaltar información específica para cualquier paso en los flujos de tareas para la aplicación móvil Warehouse Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepSelectPromotedFields, WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour, WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: e2d65f20febaf9bd1d143414054b121f8decb7c0
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689840"
---
# <a name="configure-promoted-fields-for-steps-in-the-warehouse-management-mobile-app"></a>Configurar campos promocionados para los pasos en la aplicación móvil Warehouse Management

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Las características que se describen en este artículo se aplican solo a la nueva aplicación móvil Warehouse Management. No afectan a la antigua aplicación de almacén, que ahora está obsoleta.

Este artículo describe cómo promocionar y resaltar información específica para cualquier paso en los flujos de tareas para la aplicación móvil Warehouse Management. Esta capacidad puede ayudar a centrar la atención de los trabajadores en los campos más importantes mientras trabajan en un flujo. Para cada paso de cada proceso, los administradores pueden seleccionar qué campos promover y qué campos resaltar.

## <a name="enable-promoted-fields-in-your-system"></a>Habilitar los campos promocionados en su sistema

Si ejecuta Supply Chain Management version 10.0.28 o anterior, antes de poder configurar campos promocionados, debe completar el siguiente procedimiento para habilitar las funciones requeridas y generar los nombres de campo requeridos en la aplicación móvil Warehouse Management. Si está ejecutando Supply Chain Management versión 10.0.29 o posterior, las funciones son obligatorias y no se pueden desactivar, por lo que puede omitir este procedimiento.

1. Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**. (Vea [Visión general de la Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para obtener más información acerca de esta página).
1. Asegúrese de que la función *Instrucciones paso a paso de la aplicación de almacén* está activada para su sistema. Esta característica es un requisito previo para la característica *Campos promocionados de aplicaciones de Warehouse Management*. A partir de la versión 10.0.29 de Supply Chain Management, es obligatoria y no se puede desactivar. Para obtener más información sobre la característica *Instrucciones de los pasos de la aplicación de almacén*, consulte [Personalizar los títulos y las instrucciones de los pasos para la aplicación móvil Warehouse Management](mobile-app-titles-instructions.md).
1. Asegúrese de que la función *Campos promocionados de la aplicación de almacén* está activada para su sistema. Esta es la característica principal descrita en este artículo. A partir de la versión 10.0.29 de Supply Chain Management, es obligatoria y no se puede desactivar.
1. Actualice los nombres de los campos en la aplicación móvil Warehouse Management yendo a **Warehouse Management \> Configuración \> Dispositivo móvil \> Nombres de campo de Warehouse Management** y seleccione **Crear configuración predeterminada**. Repita este paso para cada entidad jurídica (empresa) en la que utilice la aplicación móvil Warehouse Management. Para más información, consulte [Configurar campos para la aplicación](configure-app-field-names-priorities-warehouse.md).

## <a name="configure-promoted-fields-from-a-menu-specific-override"></a>Configurar campos promocionados de una invalidación específica del menú

Use el siguiente procedimiento para configurar campos promocionados.

1. Cree una invalidación específica del menú para el menú y el paso relevantes como se describe en [Personalizar los títulos y las instrucciones de los pasos para la aplicación móvil Warehouse Management](mobile-app-titles-instructions.md).
1. Busque la combinación de los valores de **Id. de paso** y **Nombre del elemento del menú** que desea editar y luego seleccione el valor en la columna **Id. de paso**.
1. En la página que aparece, en la ficha desplegable **Seleccionar campos promocionados**, seleccione **Seleccionar campos** en la barra de herramientas.
1. En el cuadro de diálogo **Campos promocionados**, seleccione los campos que desea promocionar. También puede resaltar hasta dos de los campos seleccionados. Los campos resaltados se mostrarán en negrita en la aplicación móvil Warehouse Management. Al seleccionar campos, tenga en cuenta el hecho de que algunas pantallas pueden ser lo suficientemente grandes como para mostrar solo uno o dos campos promocionados superiores. Para ver un ejemplo que muestra cómo usar esta configuración, consulte el escenario más adelante en este artículo.

    > [!NOTE]
    > La lista **Campos disponibles** se limita a los campos que pueden aparecer para el elemento del menú. Sin embargo, otros factores (como la composición del artículo) determinan si un campo aparece realmente en la aplicación móvil Warehouse Management. Si ha configurado campos promocionados, solo los campos seleccionados aparecerán en la página principal de la aplicación móvil Warehouse Management. Sin embargo, los trabajadores aún pueden ver los campos restantes si tocan en la página de detalles.

1. Seleccione **Aceptar** para aplicar su configuración. Sus campos seleccionados ahora se enumeran en la ficha desplegable **Seleccionar campos promocionados**.

## <a name="example-scenario"></a>Supuesto de ejemplo

### <a name="enable-sample-data"></a>Habilitar datos de muestra

Para usar los registros de ejemplos y valores especificados para trabajar en este escenario, debe usar un sistema donde se hayan instalado los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar. También debe seleccionar la entidad legal **USMF** antes de comenzar.

### <a name="configure-sales-picking-with-promoted-steps-on-the-license-plate-step"></a>Configurar la selección de ventas con pasos promocionados en el paso de la matrícula

En este procedimiento, configurará campos promocionados y resaltados el elemento del menú **Selección de ventas** en el paso de la matrícula de entidad.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \>Pasos del dispositivo móvil**.
1. Encuentre el id. de paso con el nombre *LicensePlateId* y selecciónelo.
1. En el panel de acciones, seleccione **Agregar configuración de paso**.
1. En el cuadro de diálogo desplegable, utilice el campo **Elemento de menú** para buscar y seleccionar *Selección de ventas*.
1. Seleccione **Aceptar**.
1. Aparece la página de detalles de la invalidación que acaba de crear. En la ficha desplegable **Seleccionar campos promocionados**, seleccione **Seleccionar campos** en la barra de herramientas.
1. En el cuadro de diálogo **Campos promocionados**, puede seleccionar los campos que desea promocionar y resaltar. En la lista **Campos disponibles**, busque y seleccione los siguientes campos y use los botones para moverlos a la lista **Campos seleccionados**:

    - Ubicación
    - Artículo
    - Nombre del producto
    - Estado de inventario

1. Utilice los botones de flecha hacia arriba y flecha hacia abajo para personalizar el orden de los campos en la lista **Campos seleccionados**. En la aplicación móvil Warehouse Management, los campos aparecerán en el orden que establezca aquí.
1. Seleccione el campo **Ubicación** y luego seleccione **Resaltar**.
1. Seleccione **Aceptar** para guardar la configuración.

### <a name="view-the-promoted-fields-in-the-warehouse-management-mobile-app"></a>Consultar los campos promocionados en la aplicación móvil Warehouse Management

En este procedimiento, abrirá la aplicación móvil Warehouse Management y seguirá los pasos para ver los campos que promocionó y resaltó en el procedimiento anterior.

1. En Microsoft Dynamics 365 Supply Chain Management, cree un pedido de ventas que requiera un paso de selección para realizar la selección en una ubicación con seguimiento de matrículas de entidad. Después, lance el pedido de ventas al almacén. Anote el identificador de trabajo que se genera.
1. Abra la aplicación móvil Warehouse Management e inicie sesión en el almacén 24. (En los datos de demostración estándar, inicie sesión utilizando *24* como el Id. de usuario y *1* como la contraseña).
1. Seleccione el menú **Salida** y luego seleccione el elemento de menú **Selección de ventas**.
1. Siga las instrucciones para introducir datos en la pantalla para escribir el id. de trabajo que se generó en el paso 1.
1. En el paso que contiene el texto **Escanear una matrícula**, debería ver los cambios que realizó en la página de detalles. Los campos aparecen en el orden que establezca para los campos promocionados y el campo **Ubicación** se muestra en negrita.
