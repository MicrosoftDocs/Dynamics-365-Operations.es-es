---
title: Crear un proyecto de integración de datos
description: Este tema explica cómo crear un proyecto de integración de datos.
author: ShivamPandey-msft
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 50f435f9d461667a1908baa529d73766085c183a
ms.sourcegitcommit: 6526acd0300d9c5800d3d7675d54e23090d031df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2022
ms.locfileid: "8107296"
---
# <a name="create-a-data-integration-project"></a>Crear un proyecto de integración de datos

[!include [banner](../includes/banner.md)]

Este tema explica cómo crear un proyecto de integración de datos.

1. Inicie sesión en Microsoft Dynamics 365 Finance.
2. Vaya a **Espacios de trabajo \> Administración de datos** y seleccione **Entidades de datos**. Espere hasta que se hayan actualizado todas las entidades de datos antes de continuar con el siguiente paso.
3. Abra el [Portal de Power Apps](https://make.powerapps.com/) y siga estos pasos:

    1. Seleccione el entorno adecuado.
    2. En el panel de navegación izquierdo, seleccione **Dataverse \> Conexiones**.
    3. Conéctese a las instancias adecuadas de los siguientes elementos:

        - Dynamics 365
        - Dynamics 365 para Fin & Ops

4. Abra los [entornos de Power Apps](https://admin.powerapps.com/environments) y siga estos pasos:

    1. Seleccione **Integración de datos**.
    2. Seleccione **Conjuntos de conexión**.
    3. Seleccione **Nuevo conjunto de conexión**.
    4. Escriba un nombre para la conexión.
    5. Seleccione las conexiones adecuadas para los siguientes elementos:

        - Dynamics 365
        - Dynamics 365 para Fin & Ops

    6. Seleccione el mapeo de la organización apropiado.
    7. Seleccione **Crear**.

5. Abra los [entornos de Power Apps](https://admin.powerapps.com/environments) y siga estos pasos:  

    1. Cree proyectos de integración de datos para las siguientes plantillas utilizando el conjunto de conexiones que acaba de crear:

        - Resultado de información sobre pagos del cliente (CDS a Fin and Ops 10.0.17+)
        - Resultados de series de tiempo de flujo de efectivo (CDS a Fin and Ops)
        - Resultados de series de tiempo de presupuestos (CDS a Fin and Ops)

    2. Establezca la programación adecuada para cada proyecto.

> [!NOTE]
> Si no ve las entidades requeridas en Dataverse, vaya a **Crédito y cobros** > **Configuración** > **Finance Insights** > **Parámetros de Finance Insights**, habilite la característica de **predicciones de pago del cliente** y seleccione **Crear modelo de predicción**. Cuando se complete la implementación del modelo de IA, las entidades de Dataverse necesarias para crear la integración se implementarán.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
