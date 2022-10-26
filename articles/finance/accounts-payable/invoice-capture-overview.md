---
title: Información general de la solución Invoice Capture
description: Este artículo proporciona información sobre la solución Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76441220b93744527f412110db536601a2fa1dd9
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691208"
---
# <a name="invoice-capture-solution"></a>Solución Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artículo proporciona información sobre la solución de Invoice Capture  que crea automáticamente facturas de proveedores a partir de imágenes de facturas digitales.

El departamento de cuentas por pagar (AP) administra y procesa las facturas de bienes y servicios que se reciben. El contador de cuentas por pagar verifica los datos en las facturas de los proveedores por las siguientes razones:

- Para evitar un esfuerzo adicional si se requieren ajustes o correcciones durante el cierre del período
- Para pagar las facturas de los proveedores de manera oportuna y evitar pérdidas financieras debido a errores o fraudes

El reconocimiento óptico de caracteres (OCR) se ha vuelto ampliamente utilizado por diferentes industrias en los últimos años. Ahora es común que los textos impresos se digitalicen, para que puedan editarse electrónicamente, buscarse, almacenarse de manera más compacta y mostrarse en línea. El texto digital se puede utilizar en procesos de máquina como computación cognitiva, traducción automática, texto a voz, datos clave y minería de texto.

La evolución de la tecnología de inteligencia artificial (IA) ha permitido que las soluciones modernas de OCR lean diferentes formatos de factura de diferentes proveedores sin requerir mucha intervención humana. Más empresas están reconociendo que pueden ahorrar esfuerzo y mejorar la precisión procesando facturas a través de la automatización en lugar de realizar un procesamiento manual.

## <a name="system-landscape"></a>Panorama del sistema

La siguiente ilustración muestra los principales componentes y pasos de la solución de Invoice Capture .

[![Componentes y pasos en la solución de Invoice Capture .](./media/Invoice-capture2.png)](./media/Invoice-capture2.png)

## <a name="required-roles"></a>Roles necesarios

La siguiente tabla muestra los roles que se requieren para configurar y utilizar la solución de Invoice Capture .

| Rol          | Acciones | Sistemas | Nombres de rol |
|---------------|---------|---------|-----------|
| Administrador | <ul><li>Configurar entornos en Microsoft Power Platform.</li><li>Implementar soluciones en Microsoft Power Platform.</li><li>Configurar conexiones entre Dynamics 365 y AI Builder.</li><li>Configurar ubicaciones de Azure Data Lake Storage.</li></ul> | <ul><li>Dynamics 365</li><li>Microsoft Power Platform</li><li>Azure Data Lake Storage</li></ul> | <ul><li>Administrador de Dynamics 365</li><li>Administrador de Power Platform</li><li>Propietario de datos de Storage Blob</li></ul> |
| Creador de IA      | <ul><li>Mantener los flujos.</li><li>Crear modelos de IA personalizados.</li></ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Creadores civiles</li></ul> |
| Empleado de cuentas por pagar      | <ul><li>Revisar y tomar medidas en el área de preparación de facturas de proveedores.</li><ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Nuevo rol de empleado de AP en Power Platform</li></ul> |
| Empleado de cuentas por pagar      | <ul><li>Realizar operaciones diarias como empleado de AP.</li><li>Navegar hasta el área de preparación de facturas de proveedor.</li></ul> | <ul><li>Dynamics 365</li></ul> | <ul><li>Funcionario de proveedores</li></ul> |
  
Para obtener más información sobre la instalación de Invoice Capture, consulte [Instalar Invoice Capture](../accounts-payable/install-invoice-capture.md).  
