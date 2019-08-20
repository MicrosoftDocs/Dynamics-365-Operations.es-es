---
title: Depreciación de activo fijo
description: Este tema proporciona información general de la depreciación de los activos fijos.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1056dadab4294072cc064670f5cfcda239e22e19
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840490"
---
# <a name="fixed-asset-depreciation"></a>Depreciación de activo fijo

[!include [banner](../includes/banner.md)]

Este tema proporciona información general de la depreciación de los activos fijos.

La depreciación es una transacción periódica que reduce normalmente el valor del activo fijo en el balance de situación y que se carga como un gasto en la cuenta de pérdidas y ganancias. Por lo tanto, se usa normalmente una cuenta principal para abonar la depreciación periódica en el balance de situación. Una cuenta de contrapartida es una cuenta en la parte de pérdidas y ganancias del plan contable.

## <a name="depreciation-adjustment"></a>Ajuste de depreciación
Normalmente, solo se registra una corrección en una transacción de depreciación registrada como un ajuste de depreciación. Por lo tanto, la cuenta principal y la cuenta de contrapartida se configuran de la misma forma que las cuentas para depreciación. Un ajuste de depreciación puede ser un importe positivo o negativo, pero la función de la cuenta principal (como una cuenta de balance de situación) y la función de la cuenta de contrapartida (por lo general, una cuenta de pérdidas y ganancias) no se modifica.

## <a name="extraordinary-depreciation"></a>Depreciación extraordinaria
La depreciación extraordinaria funciona como la depreciación básica. Por lo tanto, se usa una cuenta principal para abonar el importe de depreciación al balance y reducir el valor del activo fijo. Una cuenta de contrapartida es una cuenta de pérdidas y ganancias, donde la depreciación calculada para el período fiscal se carga como gasto. 

La depreciación extraordinaria funciona independientemente de la depreciación básica. Al tratar la depreciación extraordinaria como un tipo de transacción individual, puede registrar y notificar la depreciación extraordinaria aparte de la depreciación básica.

## <a name="special-depreciation-allowance"></a>Método de amortización por depreciación especial
Puede utilizar las amortizaciones por depreciación especial para disponer de importes de depreciación adicionales durante el primer año en que un activo se pone en servicio y se deprecia. Los métodos de amortización por depreciación especial se debe realizar antes de cualquier cálculo de depreciación. Dado que los métodos de amortización por depreciación especial a menudo son desconocidos hasta tiempo más tarde en la vida del activo fijo, es mejor usar este tipo de depreciación con un libro que no se registre en la contabilidad general. Puede usar la función periódica de Borrar transacciones no registradas en la contabilidad general para eliminar el historial de transacciones de esos libros. A continuación puede eliminar el historial de la depreciación del libro de activos fijos, registrar el método de amortización por depreciación especial cuando lo conozca y enviar las transacciones de depreciación restantes del año. 

Puede crear un número ilimitado de registros de amortización por depreciación especial. Cuando haya asignado dichos registros a un libro del grupo de activos, se aplican al libro de activos. 

La amortización por depreciación especial se especifica como porcentaje o como importe fijo. Cuando se registran las propuestas de depreciación, las transacciones de depreciación de bonificación se registran en el libro como transacciones independientes de las transacciones de depreciación.

## <a name="depreciation-calendars"></a>Calendarios de depreciación
Cada libro tiene un calendario que se utiliza cuando deprecia activos fijos. De forma predeterminada, si no indica un calendario en el libro, el libro utiliza el calendario fiscal del libro mayor. Debe seleccionar un calendario fiscal para un libro cuando el perfil de depreciación asociado al libro utiliza un año de depreciación fiscal. 

Puede crear calendarios compartidos mediante la **página de Calendarios fiscales de** la Contabilidad general.

Para obtener más información, consulte [Convenciones y métodos de depreciación](depreciation-methods-conventions.md).



