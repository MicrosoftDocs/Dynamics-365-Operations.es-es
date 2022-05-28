---
title: Registrar los números de los certificados de concesión de TDS
description: Este tema explica cómo registrar los números de certificado de concesión de impuestos deducidos en el origen (TDS) que se emiten a los proveedores.
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
ms.openlocfilehash: 994ddbb4666c326d237d53d529ba126f42d48595
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727156"
---
# <a name="record-tds-concession-certificate-numbers"></a>Registrar los números de los certificados de concesión de TDS

[!include [banner](../includes/banner.md)]

Este tema explica cómo registrar los números de certificado de concesión de impuestos deducidos en el origen (TDS) que se emiten a los proveedores.

1. Vaya a **Impuestos \> Impuestos indirectos \> Retención de impuestos \> Concesiones de retenciones de impuestos**.
2. En el campo **Tipo de impuesto**, seleccione **TDS** para registrar certificados de concesión para el tipo de impuesto TDS.
3. En la pestaña **Información general**, seleccione **Alt + N** para crear una línea.

    [![Encabezado de la nueva línea.](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)

4. En el campo **Código de retención de impuestos**, seleccione el código de impuestos TDS para el que se emiten los certificados de concesión del proveedor. El campo **Nombre del código de retención de impuestos** muestra el nombre del código de impuestos de TDS.
5. En los campos **Fecha inicial** y **Fecha final**, defina el periodo de validez del certificado de concesión que utiliza el código de impuestos de TDS para calcular los TDS para el proveedor en condiciones favorables.
6. En el campo **Observaciones**, introduzca cualquier comentario.
7. En el campo **Sección**, introduzca el código de la sección legal bajo la cual se hace uso del certificado de concesión TDS.

    Si el código de la sección es 197, el valor "A" aparece tanto en la columna "Razón de la no deducción/deducción más baja" en el formulario 26Q, como en la columna "Razón de la no deducción/deducción más baja/pago de impuestos (si corresponde)" en formulario 27Q. Si el código de sección es 197A, el valor "B" aparece en ambos lugares.

8. Seleccione la ficha despegable **Certificado** para registrar los números de certificados de concesión de TDS para los proveedores.
9. En el campo **Cuenta del proveedor**, seleccione la cuenta del proveedor para la que se emite el certificado de concesión de TDS.
10. En los campos **Fecha inicial** y **Fecha final**, defina el periodo de validez del certificado de concesión de TDS.

    El cálculo de TDS en condiciones favorables se basa en el periodo en el que se crea el certificado para el proveedor.

11. En el campo **Certificado**, introduzca el número del certificado de concesión de TDS.

    [![Ficha desplegable Certificado.](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)

12. Cierre la página.
