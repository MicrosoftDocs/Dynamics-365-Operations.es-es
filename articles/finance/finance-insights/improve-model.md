---
title: Mejorar el modelo de predicción (versión preliminar)
description: Este tema describe las características que puede utilizar para mejorar el rendimiento de los modelos de predicción.
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 0bf4dd0f7edc528393af628eb3776c32957c459d3eaa166b0bc54d9318b54916
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768804"
---
# <a name="improve-the-prediction-model-preview"></a>Mejorar el modelo de predicción (versión preliminar)

[!include [banner](../includes/banner.md)]

Este tema describe las características que puede utilizar para mejorar el rendimiento de los modelos de predicción. Empezará a mejorar tu modelo en el espacio de trabajo **Predicciones de pago de clientes**, en Microsoft Dynamics 365 Finance. Luego, los pasos de mejora se completan en AI Builder.

## <a name="select-historical-outcomes"></a>Seleccionar resultados históricos

Primero seleccione uno o más de los tres posibles resultados para las facturas: **Puntual**, **Tarde** y **Muy tarde**. Deben seleccionarse los tres resultados. Si borra la selección de cualquiera de los resultados, las facturas se filtrarán fuera del proceso de capacitación y se reducirá la precisión de la predicción.

[![Confirmar resultados.](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Si su organización requiere solo dos resultados, cambie los umbrales **Tarde** y **Muy tarde** a 0 (cero) días. De esta manera, colapsa efectivamente la predicción a un estado binario de **Puntual** o **Tarde**.

## <a name="select-fields"></a>Seleccionar campos

Cuando seleccione campos para incluirlos en el modelo, tenga en cuenta que la lista incluye todos los campos disponibles en la tabla Microsoft Dataverse que se asigna a los datos en el lago de datos de Azure. Algunos de estos campos **no** deberían seleccionarse. Los campos que no deben seleccionarse pertenecen a una de estas tres categorías:

- El campo es obligatorio para la tabla Dataverse, pero no hay datos de respaldo para ella en el lago de datos.
- El campo es un id. y, por lo tanto, no tiene sentido para una función de aprendizaje automático.
- El campo representa información que no estará disponible durante la predicción.

Las siguientes secciones muestran los campos que están disponibles para la factura y las entidades del cliente, y enumeran los campos que **no** deben seleccionarse para el entrenamiento. La categoría que se especifica para cada uno de esos campos se refiere a las categorías de la lista anterior.
 
### <a name="invoice-dataverse-table"></a>Tabla de Dataverse de factura

La siguiente ilustración muestra los campos que están disponibles para la tabla de factura.

[![Campos disponibles para la tabla de factura.](./media/available-fields.png)](./media/available-fields.png)

Los siguientes campos no deben seleccionarse para el entrenamiento:

- **Cuenta de factura** (categoría 2)
- **Está cerrado** (categoría 3): este campo se utiliza para filtrar facturas para entrenamiento (cerrado) y predicción (no cerrado).
- **Nombre** (categoría 1)
- **Id. de origen** (categoría 2)
- **Registro de origen** (categoría 2)
- **Tabla de origen** (categoría 2)

### <a name="customer-dataverse-table"></a>Tabla de Dataverse de cliente

La siguiente ilustración muestra los campos que están disponibles para la tabla de cliente.

[![Campos disponibles para la tabla de cliente.](./media/related-entities.png)](./media/related-entities.png)

El campo siguiente no debe seleccionarse para el entrenamiento:

- **Clave única de fila** (categoría 2)

## <a name="filters"></a>Filtros

Puede filtrar las facturas que se utilizan para la formación estableciendo criterios de filtrado para los campos de la factura o en las tablas de clientes. Por ejemplo, puede establecer un umbral para incluir solo las facturas en las que el total sea igual o superior a una cantidad específica. Alternativamente, puede excluir facturas asociadas con clientes en un grupo de clientes específico.

Para obtener más información sobre cómo filtrar sus datos, consulte [Crea un modelo de predicción](https://docs.microsoft.com/ai-builder/prediction-create-model#filter-your-data).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
