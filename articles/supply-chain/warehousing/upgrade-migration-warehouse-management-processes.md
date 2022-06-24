---
title: Actualizar la gestión de almacenes Microsoft Dynamics AX 2012 a Supply Chain Management
description: En este artículo se proporciona una visión general de las opciones de la migración de la gestión de productos y almacenes.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d85f4e5c44db511970b3e22490341228fa0d1abd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857094"
---
# <a name="upgrade-warehouse-management-from-microsoft-dynamics-ax-2012-to-supply-chain-management"></a>Actualizar la gestión de almacenes Microsoft Dynamics AX 2012 a Supply Chain Management 


[!include [banner](../includes/banner.md)]

Este artículo proporciona una visión general del proceso de actualización de Microsoft Dynamics AX 2012 R3, que ejecuta el módulo de WMSII, a Supply Chain Management.

Supply Chain Management ya no admite el antiguo módulo **WMSII** de Microsoft Dynamics AX 2012. En su lugar, puede utilizar el módulo **Gestión de almacenes** . En el módulo WMSII, las dimensiones de inventario Ubicación e Id. de palet se podían seleccionar para el inventario financiero; sin embargo, la dimensión de inventario Id. de palet no se puede usar para un inventario financiero en Supply Chain Management.

Durante una actualización se identifican todos los productos asociados a un grupo de dimensiones de almacenamiento que utilice la dimensión de inventario Id. de pallet, se marcan como bloqueados y no se procesan para la actualización.

## <a name="upgrading-to-supply-chain-management-when-ax-2012-r3-wmsii-is-used"></a>Actualizar a Supply Chain Management cuando se usa AX 2012 R3 WMSII
Después de la actualización, puede usar un conjunto de opciones de migración en el proceso **Cambiar grupo de dimensiones de almacenamiento para artículos** para desbloquear los productos bloqueados durante la actualización y después procesar transacciones para estos productos.

### <a name="enabling-items-in-supply-chain-management"></a>Habilitar artículos en Supply Chain Management 
Este cambio es necesario porque en Supply Chain Management el seguimiento de artículos forma parte de los procesos de gestión de almacenes. Para estos procesos, todos los almacenes y sus ubicaciones deben estar asociadas a un perfil de ubicación. Si desea utilizar procesos de gestión de almacenes, debe configurar lo siguiente:
-   Los almacenes existentes deben habilitarse para usar los procesos de gestión de almacenes 
-   Los productos emitidos existentes deben asociarse a un grupo de dimensiones de almacenamiento que utilice procesos de gestión de almacenes 

Si los grupos de dimensiones de almacenamiento de origen usan la dimensión de inventario identificador de palé, las ubicaciones de inventario disponible existentes que utilizaron la dimensión de inventario identificador de palé se deben asociar a un perfil de ubicación donde esté seleccionado el parámetro **Usar seguimiento de matrículas de entidad de almacén**. Si los almacenes existentes no deben habilitarse para utilizar procesos de gestión de almacenes, puede cambiar los grupos de dimensiones de almacenamiento del inventario disponible existentes que usen únicamente las dimensiones de inventario sitio, almacén y ubicación. 

> [!NOTE] 
>  Puede cambiar el grupo de dimensiones de almacenamiento de artículos incluso si existen transacciones de inventario abiertas.

## <a name="find-products-that-were-blocked-because-of-pallet-id"></a>Buscar productos bloqueados a causa del Id. de pallet
Para ver la lista de productos emitidos que se bloquearon durante la actualización y no pueden procesarse, haga clic en **Gestión del inventario** &gt; **Configuración** &gt; **Inventario** &gt; **Artículos bloqueados para las actualizaciones de inventario**.

## <a name="change-storage-dimension-group-for-blocked-products"></a>Cambiar el grupo de dimensiones de almacenamiento de los productos bloqueados 
 
Para usarse como parte de un proceso de gestión de almacenes, un artículo debe estar asociado a un grupo de dimensiones de almacenamiento en el que la dimensión de inventario Ubicación esté activa y el parámetro **Usar procesos de gestión de almacenes** esté seleccionado. Cuando se selecciona este valor, se activan las dimensiones de inventario de sitio, almacén, estado de inventario, ubicación y número de matrícula.

Para desbloquear los productos bloqueados durante la actualización, debe seleccionar un nuevo grupo de dimensiones de almacenamiento para los productos. Tenga en cuenta que puede cambiar el grupo de dimensiones de almacenamiento incluso si existen transacciones de inventario abiertas. Para usar los artículos bloqueados durante la actualización, tiene dos opciones:

-   Cambiar el grupo de dimensiones de almacenamiento del artículo a un grupo de dimensiones de almacenamiento que use únicamente las dimensiones de sitio, almacén y ubicación. Como resultado de este cambio, la dimensión de inventario identificador de palé ya no se usa.
-   Cambiar el grupo de dimensiones de almacenamiento del artículo a un grupo de dimensiones de almacenamiento que use los procesos de gestión de almacenes. Como resultado de este cambio, la dimensión de inventario del número de matrícula ahora se usa.

## <a name="configure-warehouse-management-processes"></a>Configurar procesos de gestión de almacenes
Para poder usar los productos emitidos en el módulo **Gestión de almacenes**, los productos deben usar un grupo de dimensiones de almacenamiento donde esté seleccionado el parámetro **Usar procesos de gestión de almacenes** .

### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Habilite los almacenes para usar los procesos de gestión de almacenes

1.  Cree al menos un nuevo perfil de ubicación.
2.  Haga clic en **Gestión de almacenes** &gt; **Configuración** &gt; **Habilitar procesos de gestión de almacenes** &gt; **Habilitar la configuración del almacén**.
3.  En la página **Habilitar la configuración del almacén**, agregue los almacenes que deban habilitarse. Puede completar este paso directamente en la página o mediante la integración de Microsoft Office.
4.  Asigne un perfil de ubicación a todas las ubicaciones. Puede completar fácilmente este paso usando la integración de Microsoft Office directamente en la página. Puede exportar e importar los datos, o utilizar el procesamiento de entidades de datos en [Administración de datos](../../fin-ops-core/dev-itpro/data-entities/data-entities.md).
5.  Valide los cambios. Como parte del proceso de validación se producen varias validaciones de la integridad de datos. Como parte de un proceso de actualización mayor, es posible que los problemas que aparezcan tengan que ajustarse en la implementación de origen. En este caso, una actualización de datos adicional será necesaria.
6.  Procese los cambios.

### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>Cambie el grupo de dimensiones de almacenamiento de los artículos para que use procesos de gestión de almacenes

1.  Cree un nuevo valor **Estado de inventario** y asígnelo como valor **Id. del estado de inventario predeterminado** en la configuración de **Parámetros de gestión de almacenes**.
2.  Cree un nuevo grupo de dimensiones de almacenamiento donde esté seleccionado el parámetro **Usar procesos de gestión de almacenes**.
3.  En la página **Jerarquía de reserva**, defina una nueva jerarquía de la reserva en función del almacenamiento y los grupos de dimensiones de seguimiento del artículo.
4.  Cree uno o varios grupos de secuencias de unidades que incluyen al menos las mismas unidades que se usan para las unidades de inventario de los artículos.
5.  Haga clic en **Gestión de almacenes** &gt; **Configuración** &gt; **Habilitar procesos de gestión de almacenes** &gt; **Cambiar grupo de dimensiones de almacenamiento para artículos**.
6.  En la página **Cambiar grupo de dimensiones de almacenamiento para artículos**, agregue los números de artículo, los grupos de dimensiones de almacenamiento y los grupos de secuencias de unidades. Puede completar este paso directamente en la página, mediante la integración de Microsoft Office, o mediante el proceso de entidades de datos en [Administración de datos](../../fin-ops-core/dev-itpro/data-entities/data-entities.md).
7.  Valide los cambios. Como parte del proceso de validación se producen varias validaciones de la integridad de datos. Como parte de un proceso de actualización mayor, es posible que los problemas que aparezcan tengan que ajustarse en la implementación de origen. En este caso, será necesaria otra actualización de datos.
8.  Procese los cambios. Una actualización de todas las dimensiones de inventario puede tardar. Puede controlar el progreso mediante las tareas de los trabajos por lotes.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]