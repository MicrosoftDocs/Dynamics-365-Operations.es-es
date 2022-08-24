---
title: Versión 4.0 del diseño CFDI
description: Este artículo proporciona información sobre la versión 4.0 del diseño Comprobante Fiscal Digital por Internet (CFDI) para México.
author: AdamTrukawka
ms.date: 06/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: atrukawk
ms.search.validFrom: 2022-04-01
ms.search.form: CustPosting, VendParameters
ms.openlocfilehash: bf7e26d3473723f34ff664c9746a339aaeffd2c2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279795"
---
# <a name="cfdi-layout-version-40"></a>Versión 4.0 del diseño CFDI

[!include [banner](../includes/banner.md)]

Si su organización utiliza facturas electrónicas que son validadas y certificadas por un proveedor de servicios de firma digital de terceros (PAC), habilite la facturación electrónica mediante los campos del área **CFDI** de la página **Parámetros de factura electrónica**.

Para trabajar con la versión 4.0, configure los siguientes valores para los parámetros de la factura electrónica:

- En la página **Parámetros de factura electrónica**, en el campo **Versión CFDI**, seleccione **4.0**.
- En la pestaña **CFDI**, en los campos **Archivo de esquema CFDI XML** y **Archivo de esquema XML de pago de CFDI**, seleccione un nuevo archivo de esquema XML.
- En la página **Parámetros de factura electrónica**, en el campo **Período**, puede establecer un tipo de período predeterminado. El valor de este campo se utiliza para las facturas globales de Comprobante Fiscal Digital por Internet (CFDI). Puede actualizar este valor cuando registra una factura de pedido de ventas, una factura de texto sin formato o una propuesta de factura. Si el número de Registro Federal de Contribuyentes (RFC) de un cliente es 'XAXX010101000', el sistema completa el elemento **InformacionGlobal** en el archivo XML con los atributos **Periodicidad**, **Meses**, y **Año**.
- En la pestaña **Retención CFDI**, en el campo **Archivo de esquema CFDI XML**, seleccione un nuevo archivo de esquema XML.
- Vaya a **Clientes** \> **Clientes**, y luego, en la ficha desplegable **Factura y entrega**, en la sección **Facturas electrónicas**, introduzca el régimen fiscal de los clientes.

Para una exportación temporal, abra el registro del cliente y, a continuación, en la pestaña **Factura y entrega**, configure la opción **Exportación temporal** en **Sí**. Esta configuración se utiliza como valor predeterminado para pedidos de venta relacionados o facturas de texto sin formato.

Cuando registra una factura de proveedor, puede agregar una referencia de CFDI a la factura relacionada, eligiendo **Archivos adjuntos** \> **Referencia CFDI**.

Si el campo **Tipo de retención** de los detalles de la línea de compra tiene un valor de **28**, los dos nuevos campos, **Importe de beneficio bimestral** e **Importe correspondiente al ISR**, se incluyen en los detalles del diario de retenciones del CFDI. Introduzca un valor estos dos campos. A continuación, los atributos correspondientes se establecen en el archivo XML.

Para obtener más información acerca la configuración de CFDI y de cómo trabajar con documentos CFDI, consulte los temas siguientes:

- [Versión 3.3 del diseño CFDI](latam-mex-cfdi-3-3.md)
- [Facturación electrónica de CFDI](tasks/mx-00010-e-invoicing-cfdi.md)
- [Facturas electrónicas (CFDI)](latam-mex-cfdi-electronic-invoices.md)
- [Complemento Hoja de ruta (Carta de Porte)](latam-mex-carta-de-porte.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
