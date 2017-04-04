---
title: "Definiciones de contabilización"
description: "Este artículo proporciona información acerca de las definiciones de contabilización, y acerca de cómo definirlas y vincularlas. Para los tipos de contabilización y documentos admitidos, puede usar definiciones de contabilización en lugar de los perfiles de contabilización para clasificar cuentas principales y las dimensiones financieras de asientos contables."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 357ae498e84ef27e46142c7dcc0f90ecb0ee9f1c
ms.lasthandoff: 03/31/2017


---

# <a name="posting-definitions"></a>Definiciones de contabilización

Este artículo proporciona información acerca de las definiciones de contabilización, y acerca de cómo definirlas y vincularlas. Para los tipos de contabilización y documentos admitidos, puede usar definiciones de contabilización en lugar de los perfiles de contabilización para clasificar cuentas principales y las dimensiones financieras de asientos contables.

Para los tipos de contabilización y documentos admitidos, puede usar definiciones de contabilización en lugar de los perfiles de contabilización para clasificar cuentas principales y las dimensiones financieras de asientos contables. Puede ver los documentos y los tipos de registro que admite la página **Definiciones de contabilización de transacciones**. 

Para empezar a usar definiciones de contabilización, seleccione** Usar definiciones de contabilización** en la página **Parámetros de contabilidad general**. Incluso al usar definiciones de contabilización, deberá definir los perfiles de contabilización para las entradas de origen y los documentos y los tipos de contabilización no admitidos. 

Debe usar definiciones de contabilización para habilitar contabilidad de reserva de gasto para solicitudes de compra y contabilidad de pre-reserva de gasto para solicitudes de compra.

## <a name="defining-posting-definitions"></a>Establecimiento de definiciones de contabilización
Use la página** Definiciones de contabilización** para especificar los criterios de coincidencia y para definir las entradas que se deben generar cuando se produce una coincidencia. Los criterios de coincidencia se evalúan para las entradas que se originan como distribuciones contables. 

En la página **Definiciones de contabilización** puede también asignar números de prioridad a líneas de entradas para controlar el orden en el que se evalúan las líneas. Las líneas con el número de prioridad más baja se evalúan primero. Por ejemplo, se evalúan todas las líneas con una prioridad de 1, a continuación las líneas con una prioridad de 2, y así sucesivamente. Cuando se encuentra una coincidencia, se omiten los demás criterios de coincidencia. Además, solo los criterios del grupo que coincidan con la transacción de origen crearán entradas generadas. 

Puede validar las definiciones de contabilización mediante el **asistente para definición de contabilización de prueba**. Tras definir una entrada de origen de muestra para una definición de contabilización, verá las entradas generadas. 

Puede usar versiones de definición de contabilización junto con fechas de vigencia. Por ejemplo, puede crear una versión futura de una definición de contabilización para registrar en una cuenta contable diferente en un nuevo ejercicio. 

Use la página **Definiciones de contabilización de transacciones** para asignar definiciones de contabilización a los tipos transacciones.

## <a name="linking-posting-definitions"></a>Vinculación de definiciones de contabilización
Al crear definiciones de contabilización, puede crear un vínculo de una definición de contabilización a otra. Los criterios de la definición a los que ha creado el vínculo se consideran además de los criterios de la definición de contabilización actual. Esta función contribuye a ahorrar tiempo, ya que no tiene que volver a especificar criterios en la ficha desplegable **Entradas** de la página **Definiciones de contabilización** para la definición de contabilización actual si ya se han especificado esas líneas en otra definición. 

En los diagramas o tablas, incluya los vínculos que pueda usar. Para evitar conflictos con la definición de contabilización actual, asegúrese de que las líneas de las definiciones de contabilización a las que está creando vínculos sean únicas. 

Al crear vínculos en definiciones de contabilización, se aplicarán las siguientes restricciones:

-   Cualquier definición de contabilización puede vincular a otra definición de contabilización o puede ser vinculada desde otra definición de contabilización, pero no las dos cosas. No obstante, una definición de contabilización puede usarse como vínculo a varias definiciones de contabilización.
-   Puede configurar vínculos sólo entre definiciones de contabilización que se encuentren en el mismo módulo.
-   Puede asignar una definición de contabilización a cualquier tipo de transacción, pero el tipo de transacción debe estar en el mismo módulo que la definición de contabilización. Use la página **Definiciones de contabilización de transacciones** para ver en qué módulo se encuentra un tipo de transacción.


Para obtener más información, consulte [] los ejemplos de las definiciones de contabilización (/general-ledger/example-posting-definitions.md). 

