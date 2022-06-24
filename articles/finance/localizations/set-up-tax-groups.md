---
title: Configurar grupos de impuestos
description: En este artículo se explica cómo configurar grupos de impuestos en el servicio de cálculo de Impuestos.
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
ms.openlocfilehash: 89c5670ee7e78f2dc51f128c3ae8d284bb6b925b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862910"
---
# <a name="set-up-tax-groups"></a>Configurar grupos de impuestos

[!include [banner](../includes/banner.md)]

En este artículo se explica cómo configurar grupos de impuestos en el servicio de cálculo de Impuestos. También se explica cómo configurar la matriz de reglas de aplicabilidad de los grupos de impuestos y configurar las líneas en la matriz.

El concepto de grupos de impuestos en el servicio de cálculo de impuestos se asemeja al concepto de grupos de impuestos de ventas en Microsoft Dynamics 365 Finance. Son grupos de códigos de impuestos. El servicio de cálculo de impuestos utiliza la intersección de un grupo de impuestos y un grupo de impuestos de artículos para determinar los códigos de impuestos.

Sin embargo, los grupos de impuestos en el servicio de cálculo de impuestos se diferencian de los grupos de impuestos sobre las ventas en Finanzas en que no hay parámetros adicionales en ellos, como **Impuesto de uso** e **Impuesto exento**. En cambio, esos parámetros están disponibles a nivel de código de impuestos.

> [!IMPORTANT]
> La configuración de grupos de impuestos en el servicio de cálculo de impuestos es independiente de la entidad jurídica. Puede completar esta configuración en Regulatory Configuration Service (RCS) solo una vez. Cuando se activa el servicio de cálculo de impuestos en Finanzas, los grupos de impuestos se sincronizan automáticamente para la entidad jurídica seleccionada.

## <a name="set-up-a-tax-group"></a>Configurar un grupo de impuestos

Siga estos pasos para configurar un grupo de impuestos.

1. Inicie sesión en [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Vaya a **Espacios de trabajo** \> **Características de globalización** \> **Cálculo de impuestos**.
3. Seleccione la característica y la versión que desee configurar y, a continuación, seleccione **Editar**.
4. En la pestaña **General**, seleccione **Versión de configuración**.
5. En la pestaña **Grupo de impuestos**, seleccione **Administrar columna**. Si está configurando un grupo de impuestos por primera vez, los campos del cuadro de diálogo **Administrar columna** se establecen automáticamente.
6. En la lista de la izquierda, expanda el nodo **Líneas** y seleccione la casilla de verificación **Grupo de impuestos**.

    ![Grupo de impuestos seleccionado en el nodo Líneas del cuadro de diálogo Administrar columnas.](media/select-tax-group.png)

7. Seleccione el botón de flecha derecha para agregar **Grupo de impuestos** a la lista **Columnas seleccionadas** de la derecha.

    ![Grupo de impuestos agregado a la lista Columnas seleccionadas.](media/add-tax-group.png)

8. Seleccione **Aceptar**.

## <a name="configure-a-tax-group"></a>Configurar un grupo de impuestos

Después de configurar un grupo de impuestos, se crea la matriz de reglas de aplicabilidad de grupos de impuestos. Puede agregar líneas a la matriz para configurar el grupo de impuestos.

1. En la pestaña **Grupo de impuestos** haga clic en **Agregar**.
2. En el campo **Grupo de impuestos**, especifique el nombre del grupo de impuestos.

    > [!IMPORTANT]
    > Le recomendamos que limite el nombre del grupo de impuestos a 10 caracteres. Este nombre está sincronizado con Finanzas, que tiene un límite de 10 caracteres para los nombres de los grupos de impuestos sobre ventas.

3. En el campo **Códigos de impuestos**, seleccione la casilla de verificación para cada código de impuestos que desee incluir en el grupo de impuestos. Puede incluir varios códigos de impuestos en un grupo de impuestos.

    ![Varios códigos de impuestos seleccionados en el campo Códigos de impuestos.](media/multiple-tax-codes-selection.png)

4. Repita los pasos del 1 al 3 para agregar más grupos de impuestos.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
