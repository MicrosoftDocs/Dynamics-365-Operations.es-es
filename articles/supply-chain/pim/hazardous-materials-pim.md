---
title: Materiales peligrosos
description: Este tema proporciona información sobre documentos de materiales peligrosos e información almacenada en su entorno.
author: lachlancashMS
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 079c8d23250368c92e5d79f0e2624f8340db2077
ms.sourcegitcommit: c009ec75f53872272f11c92a1ce81a391e3845a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "3699545"
---
# <a name="hazardous-materials"></a>Materiales peligrosos

[!include [banner](../includes/banner.md)]

La información sobre materiales peligrosos se configura en la gestión de información del producto. Este módulo también proporciona documentos que se pueden imprimir a través de la gestión del almacén.

Cuando envía materiales clasificados como mercancías peligrosas, debe incluir documentación adicional con los envíos. La funcionalidad de materiales peligrosos permite que los clientes almacenen información de clasificación y la relacionen para despachar artículos. Esta información se puede utilizar para ayudar a preparar la documentación de envío.

> [!IMPORTANT]
> Las características de materiales peligrosos en Microsoft Dynamics 365 Supply Chain Management proporcionan una colección de campos de información de productos útiles y funciones relacionadas que pueden ayudarle a registrar y hacer referencia a información relacionada con sus productos peligrosos. Estas características también pueden ayudarle a diseñar e imprimir documentos de envío que incluyan parte de la misma información sobre cualquier material peligroso que esté enviando. Sin embargo, el sistema no hará que cumpla automáticamente todas las regulaciones de su país o región. Si bien estas herramientas están destinadas a ayudarla a cumplir con las regulaciones comunes, no son suficientes por sí mismas ni se garantiza que lo sean. Su organización es responsable de conocer todas las regulaciones aplicables y de tomar todas las medidas necesarias para cumplirlas.

Antes de poder usar esta funcionalidad, se requiere la siguiente configuración:

- **Gestión de la información del producto:** configure códigos que se pueden aplicar a productos despachados.
- **Gestión de almacenes:** use documentos de envío adicionales para imprimir la información de envío.

## <a name="product-information-management"></a>Gestión de información de productos

En la gestión de la información del producto, hay una variedad de tablas de configuración donde puede agregar la información de referencia que se proporciona en las listas de mercancías peligrosas para el transporte por carretera, aéreo y marítimo.

Estas son algunas de las regulaciones a las que se suele hacer referencia:

- **ADR** - Regulaciones relacionadas con el transporte internacional de mercancías peligrosas por carretera.
- **CFR 49** - Regulaciones en los Estados Unidos para el transporte de mercancías peligrosas
- **IMDG** - El código internacional de mercancías peligrosas marinas (IMDG)
- **IATA** - Las regulaciones de mercancías peligrosas de la Asociación Internacional de Transporte Aéreo (IATA)

Cada una de estas regulaciones tiene una lista de productos peligrosos que incluye códigos de referencia. Las listas para cada tipo de transporte se combinan en clasificaciones internacionales compartidas. Supply Chain Management proporciona una tabla de referencia para los códigos compartidos en esas listas. Cada lista también tiene algunos códigos únicos que se pueden definir.

Para comenzar a configurar esta información, cree una regulación que pueda usar para configurar los parámetros iniciales.

## <a name="warehouse-management"></a>Gestión de almacenes

Cuando se prepara un envío, se pueden imprimir varios informes nuevos. Estos informes utilizan la información que configuró en la gestión de información del producto.
