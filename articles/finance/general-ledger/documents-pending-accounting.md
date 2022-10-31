---
title: Contabilidad pendiente de documentos
description: En este artículo se describe como usar la funcionalidad en la página Contabilidad pendiente de documentos.
author: ryanCCarlson2
ms.date: 09/02/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: f37d46659b2fc5bf9933719811a7b90cc4e80f52
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709261"
---
# <a name="documents-pending-accounting"></a>Contabilidad pendiente de documentos

[!include [banner](../includes/banner.md)]

En este artículo se describe como usar la funcionalidad en la página **Contabilidad pendiente de documentos**.

En Microsoft Dynamics 365 Finance 10.0.30, la característica **Rendimiento mejorado del marco de contabilidad de documentos de origen** está disponible. Esta característica mejora los procesos de registro para registros de documentos habilitados para documentos de origen, que comienza con el proceso de registro para facturas de servicios.

Cuando esta característica está habilitada, el registro del documento del subdiario se realiza por separado del proceso de generación de contabilidad o de *registro en el diario*, que crea el detalle contable completo que se transfiere a la contabilidad general. Por ejemplo, en el proceso de registro de facturas de servicios, la factura de cliente en el módulo **Clientes** se registra antes de que se genere la contabilidad completa. Esta característica de rendimiento mejorada permite que las facturas de los clientes se registren más rápido mientras se retrasa la generación de contabilidad.

Los siguientes botones están disponibles en la página **Contabilidad pendiente de documentos**.

- **Generar contabilidad:** envíe un documento que actualmente esté pendiente de generación de cuenta para el registro en el diario.
- **Ver distribuciones:** vea las distribuciones contables para un documento seleccionado en la lista.
- **Ver registro de errores:** vea los detalles de cualquier mensaje de error que exista para un documento donde el estado contable indica errores. Puede ver los mismos detalles del mensaje de error seleccionando el vínculo **Registro de errores** en la línea del documento.

La generación de contabilidad se realiza mediante un proceso en segundo plano para la automatización de procesos que se denomina **Procesador de marco de contabilidad**. Para obtener más información sobre la instalación y la configuración de todas las automatizaciones de procesos, consulte [Automatización de procesos](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
