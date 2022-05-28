---
title: Reembolsar a clientes
description: En este tema se explica cómo crear transacciones de reembolso de un grupo de clientes.
author: JodiChristiansen
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47d464dd23d70e1a340211eb83828550d807a543
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735650"
---
# <a name="reimburse-customers"></a>Reembolsar a clientes

[!include [banner](../includes/banner.md)]

En este tema se explica cómo crear transacciones de reembolso de un grupo de clientes. Si un cliente tiene un saldo de crédito, puede reembolsar al cliente por el importe del saldo. 

La tabla siguiente muestra los requisitos previos que deben cumplirse antes de comenzar.

| Requisito previo                                                            | Descripción |
|-------------------------------------------------------------------------|-------------|
| Especifique el importe mínimo de reembolso para la entidad jurídica.          | En la página **Parámetros de clientes**, en el área **General**, en el campo **Reembolso mínimo**, especifique el importe mínimo que se puede reembolsar paras los sobrepagos del cliente. |
| Opcional: agregar una cuenta de proveedor a cada cliente que se puede reembolsar. | En la página **Clientes**, en la ficha desplegable **Detalles varios**, en el campo **Cuenta de proveedor**, seleccione la cuenta de proveedor para el cliente. |

Cuando crea transacciones de reembolso, se crea una factura de proveedor para el importe del saldo de crédito. El proceso de reembolso quita el saldo de crédito para la cuenta de cliente y crea un saldo pendiente para la cuenta de proveedor que corresponde al cliente.

1. En Clientes, ejecute el proceso **Reembolso** (**Clientes \> Tareas periódicas \> Reembolso**).
2. Para agrupar todas las transacciones, independientemente de las dimensiones del libro mayor, establezca la opción **Resumir cliente** en **Sí**. Para agrupar solo transacciones que tienen dimensiones de libro mayor similares, establezca la opción en **No**.
3. Seleccione **Incluir clientes con transacciones de débito pendientes** para seleccionar clientes que tienen importes de débito sin liquidar.
4. Para reembolsar cuentas de clientes específicas, en la ficha desplegable **Registros a incluir**, seleccione **Filtrar** y luego especifique las cuentas de cliente en la consulta.

    Los importes de crédito se transfieren a las cuentas de proveedor de los clientes y se procesan como pagos normales. Si un cliente no dispone de cuenta de proveedor, el programa creará automáticamente una cuenta de proveedor plantilla para dicho cliente.

5. Para ver las transacciones de reembolso que se crearon, utilice el informe **Reembolso** (**Clientes \> Consultas e informes \> Informe de reembolso**).
6. En Proveedores, cree un pago para las facturas de proveedor que se crearon por el proceso de reembolso. Para obtener información sobre cómo pagar a los proveedores, consulte [Información general de pagos a proveedores](../accounts-payable/Vendor-payments-workspace.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
