---
title: Trabajos de embalaje para empaquetar contenedores de salida y procesar envíos
description: Este artículo describe el tipo de orden de trabajo "Embalaje", que administra el trabajo para empacar contenedores y admite envíos parciales de contenedores empacados que están relacionados con cargas donde los artículos de inventario permanecen sin empacar.
author: perlynne
ms.date: 7/13/2022
ms.topic: article
ms.search.form: WHSPackingWorkLocationSetup, WHSPack, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 34a7087df7e7768d0012ea4f534aa109654af8fa
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220595"
---
# <a name="packing-work-for-packing-outbound-containers-and-processing-shipments"></a>Trabajos de embalaje para empaquetar contenedores de salida y procesar envíos

[!include [banner](../../includes/banner.md)]

Este artículo describe el tipo de orden de trabajo *Embalaje*, que administra el trabajo para empacar contenedores y admite envíos parciales de contenedores empacados que están relacionados con cargas donde los artículos de inventario permanecen sin empacar. El trabajo de embalaje le permite utilizar la funcionalidad de [confirmar y transferir](confirm-and-transfer.md) para confirmar envíos salientes que están asociados con contenedores.

El trabajo de embalaje se crea automáticamente cuando el inventario relacionado con el trabajo del documento de origen se coloca en las ubicaciones del tipo *Ubicación de embalaje*. El trabajo consta de dos líneas, una para *Elegir* y una para *Poner*, y se mantiene automáticamente como parte del proceso de cierre/reapertura de un contenedor.

Para obtener más información sobre cómo configurar y utilizar el proceso de embalaje de contenedores, consulte [Embalar contenedores para envío](packing-containers.md).

## <a name="turn-on-the-feature"></a>Activar la característica

Si su sistema aún no incluye las funciones que se describen en este artículo, vaya a [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active las características siguientes por este orden: Ambas características son parte del módulo **Gestión de almacenes**.

1. *Confirmar y transferir*
1. *Trabajo de embalaje para estaciones de embalaje*

## <a name="set-up-a-location-for-packing-work"></a>Configurar una ubicación para el trabajo de embalaje

Use el siguiente procedimiento para configurar ubicaciones de embalaje. Para cada ubicación, puede seleccionar si el sistema crea automáticamente el trabajo de embalaje.

1. Vaya a **Gestión de almacenes \> Configurar \> Embalaje \> Configuración de estación de embalaje**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar registro de configuración de estación.
1. Establezca los siguientes campos en el nuevo registro:

    - **Almacén** - Seleccione o introduzca el almacén donde se encuentra la ubicación de empaque.
    - **Ubicación**: seleccione o especifique la ubicación de empaque. Esta ubicación se debe asignar a un perfil de ubicación que utilice el tipo de ubicación que está configurado como el tipo de ubicación de embalaje para su empresa en la página **Parámetros de gestión de almacenes**. Para más información, vea [Embalar contenedores para envío](packing-containers.md).
    - **Crear trabajo de embalaje** – Seleccione esta casilla de verificación para crear un trabajo de embalaje cada vez que los artículos se entreguen en la ubicación de embalaje. El trabajo incluirá enlaces a líneas de carga relacionadas, de modo que las cargas parciales puedan empaquetarse y enviarse.

## <a name="example-scenario"></a>Supuesto de ejemplo

Este escenario de ejemplo muestra cómo procesar un flujo de pedido de ventas saliente al empacar un contenedor y enviar una carga parcial.

### <a name="make-sample-data-available"></a>Hacer que los datos de muestra estén disponibles

Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

También puede usar este escenario como guía para usar la característica en un sistema de producción. Sin embargo, en ese caso, debe sustituir sus propios valores para cada configuración aquí descrita.

### <a name="configure-packing-work-for-warehouse-packing-location"></a>Configurar el trabajo de embalaje para la ubicación de embalaje del almacén

Para empezar, debe configurar el proceso de trabajo *Embalaje* para un almacén y ubicación específicos.

1. Vaya a **Gestión de almacenes \> Configurar \> Embalaje \> Configuración de estación de embalaje**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar un registro de configuración.
1. Establezca los siguientes valores en el nuevo registro:

    - **Almacén**: *62*
    - **Ubicación:** *Paquete*
    - **Crear trabajo de embalaje**: *Sí*

1. Cierre la página **Configuración de estación de empaque**.

### <a name="create-a-load-template-that-allows-partial-shipping"></a>Crear una plantilla de carga que permita un envío parcial

Para permitir que una carga se entregue en varios envíos, debe asociarla con una plantilla de carga que permita el envío parcial. Siga estos pasos para crear la plantilla necesaria.

1. Vaya a **Administración de almacenes \> Configuración \> Carga \> Plantillas de carga**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar un registro de configuración.
1. Establezca los siguientes valores en el nuevo registro:

    - **Identificador de la plantilla de carga**: *Parcial*
    - **Permitir división de carga durante confirmación de envío**: *Sí*

1. Cierre la página **Plantillas de carga**.

Para más información, consulte [Confirmar y transferir](Confirm-and-transfer.md).

### <a name="process-a-sales-order"></a>Procesar un pedido de ventas

Siga estos pasos para procesar una orden de venta y enviarla parcialmente.

1. Complete el [escenario de ejemplo](packing-containers.md#scenario) que se proporciona en [Embalar contenedores para envío](packing-containers.md). Durante ese escenario, creará una orden de venta para dos piezas de un artículo. Luego empacará solo una de las piezas en un contenedor y cerrará el contenedor. Debe anotar el ID de envío que crea, como se indica en el escenario.
1. Vaya a **Gestión de almacenes \> Trabajo\> Todos los trabajos**.
1. En el área de filtro, seleccione la casilla **Mostrar trabajo cerrado**. Luego ingrese la identificación del envío en el campo **Filtrar** y seleccione para filtrar por el valor **Identificación del envío**. Ahora debería ver tres encabezados de trabajo. Uno es para el trabajo de preparación de pedidos de venta y tiene un estado de *Cerrado*. Dos son para el proceso de embalaje: uno está relacionado con el contenedor cerrado y tiene un estado de *Cerrado* y el otro está relacionado con el artículo restante sin embalar y tiene un estado de *Abierto*.
1. Seleccione el valor **ID de carga** para cualquiera de los encabezados de trabajo para abrir la página **Cargar detalles** para la carga.
1. Cambie a la vista **Encabezado**.
1. Sobre la ficha desplegable **General**, seleccione el botón **Editar** para el campo **Cargar ID de plantilla**. Luego seleccione la plantilla de carga de envío parcial que creó para este escenario (*Parcial*).
1. En el panel de acciones, en la ficha **Enviar y recibir**, en el grupo **Confirmar**, seleccione **Envío de salida**.
1. En el cuadro de diálogo **Confirmar envío**, seleccione la opción **Dividir cantidad a nueva carga**.
1. Seleccione **Aceptar**.

Ahora ha enviado un contenedor que está relacionado con la carga original y el sistema ha creado una nueva carga para los artículos restantes que aún deben empaquetarse en contenedores.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
