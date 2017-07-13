---
title: Dimensiones financieras
description: "Este tema describe los diferentes tipos de dimensiones financieras y cómo se configuran."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ems.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: a0edbad63c51d111d7c8985aa7fdf7312da6149d
ms.openlocfilehash: e82d53b3f6b4c8d3e2363f26576331e1d03434d9
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Dimensiones financieras
<a id="financial-dimensions" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Este tema explica los diferentes tipos de dimensiones financieras y cómo se configuran.

Use la página **Dimensiones financieras** para crear las dimensiones financieras que se pueden usar como segmentos de cuentas para los planes contables compartidos. Existen dos tipos de dimensiones financieras: dimensiones personalizadas y dimensiones respaldadas por entidad. Las dimensiones personalizadas se comparten entre entidades jurídicas y los valores los introduce y mantiene los usuarios. Para dimensiones respaldadas por entidad, los valores se definen en otra ubicación del sistema, como Clientes o Tiendas. Algunas dimensiones respaldadas por entidad se comparten entre entidades jurídicas, mientras que otras dimensiones respaldadas por entidad son específicas de una empresa. 

Una vez creadas las dimensiones financieras, use la página **Valores de la dimensión financiera** para asignar propiedades adicionales a cada dimensión financiera. 

Puede usar dimensiones financieras para representar las entidades jurídicas. No es necesario crear las entidades jurídicas en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. No obstante, las dimensiones financieras no están diseñadas para abordar los requisitos operativos o empresariales de las entidades jurídicas. La funcionalidad de contabilidad de interunidad de Finance and Operations está diseñada para tratar solo los asientos contables creados por cada transacción. 

Antes de configurar dimensiones financieras como entidades jurídicas, evalúe sus procesos empresariales en las áreas siguientes para determinar si esta configuración funcionará para su organización:

- Inventario
- Ventas y compras entre las dimensiones financieras y las entidades jurídicas
- Cálculo de impuestos y generación de informes
- Informes operativos

A continuación se muestran algunas limitaciones:

- Puede usar la funcionalidad de impuestos solo con entidades jurídicas, no con dimensiones financieras.
- Algunos informes no incluyen dimensiones financieras. Por lo tanto, para informar por dimensión financiera, puede que necesite modificar los informes.

## Dimensiones personalizadas
<a id="custom-dimensions" class="xliff"></a>

Para crear una dimensión financiera definida por el usuario, en el campo **Usar valores desde** seleccione **&lt; Dimensión personalizada &gt;**. También puede especificar una máscara de cuenta para limitar el importe y el tipo de información que puede especificar para valores de dimensión. Puede especificar los caracteres que permanecen iguales para cada valor de dimensión, como letras o un guion (-). También puede especificar signos de número (\#) ) y ampersands (&) como marcadores de posición para las letras y los números que se modificarán cada vez que se cree un valor de dimensión. Use un signo de número (\#) ) como marcador de posición para un número y un ampersand (&) como marcador de posición para una letra. El campo para la máscara de formato solo está disponible si selecciona el campo **&lt; Dimensión personalizada &gt;** en el campo **Usar valores desde**.

**Ejemplo**

Para limitar el valor de dimensión a letras "CC", un guion y tres números, debe especificar **CC\#\#\#** como la máscara de formato.

## Dimensiones respaldadas por entidad
<a id="entity-backed-dimensions" class="xliff"></a>

Para crear una dimensión financiera respaldada por entidad, en el campo **Usar valores desde**, seleccione una entidad definida por el sistema en la que basar la dimensión financiera. Los valores de la dimensión financiera se crean después a partir de esta entidad. Por ejemplo, para crear valores de dimensión para proyectos, seleccione **Proyectos**. Después, se creará un valor de dimensión para cada nombre de proyecto. La página **Valores de la dimensión financiera** muestra los valores para la entidad. Si estos valores son específicos par la empresa, la página también muestra la empresa.

## Activación de dimensiones
<a id="activating-dimensions" class="xliff"></a>

Al activar una dimensión financiera, se actualizará la tabla de modo que incluya el nombre de la dimensión financiera. Se quitan las dimensiones eliminadas. Puede especificar los valores de la dimensión antes de que se active una dimensión financiera. Sin embargo, una dimensión financiera no puede ser consumida en cualquier lugar hasta que se haya activado. Por ejemplo, no puede agregar una dimensión financiera a una estructura contable hasta que se active la dimensión financiera. Cuando se hace clic en **Activar**, todas las dimensiones se actualizan y muestran cambios de estado. 

## Conversiones
<a id="translations" class="xliff"></a>

En la página **Traducción de texto**, puede escribir texto para la dimensión financiera seleccionada en varios idiomas. En la página **Traducción de cuenta principal**, puede escribir texto para la cuenta principal en varios idiomas. 

## Anulaciones de entidad jurídica
<a id="legal-entity-overrides" class="xliff"></a>

No todas las dimensiones son válidas para todas las entidades jurídicas. Además, algunas dimensiones pueden tener relevancia solo durante un período específico. En estos casos, puede usar la sección **Anulaciones de entidad jurídica** para especificar las empresas para las que se debe suspender la dimensión, quién es el propietario y el período de tiempo que la dimensión está activa.

## Eliminar dimensiones financieras
<a id="deleting-financial-dimensions" class="xliff"></a>

Para ayudar a mantener la integridad referencial de los datos, nos es habitual que se puedan eliminar las dimensiones financieras. Si intenta eliminar una dimensión financiera, se evalúan los siguientes criterios:

- ¿La dimensión financiera se ha utilizado en las transacciones registradas o sin registrar o algún tipo de combinación de valor de dimensión?
- ¿La dimensión financiera se usa en estructura contable activa, estructura de regla avanzada o conjunto de dimensiones financieras?
- ¿La dimensión financiera forma parte de un formato de integración de dimensión financiera predeterminado?
- ¿La dimensión financiera se ha configurado como dimensión predeterminada?

Si se cumple cualquiera de los criterios, no puede eliminar la dimensión financiera.

