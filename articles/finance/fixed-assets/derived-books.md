---
title: Libros derivados
description: Este artículo proporciona información general de la función del libro derivado.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee7471e952409c7848015d2af07738e034e0d222
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241155"
---
# <a name="derived-books"></a>Libros derivados

[!include [banner](../includes/banner.md)]

Este artículo proporciona información general de la función del libro derivado.

El propósito de los libros derivados es simplificar el registro de transacciones de libro de activos fijos que se planifican para intervalos regulares.  Debe elegir un libro como libro principal. Este libro es el que se usa normalmente para la depreciación contable. A continuación, vincúlelo a otros libros que se configuran para registrar transacciones en los mismos intervalos que el libro principal. Los libros de depreciación fiscal se suelen configurar como libros derivados. 

Las transacciones que se configuran habitualmente para registrar los libros derivados son las adquisiciones, los ajustes de adquisición y las cancelaciones. 

## <a name="example"></a>Ejemplo

El libro B y el C se configuran como libros derivados para el libro A para el tipo de transacción de adquisición. En el libro A, introduzca una transacción de adquisición de 1.500,00 para el activo 123. 

Una vez registrada la transacción, se genera una transacción de adquisición y se registra en el activo 123 para el libro B y en el activo 123 para el libro C de 1.500,00. Cuando se preparan las transacciones del libro principal para registrarlas en el diario de activos fijos, también puede ver y modificar las transacciones de libros derivados. Si prepara las transacciones del libro principal en otro diario, no se mostrarán las transacciones del valor derivado. Sin embargo, se registrarán en las cuentas y capas de registro adecuadas cuando registre las transacciones del libro principal.

> [!NOTE]                                                                                                                               
> Los libros que se configuran para registrar transacciones en intervalos distintos a los intervalos del libro principal, se deben vincular al activo fijo como libros independientes y no como libros derivados.  

Para obtener más información, consulte [Registrar con libros derivados](post-derived-value-models.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]