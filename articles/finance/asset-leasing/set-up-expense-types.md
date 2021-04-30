---
title: Configurar tipos de gastos
description: En este tema se explica cómo configurar tipos de gastos en Arrendamiento de activos.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseExpenseTypeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a1d6667a7c6fe1cd44196f2e753ca72b2ca97649
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880993"
---
# <a name="set-up-expense-types"></a>Configurar tipos de gastos

[!include [banner](../includes/banner.md)]

En este tema se explica cómo configurar tipos de gastos en Arrendamiento de activos. Los costes que no están representados mediante la programación de pagos se conocen como *costes de gastos*. Ejemplos de estos costes son los impuestos a la propiedad, costes de mantenimiento de áreas comunes y gastos de seguros.

## <a name="add-an-administrative-expense-type"></a>Agregar un tipo de gasto administrativo

1. Vaya a **Arrendamiento de activos \> Configuración \> Tipos de gastos**.
2. Seleccione **Nuevo**.
3. En los campos correspondientes, introduzca el nuevo tipo de gasto y una descripción.

## <a name="assign-accounts-to-administrative-costs"></a>Asignar cuentas a costes administrativos

A continuación, debe asociar las cuentas con los tipos de gastos. Estas cuentas se adeudarán cuando se registren las entradas de la programación de gastos. La cuenta de contrapartida se especifica en las líneas **Programación de pagos de gastos a cargo del arrendatario en un arrendamiento de capital** de cada arrendamiento.

1. Vaya a **Arrendamiento de activos \> Configuración \> Parámetros de arrendamiento de activos**.
2. En la pestaña **Cuentas**, en la ficha desplegable **Gastos a cargo del arrendatario en un arrendamiento de capital**, en el campo **Tipo de gasto**, seleccione el tipo de gasto.
3. Seleccione **Agregar**.
4. En el campo **Tipo de libro**, seleccione el tipo de libro para vincular a los costos administrativos.

    > [!NOTE]
    > Se pueden vincular varios tipos de libros a la misma cuenta de gastos.

5. En el campo **Código de cuenta**, especifique a qué arrendamientos se debe aplicar el libro:

    - **Todos**: aplicar el libro a todos los arrendamientos.
    - **Grupo**: aplicar el libro a un grupo específico de arrendamientos.
    - **Tabla**: aplicar el libro a arrendamientos específicos.

6. Si seleccionó **Tabla** o **Grupo** en el campo **Código de cuenta**, seleccione un número de cuenta o número de grupo en el campo **Número de cuenta/grupo**.
7. En los campos correspondientes, seleccione la cuenta principal del arrendamiento financiero y la cuenta principal del arrendamiento operativo.

Cuando haya completado estos pasos, puede agregar gastos a través de las líneas **Calendario de pago de gastos a cargo del arrendatario en un arrendamiento de capital** en la página **Detalles del arrendamiento** de un arrendamiento seleccionado. Alternativamente, puede agregar gastos cuando crea un nuevo contrato de arrendamiento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
