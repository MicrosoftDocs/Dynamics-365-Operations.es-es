---
title: Recuento de inventario en un almacén
description: En este tema se describe el proceso para crear y registrar un diario de recuento de inventario para contar un artículo específico en una ubicación del almacén.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 452822eaf26c26e4c9e00f909dbd18127f6fc781
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230113"
---
# <a name="count-inventory-in-a-warehouse"></a>Recuento de inventario en un almacén

[!include [banner](../../includes/banner.md)]

En este tema se describe el proceso para crear y registrar un diario de recuento de inventario para contar un artículo específico en una ubicación del almacén. El procedimiento se aplica a la funcionalidad de “almacenamiento básico”, disponible en el módulo Gestión del inventario, no en la funcionalidad de almacenamiento que está disponible en el módulo Gestión de almacenes. Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos. Si usa sus propios datos, asegúrese de que tiene los productos y las ubicaciones configurados, y de que ha creado un nombre de diario de inventario para contar los diarios. El recuento de inventario lo lleva a cabo normalmente un empleado de almacén.


## <a name="create-an-inventory-counting-journal"></a>Crear un diario de recuento de inventario
1. Vaya a **Panel de exploración > Módulos > Gestión del inventario > Movimientos de diario > Recuento de artículos > Recuento**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, seleccione en la lista desplegable el nombre del diario de recuento de inventario que desea usar. Algunos otros campos se rellenarán según la configuración del nombre de diario de recuento de inventario que seleccione.  
4. En el campo **Trabajador**, seleccione el botón desplegable para abrir la búsqueda.
5. En la lista, haga clic en **Seleccionar** para seleccionar el trabajador que desea usar.
6. Seleccione **Aceptar**.

## <a name="create-journal-lines"></a>Crear líneas de diario
1. Seleccione **Nuevo**.
2. En el campo **Código de artículo**, seleccione en la lista desplegable el registro que desea. Si va a utilizar los datos de demostración de la empresa USMF, seleccione **A0001**.  
3. En el campo **Sitio**, seleccione en la lista desplegable el registro que desea. Si utiliza los datos de la empresa de demostración USMF, seleccione el sitio **2**.
4. En el campo **Almacén**, seleccione en la lista desplegable el registro que desea. Si utiliza los datos de demostración de la empresa USMF, seleccione el almacén **24**.  
5. En el campo **Ubicación**, seleccione en la lista desplegable el registro que desea. Si utiliza los datos de demostración de la empresa USMF, seleccione la ubicación **BULK-001**.  
6. En el campo Contado, especifique un número. Si especifica un número contado diferente al número mostrado en el campo **Disponible**, el campo **Cantidad** se actualiza para mostrar la discrepancia.  
7. Seleccione **Guardar**.

## <a name="post-the-inventory-counting-journal"></a>Registrar el diario de recuento de inventario
1. Seleccione **Registrar**. Cuando registra un diario de recuento de inventario, si el importe contado es diferente del importe que se notifica en el campo **Disponible** en que se registra una recepción o emisión del inventario, se modifican el nivel y el valor del inventario, y se generan las transacciones contables.
2. Seleccione **Aceptar**.

## <a name="view-inventory-transactions"></a>Ver transacciones de inventario
1. Seleccione **Inventario**.
2. Seleccione **Transacciones**. Aquí puede ver las transacciones relacionadas que se creará al registrar el diario de recuento de inventario.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]