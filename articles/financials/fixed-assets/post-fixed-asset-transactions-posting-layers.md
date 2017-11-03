---
title: Registrar las transacciones de activos fijos para registrar capas
description: "Este artículo ofrece una visión general de la funcionalidad de la capa de registro para las transacciones de activos fijos."
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 10e7fc67f8f13a6363b4359fd1b7684f1b80675e
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Registrar las transacciones de activos fijos para registrar capas

[!include[banner](../includes/banner.md)]


Este artículo ofrece una visión general de la funcionalidad de la capa de registro para las transacciones de activos fijos.

Un activo fijo se deprecia de distintas formas y para distintos fines. La depreciación relacionada con los impuestos se calcula usando las reglas actuales de impuestos para lograr la depreciación más alta posible antes de los impuestos, pero la depreciación a efectos de notificación se calcula de acuerdo con los estándares y leyes contables. Los distintos tipos de depreciación se calculan y registran independientemente en las capas de registro.

Cada libro vinculado a un activo fijo se configura para una capa de registro concreta que tiene un objetivo de depreciación general. Existen diez capas de registro: Actual, operaciones, Impuesto y siete niveles personalizados. También puede deshabilitar el registro del libro en la contabilidad general configurando el campo Registrar en el libro mayora No. El campo de Capa de registro se establece automáticamente como Ninguno. Normalmente, los libros que no se registran en la contabilidad general se usan para fines de informes tributarios. Este método proporciona flexibilidad adicional para eliminar las transacciones históricas para el libro de activos, ya que no se han asignado a la contabilidad general.

Los diarios de activos se definen mediante la página de Nombres de diario en Contabilidad general > Configuración del diario > Nombres de diario. Cada diario en el que puede registrar las depreciaciones se define por su nombre de diario para una capa de registro únicamente. La capa de registro del diario no se puede cambiar. Esta restricción permite garantizar que las transacciones de cada capa de registro se mantengan aparte. Se debe crear un nombre de diario como mínimo para cada capa de registro. Si utiliza libros que no se registran en la contabilidad general, también deberá crear un diario en el que la capa de registro se establezca en Ninguno.

Puede especificar las cuentas contables para las transacciones de activos fijos en la página de Perfiles de contabilización de activos fijos. Para cada perfil de registro, debe seleccionar el tipo de transacción y el libro correspondiente, y después designar las cuentas contables. Configurar un registro del perfil de contabilización para cada libro que se envía a la contabilidad general.

> [!NOTE] 
> El uso de libros derivados le permite registrar transacciones para distintas capas de registro simultáneamente. Puede crear transacciones del libro principal en un diario con la capa de registro correspondiente a la capa de registro del libro. Durante el registro, las transacciones derivadas del libro se registran en sus capas de registro adecuadas.

Para obtener más información, consulte [Libros derivados](derived-books.md) y [Registro con los libros derivados](post-derived-value-models.md).




