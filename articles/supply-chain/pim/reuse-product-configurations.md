---
title: Volver a utilizar configuraciones de producto
description: Puede especificar que desee volver a usar automáticamente una configuración existente para un producto. A continuación, cuando un usuario completa una sesión de configuración, el sistema comprueba si ya existe una configuración que coincide con las selecciones del usuario. Si se encuentra una configuración que coincide, se vuelven a usar el id. de configuración, la lista de materiales (L. MAT) correspondiente y la ruta.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: be153fd6376d59bee93f432d26963a2937436666
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999765"
---
# <a name="reuse-product-configurations"></a>Volver a utilizar configuraciones de producto

[!include [banner](../includes/banner.md)]

Puede especificar que desee volver a usar automáticamente una configuración existente para un producto. A continuación, cuando un usuario completa una sesión de configuración, el sistema comprueba si ya existe una configuración que coincide con las selecciones del usuario. Si se encuentra una configuración que coincide, se vuelven a usar el id. de configuración, la lista de materiales (L. MAT) correspondiente y la ruta.

<a name="requirements-for-reusing-configurations"></a>Requisitos para volver a usar las configuraciones
---------------------------------------

Para habilitar las configuraciones que se reutilizarán, debe especificar la siguiente información para componentes y atributos en la página de **Detalles del modelo de configuración de productos**:

-   **Componentes y subcomponentes**: en la ficha desplegable **General** del campo **Reutilizar configuraciones** seleccione **Sí**.
-   **Atributos**: en la ficha desplegable **Atributos**, seleccione la opción **Incluir en la reutilización**. La opción se muestra solo cuando el componente relacionado se habilita para un nuevo uso. Si no selecciona ningún atributo para un nuevo uso, la configuración siempre se vuelve a usar, independientemente de las selecciones del usuario durante una sesión de configuración. Los atributos de valor de la configuración existente deben coincidir con las selecciones del usuario. Por ejemplo, si el usuario selecciona como color el **Azul** durante una sesión de configuración, el sistema comprueba si una configuración existente del componente tiene el color azul.

## <a name="resetting-configuration-reuse"></a>Restablecer la reutilización de la configuración
Cuando restablece la reutilización de la configuración, las configuraciones anteriormente creadas ya no se tienen en cuenta. Es posible que desee restablecer la reutilización de la configuración si se ha cambiado el BOM o la ruta pero no se modificaron ningún atributo relacionado. Se restablece la reutilización de la configuración en la ficha desplegable **General** del componente.



