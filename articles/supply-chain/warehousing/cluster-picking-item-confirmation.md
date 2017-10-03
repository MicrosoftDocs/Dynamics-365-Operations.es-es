---
title: "Confirmación de producto para picking de clústeres"
description: "Este tema describe cómo se establece la comprobación de artículos junto con el picking en clúster."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 1caa8b70f1006baae6f377b0ba69ca977d6af0bd
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017

---

[!include[banner](../includes/banner.md)]

# <a name="product-confirmation-for-cluster-picking"></a>Confirmación de producto para picking de clústeres
El picking en clúster le permite elegir los artículos para varios pedidos al mismo tiempo. Cuando se aplica el picking en clúster, es esencial la confirmación del artículo para comprobar que los artículos se agregan a los clústeres. Puede comprobar los artículos del picking en clúster durante el proceso de picking en clúster.

## <a name="where-it-applies"></a>Dónde se aplica
La comprobación de artículos para trabajos de picking en clúster funcional del mismo modo que cuando se comprueban artículos en un proceso que no es de picking en clúster. La configuración se basa en la configuración del código de barras del producto.

## <a name="set-up-item-verification-with-cluster-picking"></a>Establecer la comprobación de artículos con picking en clúster
1.  En un elemento de menú del dispositivo móvil, abra el formulario de configuración para la confirmación del trabajo: **Gestión de almacenes** > **Gestión de almacenes** > **Configuración** > **Dispositivo móvil** > **Elementos de menú del dispositivo móvil**.
2.  En el elemento de menú del dispositivo móvil, abra **Configuración de la confirmación de trabajo**.

| Opción        | Descripción   | 
| ------------- | ------------- |
|Confirmación del producto | Permite que se compruebe cada pieza de inventario desde el dispositivo móvil cuando se escanea.|

