---
title: Volver a utilizar configuraciones de producto
description: Puede especificar que desee volver a usar automáticamente una configuración existente para un producto. A continuación, cuando un usuario completa una sesión de configuración, el sistema comprueba si ya existe una configuración que coincide con las selecciones del usuario. Si se encuentra una configuración que coincide, se vuelven a usar el id. de configuración, la lista de materiales (L. MAT) correspondiente y la ruta.
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb4c997e8cf8b2456ffe12a552577902da171cc1
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189853"
---
# <a name="reuse-product-configurations"></a>Volver a utilizar configuraciones de producto

[!include [banner](../includes/banner.md)]

Puede especificar que desee volver a usar automáticamente una configuración existente para un producto. A continuación, cuando un usuario completa una sesión de configuración, el sistema comprueba si ya existe una configuración que coincide con las selecciones del usuario. Si se encuentra una configuración que coincide, se vuelven a usar el id. de configuración, la lista de materiales (L. MAT) correspondiente y la ruta.

## <a name="requirements-for-reusing-configurations"></a>Requisitos para volver a usar las configuraciones

Para habilitar las configuraciones que se reutilizarán, debe especificar la siguiente información para componentes y atributos en la página de **Detalles del modelo de configuración de productos**:

-   **Componentes y subcomponentes**: en la ficha desplegable **General** del campo **Reutilizar configuraciones** seleccione **Sí**.
-   **Atributos**: en la ficha desplegable **Atributos**, seleccione la opción **Incluir en la reutilización**. La opción se muestra solo cuando el componente relacionado se habilita para un nuevo uso. Si no selecciona ningún atributo para un nuevo uso, la configuración siempre se vuelve a usar, independientemente de las selecciones del usuario durante una sesión de configuración. Los atributos de valor de la configuración existente deben coincidir con las selecciones del usuario. Por ejemplo, si el usuario selecciona como color el **Azul** durante una sesión de configuración, el sistema comprueba si una configuración existente del componente tiene el color azul.

## <a name="resetting-configuration-reuse"></a>Restablecer la reutilización de la configuración
Cuando restablece la reutilización de la configuración, las configuraciones anteriormente creadas ya no se tienen en cuenta. Es posible que desee restablecer la reutilización de la configuración si se ha cambiado el BOM o la ruta pero no se modificaron ningún atributo relacionado. Se restablece la reutilización de la configuración en la ficha desplegable **General** del componente.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]