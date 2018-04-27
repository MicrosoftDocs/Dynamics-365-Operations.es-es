---
title: "Inspeccionar la calidad de las mercancías"
description: "Este procedimiento muestra cómo procesar un pedido de calidad."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: aeed7eab750c606ea0009fa7c51baf96e2f9de51
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="inspect-the-quality-of-goods"></a>Inspeccionar la calidad de las mercancías

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo procesar un pedido de calidad. Puede ejecutar esta guía en la empresa de datos de demostración USMF. Antes de comenzar este procedimiento de ejemplo, debe confirmar el pedido de compra "000016" y registrar una recepción de producto. Esto crea automáticamente un pedido de calidad. Las inspecciones de calidad las lleva a cabo normalmente un empleado de control de calidad.


## <a name="select-a-quality-order"></a>Selección de un pedido de calidad
1. Vaya a Gestión del inventario > Tareas periódicas > Administración de calidad > Pedidos de calidad.
2. En la lista, marque la fila seleccionada.
    * Seleccione el pedido de calidad que se creó antes de empezar este procedimiento.  

## <a name="record-test-results"></a>Registrar resultados de prueba
1. Haga clic en Resultados.
2. Haga clic en Editar.
3. En el campo Cantidad de resultado, especifique un número.
4. En la lista, marque la fila seleccionada.
5. En el campo Resultado, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
    * En este ejemplo, el resultado se basa en un resultado predefinido. Normalmente, registrará un resultado de prueba más específico, como el tamaño u otra dimensión.  
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Haga clic en Guardar.
9. Cierre la página.

## <a name="validate-the-quality-order"></a>Validar el pedido de calidad
1. Haga clic en Validar.
2. En el campo Validado por, haga clic en el botón desplegable para abrir la búsqueda.
    * Seleccione el usuario que realiza la inspección.  
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Haga clic en Seleccionar.
5. Haga clic en Aceptar
6. Cierre la página.

