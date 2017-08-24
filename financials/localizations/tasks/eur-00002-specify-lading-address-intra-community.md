--- 
title: "Especificar una dirección de embarque para una transacción intracomunitaria"
description: "Este procedimiento muestra cómo especificar una dirección de embarque para una transacción de comercio intracomunitario."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d2225f54af0d9f900cadda6b418221a5592fe2e6
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="specify-a-lading-address-for-an-intra-community-transaction"></a>Especificar una dirección de embarque para una transacción intracomunitaria

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo especificar una dirección de embarque para una transacción de comercio intracomunitario. Por ejemplo, una empresa de Alemania pide artículos de un proveedor con una dirección empresarial alemana. Este proveedor tiene un almacén en Italia y envía artículos desde ahí. Esta entrega se debe notificar en Intrastat. El mismo comportamiento es válido para las devoluciones del cliente.
Este procedimiento se aplica a todos los países o regiones europeos. Esta tarea se ha creado con los datos de demostración de la empresa DEMF y con una dirección principal en Alemania. Para poder completar este procedimiento, debe configurar los informes Intrastat. Este procedimiento está pensado para contables. Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.

1. Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.
2. Haga clic en Nuevo.
3. Especifique o seleccione un valor
    * Por ejemplo, seleccione DE-001. Este proveedor tiene una dirección empresarial alemana.  
4. Haga clic en Aceptar
5. En la lista, marque la fila seleccionada.
6. En el campo Número de artículo, especifique o seleccione el valor D0001.
7. Haga clic en Guardar.
8. En el panel de acciones, haga clic en Recibir.
9. Haga clic en Detalles de transporte.
10. En el campo Fecha y hora de embarque, especifique una fecha y una hora.
11. Haga clic en Agregar dirección.
12. Haga clic en Nuevo y crear nueva dirección con propósito Embarque.
13. En el campo Nombre o descripción, escriba "Italiano".
14. Seleccione Embarque como valor.
    * Tenga en cuenta que el propósito de la dirección debe ser Embarque.  
15. En el campo País o región, especifique o seleccione un valor ITA.
16. Haga clic en Guardar.
17. Cierre la página.
18. Haga clic en Guardar.
    * Compruebe que la dirección de embarque es correcta.  
19. Cierre la página.
20. En el panel de acciones, haga clic en Compra.
21. Haga clic en Confirmar.
22. En el panel de acciones, haga clic en Factura.
23. Haga clic en Factura.
24. En el campo Número, escriba un valor.
25. En el campo Fecha de la factura, especifique una fecha.
26. Haga clic en Valor predeterminado de origen: Cantidad de recepción de producto para abrir el cuadro de diálogo desplegable.
27. En el campo Cantidad predeterminada para líneas, seleccione Cantidad pedida.
28. Haga clic en Aceptar
29. Haga clic en Detalles de transporte.
    * Compruebe que las mercancías se envían desde Italia. En caso necesario, puede editar los detalles de embarque.  
30. Cierre la página.
31. Haga clic en Registrar.
32. Cierre la página.
33. Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.
34. Haga clic en Transferir.
35. Seleccione Sí en el campo Factura de proveedor.
36. Haga clic en Aceptar
37. Haga clic en la pestaña General.
    * Busque una línea recién creada y compruebe que el remitente envió las mercancías desde Italia.  


