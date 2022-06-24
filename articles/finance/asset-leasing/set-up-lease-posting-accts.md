---
title: Configurar cuentas de registro de arrendamiento
description: Este artículo enumera las cuentas de contabilidad necesarias para las transacciones de Arrendamiento de activos y explica cómo definir cuentas de contabilidad en la página de parámetros de contabilidad de arrendamiento.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 6e3a0d8dd3bb3e58ca10b2efce0cc88a2f48d2de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859925"
---
# <a name="set-up-lease-posting-accounts"></a>Configurar cuentas de registro de arrendamiento

[!include [banner](../includes/banner.md)]

Este artículo enumera las cuentas de contabilidad necesarias para las transacciones de Arrendamiento de activos y explica cómo definir cuentas de contabilidad en la página **Parámetros de contabilidad de arrendamiento**.

Para cumplir con el Tema 842 de Codificación de Normas Contables (ASC 842) y la Norma Internacional de Información Financiera 16 (NIIF 16), es posible que deba crear cuentas en su plan de cuentas. Sin embargo, las cuentas que cree para cumplir con los estándares ASC e IFRS no son cuentas de activos fijos. Según la ASC 842, se registra un activo por derecho de uso (ROU) tanto para arrendamientos financieros como operativos. Estos arrendamientos son independientes de los activos fijos. (Sigue pudiendo mantener activos por derecho de uso mediante el uso de activos fijos).

Para obtener más información sobre cómo crear estructuras de cuentas, consulte [Crear estructuras de cuentas](../general-ledger/tasks/create-account-structures.md). Para obtener más información sobre cómo crear una cuenta principal, consulte [Crear una cuenta principal](../general-ledger/tasks/create-main-account.md).

La siguiente tabla muestra ejemplos de cuentas que debe crear para transacciones de activos arrendados, si aún no se han creado. Según IFRS 16, las relaciones de arrendamiento se siguen utiliando para arrendamientos de bajo valor y a corto plazo.

| Número de la cuenta contable | Tipo de cuenta  | Nombre de la cuenta                                          |
|-----------------------|---------------|-------------------------------------------------------|
| 180150                | Activo         | Activo por derecho de uso de vehículo                                     |
| 180160                | Activo         | Activo por derecho de uso de construcción                                    |
| 180250                | Activo         | Depreciación acumulada: vehículos                   |
| 180260                | Activo         | Depreciación acumulada: edificios                  |
| 222300                | Pasivo     | Obligación a corto plazo: arrendamientos financieros                |
| 222310                | Balance de situación | Obligación a corto plazo: arrendamientos operativos              |
| 250200                | Pasivo     | Notas a pagar                                         |
| 250601                | Balance de situación | Obligación a largo plazo: arrendamientos financieros                 |
| 250602                | Balance de situación | Obligación a largo plazo: arrendamientos operativos               |
| 250606                | Balance de situación | Arrendamiento diferido                                         |
| 300160                | Balance de situación | Ganancias retenidas                                     |
| 604500                | Gastos       | Gasto de arrendamiento                                         |
| 604501                | Gastos       | Gastos por arrendamiento operativo de vehículos: acumulación de intereses  |
| 604502                | Gastos       | Gasto por arrendamiento operativo de vehículos: amortización        |
| 605200                | Gastos       | Gastos por arrendamiento operativo de construcciones: acumulación de intereses |
| 605201                | Gastos       | Gasto por arrendamiento operativo de construcciones: amortización       |
| 607101                | Gastos       | Gasto por amortización de arrendamiento operativo de vehículos                    |
| 607102                | Gastos       | Gasto por amortización de arrendamiento de construcciones                   |
| 607103                | Gastos       | Gastos por deterioro: arrendamientos financieros                   |
| 607104                | Gastos       | Gastos por deterioro: arrendamientos operativos                 |
| 618910                | Gastos       | Gastos de arrendamiento: arrendamientos financieros                        |
| 618920                | Gastos       | Pagos variables: arrendamientos financieros                    |
| 618930                | Gastos       | Pagos variables: arrendamientos operativos                  |
| 800600                | Gastos       | Gasto por intereses de arrendamiento de vehículos                        |
| 800601                | Gastos       | Gasto por intereses de arrendamiento de construcciones                       |
| 801201                | Balance de situación | Ganancias y pérdidas: modificación de arrendamiento                      |

## <a name="configure-posting-accounts"></a>Configurar cuentas de registro

Para asignar cuentas a los libros y grupos de arrendamientos que se han creado, debe configurar los parámetros para Arrendamiento de activos.

1. Vaya a **Arrendamiento de activos \> Configuración \> Parámetros de registro de arrendamientos**.
2. En la pestaña **Cuentas**, abra la ficha desplegable **Cuentas de arrendamiento**. Determinar las cuentas principales de arrendamientos financieros y operativos para el correspondiente **Tipo de publicación**. La tabla anterior muestra las cuentas relacionadas con los arrendamientos operativos y financieros.

    > [!NOTE]
    > Este paso requiere que configure cuentas separadas para arrendamientos operativos y financieros para cada tipo de registro, excepto **Compensación de gastos de arrendamiento** y **Aumento/disminución de arrendamiento**. Las empresas que se adhieren al marco contable IFRS 16 deben agregar una cuenta principal para el arrendamiento operativo. Pero el sistema no utilizará esta cuenta a pesar de que es un campo obligatorio porque todos los arrendamientos según IFRS 16 se clasifican como arrendamientos financieros.
    >[!NOTE]
    > **Aumento/disminución de arrendamiento** se utilizará como tipo de publicación para consideraciones de activos adicionales, que incluyen **Coste directo inicial, Incentivos de arrendamiento, Prepagos de arrendamiento y Costes de desmantelamiento**, pero se publica en la cuenta principal del activo por derecho de uso, que de forma predeterminada es **Activo de arrendamiento**.        
    
3. Para seleccionar un grupo de arrendamiento específico correspondiente a la cuenta principal, en el campo **Código de cuenta**, seleccione **Grupo**. Entonces, en el campo **Número de cuenta/grupo**, seleccione el grupo de arrendamiento a asignar a la cuenta principal.
4. Para asignar códigos de cuenta a los costes administrativos que se han configurado en el sistema, en la ficha desplegable **Gastos a cargo del arrendatario en un arrendamiento de capital**, en el campo **Tipo de gasto**, seleccione un gasto. Luego, asigne las cuentas financieras y operativas que se utilizarán para cada libro.

    > [!NOTE]
    > La cuenta financiera u operativa seleccionada se adeudará cuando se registre la factura del gasto programado.
    > **Contrapartida de gastos de arrendamiento** se utilizará como tipo de registro para las transacciones de gastos a cargo del arrendatario en un arrendamiento de capital, pero se registrará en la **Cuenta de contrapartida** definida en las **Líneas de programación de pago de costos de ejecución**, en los detalles del arrendamiento o en el formulario de libro de arrendamiento.   


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
