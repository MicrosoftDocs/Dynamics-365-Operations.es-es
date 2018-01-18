---
title: "Configuración de selecciones"
description: "Este artículo describe qué es una selección y explica cómo configurar selecciones en Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15811
ms.assetid: d2580048-e798-4b33-85f9-d1bad7d262fc
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 91713a4492ad82520f7dde611c17a5ea168ed80d
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-assortments"></a>Configuración de selecciones

[!include[banner](includes/banner.md)]


Este artículo describe qué es una selección y explica cómo configurar selecciones en Microsoft Dynamics 365 for Retail.

Una selección es una colección de productos relacionados que se asigna a un canal comercial, como una tienda física o en línea. Las selecciones se usan para identificar los productos disponibles en cada tienda. Una selección puede incluir categorías de productos. Por lo tanto, todos los productos asignados a una categoría específica se incluyen en la selección. Una selección también puede incluir productos específicos y variantes específicas de producto. Al configurar una selección, puede asignar miles de productos a los canales comerciales al mismo tiempo, en cualquier combinación que las tiendas requieran. Puede configurar tantas selecciones de producto como sea necesario. Cada producto se puede incluir en una o varias selecciones y cada selección se puede asignar a uno o varios canales comerciales. Por ejemplo, puede definir una selección que incluya un conjunto básico de productos. Todas las tiendas reciben esta selección. A continuación, puede definir otra selección que incluya solo equipamiento deportivo en gran volumen. Solo sus tiendas más grandes reciben esta selección. En el diagrama siguiente se muestra cómo se pueden asignar los productos a selecciones y cómo se pueden asignar las selecciones a los canales de venta. ![Relaciones de selecciones de productos](./media/assortments_relationship.gif)

## <a name="prerequisites"></a>Requisitos previos
Antes de configurar una selección y asignarla a un canal comercial, debe completar las siguientes tareas.

| Tarea                              | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar un canal comercial.          | Los canales de venta representan una tienda física, una tienda en línea o un mercado en línea. Debe configurar al menos un canal comercial y configurar las opciones para la tienda. Las selecciones se asignan a las tiendas para identificar los productos que contiene una tienda concreta.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Cree una jerarquía organizativa. | Después de configurar los canales comerciales para la organización, debe configurar una jerarquía organizativa comercial que represente la estructura organizativa de los canales comerciales. Una jerarquía organizativa se puede usar para selecciones, reabastecimientos e informes. Al agregar canales comerciales a una jerarquía organizativa, puede asignar selecciones a grupos de tiendas. En lugar de asignar la selección individualmente a cada tienda, la asigna al nodo de alto nivel de la organización. A continuación, siempre que se agregue un canal comercial nuevo al nodo de alto nivel de la organización, ese canal comercial heredará automáticamente cualquier selección asignada al nodo de alto nivel de la organización. Puede asignar selecciones solo a los canales de venta que se incluyan en una jerarquía organizativa que tenga asignado el propósito **Selección comercial**. |
| Defina productos.                  | Para poder agregar productos a una selección, debe agregarlos a Microsoft Dynamics 365 for Retail. Puede agregar los productos manualmente, o bien importarlos de un proveedor. Después de agregar los productos, debe liberarlos para una entidad jurídica. Solo los productos liberados para una entidad jurídica pueden estar disponibles para los canales comerciales. Los productos que aún no se han liberado para una entidad jurídica se pueden agregar a una selección y la selección se puede aprobar. No obstante, los productos no estarán disponibles en los canales de venta hasta que se liberen para una entidad jurídica.                                                                                                                                                                                                                                                                                     |
| Configure una jerarquía de categoría.      | Al crear productos comerciales, puede agruparlos y categorizarlos mediante la jerarquía de categoría. Puede crear una jerarquía principal para agrupar y categorizar todos los productos que se distribuyen a través de canales comerciales. También puede crear jerarquías de categoría independientes y complementarias para agrupar o categorizar los productos con fines especiales, como promociones o selecciones. Al usar jerarquías de categoría, puede asignar todos los productos de una categoría específica a una selección. Todos los productos agregados a la categoría incluida en la selección se incluyen automáticamente en la selección. A continuación, la próxima vez que se ejecute el programador de selección comercial, estos productos estarán disponibles en canales comerciales asignados a la selección.                                            |

## <a name="setting-up-an-assortment"></a>Configuración de una selección
Después de completar los requisitos previos, puede crear una selección y asignarla a los canales comerciales. Para configurar una selección, debe completar las tareas siguientes.

1.  Crear una selección o copiar una existente.
2.  Seleccionar los canales comerciales o grupos de alto nivel de canales comerciales a los que se aplica la selección.
3.  Agregar categorías de productos, productos individuales o variantes de producto a la selección. Puede incluir todos los productos de una categoría específica o puede excluir los productos seleccionados de una categoría incluida en la selección.
4.  Publicar la selección. Al publicar una selección, se ejecuta automáticamente el programador de selecciones comerciales. Este proceso genera la lista de productos. Al completar el proceso, estos productos estarán disponibles en los canales comerciales asignados a la selección de productos. Si se realizan cambios en una selección publicada o en los canales comerciales asignados a la selección, es necesario actualizar la selección. Para actualizar la selección al realizar cambios, puede ejecutar el programador de selección comercial como trabajo por lotes.





