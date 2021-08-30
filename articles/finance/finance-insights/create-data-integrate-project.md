---
title: Crear un proyecto integrador de datos (versión preliminar)
description: Este tema explica cómo crear un proyecto integrador de datos.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: a32ad6eb1b1874a9f9ec452def3c213cd160c5faa2aec02b655a86e160e2b509
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768996"
---
# <a name="create-a-data-integrator-project-preview"></a>Crear un proyecto integrador de datos (versión preliminar)

[!include [banner](../includes/banner.md)]

Este tema explica cómo crear un proyecto integrador de datos.

1. Inicie sesión en Microsoft Dynamics 365 Finance.
2. Vaya a **Espacios de trabajo \> Administración de datos** y seleccione **Entidades de datos**. Espere hasta que se hayan actualizado todas las entidades de datos antes de continuar con el siguiente paso.
3. Abra el [Portal de Power Apps](https://make.powerapps.com/) y siga estos pasos:

    1. Seleccione el entorno adecuado.
    2. En el panel de navegación izquierdo, seleccione **Datos \> Conexiones**.
    3. Conéctese a las instancias adecuadas de los siguientes elementos:

        - Dynamics 365
        - Dynamics 365 para Fin & Ops

4. Abra los [entornos de Power Apps](https://admin.powerapps.com/environments) y siga estos pasos:

    1. Seleccione **Integrador de datos**.
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

        - Resultados de información sobre pagos del cliente (CDS a Fin and Ops)
            - Si está utilizando la versión 10.0.17 o posterior, debe utilizar la plantilla denominada Resultado de información de pago del cliente (CDS a Fin and Ops 10.0.17 +).
        - Resultados de series de tiempo de flujo de efectivo (CDS a Fin and Ops)
        - Resultados de series de tiempo de presupuestos (CDS a Fin and Ops)

    2. Establezca la programación adecuada para cada proyecto.

> [!NOTE]
> Si no ve las entidades requeridas en CDS, vaya a **Crédito y cobros > Configuración > Información financiera> Finance Insights > Parámetros de Finance Insights**, habilite la función de predicciones de pago del cliente y haga clic en el botón **Crear modelo de predicción**. Cuando se complete la implementación del modelo de IA (correcta o con errores), las entidades CDS necesarias para crear la integración se implementarán en CDS.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
