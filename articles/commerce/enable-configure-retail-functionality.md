---
title: Inicializar datos semilla en nuevos entornos de Commerce
description: En este artículo se describen los datos que se crean como parte del proceso de inicialización para Dynamics 365 Commerce.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 14d56636b48d8f8ff15863bb04c762e398f8c370664fbd52f80ed5f05f0e4895
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718740"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a>Inicializar datos semilla en nuevos entornos de Commerce

[!include [banner](includes/banner.md)]

En este artículo se describen los datos que se crean como parte del proceso de inicialización para Dynamics 365 Commerce.

Después de que la solución Commerce se haya desplegado con Microsoft Dynamics Lifecycle Services (LCS) , debe inicializar la configuración de Commerce para crear los datos de configuración básicos.

> [!IMPORTANT]
> Antes de inicializar la configuración de Commerce, asegúrese de que haya especificado un idioma y una dirección postal para cada entidad jurídica en la que va a configurar tiendas. Este paso se debe completar para cada entidad jurídica que se use para Commerce.

Para inicializar la configuración, siga estos pasos.

1. Iniciar el cliente de Commerce.
2. Haga clic en **Retail y Commerce** &gt; **Configuración de sede** &gt; **Parámetros** &gt; **Parámetros de Commerce**.
3. Haga clic en **Inicializar**.

Inicialización crea los datos de configuración siguientes predeterminados:

- Trabajos y subtrabajos del programador de Commerce
- Esquema de canal de comercio
- Programaciones de distribución de Commerce
- Diseños de pantalla predeterminados, que incluyen bloqueos, imágenes y temas
- Información de zona horaria
- Operaciones de punto de venta (PDV)
- Permisos de PDV
- Informes de canales
- Metadatos de atributos
- Plantillas de validación de entidad
- Trabajo por lotes para depurar el historial de la sesión Commerce Data Exchange

Además, el registro relacionado con la industria de la tarjeta de pago se habilita para la base de datos de Commerce.

> [!NOTE]
> Hay una opción para configurar por separado el programador de Commerce. Esta opción permite restablecer la configuración del programador de Commerce a sus valores predeterminados.

Después de que la inicialización esté completada, debe configurar los datos adicionales de Commerce. A continuación, encontrará algunos ejemplos:

- Parámetros de comercio
- Parámetros del programador de comercio
- Canales de Commerce
- Cajas registradoras y dispositivos
- Varios


[!INCLUDE[footer-include](../includes/footer-banner.md)]