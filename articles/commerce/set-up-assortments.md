---
title: Configuración de selecciones
description: Este artículo describe qué es una selección y explica cómo configurar selecciones en Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.custom: 15811
ms.assetid: d2580048-e798-4b33-85f9-d1bad7d262fc
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 32edf6534716236706847556a14b951f18ef40ae
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969835"
---
# <a name="set-up-assortments"></a>Configurar selecciones

[!include [banner](includes/banner.md)]

Este artículo describe qué es una selección y explica cómo configurar selecciones en Dynamics 365 Commerce.

Una selección es una colección de productos relacionados que se asigna a un canal de Commerce, como una tienda física o en línea. Las selecciones se usan para identificar los productos disponibles en cada tienda. Una selección puede incluir categorías de productos. Por lo tanto, todos los productos asignados a una categoría específica se incluyen en la selección. Una selección también puede incluir productos específicos y variantes específicas de producto. Al configurar una selección, puede asignar miles de productos a los canales al mismo tiempo, en cualquier combinación que las tiendas requieran. Puede configurar tantas selecciones de producto como sea necesario. Cada producto se puede incluir en una o varias selecciones y cada selección se puede asignar a uno o varios canales. Por ejemplo, puede definir una selección que incluya un conjunto básico de productos. Todas las tiendas reciben esta selección. A continuación, puede definir otra selección que incluya solo equipamiento deportivo en gran volumen. Solo sus tiendas más grandes reciben esta selección. En el diagrama siguiente se muestra cómo se pueden asignar los productos a selecciones y cómo se pueden asignar las selecciones a los canales.

![Relaciones de selecciones de productos](./media/assortments_relationship.gif)

## <a name="prerequisites"></a>Requisitos previos

Antes de configurar una selección y asignarla a un canal de Commerce, debe completar las siguientes tareas.

| Tarea                              | Descripción |
|-----------------------------------|-------------|
| Configure un canal.          | Los canales representan una tienda física, una tienda en línea o un mercado en línea. Debe configurar al menos un canal y configurar las opciones para la tienda. Las selecciones se asignan a las tiendas para identificar los productos que contiene una tienda concreta. |
| Cree una jerarquía organizativa. | Después de configurar los canales de Commerce para su organización, debe configurar una jerarquía organizativa que represente la estructura organizativa de los canales. Una jerarquía organizativa se puede usar para selecciones, reabastecimientos e informes. Al agregar canales a una jerarquía organizativa, puede asignar selecciones a grupos de tiendas. En lugar de asignar la selección individualmente a cada tienda, la asigna al nodo de alto nivel de la organización. A continuación, siempre que se agregue un canal nuevo al nodo de alto nivel de la organización, ese canal heredará automáticamente cualquier selección asignada al nodo de alto nivel de la organización. Puede asignar selecciones solo a los canales que se incluyan en una jerarquía organizativa que tenga asignado el propósito **Selección de Commerce**. |
| Defina productos.                  | Para poder agregar productos a una selección, debe agregarlos a Commerce. Puede agregar los productos manualmente, o bien importarlos de un proveedor. Después de agregar los productos, debe liberarlos para una entidad jurídica. Solo los productos liberados para una entidad jurídica pueden estar disponibles para los canales. Los productos que aún no se han liberado para una entidad jurídica se pueden agregar a una selección y la selección se puede aprobar. No obstante, los productos no estarán disponibles en los canales hasta que se liberen para una entidad jurídica. |
| Configure una jerarquía de categoría.      | Al crear productos de Commerce, puede agruparlos y categorizarlos mediante la jerarquía de categoría. Puede crear una jerarquía principal para agrupar y categorizar todos los productos que se distribuyen a través de canales. También puede crear jerarquías de categoría independientes y complementarias para agrupar o categorizar los productos con fines especiales, como promociones o selecciones. Al usar jerarquías de categoría, puede asignar todos los productos de una categoría específica a una selección. Todos los productos agregados a la categoría incluida en la selección se incluyen automáticamente en la selección. A continuación, la próxima vez que se ejecute el programador de selección de Commerce, estos productos estarán disponibles en canales asignados a la selección. |

## <a name="setting-up-an-assortment"></a>Configuración de una selección

Después de completar los requisitos previos, puede crear una selección y asignarla a los canales. Para configurar una selección, debe completar las tareas siguientes.

1. Crear una selección o copiar una existente.
2. Seleccionar los canales o grupos de alto nivel de canales a los que se aplica la selección.
3. Agregar categorías de productos, productos individuales o variantes de producto a la selección. Puede incluir todos los productos de una categoría específica o puede excluir los productos seleccionados de una categoría incluida en la selección.
4. Publicar la selección. Al publicar una selección, se ejecuta automáticamente el programador de selecciones. Este proceso genera la lista de productos. Al completar el proceso, estos productos estarán disponibles en los canales asignados a la selección de productos. Si se realizan cambios en una selección publicada o en los canales asignados a la selección, es necesario actualizar la selección. Para actualizar la selección al realizar cambios, puede ejecutar el programador de selecciones como trabajo por lotes.
