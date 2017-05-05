---
title: Dimensiones financieras
description: "Este artículo explica los diferentes tipos de dimensiones financieras y cómo se configuran."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25871
ms.assetid: af54621c-c8be-4b72-b6df-dcf886c40ce4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f849b98cac88d182875aca88aaf04cd3575ed99f
ms.lasthandoff: 03/31/2017


---

# <a name="financial-dimensions"></a>Dimensiones financieras

[!include[banner](../includes/banner.md)]


Este artículo explica los diferentes tipos de dimensiones financieras y cómo se configuran.

Use la página Dimensiones financieras para crear las dimensiones financieras que se pueden usar como segmentos de cuentas para los planes contables compartidos. Existen dos tipos de dimensiones financieras, dimensiones personalizadas y dimensiones respaldadas por entidad. Las dimensiones personalizadas se comparten entre entidades jurídicas y los valores los introduce y mantiene el usuario. Las dimensiones respaldadas por entidad son dimensiones cuyos valores se definen en otra parte del sistema, como Clientes o Tiendas. Algunas dimensiones respaldadas por entidad se comparten entre entidades jurídicas, y algunas dimensiones respaldadas por entidad son específicas de una empresa. 

Una vez creadas las dimensiones financieras, use la página Valores de la dimensión financiera para asignar propiedades adicionales a cada dimensión financiera. 

Aunque puede usar dimensiones financieras para representar entidades jurídicas sin crear entidades jurídicas en Microsoft Dynamics 365 for Operations, las dimensiones financieras no están diseñadas para satisfacer las necesidades operativas o empresariales de las entidades jurídicas. La funcionalidad de contabilidad de interunidad de Microsoft Dynamics 365 for Operations está diseñada para tratar solo los asientos contables creados por cada transacción. 

Antes de configurar dimensiones financieras como entidades jurídicas, evalúe sus procesos empresariales en las áreas siguientes para determinar si esta configuración funcionará para su organización:

-   Inventario
-   Ventas y compras entre las dimensiones financieras y las entidades jurídicas
-   Cálculo de impuestos y generación de informes
-   Informes operativos

Entre algunos ejemplos de las limitaciones se incluyen los siguientes:

-   Puede usar la funcionalidad de impuestos solo con entidades jurídicas, no con dimensiones financieras.
-   Algunos informes no incluye dimensiones financieras, por lo que no puede siempre efectuar informes por la dimensión financiera a menos que se modifiquen esos informes.

**Dimensiones personalizadas** 

Para crear una dimensión financiera definida por el usuario, en el campo Usar valores de, seleccione &lt; Dimensión personalizada &gt;. También puede especificar una máscara de cuenta para limitar el importe y el tipo de información que puede especificar para valores de dimensión. Puede especificar los caracteres que permanecen iguales para cada valor de dimensión, como letras o un guión. También puede especificar signos de número (\#) ) y ampersands (&) como marcadores de posición para las letras y los números que se modificarán cada vez que se cree un valor de dimensión. Use un signo de número (\#) ) como marcador de posición para un número y un ampersand (&) como marcador de posición para una letra. 

**Ejemplo ** 

Para limitar el valor de dimensión a letras CC, un guión y tres números, debe especificar CC-\#\#\# como la máscara de formato. Este campo sólo está disponible si selecciona el campo &lt; Dimensión personalizada &gt; en el campo Usar valores desde. 

**Dimensiones respaldadas por entidad** 

Para crear una dimensión financiera respaldada por entidad, en el campo Usar valores de, seleccione una entidad definida por el sistema en la que basar la dimensión financiera. Los valores de la dimensión financiera se crean a partir de esta selección. Por ejemplo, para crear valores de dimensión para proyectos, seleccione Proyectos. Se creará un valor de dimensión para cada nombre de proyecto. La página de los valores de la dimensión muestra los valores para la entidad y si son específicos de la empresa, la empresa para el valor. 

**Activación de dimensiones** 

La activación de la dimensión financiera actualiza la tabla con el nombre de la dimensión financiera y quita las dimensiones eliminadas. Puede especificar valores de dimensión para activar una dimensión financiera, pero no se puede consumir una dimensión financiera en ninguna parte hasta que esté activada. Por ejemplo, no puede agregar una dimensión financiera a una estructura contable hasta que se active la dimensión financiera. El hacer clic en Activar, se actualizarán todas las dimensiones con cambios de estado. 

**Traducciones** 

La página Texto le permite escribir texto que se va a mostrar en diferentes idiomas para la dimensión financiera seleccionada. La página Traducción de cuenta principal es un lugar donde puede escribir el texto que se va a mostrar en diferentes idiomas para la cuenta principal. 

**Anulaciones de entidad jurídica** 

No todas las dimensiones son válidas para todas las entidades jurídicas, y algunas solo pueden ser relevantes para un período de tiempo específico. En esta situación, puede usarse la sección Anulaciones de entidad jurídica para identificar para qué empresas se debe suspender la dimensión, quién es el propietario y el período de tiempo que la dimensión está activa.






