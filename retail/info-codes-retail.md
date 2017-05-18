---
title: "Códigos de información"
description: "Este artículo proporciona información general acerca de códigos de información, grupos de códigos de información y acerca de cómo usarlos."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 22761
ms.assetid: 99877dba-a6e3-4d88-ba0a-ee5913aea17e
ms.search.region: global
ms.search.industry: Retail
ms.author: sijoshi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: aaf02ce5bf3af94dea12344c9bfc5c8e9be7abb9
ms.contentlocale: es-es
ms.lasthandoff: 04/26/2017


---

# <a name="info-codes"></a>Códigos de información

[!include[banner](includes/banner.md)]


Este artículo proporciona información general acerca de códigos de información, grupos de códigos de información y acerca de cómo usarlos.

Los códigos de la información proporcionan una forma de capturar datos en un registro del punto de venta (PDV). Puede utilizar los códigos de información para solicitar al cajero que especifique información durante varias acciones en el PDV, como las ventas del artículo, las devoluciones de artículos o la selección de clientes. Los cajeros pueden seleccionar la entrada de una lista o escribirla como un código, un número, una fecha o texto. Puede asignar códigos de información a acciones de tienda predefinidas, artículos comerciales, métodos de pago, clientes o actividades de punto de venta específicas. Puede usar códigos de información para hacer lo siguiente:
-   Obtener información adicional en el momento de la transacción, tal como un número de vuelo o el motivo de una devolución.
-   Solicitar al cajero de la caja registradora que seleccione productos específicos de una lista de precios.
-   Vincular un subcódigo a un código de información que solicite al cajero de la caja registradora una respuesta cuando lleve a cabo una actividad específica. Por ejemplo, cuando un cliente devuelve un producto, puede solicitar al cajero consultar por qué se devuelve el producto. A continuación puede usar subcódigos para mostrar una lista de motivos entre los que el cajero pueda elegir.
-   Vender un producto como una venta regular, venta con descuento o producto gratuito.
-   Solicitar al cajero que especifique un valor o seleccione uno de una lista de subcódigos al abrir la caja registradora sin realizar una operación de ventas.

## <a name="info-codes-group-in-retail-and-commerce"></a>Grupo de códigos de información en Venta minorista y comercio
En Dynamics 365 for Operations - Retail puede crear grupos de códigos de información. Los grupos de códigos de información agregan flexibilidad al permitirle definir menos códigos de información y después usarlos de maneras más versátiles. Puede usar los grupos de códigos de información de las siguientes formas:
-   Defina menos códigos de información y reutilícelos fácilmente. Los códigos de información que se incluyen en grupos de códigos de información no tienen ninguna dependencia predefinida en otros códigos de información. Puede incluir el mismo código de información de varios grupos de códigos de información y después usar la priorización para presentar los mismos códigos de información en el orden que tiene sentido en cualquier escenario concreto.
-   Vincule códigos de información a otros códigos de información o grupos de códigos de información para recopilar información sobre un producto o una transacción sin tener que definir un código distinto de información o un código de información vinculado para cada situación.

## <a name="info-code-examples"></a>Ejemplos de códigos de información
**Ejemplo 1: Reutilización de códigos de información**: puede vincular códigos de información para que cuando se active un código de la información, se desencadene otro código de la información inmediatamente después de él. Por ejemplo, cuando vende determinados productos, puede solicitar al cajero que pregunte al cliente si desean comprar pilas y una garantía del producto. Para otros productos, puede solicitar al cajero que pregunte al cliente si desean comprar pilas y si puede proporcionarles también su código postal. Si crea códigos de información vinculados para estos casos, debe configurar cada variación del código de información para solicitar al cajero que pida la información correcta. Si usa grupos de códigos de información, los códigos de información comunes, como solicitar baterías, se pueden configurar una vez y después reutilizarlos en varios grupos de código de información. También puede usar la priorización en los grupos de códigos de información para identificar el orden en que se muestran los avisos. **Ejemplo 2: Vinculación de códigos de información a grupos de códigos de información**: cuando vende determinados productos, por ejemplo, dispositivos móviles, desea siempre recopilar un conjunto de información específica, como el número de teléfono, el identificador móvil (IMEI) y el número de serie. Sin embargo, también desea recopilar información distinta para una tableta en comparación con un teléfono móvil. Puede configurar un grupo del códigos de información que incluya los avisos para el número de teléfono, el IMEI y el número de serie, y después vincular el grupo de códigos de información a un código individual de información. Cuando se activa el código de información específico del producto, el grupo de códigos de información puede activarse a continuación para permitirle recopilar los datos comunes sin tener que definir varios conjuntos de códigos de información vinculados para cada dispositivo.

 
-






