---
title: Solucionar problemas de actualización y migración a la gestión avanzada de almacenes
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al actualizar y migrar a la gestión de almacenes avanzada.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d50c6d75ec7cc98109cf81c38ff42b4d2b105b0c
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645826"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a>Solucionar problemas de actualización y migración a la gestión avanzada de almacenes

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al actualizar y migrar a la gestión de almacenes avanzada.

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a>Recibo el siguiente mensaje de error: "java.security.cert.certPathValidatorException: no se encuentra el ancla de confianza para la ruta de certificación".

### <a name="issue-description"></a>Descripción del problema

Recibe este mensaje de error en la aplicación del almacén, porque los certificados autofirmados no son confiables en Android 8+ en entornos locales.

### <a name="issue-resolution"></a>Solución del problema

Utilice una autoridad de certificación (CA) externa (pública). Hay una solución para este problema disponible en la versión 1.9.0.0 de la aplicación de almacén. Para obtener más información sobre este problema y cómo solucionarlo, consulte [Solucionar problemas de conexión de la aplicación de almacén](troubleshoot-warehouse-app-connection.md).

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a>¿Cuál es el proceso aprobado para pasar del almacenamiento básico al almacenamiento avanzado?

### <a name="issue-description"></a>Descripción del problema

Actualmente se encuentra bajo la gestión de existencias / inventario y utiliza la funcionalidad básica de existencias, y desea pasar a un almacenamiento avanzado para aprovechar los dispositivos móviles, las olas y el trabajo. Sin embargo, está experimentando problemas cuando intenta hacer este movimiento. Por ejemplo, no puede cambiar sus productos para que utilicen dimensiones de almacenamiento (sitio, almacén y ubicación), porque los productos tienen transacciones contra ellos. Por lo tanto, debe aprender el proceso aprobado para pasar del almacenamiento básico al almacenamiento avanzado.

### <a name="issue-resolution"></a>Solución del problema

Para obtener más información sobre el proceso para pasar del almacenamiento básico al almacenamiento avanzado, consulte las siguientes publicaciones de blog y documentación:

- [Habilitar el proceso de gestión de almacén para artículos y almacenes existentes](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [Migración de Microsoft Dynamics AX WMS a la nueva funcionalidad de transporte y almacenamiento R3](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [Migración de elementos WMSI/WMS2](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [Actualizar la gestión de almacenes de Microsoft Dynamics AX 2012 a Supply Chain Management](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]