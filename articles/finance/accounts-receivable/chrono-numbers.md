---
title: Numeración cronológica de documentos y vales
description: Este tema explica cómo configurar y utilizar números cronológicos para documentos aplicables y vales relacionados.
author: ikond
manager: AnnBe
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 31745632de7339d167ac9f18f02e6611e1a78b28
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104437"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a>Numeración cronológica de documentos y vales

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

En algunos países, existe el requisito legal de numerar los documentos y los vales relacionados en orden cronológico. La cronología debe estar organizada por períodos. Todos los números que pertenecen a períodos anteriores deben ser menores que los números que pertenecen a períodos posteriores. Para cumplir con este requisito, se ha implementado la funcionalidad de numeración cronológica. Este tema explica cómo configurar y utilizar números cronológicos para documentos aplicables y vales relacionados.

## <a name="prerequisites"></a>Requisitos previos

En el espacio de trabajo Administración de funciones, active la característica **Numeración cronológica**. Para más información, consulte [Resumen de administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-chronological-numbering"></a>Configurar la numeración cronológica

La numeración cronológica afecta a los siguientes documentos.

**Clientes**
- Factura de cliente
- Asiento de la factura de cliente
- Nota de abono de ventas
- Asiento de la nota de abono de ventas
- Factura de servicios
- Asiento de servicio
- Nota de abono de texto sin formato
- asiento de la nota de abono de texto sin formato
- Traslado
- Nº Asiento del albarán
- Asiento de corrección del albarán
- Asiento de la nota de interés
- Asiento de la carta de cobro

**Proveedores**
- Nº Asiento de la factura
- Nº Asiento de la nota de abono
- Asiento de recepción de producto

**Administración de proyectos**
- Factura
- Nº Asiento de la factura
- Factura rectificativa
- Nº Asiento de la nota de abono 

### <a name="define-number-sequences"></a>Definir secuencias numéricas

Para definir secuencias numéricas, vaya a **Administración de la organización** > **Secuencias numéricas** > **Secuencias numéricas**. Puede definir tantas secuencias numéricas como sea necesario para cubrir los períodos afectados para los documentos requeridos. 

Especifique una empresa para cada secuencia numérica. Los segmentos de las secuencias numéricas deben definirse de modo que proporcionen un orden cronológico a los períodos. Por ejemplo, los nombres de los segmentos pueden contener un prefijo especial que identifique un período específico.

![Configurar secuencia numérica](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a>Configurar grupos de secuencias numéricas

Para configurar grupos de secuencias numéricas, vaya a **Clientes** > **Configuración** > **Parámetros de clientes**. En la pestaña **Secuencias numéricas**, defina tantos grupos de secuencias numéricas como sea necesario para cubrir los períodos afectados. 

Para cada grupo, en la sección **Referencia**, seleccione una de las referencias de documentos compatibles y, en el campo **Código de secuencia numérica**, haga referencia a una secuencia numérica que se creó previamente para el período relacionado.

![Configurar grupo de secuencias numéricas](media/chrono-num-sequence-group.jpg)

De manera similar, configure grupos de secuencias numéricas en los módulos **Proveedores** y **Gestión de proyectos y contabilidad**.

### <a name="configure-number-sequence-groups-chronology"></a>Configurar la cronología de grupos de secuencias numéricas

Para configurar la cronología de los grupos de secuencias numéricas, vaya a **Administración de la organización** > **Secuencias numéricas** > **Grupos de secuencias numéricas cronológicas**. Defina las condiciones de aplicabilidad para grupos de secuencias numéricas.

![Configuración de números cronológicos](media/chrono-num-sequence-group-period.jpg)

| Campo            | Descripción                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Vigente  | La fecha de inicio de la aplicabilidad del grupo de secuencias numéricas. |
| Caducidad      | La fecha de finalización de la aplicabilidad del grupo de secuencias numéricas. Si no se aplica una fecha de finalización, seleccione **Nunca**. |
| Grupo de secuencias numéricas | Grupo de secuencias numéricas que se utilizará para generar números de documentos durante el período. |
| Grupo de secuencias numéricas original | Este código de grupo de secuencias numéricas se utiliza para un filtrado adicional para los casos en los que los documentos ya tienen un grupo de secuencias numéricas *permanente* asignado. Un valor vacío se considera un valor específico. Si necesita ignorar un grupo asignado preliminarmente, use la opción **Predeterminado** para esta configuración. |
| Predeterminada | Si está activado, el sistema ignora el grupo de secuencias numéricas de documentos asignado preliminarmente y usa solo las fechas de inicio y finalización de los períodos para el análisis de aplicabilidad. Si se desactiva, el sistema usa la combinación completa **En vigor desde** + **Vencimiento** + **Grupo de secuencia numérica original** para la selección. |

## <a name="document-posting"></a>Contabilización de documentos
Al registrar un documento, el grupo de secuencias numéricas apropiado se asigna al documento, según la fecha de contabilidad del documento, y luego se usa para generar un número de documento basado en la secuencia numérica detectada. El sistema proporciona un mensaje sobre la asignación del grupo de secuencias numéricas.

![Número de documento](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> Para algunos países, ya existe una lógica específica implementada para la numeración de documentos. En este caso, la lógica específica del país anulará la característica **Numeración cronológica**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]