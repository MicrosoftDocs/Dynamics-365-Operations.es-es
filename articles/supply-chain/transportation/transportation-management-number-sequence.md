---
title: Secuencia numérica de administración de transporte
description: Este artículo describe cómo configurar secuencias numéricas para la gestión del transporte.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a1d3e1a36164215b70d88b10beb35748be2e23b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847828"
---
# <a name="transportation-management-number-sequence"></a>Secuencia numérica de administración de transporte

[!include [banner](../includes/banner.md)]

Utilice la página **Secuencias numéricas** del módulo de gestión de transporte para configurar varios números profesionales. Los transportistas utilizan los números profesionales para organizar y realizar un seguimiento del progreso de cada envío.

## <a name="create-a-number-sequence-for-a-pro-number"></a>Crear una secuencia numérica para un número profesional

Para crear una secuencia numérica para un número profesional, haga lo siguiente:

1. Vaya a **Administración de transporte \> Configuración \> Transportistas \> Secuencias numéricas**.
1. Seleccione **Nuevo** para crear una nueva secuencia numérica.
1. Escriba un identificador único y un nombre descriptivo para la secuencia numérica.
1. En el campo **Tipo de secuencia numérica**, *Número profesional* es la única opción.
1. En el campo **Comprobar dígito**, *Comprobar dígito* es la única opción y está configurada como motor genérico.
1. En la ficha desplegable **Secuencia**, proporciona información sobre la secuencia.
1. Cierre la página.

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a>Vincular una secuencia numérica a un transportista

Para vincular una secuencia numérica a un operador, haga lo siguiente:

1. Vaya a **Administración de transporte \> Configuración \> Transportistas \> Transportistas de envío**.
1. Seleccione un transportista de envío.
1. Seleccione **Editar**.
1. En la ficha desplegable **Visión de conjunto**, seleccione una opción en el campo **Secuencia de números profesional**.
1. Cierre la página.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]