---
title: "Migrar la gestión de productos y almacenes de AX 2012 a Finance and Operations"
description: "En este tema se proporciona una visión general de las opciones de la migración de la gestión de productos y almacenes."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: bis
ms.search.scope: AX 7.0.0, Operations, UnifiedOperations
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 9f618e61cd1cfb7e2abbbc0c9a00b5a06792b4bc
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="migrate-products-and-warehouse-management-from-ax-2012-to-finance-and-operations"></a>Migrar la gestión de productos y almacenes de AX 2012 a Finance and Operations

Este tema proporciona una visión general de las opciones de migración de la gestión de productos y de almacenes dentro de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

<a name="introduction"></a>Introducción
------------

Durante una actualización de Finance and Operations, los productos están bloqueados si se asocian a un grupo de dimensiones de almacenamiento con valores que no coinciden con los requisitos de valores del grupo de dimensiones de almacenamiento de Finance and Operations. Sin embargo, después de la actualización, puede usar un conjunto de opciones de migración en el proceso **Cambiar grupo de dimensiones de almacenamiento para artículos** para desbloquear los productos bloqueados durante la actualización. A continuación puede procesar las transacciones de estos productos. Algunos de los elementos pueden estar ya asociados a grupos de dimensiones de almacenamiento en los que se activaron las dimensiones de sitio, almacén e inventario de ubicación y ser seguidos físicamente. En este caso, puede usar el proceso **Cambiar grupo de dimensiones de almacenamiento para artículos** para habilitar los artículos que se utilizarán en procesos de gestión de almacenes. Esta función resulta útil si desea usar la funcionalidad de gestión de almacenes para los artículos existentes.

## <a name="upgrading-to-finance-and-operations-when-ax-2012-r3-wmsii-is-used"></a>Actualización de Finance and Operations cuando se utiliza AX 2012 R3 WMSII
Finance and Operations ya no admite el antiguo módulo **WMSII** de Microsoft Dynamics AX 2012. En su lugar, puede utilizar el nuevo módulo **Gestión de almacenes** . En versiones anteriores, las dimensiones de inventario de la ubicación y del ID de palé se podían seleccionar para el inventario financiero. Sin embargo, como parte del proceso de actualización, la dimensión de inventario de identificador de palé ya no se puede habilitar para el inventario financiero. Todos los productos asociados a un grupo de dimensiones de almacenamiento que utilice la dimensión de inventario de identificador de palé se bloquean y no se procesan.

### <a name="enabling-items-in-finance-and-operations"></a>Habilitación de artículos en Finance and Operations

En Finance and Operations, los artículos que se usarán como parte de procesos de gestión de almacenes se deben asociar a un grupo de dimensiones de almacenamiento donde se selecciona el parámetro **Usar procesos de gestión de almacenes** . Cuando se selecciona este valor, se activan las dimensiones de inventario de sitio, almacén, estado de inventario, ubicación y número de matrícula. Puede cambiar a este tipo de grupo de dimensiones de almacenamiento únicamente para los artículos que ya están asociados a los grupos de dimensiones de almacenamiento donde está activa la dimensión de inventario de la ubicación.

### <a name="items-that-are-blocked-for-inventory-updates"></a>Artículos que se bloquean para las actualizaciones de inventario

Para ver la lista de productos emitidos que se bloquearon durante la actualización y no pueden procesarse, haga clic en **Gestión del inventario** &gt; **Configuración** &gt; **Inventario** &gt; **Artículos bloqueados para las actualizaciones de inventario**.

### <a name="reapplying-blocked-products"></a>Reaplicación de productos bloqueados

Para desbloquear los productos bloqueados durante la actualización, debe seleccionar un nuevo grupo de dimensiones de almacenamiento para los productos. Tenga en cuenta que puede cambiar el grupo de dimensiones de almacenamiento incluso si existen transacciones de inventario abiertas. Para usar los artículos bloqueados durante la actualización, tiene dos opciones:

-   Cambiar el grupo de dimensiones de almacenamiento del artículo a un grupo de dimensiones de almacenamiento que use únicamente las dimensiones de sitio, almacén y ubicación. Como resultado de este cambio, la dimensión de inventario identificador de palé ya no se usa.
-   Cambiar el grupo de dimensiones de almacenamiento del artículo a un grupo de dimensiones de almacenamiento que use los procesos de gestión de almacenes. Como resultado de este cambio, la dimensión de inventario del número de matrícula ahora se usa.

### <a name="migration-processes"></a>Procesos de migración

En Finance and Operations, el seguimiento de artículos forma parte de los procesos de gestión de almacenes. Para estos procesos, todos los almacenes y sus ubicaciones deben estar asociadas a un perfil de ubicación. Conceptualmente, si desea utilizar procesos de gestión de almacenes, debe trabajar con dos procesos:

-   Los almacenes existentes deben habilitarse para usar los procesos de gestión de almacenes.
-   Los productos emitidos existentes deben asociarse a un nuevo grupo de dimensiones de almacenamiento que utilice procesos de gestión de almacenes.

Si los grupos de dimensiones de almacenamiento de origen usan la dimensión de inventario identificador de palé, las ubicaciones de inventario disponible existentes que utilizaron la dimensión de inventario identificador de palé se deben asociar a un perfil de ubicación donde esté seleccionado el parámetro **Usar seguimiento de matrículas de entidad de almacén**. Si los almacenes existentes no deben habilitarse para utilizar procesos de gestión de almacenes, puede cambiar los grupos de dimensiones de almacenamiento del inventario disponible existentes que usen únicamente las dimensiones de inventario sitio, almacén y ubicación.

### <a name="using-the-warehouse-management-processes"></a>Uso de los procesos de gestión de almacenes

Para poder usar los productos emitidos en el módulo **Gestión de almacenes**, los productos deben usar un grupo de dimensiones de almacenamiento donde esté seleccionado el parámetro **Usar procesos de gestión de almacenes** .

#### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Habilite los almacenes para usar los procesos de gestión de almacenes

1.  Cree al menos un nuevo perfil de ubicación.
2.  Haga clic en **Gestión de almacenes** &gt; **Configuración** &gt; **Habilitar procesos de gestión de almacenes** &gt; **Habilitar la configuración del almacén**.
3.  En la página **Habilitar la configuración del almacén**, agregue los almacenes que deban habilitarse. Puede completar este paso directamente en la página o mediante la integración de Microsoft Office.
4.  Asigne un perfil de ubicación a todas las ubicaciones. Puede completar fácilmente este paso usando la integración de Microsoft Office directamente en la página. Puede exportar e importar los datos, o utilizar el procesamiento de entidades de datos en [Administración de datos](../../dev-itpro/data-entities/data-entities.md).
5.  Valide los cambios. Como parte del proceso de validación se producen varias validaciones de la integridad de datos. Como parte de un proceso de actualización mayor, es posible que los problemas que aparezcan tengan que ajustarse en la implementación de origen. En este caso, una actualización de datos adicional será necesaria.
6.  Procese los cambios.

#### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>Cambie el grupo de dimensiones de almacenamiento de los artículos para que use procesos de gestión de almacenes

1.  Cree un nuevo valor **Estado de inventario** y asígnelo como valor **Id. del estado de inventario predeterminado** en la configuración de **Parámetros de gestión de almacenes**.
2.  Cree un nuevo grupo de dimensiones de almacenamiento donde esté seleccionado el parámetro **Usar procesos de gestión de almacenes**.
3.  En la página **Jerarquía de reserva**, defina una nueva jerarquía de la reserva en función del almacenamiento y los grupos de dimensiones de seguimiento del artículo.
4.  Cree uno o varios grupos de secuencias de unidades que incluyen al menos las mismas unidades que se usan para las unidades de inventario de los artículos.
5.  Haga clic en **Gestión de almacenes** &gt; **Configuración** &gt; **Habilitar procesos de gestión de almacenes** &gt; **Cambiar grupo de dimensiones de almacenamiento para artículos**.
6.  En la página **Cambiar grupo de dimensiones de almacenamiento para artículos**, agregue los números de artículo, los grupos de dimensiones de almacenamiento y los grupos de secuencias de unidades. Puede completar este paso directamente en la página, mediante la integración de Microsoft Office, o mediante el proceso de entidades de datos en [Administración de datos](../../dev-itpro/data-entities/data-entities.md).
7.  Valide los cambios. Como parte del proceso de validación se producen varias validaciones de la integridad de datos. Como parte de un proceso de actualización mayor, es posible que los problemas que aparezcan tengan que ajustarse en la implementación de origen. En este caso, será necesaria otra actualización de datos.
8.  Procese los cambios. Una actualización de todas las dimensiones de inventario puede tardar. Puede controlar el progreso mediante las tareas de los trabajos por lotes.



