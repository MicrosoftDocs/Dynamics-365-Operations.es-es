---
title: Utilizar una ruta relativa en vínculos de datos de modelos y formatos de ER
description: La herramienta Informes electrónicos le permite definir estructuras en formato electrónico y, a continuación, describir cómo deben rellenarse esas estructuras.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 555e7c78dae85034bfcde417d8ac86bea5073d85
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565769"
---
# <a name="use-a-relative-path-in-data-bindings-of-er-models-and-formats"></a>Utilizar una ruta relativa en vínculos de datos de modelos y formatos de ER

[!include[banner](../includes/banner.md)]

La herramienta Informes electrónicos (ER) permite a los usuarios definir estructuras en formato electrónico y, a continuación, describir cómo deben rellenarse esas estructuras con los datos y algoritmos que existen en la aplicación. Para obtener más información, consulte [Crear configuraciones de informes electrónicos (ER)](electronic-reporting-configuration.md). Para especificar el flujo de datos con el fin de recuperar los datos de Finance and Operations y utilizarlos para generar un documento electrónico, debe hacer lo siguiente:

- Enlace los orígenes de datos configurados con los elementos del [modelo de datos](general-electronic-reporting.md#data-model-and-model-mapping-components) específico del dominio diseñado. La estructura del modelo y los orígenes de datos seleccionados podrían formar parte de una estructura jerárquica compleja. Debido a esto, los enlaces finales pueden ser bastante grandes y contener muchos elementos de diferentes tipos (por ejemplo, relaciones, tablas y métodos,). Los enlaces pueden ser menos legibles y bastante complejos de revisar y entender, especialmente para los que no son propietarios. 
- Enlace elementos del modelo de datos con componentes del [formato](general-electronic-reporting.md#FormatComponentOutbound) para definir qué datos se rellenarán del modelo de datos a la salida del formato generado.

Para mejorar la facilidad de uso de los diseñadores de asignación de ER, se ha liberado la función de [ruta relativa](er-formula-language.md#relative-path). De forma predeterminada, la opción de representación de la ruta relativa está activada para cualquier nueva instancia de la aplicación donde se habilita la experiencia de diseño de ER ( Microsoft Dynamics 365 Finance, Microsoft Regulatory Configuration Service). Implementamos el parámetro de la ruta relativa de modo que los usuarios puedan seguir utilizando la ruta completa cuando trabajen con esta presentación de enlaces de ER.

[![Parámetros de usuario](./media/relative-path-01.png)](./media/relative-path-01.png)

 
Cuando se activa el parámetro de uso de la ruta relativa, un único carácter @ reemplaza la ruta del elemento principal en el enlace del elemento del modelo actual. La ruta de enlace completa se acorta, lo que hace que toda la asignación sea más obvia y más fácil de entender. En la mayoría de los casos, no se requiere desplazamiento adicional en el diseñador de ER para ver todos los enlaces del modelo de datos.

[![Diseñador de asignación de modelo](./media/relative-path-02.png)](./media/relative-path-02.png)
 
Cuando empiece a diseñar una nueva expresión de ER, debe introducir solo un carácter para definir un enlace a un campo del elemento principal.

[![Diseñador de fórmula](./media/relative-path-03.png)](./media/relative-path-03.png)
 
Si decide cambiar el origen de datos del elemento del modelo principal, con un uso de ruta absoluta, tiene que volver a enlazar manualmente este elemento del modelo, así como todos los elementos anidados, a un nuevo origen de datos. Cuando se activa el uso de una ruta relativa y selecciona un nuevo origen de datos que se enlazará a un elemento principal, se le ofrece una opción para volver a enlazar automáticamente todos los elementos anidados de este elemento principal con un clic.

[![Reemplazar mensaje de ruta existente](./media/relative-path-04.png)](./media/relative-path-04.png)
 
Si confirma que vuelve a enlazar elementos anidados, el nuevo elemento principal se colocará en la ruta de cada elemento anidado que contenga el elemento principal existente.
Esta característica no interrumpe la compatibilidad con versiones anteriores del marco de ER. Todas las configuraciones de ER previamente diseñadas funcionarán con esta nueva característica, y no se requiere ninguna actualización o conversión.

> [!NOTE]
> Todos los cambios introducidos por la modificación masiva de enlaces de elementos anidados en asignaciones de modelo se guardan correctamente en un delta de configuración (seguimiento de cambios). Esto permite a los clientes reorganizar su versión derivada de asignaciones de modelo a cualquier nueva versión base de esta que se ha modificado mediante esta nueva característica.

## <a name="additional-resources"></a>Recursos adicionales

[Idioma de fórmula ER](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]