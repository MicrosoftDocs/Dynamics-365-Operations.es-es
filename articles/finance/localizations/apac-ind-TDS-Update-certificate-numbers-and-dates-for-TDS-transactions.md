---
title: Actualizar números y fechas de certificados para transacciones de TDS
description: Este tema explica cómo actualizar los certificados recuperables para registrar los números y las fechas de los certificados que se registraron para cuentas de proveedor, cliente y contables con impuestos deducidos en el origen (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7f8b5713e8ce3f9e9c89b8b3bc6ea84fe1f0fa54
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724822"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a>Actualizar números y fechas de certificados para transacciones de TDS

[!include [banner](../includes/banner.md)]

Este tema explica cómo actualizar los certificados recuperables para registrar los números y las fechas de los certificados que se registraron para cuentas de proveedor, cliente y contables con impuestos deducidos en el origen (TDS). Puede ver los certificados para transacciones de TDS en la página **Certificados recuperables**. Puede actualizar los certificados utilizando el la página **Actualizar certificados**.

Siga estos pasos para actualizar los números y fechas de certificados para transacciones de TDS.

1. Vaya a **Impuesto \> Declaraciones \> Retención de impuestos \> Actualizar certificado**.

    [![Página Actualizar certificado.](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)

2. En la página **Actualizar certificado**, en la sección **Seleccionar**, en el campo **Tipo de impuesto**, seleccione **TDS**.
3. En el campo **Número de certificado**, seleccione el número de certificado de TDS del cliente o del proveedor.

    > [!NOTE]
    > El campo **Número de certificado** enumera solo los números de certificado de TDS para los que se ha marcado la casilla **Cerrado** en la página **Certificados recuperables**.

    El campo **Fecha del certificado** muestra la fecha del certificado. El campo **Tipo de cuenta** muestra el tipo de cuenta para la que se recibe el número de certificado de TDS y el campo **Nombre** muestra el nombre de la cuenta.

5. En los campos **Fecha inicial** y **Fecha final**, seleccione las fechas iniciales y finales del período para mostrar las transacciones de TDS.
6. Seleccione **Mostrar datos** para ver las transacciones de TDS que se registraron durante el período seleccionado.

    En la pestaña **Información general**, la cuadrícula en el panel superior muestra la siguiente información sobre cada transacción de TDS que se publicó para el proveedor o cliente durante el período seleccionado:

    - **Asiento**: el número de asiento de la transacción de TDS.
    - **Fecha**: la fecha de la transacción de TDS.
    - **Importe**: el importe de la factura sobre el que se calcularón los TDS.
    - **Importe del impuesto**: el importe del impuesto TDS que se calculó para la transacción.

7. Para mover transacciones de TDS específicas de la cuadrícula superior a la cuadrícula inferior, seleccione las transacciones y luego seleccione **Incluir**. Alternativamente, seleccione **Incluir todo** para mover todas las transacciones de TDS de la cuadrícula superior a la cuadrícula inferior.

    Para mover transacciones de TDS específicas o todas las transacciones de TDS de la cuadrícula inferior a la cuadrícula superior, use el botón **Excluir** o **Excluir todo**.

8. Seleccione **Actualizar** para actualizar los campos **Número de certificado** y la **Fecha del certificado** para transacciones de TDS en la cuadrícula inferior.
10. Vaya a **Impuesto \> Impuestos indirectos \> Retención de impuestos \> Certificado recuperable** y seleccione **Consulta** para ver las líneas de transacciones actualizadas que tienen los nuevos números de certificado en la página **Transacciones de certificados**.

    [![Página Transacciones de certificados.](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)
