---
title: Filtrado mejorado de RCS en el repositorio RCS/Global
description: Este artículo describe capacidades de filtrado mejoradas para el repositorio global de RCS, que se han mejorado para incluir los filtros adicionales.
author: JaneA07
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: a343b9f1af68a727cb2a8d1e390f85e10aab2d39
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901223"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>Opciones de filtrado de RCS mejoradas para encontrar configuraciones en el repositorio RCS/global

[!include [banner](../includes/banner.md)]

Este artículo describe capacidades de filtrado mejoradas para el repositorio global Regulatory Configuration Services (RCS), que se han mejorado para incluir la capacidad de filtrar con los siguientes criterios: 
- **País/región**: basado en los códigos de país ISO  
- Tipos de **Etiquetas** para:
  - Área funcional
  - Área de características
  - Sector 
  - Documento empresarial 

Para facilitar el descubrimiento de configuraciones específicas o relacionadas, puede aplicar filtros, individualmente o en grupos. Por ejemplo, para encontrar un solo tipo de "documentos comerciales configurables" que estén relacionados con las facturas de proveedores, puede aplicar un filtro de **Tipo de documento comercial** para buscar ese tipo de documento. 

[![Sección de filtro para el repositorio global.](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

Puede refinar aún más la búsqueda seleccionando el tipo de documento, por ejemplo, "factura de proveedor" y haciendo clic en **Aplicar filtro**. El siguiente ejemplo muestra los resultados al filtrar en **Tipo de documento comercial** con el tipo de documento agregado. 

[![Filtro aplicado e importación para tipo de documento empresarial.](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

Los resultados filtrados se pueden importar en un repositorio RCS de usuarios o en un entorno de Dynamics 365 Finance, ya sea individualmente o como un conjunto. Para hacer esto, seleccione el grupo de configuraciones y haga clic en **Importar**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]