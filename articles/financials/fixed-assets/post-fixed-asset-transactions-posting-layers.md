---
title: Registrar las transacciones de activos fijos para registrar capas
description: Este artículo ofrece una visión general de la funcionalidad de la capa de registro para las transacciones de activos fijos.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ab5adfdec259207898d25778e4e3bbbaebb452f1
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840274"
---
# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Registrar las transacciones de activos fijos para registrar capas

[!include [banner](../includes/banner.md)]

Este artículo ofrece una visión general de la funcionalidad de la capa de registro para las transacciones de activos fijos.

Un activo fijo se deprecia de distintas formas y para distintos fines. La depreciación relacionada con los impuestos se calcula usando las reglas actuales de impuestos para lograr la depreciación más alta posible antes de los impuestos, pero la depreciación a efectos de notificación se calcula de acuerdo con los estándares y leyes contables. Los distintos tipos de depreciación se calculan y registran independientemente en las capas de registro.

Cada libro vinculado a un activo fijo se configura para una capa de registro concreta que tiene un objetivo de depreciación general. Existen diez capas de registro: Actual, operaciones, Impuesto y siete niveles personalizados. También puede deshabilitar el registro del libro en la contabilidad general configurando el campo Registrar en el libro mayora No. El campo de Capa de registro se establece automáticamente como Ninguno. Normalmente, los libros que no se registran en la contabilidad general se usan para fines de informes tributarios. Este método proporciona flexibilidad adicional para eliminar las transacciones históricas para el libro de activos, ya que no se han asignado a la contabilidad general.

Los diarios de activos se definen mediante la página de Nombres de diario en Contabilidad general > Configuración del diario > Nombres de diario. Cada diario en el que puede registrar las depreciaciones se define por su nombre de diario para una capa de registro únicamente. La capa de registro del diario no se puede cambiar. Esta restricción permite garantizar que las transacciones de cada capa de registro se mantengan aparte. Se debe crear un nombre de diario como mínimo para cada capa de registro. Si utiliza libros que no se registran en la contabilidad general, también deberá crear un diario en el que la capa de registro se establezca en Ninguno.

Puede especificar las cuentas contables para las transacciones de activos fijos en la página de Perfiles de contabilización de activos fijos. Para cada perfil de registro, debe seleccionar el tipo de transacción y el libro correspondiente, y después designar las cuentas contables. Configurar un registro del perfil de contabilización para cada libro que se envía a la contabilidad general.

> [!NOTE] 
> El uso de libros derivados le permite registrar transacciones para distintas capas de registro simultáneamente. Puede crear transacciones del libro principal en un diario con la capa de registro correspondiente a la capa de registro del libro. Durante el registro, las transacciones derivadas del libro se registran en sus capas de registro adecuadas.

Para obtener más información, consulte [Libros derivados](derived-books.md) y [Registro con los libros derivados](post-derived-value-models.md).



