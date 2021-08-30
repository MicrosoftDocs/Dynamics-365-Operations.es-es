---
title: Conjuntos de dimensiones financieras
description: Este tema describe los conjuntos de dimensiones financieras y proporciona algunos consejos para optimizar su uso.
author: yukonpeegs
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 415a41100cc5be740f064d52598cd256c0aa2ae1d45473c8039bdc6e22381b3c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739987"
---
# <a name="financial-dimension-sets"></a>Conjuntos de dimensiones financieras

[!include [banner](../includes/banner.md)]

Este tema describe los conjuntos de dimensiones financieras y proporciona algunos consejos para optimizar su uso.

Un conjunto de dimensiones es una lista ordenada de dimensiones financieras que se puede utilizar para resumir los datos del libro mayor de una manera definida por el usuario. Un uso principal de los conjuntos de dimensiones es definir un balance de prueba.

El único conjunto de dimensiones estándar es el conjunto de dimensiones que contiene solo la cuenta principal.

Usa la página **Conjuntos de dimensiones financieras** para crear y gestionar conjuntos de dimensiones financieras.

## <a name="dimension-set-balances"></a>Saldos de conjuntos de dimensiones

Un conjunto de dimensiones puede tener saldos basados en sus dimensiones financieras. Los saldos existen en el Libro mayor y se basan en la definición del conjunto de dimensiones. Los saldos se resumen a partir de los datos del libro mayor para ayudar a mejorar el rendimiento cuando se recuperan (por ejemplo, cuando se genera un saldo de prueba).

## <a name="create-balances"></a>Crear saldos

Utilice el botón **Crear saldos** para inicializar los saldos de un conjunto de dimensiones que actualmente no tiene saldos.

> [!NOTE]
> Le recomendamos que limite el número de conjuntos de dimensiones que tienen saldos, porque las actualizaciones de saldos afectan a todas las actividades de contabilización del Libro mayor.

## <a name="update-balances"></a>Actualizar saldos

Utilice **Actualizar saldos** para incluir la última actividad de contabilización del Libro mayor en los saldos. Las actualizaciones de equilibrio son operaciones ligeras. Deben procesar solo la actividad de contabilización del Libro mayor que se ha producido desde la última actualización.

> [!NOTE]
> La visualización del balance de prueba fuerza una actualización, para garantizar que los saldos que se muestran sean actuales. Considere la posibilidad de utilizar un trabajo por lotes recurrente para que las actualizaciones de los conjuntos de dimensiones que utiliza con más frecuencia sean rápidas. De esta forma, ayuda a minimizar el tiempo que deben esperar los usuarios del balance de prueba.

## <a name="rebuild-balances"></a>Volver a elaborar saldos

Utilice el botón **Reconstruir saldos** para recrear los saldos desde cero. De esta manera, ayuda a garantizar que coincidan con los datos del Libro mayor. La reconstrucción de los saldos requiere mucho procesamiento y, por lo general, no debería ser necesaria.

> [!NOTE]
> Si tiene un escenario que regularmente requiere una reconstrucción de saldos, le recomendamos que se comunique con el servicio de atención al cliente. El servicio de atención al cliente puede ayudarlo a determinar por qué los saldos no coinciden con los datos del Libro mayor.

## <a name="clear-balances"></a>Borrar saldos

Utilice **Saldos claros** para eliminar los saldos y detener cualquier actualización adicional. El conjunto de dimensiones ya no tendrá un impacto en las actividades de contabilización del libro mayor.

Para obtener más información, consulte [Dimensiones financieras](financial-dimensions.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
