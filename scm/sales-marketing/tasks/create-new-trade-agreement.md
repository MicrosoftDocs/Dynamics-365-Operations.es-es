--- 
title: Crear un nuevo acuerdo comercial
description: "Este procedimiento muestra cómo crear un acuerdo comercial por el que se registra un nuevo precio de venta acordado con un cliente específico."
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 1178c7a5db129801f83afa8b4caf9357ccf76b71
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-new-trade-agreement"></a>Crear un nuevo acuerdo comercial

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear un acuerdo comercial por el que se registra un nuevo precio de venta acordado con un cliente específico. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Si utiliza sus propios datos, antes de comenzar este procedimiento deberá asegurarse de que exista un nombre de diario de acuerdo comercial en el que la relación predeterminada esté establecida en Precio (ventas).


## <a name="create-and-post-a-new-trade-agreement-journal"></a>Creación y registro de un diario de acuerdos comerciales nuevos
1. Vaya Ventas y marketing > Precios y descuentos > Diarios de acuerdos comerciales.
2. Haga clic en Nuevo.
3. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en Líneas.
7. En el campo Código de cuenta, seleccione Tabla.
    * En este ejemplo, va a actualizar el precio para un cliente específico, por lo que tiene que elegir Tabla. Si fuera a actualizar el precio de lista del producto, seleccionaría Todo, de modo que el nuevo precio fuera válido para todos los clientes. Si fuera a diferenciar precios entre distintos segmentos de cliente, seleccionaría Grupo. Para seleccionar Grupo debe haber configurado grupos de precios de cliente.  
8. En el campo Selección de cuentas, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, busque y seleccione el registro deseado.
10. En el campo Código de artículo, seleccione Tabla.
    * Al introducir un acuerdo comercial del tipo Precio (ventas), solo se debe seleccionar Tabla en el campo Código de artículo. Esto es así porque un precio es un valor absoluto, y no puede ser el mismo para todos los productos o un grupo de productos.  
11. En el campo Relación de artículos, haga clic en el botón desplegable para abrir la búsqueda.
12. En la lista, seleccione el producto que desee incluir en el acuerdo.
    * Anote el producto que ha seleccionado.  
13. En la lista, haga clic en el vínculo de la fila seleccionada.
14. Especifique una cantidad mínima en el campo Desde.
    * Si el cliente tiene que pedir una cantidad mínima para poder optar al nuevo precio, deberá especificar la cantidad aquí.  
    * Especifique un valor en el campo A para especificar la cantidad máxima por encima de la cual no será válido el precio del acuerdo. Si ofrece precios y descuentos según distintas cantidades por niveles, especifique cada segmento de cantidad como par de cantidades mínima y máxima en los campos Desde y Hasta, respectivamente.  
15. En el campo Importe en divisa, escriba un precio.
16. En el campo Fecha inicial, especifique una fecha desde la cual será válido este acuerdo.
17. Haga clic en Guardar.
18. Haga clic en Validar.
19. Haga clic en Validar las líneas seleccionadas.
20. Haga clic en Aceptar
21. Haga clic en Registrar.
22. Haga clic en Aceptar

## <a name="view-trade-agreements-for-a-product"></a>Visualización de acuerdos comerciales para un producto
1. Vaya a Gestión de información de productos > Productos > Productos emitidos.
2. En la lista, busque y seleccione el producto cuyo precio acaba de actualizar.
3. En el panel de acciones, haga clic en Vender.
4. Haga clic en Ver acuerdos comerciales.
    * Revise los detalles del acuerdo comercial de precios que acaba de crear.    
5. Cierre la página.


