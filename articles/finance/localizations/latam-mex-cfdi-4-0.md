---
title: Versión 4.0 del diseño CFDI
description: Este artículo proporciona información sobre la versión 4.0 del diseño Comprobante Fiscal Digital por Internet (CFDI) para México.
author: v-oskinaolga
ms.date: 4/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, VendParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: v-oskinaolga
ms.search.validFrom: 2022-04-01
ms.openlocfilehash: 059a397d0f26819b1d09110ac51b66d2f11b2031
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896217"
---
# <a name="cfdi-layout-version-40"></a>Versión 4.0 del diseño CFDI

[!include [banner](../includes/banner.md)]

Si su organización utiliza facturas electrónicas que son validadas y certificadas por un proveedor de servicios de firma digital de terceros (PAC), habilite la facturación electrónica mediante los campos del área **CFDI** de la página **Parámetros de factura electrónica**.

Para trabajar con la versión 4.0, configure los siguientes valores para los parámetros de la factura electrónica:

- En la página **Parámetros de factura electrónica**, en el campo **Versión CFDI**, seleccione **4.0**.
- En la pestaña **CFDI**, en los campos **Archivo de esquema CFDI XML** y **Archivo de esquema XML de pago de CFDI**, seleccione un nuevo archivo de esquema XML.
- En la pestaña **Retención CFDI**, en el campo **Archivo de esquema CFDI XML**, seleccione un nuevo archivo de esquema XML.
- Vaya a **Clientes** \> **Clientes**, y luego, en la ficha desplegable **Factura y entrega**, en la sección **Facturas electrónicas**, introduzca el régimen fiscal de los clientes.

Para una exportación temporal, abra el registro del cliente y, a continuación, en la pestaña **Factura y entrega**, configure la opción **Exportación temporal** en **Sí**. Esta configuración se utiliza como valor predeterminado para pedidos de venta relacionados o facturas de texto sin formato.

Cuando registra una factura de proveedor, puede agregar una referencia de Comprobante Fiscal Digital por Internet (CFDI) a la factura relacionada, eligiendo **Archivos adjuntos** \> **Referencia CFDI**.

Si el campo **Tipo de retención** de los detalles de la línea de compra tiene un valor de **28**, los dos nuevos campos, **Importe de beneficio bimestral** e **Importe correspondiente al ISR**, se incluyen en los detalles del diario de retenciones del CFDI. Introduzca un valor estos dos campos. A continuación, los atributos correspondientes se establecen en el archivo XML.

Para obtener más información acerca la configuración de CFDI y de cómo trabajar con documentos CFDI, consulte los temas siguientes:

- [Versión 3.3 del diseño CFDI](latam-mex-cfdi-3-3.md)
- [Facturación electrónica de CFDI](tasks/mx-00010-e-invoicing-cfdi.md)
- [Facturas electrónicas (CFDI)](latam-mex-cfdi-electronic-invoices.md)
- [Complemento Hoja de ruta (Carta de Porte)](latam-mex-carta-de-porte.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
