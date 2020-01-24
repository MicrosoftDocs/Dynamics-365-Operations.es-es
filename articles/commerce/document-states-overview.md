---
title: Estados y ciclo de vida de documentos
description: En este tema se tratan los diversos estados de documentos de elementos de página en Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: edb81efc45fc5e7eed32cb7d9b8fda5ade987dd4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914896"
---
# <a name="document-states-and-lifecycle"></a>Estados y ciclo de vida de documentos

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los diversos estados de documentos de elementos de página en Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Descripciones de estado de documento

El tema [Elementos de página](page-elements-overview.md) muestra diversos tipos de documentos en el sistema de gestión de contenidos (CMS). Estos tipos de documento pueden tener varios estados en la herramienta de creación. Los estados de documentos ayudan a evitar conflictos de datos y a aplicar el control de versiones. Determinan quién puede cambiar los documentos, cuándo se pueden cambiar los documentos y cuándo se pueden ver los cambios por otras personas.

En la tabla siguiente se muestran los posibles estados de documentos de elementos de página en Commerce.

| Estado del documento | Descripción |
|---|---|
| Desprotegido | Si un artículo de CMS se desprotege para usted, no lo podrán editar otros usuarios del sistema autenticados. Los cambios que realice al artículo solo serán visibles para usted. |
| Protegido | Cuando se protege un artículo de CMS, todos los cambios son visibles para otros usuarios del sistema autenticados y dichos usuarios pueden desproteger a continuación el artículo y editarlo. Cada protección crea un registro de versión de documento en el historial del artículo. |
| Publicada | Cuando se publica un artículo de CMS, se envía a su sitio activo y usuarios externos no autenticados pueden detectarlo en Internet. Los artículos se pueden publicar solo si se han protegido. |
| Guardado | Los cambios realizados en un artículo de CMS desprotegido se pueden guardar en el CMS antes de que el artículo se proteja o se publique. Estos cambios guardados no son visibles para otros usuarios del sistema autenticados hasta que el artículo se protege. No están visibles para usuarios externos hasta que se publica el artículo. |
| Desprotección descartada | Cuando se descarta un artículo de CMS desprotegido, se eliminan todos los cambios guardados y el artículo se revierte a la versión que se protegió más recientemente. |

## <a name="additional-resources"></a>Recursos adicionales

[Métodos para agregar contenido](add-manage-content.md)

[Glosario del modelo de página](page-elements-overview.md)

[Trabajar con grupos de publicación](publish-groups.md)

[Trabajar con módulos](work-with-modules.md)

[Trabajar con fragmentos](work-with-fragments.md)

[Visión general de plantillas y diseños](templates-layouts-overview.md)

[Personalizar navegación del sitio](customize-site-navigation.md)
