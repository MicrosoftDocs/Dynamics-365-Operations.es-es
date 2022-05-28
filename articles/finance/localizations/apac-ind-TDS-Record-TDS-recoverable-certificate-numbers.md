---
title: Registrar los números de los certificados recuperables de TDS
description: Este tema explica cómo usar la página de certificados recuperables para registrar los números de certificado y las fechas de los certificados con impuestos deducidos en el origen (TDS) que se reciben para un proveedor, cliente o contabilidad general específicos.
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
ms.openlocfilehash: 5d62f560fe58a5fb7bd158bed9bcb111d75c7f00
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726501"
---
# <a name="record-tds-recoverable-certificate-numbers"></a>Registrar los números de los certificados recuperables de TDS

[!include [banner](../includes/banner.md)]

Este tema explica cómo usar la página de **Certificados recuperables** para registrar los números de certificado y las fechas de los certificados con impuestos deducidos en el origen (TDS) que se reciben para un proveedor, cliente o contabilidad general específicos. Para actualizar los números de certificado de TDS y las fechas que se registran para las transacciones de TDS en esta página, utilice la página **Actualizar certificado** (**Contabilidad general \> Periódica \> Retención de impuestos \> Actualizar certificado**). Una vez que hayan terminado de actualizar los números de certificado TDS, ciérrelos.

Siga estos pasos para registrar los números y fechas del certificado TDS.

1. Vaya a **Impuestos \> Impuesto indirecto \> Retención de impuestos \> Certificados recuperables**.

    [![Página de certificados recuperables.](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png) 

2. En la página **Certificados recuperables**, en el campo **Tipo de impuesto**, seleccione **TDS**.
3. Seleccione **Nuevo** para crear un registro.
4. En el campo **Número de certificado**, introduzca el número del certificado de TDS.
5. En el campo **Tipo de cuenta**, seleccione el tipo de cuenta para la que se recibe el certificado de TDS: **Proveedor**, **Cliente** o **Contabilidad general**.
6. En el campo **Cuenta**, seleccione el número de cuenta de proveedor, cliente o contabilidad general, según el tipo de cuenta que haya seleccionado. El campo **Nombre** muestra el nombre del proveedor, cliente o cuenta contable.
7. En el campo **Importe del certificado**, introduzca el importe del certificado de TDS.
8. En el campo **Fecha**, introduzca la fecha certificada del número del certificado.
9. Seleccione **Consultas** para abrir la página **Transacciones de certificados**, donde puede ver las transacciones de TDS para las que se actualizan el número y la fecha del certificado de TDS. Esta información se puede actualizar en la página **Actualizar certificado** (**Impuesto \> Declaraciones \> Retención de impuestos \> Actualizar certificado**).

    La página **Actualizar certificado** muestra la siguiente información para cada transacción de TDS:

    - **Fecha**: la fecha de registro de la transacción de TDS.
    - **Asiento**: el número de asiento de la transacción de TDS.
    - **Origen**: el módulo en el que se creó la transacción de TDS.
    - **Cuenta**: el número de cuenta de proveedor, cliente o cuenta contable para el que se creó la transacción de TDS.
    - **Nombre**: el número de cuenta de proveedor, cliente o cuenta contable para el que se creó la transacción de TDS.
    - **Importe**: el importe de la factura sobre el que se calcularón los TDS.
    - **Importe del impuesto**: el importe del impuesto TDS que se calculó para la transacción.
    - **Fecha del certificado**: la fecha del certificado de TDS que se actualizó para la transacción de TDS.
    - **Número del certificado**: el número del certificado de TDS que se actualizó para la transacción de TDS.

10. En la página **Certificados recuperables**, seleccione la casilla **Cerrado** para cerrar el número de certificado de TDS después de que haya terminado de actualizarlo para transacciones de TDS en la página **Actualizar certificado**.

    Para seleccionar la casilla **Cerrado** para todos los registros de la página, seleccione **Marcar todo**.

    > [!NOTE]
    > Los números de certificado de TDS con la casilla **Cerrado** seleccionada no están disponibles en la página **Actualizar certificado**.
