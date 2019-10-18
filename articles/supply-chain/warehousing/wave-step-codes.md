---
title: Códigos de paso de oleada
description: Este tema proporciona una visión general de los códigos de paso de la oleada y cómo se usan.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f89c6098db9e2e3a9aa4ee3666e4b9ae608f054
ms.sourcegitcommit: d8f1135cdbc2deca70bc4b2805a0519253c9a31f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "1992366"
---
# <a name="wave-step-codes"></a>Códigos de paso de oleada

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

## <a name="about-wave-step-codes"></a>Acerca de los códigos del paso de oleada

Los códigos del paso de oleada son códigos que los usuarios pueden configurar y usar para vincular instancias específicas de los métodos de la oleada a una plantilla correspondiente. Las plantillas incluyen las plantillas para reabastecimiento, la puesta en contenedores, la impresión de etiquetas, el edificio de carga y la ordenación.

Cuando los códigos del paso de oleada no se usan, los usuarios deben introducir texto para referenciar una plantilla específica del método de la instancia de oleada. El texto libre suele tener errores, por lo que los usuarios deben asegurarse de que el texto de paso de oleada que añaden para un método específico de paso de oleada en una plantilla de oleada coincide exactamente con el texto de paso de oleada en la plantilla objetivo.

Los códigos del paso de oleada para un tipo de etapa específico de la oleada se configuran en una página independiente. Para cada instancia del método del paso de oleada en una plantilla de oleada que precisa un código del paso de oleada, el código del paso de oleada se debe seleccionar en una lista desplegable. La selección de una lista desplegable reemplaza la entrada de texto en la factura de servicios y ayuda a reducir el riesgo y el impacto de los errores humanos. Los códigos de configuración se usan para vincular un método de paso de oleada en una plantilla de oleada a una plantilla objetivo para el método.

> [!NOTE]
> El uso de la función de los códigos de paso de la oleada es opcional, y gestionada por entidad jurídica. Por lo tanto, si una entidad jurídica específica el uso de la característica, todos los códigos existentes del paso de oleada en esa entidad jurídica se actualizan a la nueva estructura.

## <a name="setup-demo"></a>Demostración de instalación 

Para esta demostración, los datos de prueba deben estar instalados y debe usar los datos de la compañía de prueba **USMF**.

### <a name="enable-wave-step-codes"></a>Habilitar códigos de paso de oleada

Siga estos pasos para activar la característica de los códigos del paso de oleada.

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
2. En la pestaña **General**, en la ficha desplegable **Procesado de oleadas**, establezca la opción **Habilitar códigos de paso de oleada** en **Sí**.

Todos los textos libres de paso de oleada se actualizarán a la nueva estructura. Una vez que la actualización se complete para una entidad jurídica, la opción **Habilitar códigos de paso de oleada** dejará de estar disponible en la página **Parámetros de la gestión de almacenes** .

Las validaciones se realizan durante la actualización y si falla la actualización, recibirá un mensaje de error. Una actualización puede fallar debido a los conflictos siguientes:

- Existen textos libres duplicados de paso de oleada.
- Existen personalizaciones.
- Un texto libre de paso de oleada está asociado con una instancia de método de paso de oleada que no coincide con el tipo de plantilla esperado.

Una vez haya resuelto los conflictos que ha identificado durante las validaciones, puede volver a ejecutar el proceso de actualización.

Cuando la actualización tiene éxito, la página **Códigos de paso de oleada** (**Administración de almacenes \> Configuración \> Oleadas  \> Códigos de paso de oleada**) pasa a estar disponible. Esta página muestra los códigos de paso de oleada actualizados cuando la función de los códigos de paso de oleada se ha activado.

### <a name="create-new-wave-step-codes"></a>Crear códigos de paso de oleada nuevos

Puede usar la página **Códigos de paso de oleada** para crear y eliminar códigos de paso de oleada.

Cada nuevo código de paso de oleada y su ID asociada deben ser únicos en todos los tipos de paso de oleada y deben definirse para un tipo de paso de oleada específico.

### <a name="apply-wave-step-codes"></a>Aplicar códigos del paso de oleada

Después de definir los códigos adecuados de paso de oleada, se pueden aplicar a los métodos de proceso de oleada.

Para aplicar los códigos de paso de oleada, vaya a la plantilla adecuada de destino. Aquí están las plantillas de destino a los que están diseñados para apuntar los códigos de paso de oleada:

- **Plantillas de reabastecimiento:** Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de reabastecimiento
- **Plantillas de planificación de carga:** Gestión de almacén \> Configuración \> Carga \> Plantillas de planificación de carga
- **Plantillas de ordenación:** Gestión de almacén \> Configuración \> Embalado \> Plantillas de ordenación salientes
- **Plantillas de contenedores:** Gestión de almacén \> Configurar \> Contenedores \> Plantillas de planificación de contenedor
- **Plantillas de impresión de etiqueta:** Gestión de almacén \> Configuración \> Ruta de documento \> Plantillas de etiqueta de oleada

Las plantillas en esta lista se aplican cuando se hacen referencia de un método de proceso de oleada seleccionado en una plantilla de oleada. Cuando el código del paso de oleada en un método de proceso de oleada en una plantilla de oleada coincide con el código de paso de oleada en uno de los tipos de plantilla, la plantilla se aplica.

### <a name="sample-scenario"></a>Escenario de ejemplo

El siguiente procedimiento ayuda a garantizar que la plantilla de reabastecimiento que ha creado se use para la plantilla de oleada.

1. Vaya a **Gestión de almacén \> Configuración \> Oleadas \> Códigos de paso de oleada** y cree un código de paso de oleada para el tipo **Reabastecimiento**.
2. Vaya a **Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de reabastecimiento** y cree una plantilla de reabastecimiento.
3. En la plantilla de reabastecimiento, seleccione el código de paso de oleada que ha creado para el tipo **Reabastecimiento**.
4. Vaya a **Gestión de almacén \> Configuración \> Oleadas \> Plantillas de oleada** y seleccione la plantilla de oleada que quiere usar.
5. En la plantilla, en la ficha desplegable **Métodos** seleccione el método **Reabastecimiento**.
6. En el campo **Código de paso de oleada**, selección el código de paso de oleada que seleccionó en la plantilla reabastecimiento.
