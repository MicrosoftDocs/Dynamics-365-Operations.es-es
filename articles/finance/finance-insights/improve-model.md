---
title: Mejorar el modelo de predicción (versión preliminar)
description: Este tema describe las características que puede utilizar para mejorar el rendimiento de los modelos de predicción.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 23c9062dcc13951792306c955b54cae6f656fec5
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646088"
---
# <a name="improve-the-prediction-model-preview"></a>Mejorar el modelo de predicción (versión preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema describe las características que puede utilizar para mejorar el rendimiento de los modelos de predicción. Empezará a mejorar tu modelo en el espacio de trabajo **Predicciones de pago de clientes**, en Microsoft Dynamics 365 Finance. Luego, los pasos de mejora se completan en AI Builder.

## <a name="select-historical-outcomes"></a>Seleccionar resultados históricos

Primero seleccione uno o más de los tres posibles resultados para las facturas: **Puntual**, **Tarde** y **Muy tarde**. Deben seleccionarse los tres resultados. Si borra la selección de cualquiera de los resultados, las facturas se filtrarán fuera del proceso de capacitación y se reducirá la precisión de la predicción.

[![Confirmar resultados](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Si su organización requiere solo dos resultados, cambie los umbrales **Tarde** y **Muy tarde** a 0 (cero) días. De esta manera, colapsa efectivamente la predicción a un estado binario de **Puntual** o **Tarde**.

## <a name="select-fields"></a>Seleccionar campos

Cuando seleccione campos para incluir en el modelo, tenga en cuenta que la lista incluye todos los campos disponibles en la entidad Common Data Service que se asigna a los datos en el lago de datos de Azure. Algunos de estos campos **no** deberían seleccionarse. Los campos que no deben seleccionarse pertenecen a una de estas tres categorías:

- El campo es obligatorio para la entidad Common Data Service, pero no hay datos de respaldo para ella en el lago de datos.
- El campo es un id. y, por lo tanto, no tiene sentido para una función de aprendizaje automático.
- El campo representa información que no estará disponible durante la predicción.

Las siguientes secciones muestran los campos que están disponibles para la factura y las entidades del cliente, y enumeran los campos que **no** deben seleccionarse para el entrenamiento. La categoría que se especifica para cada uno de esos campos se refiere a las categorías de la lista anterior.
 
### <a name="invoice-common-data-model-entity"></a>Entidad de factura de Common Data Model

La siguiente ilustración muestra los campos que están disponibles para la entidad de factura.

[![Campos disponibles para la entidad de factura](./media/available-fields.png)](./media/available-fields.png)

Los siguientes campos no deben seleccionarse para el entrenamiento:

- **Cuenta de factura** (categoría 2)
- **Está cerrado** (categoría 3): este campo se utiliza para filtrar facturas para entrenamiento (cerrado) y predicción (no cerrado).
- **Nombre** (categoría 1)
- **Id. de origen** (categoría 2)
- **Registro de origen** (categoría 2)
- **Tabla de origen** (categoría 2)

### <a name="customer-common-data-model-entity"></a>Entidad de cliente de Common Data Model

La siguiente ilustración muestra los campos que están disponibles para la entidad de cliente.

[![Campos disponibles para la entidad de cliente](./media/related-entities.png)](./media/related-entities.png)

El campo siguiente no debe seleccionarse para el entrenamiento:

- **Clave única de fila** (categoría 2)

## <a name="filters"></a>Filtros

Actualmente, los filtros no son compatibles con el escenario del predictor de pagos de clientes. Por lo tanto, seleccione **Omitir este paso** y continúe con la página de resumen.

[![Modelo de enfoque con filtros](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)

#### <a name="privacy-notice"></a>Aviso de privacidad
Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]