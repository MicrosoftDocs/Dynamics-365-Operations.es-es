---
title: Inicializar los datos de germen en un nuevo entorno al por menor
description: "Este artículo describe los datos que se crea como parte del proceso de inicialización para Microsoft Dynamics 365 para las operaciones (al por menor."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 137c675781cf75d9ce621a84c89224019c161362
ms.lasthandoff: 03/31/2017


---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a>Inicializar los datos de germen en un nuevo entorno al por menor

Este artículo describe los datos que se crea como parte del proceso de inicialización para Microsoft Dynamics 365 para las operaciones (al por menor.

Después de que la solución de venta minorista se haya desplegado con los servicios de ciclo de vida de Microsoft Dynamics, debe inicializar la configuración de venta minorista para crear los datos de configuración básicos. **Importante:** antes de inicializar la configuración de venta minorista, asegúrese de que haya especificado un idioma y una dirección postal para cada entidad jurídica en la que va a configurar tiendas de venta minorista. Este paso se debe completar para cada entidad jurídica que se use para la venta minorista. Para inicializar la configuración de venta minorista, siga estos pasos.

1.  Iniciar Dynamics 365 del cliente de las operaciones.
2.  Haga clic ** al por menor y comercio ** &gt; ** Retail Headquarters ** &gt; ** configurar los parámetros ** &gt; ** los parámetros de ventas **.
3.  Haga clic en **Inicializar**.

Inicialización crea los datos de configuración siguientes predeterminados:

-   Trabajos y subtrabajos del programador de ventas minoristas
-   Esquema del canal comercial
-   Programaciones de distribución de ventas minoristas
-   Diseños de pantalla predeterminados, que incluyen bloqueos, imágenes y temas
-   Información de zona horaria
-   Operaciones de punto de venta (PDV)
-   Permisos de PDV
-   Informes de canales
-   Metadatos de atributos
-   Plantillas de validación de entidad
-   Trabajo por lotes para purgar historial de la sesión de intercambio de datos comerciales

Además, la conexión relacionada con el sector (PCI) de la tarjeta de pago se habilita para Dynamics 365 de la base de datos de las operaciones. **Nota:** hay una opción para configurar por separado el programador de venta minorista. Esta opción permite restablecer la configuración del programador de venta minorista a sus valores predeterminados. Después de que la inicialización esté completada, debe configurar los datos adicionales de la venta minorista. A continuación se incluyen algunos ejemplos:

-   Parámetros comerciales
-   Parámetros del Programador de tareas Retail
-   Canales comerciales
-   Cajas registradoras y dispositivos
-   Varios



