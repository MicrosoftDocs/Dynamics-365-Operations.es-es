---
title: Creación de un plan de materiales para coproductos
description: El planificador de producción planifica los requisitos de material para los artículos que son coproductos de la fórmula.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27bba54db915b7ccc31fda43a00a8c9435493e07
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469544"
---
# <a name="create-a-material-plan-for-co-products"></a>Creación de un plan de materiales para coproductos

[!include [banner](../../includes/banner.md)]

El planificador de producción planifica los requisitos de material para los artículos que son coproductos de la fórmula. La empresa de datos de demostración utilizada para crear este procedimiento es USP2.

## <a name="create-requirement-for-a-co-product"></a>Creación de un requisito para un coproducto

1. Vaya a **Ventas y marketing \> Espacios de trabajo \> Procesamiento y consulta de pedidos de venta**.
1. Seleccione **Nuevo**.
1. Seleccione **Pedido de ventas**.
1. En el campo **Cuenta de cliente**, escriba un valor.
    * Ejemplo: US-001  
1. Seleccione **Aceptar**.
1. En el campo **Código de artículo**, escriba un valor.
    * Ejemplo: P6003  
1. En el campo **Cantidad**, especifique un número.
    * Ejemplo: 50000  
1. Seleccione **Guardar**.

## <a name="create-a-material-plan-for-co-products"></a>Crear un plan de materiales para coproductos

1. Cierre la página.
1. Cierre la página.
1. Seleccione **Planificación maestra**.
1. En el campo **Plan**, seleccione el botón desplegable para abrir la búsqueda.
1. En la lista, seleccione el vínculo de la fila seleccionada.
    * Ejemplo: Plan maestro  
1. Seleccione **Ejecutar**.
1. Expanda o contraiga la sección **Registros a incluir**.
1. Seleccione **Filtro**.
1. En la lista, seleccione la fila de **Campo** = *Número de artículo*.
1. En el campo **Criterios**, escriba un valor.
    * Ejemplo: P6003  
1. Seleccione **Aceptar**.
1. Seleccione **Aceptar**.
1. Seleccione **Pedidos planificados**.
1. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo **Número de artículo** con un valor de 'P6000'.
    * Filtre por el producto de fórmula que tiene como coproducto el producto para el cual ha creado un pedido de ventas.  
1. En la lista, marque la fila seleccionada.
    * Seleccione cualquiera de las filas que haya devuelto el filtro.  
1. En la lista, seleccione el vínculo de la fila seleccionada.
1. Expanda la sección **Diagrama de árbol**.
1. En la lista, seleccione el vínculo de la fila seleccionada.
    * El pedido planificado se adjunta al pedido de ventas para el coproducto.  
1. Cierre la página.

## <a name="create-a-second-requirement-for-a-co-product"></a>Creación de un segundo requisito para un coproducto

1. Vaya a **Ventas y marketing \> Espacios de trabajo \> Procesamiento y consulta de pedidos de venta**.
1. Seleccione **Nuevo**.
1. Seleccione **Pedido de ventas**.
1. En el campo **Cuenta de cliente**, escriba un valor.
    * Ejemplo: US-001  
1. Seleccione **Aceptar**.
1. En el campo **Código de artículo**, escriba un valor.
    * Ejemplo: P6003  
1. En el campo **Cantidad**, especifique un número.
    * Ejemplo: 50000  
1. Seleccione **Guardar**.

## <a name="create-a-second-material-plan-for-co-products"></a>Crear un segundo plan de materiales para coproductos

1. En el campo **Plan**, seleccione el botón desplegable para abrir la búsqueda.
2. En la lista, seleccione el vínculo de la fila seleccionada.
    * Ejemplo: Plan maestro  
3. Seleccione **Ejecutar**.
4. Expanda o contraiga la sección **Registros a incluir**.
5. Seleccione **Filtro**.
6. En la lista, seleccione la fila de **Campo** = *Número de artículo*.
7. En el campo *Criterios*, escriba un valor.
    * Ejemplo: P6003  
8. Seleccione **Aceptar**.
9. Seleccione **Aceptar**.
10. Seleccione **Pedidos planificados**.
11. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo **Número de artículo** con un valor de 'P6000'.
    * Filtre por el producto de fórmula que tiene como coproducto el producto para el cual ha creado un pedido de ventas.  
12. En la lista, marque la fila seleccionada.
    * Seleccione cualquiera de las filas que haya devuelto el filtro.  
13. En la lista, seleccione el vínculo de la fila seleccionada.
14. Expanda o contraiga la sección **Diagrama de árbol**.
15. En la lista, seleccione el vínculo de la fila seleccionada.
    * El pedido planificado se adjunta al pedido de ventas para el coproducto.  
16. Cierre la página.
17. Seleccione **Planificación maestra**.
18. Vaya a **Planificación maestra \> Configuración \> Parámetros de planificación maestra**.
19. Seleccione *No* en el campo **Deshabilitar todos los procesos de planificación**.
20. Cierre la página.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]