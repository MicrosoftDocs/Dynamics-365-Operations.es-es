---
title: "Definición de descuentos específicos de un canal"
description: "Los minoristas establecen a menudo distintos descuentos en diferentes canales. Este tema revisa los conceptos que necesita conocer para crear un descuento para un canal específico."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: b2f59db59ea49925c3bb5e1d75beee95191220d0
ms.lasthandoff: 03/31/2017


---

# <a name="define-channel-specific-discounts"></a>Definición de descuentos específicos de un canal

Los minoristas establecen a menudo distintos descuentos en diferentes canales. Este tema revisa los conceptos que necesita conocer para crear un descuento para un canal específico. 

<a name="channel-specific-discounts"></a>Descuentos específicos de un canal
--------------------------

Los minoristas con frecuencia proporcionan una distintos descuentos en varios canales. Esto es se puede hacer para guiar condiciones del mercado locales o para tratar de los minoristas de la competencia.

La ventas al por menor y el comercio de Microsoft Dynamics 365 para las operaciones usa grupos de precios para definir canal- descuentos específicos. Los grupos de precios se pueden asignar a una o más de las entidades siguientes: canales, catálogos, afiliaciones y programas de fidelidad. Este artículo describe los canales, pero los mismos conceptos se aplican a los descuentos de catálogo, descuentos de afiliaciones y los descuentos por fidelidad.

## <a name="price-groups"></a>Grupos de precio
alignnone” width= "640 "de align= de " id= " de\[datos adjuntos\_256084 "\][grupos de precios![] (. /media/price-groups-1024x608.png])(. Vínculos del grupo de precios de /media/price-groups.png) para\[al por menor /caption\]

El diagrama anterior muestra la relación entre las entidades que pueden estar en una transacción (canal, catálogo, afiliación, cliente, tarjeta de fidelización) y los distintos tipos de descuento que se pueden configurar. Todas las transacciones se producen con un canal, por lo que el canal se garantiza para que esté presente en una transacción. Las entidades restantes son opcionales. En cada página de datos maestros hay un vínculo a una página de grupos de precios relacionada donde se pueden ver y agregar grupos de precios según sea necesario. Un grupo de precios que desea relacionar cuatro diferentes tipos de entidades con los descuentos, los ajustes de precios, y los acuerdos comerciales. Es recomendable planear una estrategia para cómo se denominará los grupos de precios para organizados servicio. Una opción sería utilizar una letra o un prefijo o un sufijo del número para distinguir entre los distintos tipos. Por ejemplo, 1 xxxxx para los grupos de precios el canal y 2 xxxxx para los grupos de precios del catálogo. Existen cuatro páginas de consulta que se centran en cada una de las entidades de venta al por menor que pueden tener descuentos asociados.

-   **Grupos de precios de canal comercial **: esta página muestra una lista de canales y descuentos vinculados conjuntamente para cada grupo de precios.
-   **Grupos de precios de catálogo **: esta página muestra una lista de catálogos y descuentos vinculados conjuntamente para cada grupo de precios.
-   **Grupos de precios de fidelización **: esta página muestra una lista de programas de fidelización y descuentos vinculados conjuntamente para cada grupo de precios.
-   **Grupos de precios de afiliación **: esta página muestra una lista de afiliaciones y descuentos vinculados conjuntamente para cada grupo de precios.

## <a name="example-channel-discount-set-up"></a>Ejemplo de configuración de descuento por canal
En el ejemplo siguiente se muestran las tareas implicadas en la configuración de un descuento por canal.

1.  Para este ejemplo puede tener un canal llamado **Houston** y va a crear un nuevo descuento llamado **Vuelta al cole**.
2.  Dado que la estrategia de precios y descuentos incluye la posibilidad de descuentos por canal, siempre creará un grupo de precios específico para un canal al crear un canal.
3.  Tiene el grupo de precios **Houston-PG** asignado al canal **Houston**.
4.  Después de crear el nuevo descuento **Vuelta al cole**, debe hacer clic en **Grupos de precios**, en la parte superior de la página **Descuento**. Se abre la página **Grupos de precios de descuento**. A continuación, haga clic en **Nuevo** y seleccione el grupo de precios **Houston-PG**.
5.  Ahora puede habilitar el descuento y transferirlo al canal.

 

<a name="see-also"></a>Consulte también
--------

[Price adjustments and discounts](price-adjustments-discounts.md)


