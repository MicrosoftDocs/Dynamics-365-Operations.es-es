---
title: Reembolsar a clientes
description: "En este artículo se explica cómo crear transacciones de reembolso de un grupo de clientes. Si un cliente tiene un saldo de crédito, puede reembolsar al cliente por el importe del saldo."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c3201166eb7054205647a54ed80f98968fcfda6e
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="reimburse-customers"></a>Reembolsar a clientes

[!include[banner](../includes/banner.md)]


En este artículo se explica cómo crear transacciones de reembolso de un grupo de clientes. Si un cliente tiene un saldo de crédito, puede reembolsar al cliente por el importe del saldo. 

La tabla siguiente muestra los requisitos previos que deben cumplirse antes de comenzar.

| Requisito previo                                                            | Descripción                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Especifique el importe mínimo de reembolso para la entidad jurídica.          | En la página **Parámetros de clientes**, en el área **General**, en el campo **Reembolso mínimo**, especifique el importe mínimo que se puede reembolsar paras los sobrepagos del cliente. |
| Opcional: agregar una cuenta de proveedor a cada cliente que se puede reembolsar. | En la página **Clientes**, en la ficha desplegable **Detalles varios**, en el campo **Cuenta de proveedor**, seleccione la cuenta de proveedor para el cliente.                                           |

Cuando crea transacciones de reembolso, se crea una factura de proveedor para el importe del saldo de crédito. El proceso de reembolso quita el saldo de crédito para la cuenta de cliente y crea un saldo pendiente para la cuenta de proveedor que corresponde al cliente.

1.  En Clientes, ejecute el proceso **Reembolso**.
2.  Siga uno de estos pasos:
    -   Para reembolsar cuentas de cliente específicas, haga clic en **Seleccionar** y especifique las cuentas en la consulta.
    -   Para reembolsar todas las cuentas de cliente, haga clic en **Aceptar**.

    Los importes de crédito se transfieren a las cuentas de proveedor de los clientes y se procesan como pagos normales. Si un cliente no dispone de cuenta de proveedor, el programa creará automáticamente una cuenta de proveedor plantilla para dicho cliente.
3.  Para ver las transacciones de reembolso creadas, use la página **Reembolso**.
4.  En Proveedores, cree un pago para las facturas de proveedor que se crearon por el proceso de reembolso.





