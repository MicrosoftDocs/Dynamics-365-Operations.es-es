---
title: Ajuste de niveles de existencias en el almacén (almacenaje básico)
description: Este procedimiento muestra el proceso para crear y registrar un diario de ajuste de inventario para ajustar niveles de existencias de productos en el almacén.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 02458d588c9925a1f4cb9afeada793dfc55a2071
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573834"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a>Ajuste de niveles de existencias en el almacén (almacenaje básico)

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra el proceso para crear y registrar un diario de ajuste de inventario para ajustar niveles de existencias de productos en el almacén. Antes de comenzar, necesita tener configurado un nombre de diario de inventario para los ajustes de inventario. Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos. Estas tareas las realizará normalmente el empleado del almacén.


## <a name="create-an-inventory-adjustment-journal"></a>Creación de un diario de ajuste de inventario
1. Vaya a Gestión del inventario > Movimientos de diario > Artículos > Ajuste de inventario.
2. Haga clic en Nuevo.
3. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, haga clic en el nombre del diario de ajuste de inventario que desea usar.
    * Algunos otros campos se rellenarán según la configuración del nombre de diario de ajuste de inventario que seleccione.  
5. Haga clic en Aceptar

## <a name="create-journal-lines"></a>Creación de líneas de diario
1. Haga clic en Nuevo.
2. En la lista, marque el campo con el número de artículo.
3. En el campo Número de artículo, seleccione un artículo. Si utiliza los datos de la empresa de demostración USMF, escriba "D0001".
4. En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.
5. Seleccione un sitio en la lista.
6. En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.
7. Seleccione un almacén en la lista.
    * Si ha seleccionado un artículo con Ubicación como dimensión obligatoria, tendrá que especificar la ubicación aquí.  
8. En el campo Cantidad, especifique un número.
    * El campo de precio de coste especifica el coste por unidad para recepciones de inventario. Si no se especifica el coste del número de artículo, o si deseara cambiarlo manualmente, lo haría aquí.  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a>Validación y registro del diario de ajuste de inventario
1. Haga clic en Validar.
2. Haga clic en Aceptar
3. Haga clic en Registrar.
    * Al registrar este tipo de diario, se registra una recepción o emisión del inventario, se modifican el valor y el nivel del inventario y se generan transacciones contables.  
4. Haga clic en Aceptar
5. Cierre el formulario.
6. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]