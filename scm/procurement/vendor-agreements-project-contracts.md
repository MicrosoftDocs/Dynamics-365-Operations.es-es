---
title: Acuerdos de pago al cobro con el proveedor
description: "Este artículo explica las condiciones de pago al cobro (AaC) para los acuerdos de proveedor. Las condiciones de AaC le permiten retener parcial o completamente el pago a un proveedor hasta que el cliente del proyecto le paga. Este artículo también proporciona un ejemplo de la vida real para mostrar cómo puede usar las condiciones de AaC para un proyecto."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProjProjectsListPage
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23131
ms.assetid: 20bf1d7f-8813-4c69-9cd7-576884a7e169
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 0ca75dbd00ad260c911a323f17717d0ff83331dd
ms.lasthandoff: 03/31/2017


---

# <a name="pay-when-paid-vendor-agreements"></a>Acuerdos de pago al cobro con el proveedor

[!include[banner](../includes/banner.md)]


Este artículo explica las condiciones de pago al cobro (AaC) para los acuerdos de proveedor. Las condiciones de AaC le permiten retener parcial o completamente el pago a un proveedor hasta que el cliente del proyecto le paga. Este artículo también proporciona un ejemplo de la vida real para mostrar cómo puede usar las condiciones de AaC para un proyecto.

Al aprobar a un proveedor como subcontratista para trabajar en un proyecto, puede ser conveniente retener el pago al proveedor o al subcontratista hasta que el cliente le haya pagado el proyecto. Para retener el pago a un proveedor, configure las condiciones de pago al cobro (AaC) cuando configure el pedido de compra con el proveedor. Cuando se crea un pedido de compra para el proveedor y se asigna un identificador de proyecto al pedido de compra, las condiciones de AaC del proyecto se asocian con el pedido de compra y el proveedor. En la página **Facturas de proveedor con pago al cobro**, puede ver una lista de las facturas de proveedor no pagadas para un pedido de compra y las facturas de cliente asociadas. Use este formulario para determinar si se debe pagar a un proveedor y qué cantidad se debe pagar. Por ejemplo, cuando un cliente paga un importe de una factura de proyecto, se puede liberar una parte o todas las facturas de proveedor relacionadas para el pago. Puede configurar condiciones de AaC para especificar que se paga a un proveedor después de recibir un porcentaje específico del pago relacionado de un cliente. Cuando recibe el pago parcial de un cliente, puede liberar manualmente algunas de las facturas de proveedor relacionadas para el pago. En el ejemplo siguiente se muestra cómo se pueden utilizar las condiciones de AaC para retener el pago a un proveedor o subcontratista hasta que el cliente realice el pago. Su organización llega a un acuerdo con un cliente para proporcionar 100 equipos en los que instala el software solicitado por el cliente. El precio que usted y el cliente han acordado para cada equipo es de 150,00. Contrata servicios de un proveedor de terceros para que le proporcione los equipos. El cliente desea aprobar la calidad de los equipos antes de pagar a su organización. La directiva de su organización es retener el pago a un proveedor de terceros hasta que el cliente de un proyecto le haya pagado. Por lo tanto, debe configurar el proyecto con un porcentaje de AaC del 100 por ciento, de modo que retiene todos los pagos al proveedor hasta que reciba el pago completo de la factura de cliente. El proveedor cobra 100,00 por cada equipo. Cuando el proveedor le envía los equipos, el envío incluye una factura de 10.000,00 por los 100 equipos. Dado que ha configurado el proyecto con las condiciones de AaC, no paga al proveedor. Una vez recibidos los equipos del proveedor, instala el software requerido en los equipos. Cuando envía los equipos al cliente, también le envía una factura de 15.000,00. El cliente examina los equipos y aprueba la calidad del producto. El cliente paga a su organización el importe total de la factura del proyecto. Una vez recibido el pago completo del cliente, paga 10.000,00 al proveedor por el importe total de la factura de proveedor.




