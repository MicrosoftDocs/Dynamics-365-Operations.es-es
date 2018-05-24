---
title: "Reglas de configuración"
description: "Este artículo ofrece información general relativa a las reglas de configuración. Las reglas de configuración definen relaciones entre artículos de una lista de materiales (L. MAT) para los productos que usan la tecnología de configuración basada en dimensiones."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 8bbec5a0e6b6d9c3001fc36c7bdd053f92112fea
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="configuration-rules"></a>Reglas de configuración

[!include [banner](../includes/banner.md)]

Este artículo ofrece información general relativa a las reglas de configuración. Las reglas de configuración definen relaciones entre artículos de una lista de materiales (L. MAT) para los productos que usan la tecnología de configuración basada en dimensiones.

Las reglas de configuración están disponibles si define modelos de configuración basada en dimensiones. Las reglas de configuración se usan para hacer cumplir o prohibir combinaciones específicas de artículos en una lista de materiales (L. MAT.). Después de crear una L. MAT. y asignar los artículos relevantes a los grupos de configuración respectivos, pueden definirse una o más reglas de configuración. Si dos artículos deben ir juntos, se usará el operador **Seleccionar** para garantizar la inclusión. Si dos artículos se excluyen mutuamente, se usa el operador **Anular selección** para garantizar la exclusión.  

**Nota**: esta información solo se aplica a los productos maestros que utilizan la tecnología de configuración basada en dimensiones.  

Las configuraciones existentes no se ven afectadas por los cambios posteriores en las reglas de configuración. No obstante, es importante establecer las reglas antes de definir una nueva configuración y comprobarlas si cree que las reglas se han cambiado.  

**Nota**: para el método **Seleccionar**, el grupo de configuración derivado, el número de artículo y la configuración se seleccionan automáticamente. Para el método **Anular selección**, el grupo de configuración derivado, el número de artículo y la configuración no se pueden seleccionar.

<a name="additional-resources"></a>Recursos adicionales
--------

[Configuración de producto basada en dimensiones](dimension-based-product-configuration.md)




