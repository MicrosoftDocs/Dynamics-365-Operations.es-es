---
title: Clientes plantilla
description: "Este tema proporciona información sobre los clientes plantilla."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustTable
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264394
ms.assetid: 28357e20-5e7e-4fe9-bbdf-d4812951369e
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 06218c254faec6a63a3f6c9ee200cf32cd817e79
ms.lasthandoff: 03/31/2017


---

# <a name="one-time-customers"></a>Clientes plantilla

[!include[banner](../includes/banner.md)]


Este tema proporciona información sobre los clientes plantilla.  

Un cliente plantilla es un cliente que no tiene una relación a largo plazo con su empresa. Para los clientes plantilla, normalmente no es necesario guardar información como la dirección, el contacto, o los detalles de identificación fiscal. Para indicar que un cliente es un cliente plantilla, siga estos pasos:

1.  Abra la página **Todos los clientes**.
2.  Seleccione un nombre de cliente para abrir el registro del cliente.
3.  En la ficha desplegable **Detalles varios**, establezca la opción **Cliente plantilla** en **Sí**.
4.  Haga clic en **Guardar**.

**Nota:** para poder registrar transacciones para un cliente plantilla, debe especificar una cuenta para dicho cliente en el campo **Cuenta de cliente plantilla** de la página **Parámetros de clientes**. Para España, puede especificar restricciones de usuario para la creacción de contratos de proyecto para clientes plantilla. Para ello, realice los pasos siguientes:

1.  Abra la página **Parámetros de gestión de proyectos y contabilidad**.
2.  Establezca el parámetro **No se permite usar clientes plantilla para contratos de proyectos** en **Verdadero**.
3.  Haga clic en **Guardar**.





