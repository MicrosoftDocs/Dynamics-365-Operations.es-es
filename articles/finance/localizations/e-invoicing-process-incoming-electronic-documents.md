---
title: Procesamiento de documentos electrónicos entrantes
description: Este artículo proporciona una visión general del procesamiento de documentos electrónicos entrantes.
author: gionoder
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 554bc8fde3b2135eb878d885541c76ecd6d66493
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277313"
---
# <a name="processing-of-incoming-electronic-documents"></a>Procesamiento de documentos electrónicos entrantes

[!include [banner](../includes/banner.md)]

Los documentos electrónicos entrantes, como facturas electrónicas de proveedores, se pueden importar y procesar de dos maneras:

- Los archivos se recuperan de canales externos y se pasan directamente a su aplicación conectada. Allí, se someten a una transformación adicional y luego se importan en la base de datos.
- Los archivos se procesan previamente en el servicio de Facturación electrónica y luego se pasan a su aplicación conectada.

La facturación electrónica admite dos canales para documentos entrantes: correo electrónico y carpetas de Microsoft SharePoint.

Hay dos tipos de configuración para especificar si los documentos se procesan previamente o se pasan directamente a su aplicación conectada:

- **Canal de datos**: el sistema pasará el documento directamente a la aplicación conectada.
- **Canal de datos con canalización de procesamiento**: puede configurar acciones adicionales que se ejecutarán antes de que el documento se pase a la aplicación conectada.

Para obtener información sobre cómo configurar los escenarios para el procesamiento de documentos electrónicos entrantes para los diferentes canales, consulte [Configurar un canal de correo electrónico](e-invoicing-configure-email.md) y [Configurar un canal de SharePoint](e-invoicing-configure-sharepoint-channel.md).
