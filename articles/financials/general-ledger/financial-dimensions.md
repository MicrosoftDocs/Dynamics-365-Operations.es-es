---
title: Dimensiones financieras
description: Este tema describe los diferentes tipos de dimensiones financieras y cómo se configuran.
author: aprilolson
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ems.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 2fb325e143eff067e1c9d0f23a1f913fc2dc36f3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "317554"
---
# <a name="financial-dimensions"></a>Dimensiones financieras

[!include [banner](../includes/banner.md)]

Este tema explica los diferentes tipos de dimensiones financieras y cómo se configuran.

Use la página **Dimensiones financieras** para crear las dimensiones financieras que se pueden usar como segmentos de cuentas para los planes contables compartidos. Existen dos tipos de dimensiones financieras: dimensiones personalizadas y dimensiones respaldadas por entidad. Las dimensiones personalizadas se comparten entre entidades jurídicas y los valores los introduce y mantiene los usuarios. Para dimensiones respaldadas por entidad, los valores se definen en otra ubicación del sistema, como en Clientes o Tiendas. Algunas dimensiones respaldadas por entidad se comparten entre entidades jurídicas, mientras que otras dimensiones respaldadas por entidad son específicas de una empresa.

Una vez creadas las dimensiones financieras, use la página **Valores de la dimensión financiera** para asignar propiedades adicionales a cada dimensión financiera.

Puede usar dimensiones financieras para representar las entidades jurídicas. No es necesario crear las entidades jurídicas en Microsoft Dynamics 365 for Finance and Operations. No obstante, las dimensiones financieras no están diseñadas para abordar los requisitos operativos o empresariales de las entidades jurídicas. La funcionalidad de contabilidad de interunidad de Finance and Operations está diseñada para tratar solo los asientos contables creados por cada transacción.

Antes de configurar dimensiones financieras como entidades jurídicas, evalúe sus procesos empresariales en las áreas siguientes para determinar si esta configuración funcionará para su organización:

- Inventario
- Ventas y compras entre las dimensiones financieras y las entidades jurídicas
- Cálculo de impuestos y generación de informes
- Informes operativos

A continuación se muestran algunas limitaciones:

- Puede usar la funcionalidad de impuestos solo con entidades jurídicas, no con dimensiones financieras.
- Algunos informes no incluyen dimensiones financieras. Por lo tanto, para informar por dimensión financiera, puede que necesite modificar los informes.

## <a name="custom-dimensions"></a>Dimensiones personalizadas

Para crear una dimensión financiera definida por el usuario, en el campo **Usar valores de**, seleccione **Dimensión personalizada**.

También puede especificar una máscara de cuenta para limitar el importe y el tipo de información que puede especificarse para valores de dimensión. Puede especificar los caracteres que permanecen iguales para cada valor de dimensión, como letras o un guion (-). También puede especificar signos de número (\#) y ampersands (&) como marcadores de posición para los caracteres que se modificarán cada vez que se cree un valor de dimensión. Use un signo de número (\#) ) como marcador de posición para un número y un ampersand (&) como marcador de posición para una letra. El campo para la máscara de formato solo está disponible si selecciona el campo **Dimensión personalizada** en el campo **Usar valores desde**.

**Ejemplo**

Para limitar el valor de dimensión a letras "CC", un guion y tres números, debe especificar **CC\#\#\#** como la máscara de formato.

## <a name="entity-backed-dimensions"></a>Dimensiones respaldadas por entidad

Para crear una dimensión financiera respaldada por entidad, en el campo **Usar valores desde**, seleccione una entidad definida por el sistema en la que basar la dimensión financiera. Los valores de la dimensión financiera se crean después a partir de esta entidad. Por ejemplo, para crear valores de dimensión para proyectos, seleccione **Proyectos**. Después, se creará un valor de dimensión para cada nombre de proyecto. La página **Valores de la dimensión financiera** muestra los valores para la entidad. Si estos valores son específicos par la empresa, la página también muestra la empresa.

## <a name="activating-dimensions"></a>Activación de dimensiones

Al activar una dimensión financiera, se actualizará la tabla de modo que incluya el nombre de la dimensión financiera. Se quitan las dimensiones eliminadas. Puede especificar los valores de la dimensión antes de que se active una dimensión financiera. Sin embargo, una dimensión financiera no puede ser consumida en cualquier lugar hasta que se haya activado. Por ejemplo, no puede agregar una dimensión financiera a una estructura contable hasta que se active la dimensión financiera. Cuando se selecciona **Activar**, todas las dimensiones se actualizan y muestran cambios de estado.

## <a name="translations"></a>Conversiones

En la página **Traducción de texto**, puede escribir texto para la dimensión financiera seleccionada en varios idiomas. En la página **Traducción de cuenta principal**, puede escribir texto para la cuenta principal en varios idiomas. 

## <a name="legal-entity-overrides"></a>Anulaciones de entidad jurídica

No todas las dimensiones son válidas para todas las entidades jurídicas. Además, algunas dimensiones pueden tener relevancia solo durante un período específico. En estos casos, puede usar la sección **Anulaciones de entidad jurídica** para especificar las empresas para las que se debe suspender la dimensión, quién es el propietario y el período de tiempo que la dimensión está activa.

## <a name="deleting-financial-dimensions"></a>Eliminar dimensiones financieras

Para ayudar a mantener la integridad referencial de los datos, nos es habitual que se puedan eliminar las dimensiones financieras. Si intenta eliminar una dimensión financiera, se evalúan los siguientes criterios:

- ¿La dimensión financiera se ha utilizado en las transacciones registradas o sin registrar o en algún tipo de combinación de valor de dimensión?
- ¿La dimensión financiera se usa en estructura contable activa, estructura de regla avanzada o conjunto de dimensiones financieras?
- ¿La dimensión financiera forma parte de un formato de integración de dimensión financiera predeterminado?
- ¿La dimensión financiera se ha configurado como dimensión predeterminada?

Si se cumple cualquiera de los criterios, no puede eliminar la dimensión financiera.

## <a name="default-dimension-values"></a>Valores de dimensión predeterminados

Puede utilizar valores de registros maestros, como cliente y proveedor, como valores predeterminados en nuevas dimensiones. Cuando se crean nuevas dimensiones, el identificador del registro maestro se especifica en los valores de dimensión para dichos registros maestros. Por ejemplo, al crear un nuevo cliente, el identificador del cliente se especifica en la dimensión del cliente. Al crear pedidos de ventas, facturas, u otros documentos que requieren un identificador de cliente, se usan las reglas de establecimiento como valor predeterminado ya existentes, y el identificador del cliente se agrega al documento.

Esta función se controla mediante un valor de la dimensión. Este valor se denomina **Copiar la configuración con la dimensión de cada nuevo DimensionName creado**, donde **DimensionName** es el nombre de la dimensión. De forma predeterminada, esta característica está desactivada. Sin embargo, es posible activarla en cualquier momento.

Si ya existen registros para la dimensión, se actualizan los registros maestros cuando se activa la función. Sin embargo, los documentos y las transacciones existentes no se actualizan.

Si utiliza una plantilla para crear una registro maestro, asegúrese de que el valor de la plantilla para la dimensión principal está desactivada. Por ejemplo, si está creando clientes desde una plantilla, asegúrese de que la dimensión del cliente en la plantilla esté en blanco. El valor de dimensión del cliente se establecerá como valor predeterminado desde el nuevo número de cliente cuando se cree el nuevo cliente.  

## <a name="derived-dimensions"></a>Dimensiones derivadas

Puede configurar una dimensión para especificar información para otras dimensiones automáticamente al especificar dicha dimensión en un documento. Por ejemplo, si especifica el centro de coste 10, un valor **20** se puede especificar automáticamente en la dimensión de departamento.

Puede configurar valores derivados en la página de las dimensiones.

1. Seleccione una dimensión y después seleccione **Dimensiones derivadas**.

    La página **Dimensiones derivadas** incluye una cuadrícula. El segmento de dimensión seleccionado es la primera columna de la cuadrícula.

2. Agregue los segmentos que se deben derivar. Cada segmento aparece como una columna.

Especifique combinaciones de dimensiones que se deben derivar de la dimensión en la primera columna. Por ejemplo, para usar el centro de coste como la dimensión de la que se derivan el departamento y la ubicación, especifique el centro de coste 10, el Departamento 20, y la ubicación 30. A continuación, al especificar el centro de coste 10 en un registro maestro o en una página de transacción, el departamento 20 y la ubicación 30 se especifican de forma predeterminada.

### <a name="overriding-existing-values-with-derived-dimensions"></a>Anular valores existentes con dimensiones derivadas
 
De forma predeterminada, el proceso de la dimensión derivada no anula los valores existentes para las dimensiones derivadas. Por ejemplo, si especifica en el centro de coste 10 y ninguna otra dimensión, el departamento 20 y la ubicación 30 se especifican de forma predeterminada. Sin embargo, si cambia el centro de coste, los valores que ya se establecieron no se modifican. Por lo tanto, puede establecer dimensiones predeterminadas en registros maestros y dichas dimensiones no se cambiarán por dimensiones derivadas.

Puede cambiar el comportamiento de dimensiones derivadas para anular valores existentes seleccionando la casilla de verificación **Reemplazar los valores de dimensión existentes con valores derivados** en la página **Dimensiones derivadas**. Si se selecciona este campo, puede especificar una dimensión con valores de dimensión derivados y dichos valores de dimensión derivados anulan cualquier valor que ya existe. Usando el ejemplo anterior, si especifica en el centro de coste 10 y ninguna otra dimensión, el departamento 20 y la ubicación 30 se especifican de forma predeterminada. Sin embargo, si los valores eran ya el departamento 50 y la ubicación 60, ahora los valores se cambiarán al departamento 20 y la ubicación 30.
 
Las dimensiones derivadas con este valor no sustituyen automáticamente los valores existentes de dimensiones predeterminadas cuando se establecen como valor predeterminado los valores de dimensión. Los valores de dimensión solo se anularán si especifica un nuevo valor de dimensión en una página y hay valores derivados existentes para dicha dimensión en la página.

### <a name="preventing-changes-with-derived-dimensions"></a>Evitar cambios con dimensiones derivadas
 
Cuando usa **Agregar segmento”** en la **Página de dimensiones derivadas** para agregar un segmento como dimensión derivada, una opción se proporciona en la parte inferior de la página **Agregar segmento** que le permite evitar cambios a esa dimensión cuando se deriva en una página. La configuración predeterminada está desactivada, por lo que no impide que se cambien los valores de dimensión derivados. Cambie el valor a **Sí** si desea impedir que la dimensión se modifique después de que se haya derivado. Por ejemplo, si el valor de la dimensión de departamento se deriva del valor de la dimensión de centro de coste, el valor de departamento no se puede modificar si la configuración **Evitar cambios** es **Sí**. 
 
El valor no impide cambios si el valor de dimensión es válido pero no aparece en la lista de dimensiones derivadas. Por ejemplo, si derivan el departamento 20 del centro de coste 10 y especifica el centro de coste 10, no posible editar el departamento 20. Sin embargo, si especifica el centro de coste 20 y no aparece en la lista de dimensiones derivadas del centro de coste, puede editar el valor de departamento. 
 
En todos los casos, el valor de cuenta y todos los valores de dimensiones seguirán validándose con las estructuras contables después de que se hayan aplicado los valores de dimensiones derivadas. Si usa dimensiones derivadas y se produce un error de validación cuando se utilizan en una página, debe cambiar los valores de dimensiones derivadas en la página de dimensiones derivadas antes de que pueda utilizarlos en las transacciones. 
 
Cuando cambia las dimensiones de la ficha desplegable **Dimensiones financieras**, la dimensión que se marca para evitar cambios no se puede editar. Si especifica una cuenta y dimensiones en el control segmentado de la entrada de una página, las dimensiones se pueden editar. Sin embargo, cuando mueva el resalte fuera del control de entrada segmentada y lo mueva a otro campo o ejecute una acción, la cuenta y las dimensiones se validarán de acuerdo con la lista de las dimensiones derivadas y las estructuras contables para asegurarse de que ha especificado la configuración adecuada. 

### <a name="derived-dimensions-and-entities"></a>Dimensiones derivadas y entidades

Puede configurar los segmentos de dimensiones derivadas y valores usando entidades.

- La entidad de dimensiones derivadas configura las dimensiones de conducción y los segmentos que se usan para dichas dimensiones.
- La entidad valor de dimensiones derivadas permite importar los valores que se deben derivar de cada dimensión de conducción.

Al usar una entidad para importar datos, si dicha entidad importa dimensiones, las reglas de dimensión derivadas se aplican durante la importación a menos que la entidad anule específicamente dichas dimensiones.

Para obtener más información, consulte los siguientes temas:

- [Definir dimensiones financieras](tasks/define-financial-dimensions.md)
- [Mantener plantillas predeterminadas de la dimensión financiera](tasks/maintain-financial-dimension-default-templates.md)
