---
title: Definición de descuentos específicos de un canal
description: Los minoristas establecen a menudo distintos descuentos en diferentes canales. Este artículo revisa los conceptos que necesita conocer para crear un descuento para un canal específico.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.industry: Retail
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
ms.openlocfilehash: f426503a6897a73010b77082f4277b65545bfcc3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273564"
---
# <a name="define-channel-specific-discounts"></a>Definir descuentos específicos de un canal

[!include [banner](includes/banner.md)]

Este artículo revisa los conceptos que necesita conocer para crear un descuento para un canal específico.

## <a name="channel-specific-discounts"></a>Descuentos específicos de un canal

Los minoristas ofrecen a menudo distintos descuentos en diferentes canales. Esto se puede realizar para responder a condiciones empresariales locales o para afrontar a la competencia.

Commerce usa grupos de precios para definir descuentos específicos de canal. Los grupos de precios se pueden asignar a una o más de las entidades siguientes: canales, catálogos, afiliaciones y programas de fidelidad. Este artículo describe los canales, pero los mismos conceptos se aplican a los descuentos de catálogo, descuentos de afiliaciones y los descuentos por fidelidad.

## <a name="price-groups"></a>Grupos de precios

[![Grupos de precio.](./media/price-groups-1024x608.png)](./media/price-groups.png)

En el diagrama anterior se muestra la relación entre las entidades que pueden estar incluidas en una transacción (canal, catálogo, afiliación, cliente o tarjeta de fidelización) y los distintos tipos de descuento que pueden configurarse. Todas las transacciones se producen en un canal, por lo que se garantiza la presencia del canal en una transacción. Las entidades restantes son opcionales. En cada página de datos maestros hay un vínculo a una página de grupos de precios relacionada donde se pueden ver y agregar grupos de precios según sea necesario. El grupo de precios se usa para relacionar cuatro tipos diferentes de entidades a los descuentos, los ajustes de precios y los acuerdos comerciales. Se recomienda planear una estrategia para nombrar a los grupos de precios con objeto de tenerlos organizados. Una opción sería usar una letra o un prefijo o un sufijo numérico para distinguir entre los diferentes tipos. Por ejemplo, 1-xxxxx para grupos de precios de canal y 2-xxxxx para grupos de precios de catálogo. Existen cuatro páginas de consulta que se centran en cada una de las entidades de Commerce que pueden tener descuentos asociados.

- **Grupos de precios de canal**: esta página muestra una lista de canales y descuentos vinculados conjuntamente para cada grupo de precios.
- **Grupos de precios de catálogo**: esta página muestra una lista de catálogos y descuentos vinculados conjuntamente para cada grupo de precios.
- **Grupos de precios de fidelización**: esta página muestra una lista de programas de fidelización y descuentos vinculados conjuntamente para cada grupo de precios.
- **Grupos de precios de afiliación**: esta página muestra una lista de afiliaciones y descuentos vinculados conjuntamente para cada grupo de precios.

## <a name="example-channel-discount-set-up"></a>Ejemplo de configuración de descuento por canal

En el ejemplo siguiente se muestran las tareas implicadas en la configuración de un descuento por canal.

1. Para este ejemplo puede tener un canal llamado **Houston** y va a crear un nuevo descuento llamado **Vuelta al cole**.
2. Dado que la estrategia de precios y descuentos incluye la posibilidad de descuentos por canal, siempre creará un grupo de precios específico para un canal al crear un canal.
3. Tiene el grupo de precios **Houston-PG** asignado al canal **Houston**.
4. Después de crear el nuevo descuento **Vuelta al cole**, debe hacer clic en **Grupos de precios**, en la parte superior de la página **Descuento**. Se abre la página **Grupos de precios de descuento**. A continuación, haga clic en **Nuevo** y seleccione el grupo de precios **Houston-PG**.
5. Ahora puede habilitar el descuento y transferirlo al canal.

## <a name="additional-resources"></a>Recursos adicionales

[Ajustes de precios y descuentos](price-adjustments-discounts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
