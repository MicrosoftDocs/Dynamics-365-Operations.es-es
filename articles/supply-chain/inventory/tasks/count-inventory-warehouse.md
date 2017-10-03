---
title: "Recuento de inventario en un almacén"
description: "Este procedimiento muestra el proceso para crear y registrar un diario de recuento de inventario para contar un artículo específico en una ubicación del almacén."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 1d2ecf1cd80e05b59f206fb5f684d6a86fa5733e
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="count-inventory-in-a-warehouse"></a>Recuento de inventario en un almacén

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra el proceso para crear y registrar un diario de recuento de inventario para contar un artículo específico en una ubicación del almacén. El procedimiento se aplica a la funcionalidad de “almacenamiento básico”, disponible en el módulo Gestión del inventario, no en la funcionalidad de almacenamiento que está disponible en el módulo Gestión de almacenes. Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos. Si usa sus propios datos, asegúrese de que tiene los productos y las ubicaciones configurados, y de que ha creado un nombre de diario de inventario para contar los diarios. El recuento de inventario lo lleva a cabo normalmente un empleado de almacén.


## <a name="create-an-inventory-counting-journal"></a>Crear un diario de recuento de inventario
1. Vaya a Gestión del inventario > Movimientos de diario > Recuento de artículos > Recuento.
2. Haga clic en Nuevo.
3. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, haga clic en el nombre de diario de recuento de inventario que desea usar.
    * Algunos otros campos se rellenarán según la configuración del nombre de diario de recuento de inventario que seleccione.  
5. En el campo Trabajador, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, seleccione el trabajador que desee usar.
7. Haga clic en Seleccionar.
8. Haga clic en Aceptar

## <a name="create-journal-lines"></a>Creación de líneas de diario
1. Haga clic en Nuevo.
2. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el registro deseado.
    * Si utiliza los datos de la empresa de demostración USMF, seleccione "A0001".  
4. En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, busque y seleccione el registro deseado.
    * Si utiliza los datos de la empresa de demostración USMF, seleccione el sitio "2".  
6. En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, busque y seleccione el registro deseado.
    * Si utiliza los datos de la empresa de demostración USMF, seleccione el almacén "24".  
8. En el campo Ubicación, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, busque y seleccione el registro deseado.
    * Si utiliza los datos de la empresa de demostración USMF, seleccione la ubicación "BULK-001".  
10. En el campo Contado, especifique un número.
    * Si especifica un número contado diferente al número mostrado en el campo Disponible, el campo Cantidad se actualiza para mostrar la discrepancia.  
11. Haga clic en Guardar.

## <a name="post-the-inventory-counting-journal"></a>Registrar el diario de recuento de inventario
1. Haga clic en Registrar.
    * Cuando registra un diario de recuento de inventario, si el importe contado es diferente del importe que se notifica en el campo Disponible en que se registra una recepción o emisión del inventario, se modifican el nivel y el valor del inventario, y se generan las transacciones contables.  
2. Haga clic en Aceptar

## <a name="view-inventory-transactions"></a>Ver transacciones de inventario
1. Haga clic en Inventario.
2. Haga clic en Transacciones.
    * Aquí puede ver las transacciones relacionadas que se creará al registrar el diario de recuento de inventario.   

