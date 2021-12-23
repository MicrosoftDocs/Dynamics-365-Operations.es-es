---
title: Configurar grupos de impuestos de artículos
description: En este tema se explica cómo configurar grupos de impuestos de artículos en el servicio de cálculo de Impuestos.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 88dd8e2fd9d4d4e5172dcc7b1bd27a70a2f59f03
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883878"
---
# <a name="set-up-item-tax-groups"></a>Configurar grupos de impuestos de artículos

[!include [banner](../includes/banner.md)]

En este tema se explica cómo configurar grupos de impuestos de artículos en el servicio de cálculo de Impuestos. También se explica cómo configurar la matriz de reglas de aplicabilidad de los grupos impositivos de artículos y configurar las líneas en la matriz.

El concepto de grupos de impuestos de artículos en el servicio de cálculo de impuestos se asemeja al concepto de grupos de impuestos de ventas de artículos en Microsoft Dynamics 365 Finance. Son grupos de códigos de impuestos. El servicio de cálculo de impuestos utiliza la intersección de un grupo de impuestos y un grupo de impuestos de artículos para determinar los códigos de impuestos.

> [!IMPORTANT]
> La configuración de grupos de impuestos de artículos en el servicio de cálculo de impuestos es independiente de la entidad jurídica. Puede completar esta configuración en Regulatory Configuration Service (RCS) solo una vez. Cuando se activa el servicio de cálculo de impuestos en Finanzas, los grupos de impuestos de los artículos se sincronizan automáticamente para la entidad jurídica seleccionada.

## <a name="set-up-an-item-tax-group"></a>Configurar un grupo de impuestos de artículos 

Para configurar un grupo de impuestos de artículos, siga estos pasos:

1. Inicie sesión en [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Vaya a **Espacios de trabajo** \> **Características de globalización** \> **Cálculo de impuestos**.
3. Seleccione la característica y la versión que desee configurar y, a continuación, seleccione **Editar**.
4. En la pestaña **General**, seleccione **Versión de configuración**.
5. En la pestaña **Grupo de impuestos de artículos**, seleccione **Administrar columna**. Si está configurando un grupo de impuestos de artículos por primera vez, los campos del cuadro de diálogo **Administrar columna** se establecen automáticamente.
6. En la lista de la izquierda, expanda el nodo **Líneas** y seleccione la casilla de verificación **Grupo de impuestos de artículos**.

    ![Grupo de impuestos de artículos seleccionado en el nodo Líneas del cuadro de diálogo Administrar columnas.](media/select-item-tax-group.png)

7. Seleccione el botón de flecha derecha para agregar **Grupo de impuestos de artículos** a la lista **Columnas seleccionadas** de la derecha.

    ![Grupo de impuestos de artículos agregado a la lista Columnas seleccionadas.](media/add-item-tax-group.png)

8. Seleccione **Aceptar**.

## <a name="configure-an-item-tax-group"></a>Configurar un grupo de impuestos de artículos

Después de configurar un grupo de impuestos de artículos, se crea la matriz de reglas de aplicabilidad. Puede agregar líneas a la matriz para configurar el grupo de impuestos de artículos.

1. En la pestaña **Grupo de impuestos de artículos**, seleccione **Agregar**.
2. En el campo **Grupo de impuestos de artículos**, especifique el nombre del grupo de impuestos de artículos.

    > [!IMPORTANT]
    > Le recomendamos que limite el nombre del grupo de impuestos de artículos a 10 caracteres. Este nombre está sincronizado con Finanzas, que tiene un límite de 10 caracteres para los nombres de los grupos de impuestos sobre la venta de artículos.

3. En el campo **Códigos de impuestos**, seleccione la casilla de verificación para cada código de impuestos que desee incluir en el grupo de impuestos de artículos. Puede incluir varios códigos de impuestos en un grupo de impuestos de artículos.

    ![Varios códigos de impuestos seleccionados en el campo Códigos de impuestos.](media/multiple-tax-codes-selection.png)

4. Repita los pasos 1 a 3 para agregar más grupo de impuestos de artículos.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
