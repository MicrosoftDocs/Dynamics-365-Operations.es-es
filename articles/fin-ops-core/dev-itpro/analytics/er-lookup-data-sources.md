---
title: Configurar las fuentes de datos de búsqueda para utilizar parámetros específicos de la aplicación de informes electrónicos
description: En este artículo se explica cómo puede configurar orígenes de datos de búsqueda en formatos de informes electrónicos (ER) para usar parámetros específicos de la aplicación de ER.
author: kfend
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.custom: ''
ms.assetid: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
ms.openlocfilehash: f3ce5837b1d20860588848a1b518b3d801a05db4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285133"
---
# <a name="configure-lookup-data-sources-to-use-er-application-specific-parameters"></a>Configurar las fuentes de datos de búsqueda para utilizar parámetros específicos de la aplicación de informes electrónicos 

[!include[banner](../includes/banner.md)]

La característica de parámetros específicos de la aplicación de [informes electrónicos (ER)](general-electronic-reporting.md) permite a los usuarios avanzados configurar el filtrado de datos en un formato de ER de modo que se base en un conjunto de reglas abstractas. Este conjunto de reglas se puede configurar para utilizar el origen de datos del tipo **búsqueda** disponible en un formato de ER. Luego puede especificar reglas reales más allá de los diseñadores de componentes de ER mediante la interfaz de usuario (UI) que se genera automáticamente en función de la configuración del origen de datos de **búsqueda** del formato de ER correspondiente y de los datos de la entidad jurídica actual. Eventualmente, el origen de datos de **búsqueda** del formato ER accederá a las reglas especificadas cuando se ejecuta este formato ER.

> [!NOTE]
> Utilice las fuentes de datos configuradas del formato ER editable para especificar qué datos de la aplicación se utilizan para configurar reglas reales.

Utilizar el [Diseñador de operaciones de ER](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) para traer una fuente de datos de tipo de **búsqueda** en su formato ER. La fuente de datos debe configurarse para describir cómo se ven sus reglas abstractas, incluidas las siguientes:

   - El conjunto de parámetros de cierto tipo de datos cuyo valor se proporciona para especificar una sola regla.
   - El tipo de valor de cierto tipo de datos que es devuelto por una sola regla cuando esta regla se considera la más apropiada entre otras.

Puede configurar los siguientes tipos de orígenes de datos de **búsqueda** según el tipo de valor devuelto por cualquier regla configurada:

   - Utilizar el tipo **Modelo de datos\Búsqueda** cuando deba devolverse un valor de enumeración de modelo.
   - Utilizar el tipo **Dynamics 365 Operations\Búsqueda** cuando un valor de enumeración de la aplicación o un valor de aplicación de [tipo de datos extendido](../extensibility/extensible-edts.md) debe devolverse.
   - Utilizar el tipo **Enuemración de formato\Búsqueda** cuando deba devolverse un valor de enumeración de formato.

La siguiente ilustración muestra cómo se puede configurar una enumeración de formato en el formato ER de muestra.

   ![Mostrar una enumeración de formato como base para la fuente de datos de búsqueda configurada.](./media/er-lookup-data-sources-img1.gif)

La siguiente ilustración muestra los componentes de formato que se configuraron para informar diferentes tipos de impuestos en una sección diferente de un informe generado.

   ![Mostrar las secciones de formato para informar por separado diferentes tipos de impuestos.](./media/er-lookup-data-sources-img2.png)

La siguiente ilustración muestra cómo el diseñador de operaciones de ER permite la adición de una fuente de datos del tipo **Formato de enumeración\Búsqueda**.  La fuente de datos agregada se configura para devolver un valor de la enumeración de formato de `List of taxation levels`.

   ![Agregar una fuente de datos ER del tipo de enumeración\Búsqueda de formato.](./media/er-lookup-data-sources-img3.gif)

La siguiente ilustración muestra cómo la fuente de datos agregada está configurada para usar el campo **Código** de la lista de registros **Model.Data.Tax** del origen de datos **Modelo** como parámetro que debe especificarse para cada regla configurada.

![Configuración de parámetros de la fuente de datos agregada del tipo de enumeración\Búsqueda de formato.](./media/er-lookup-data-sources-img4.gif)

La fuente de datos `Model.Data.Tax` agregada está configurada para especificar un código de impuestos para cada regla configurada accediendo a los registros de la tabla de aplicaciones **TaxTable**.

   ![Revisión del origen de datos de búsqueda de una empresa de tipo de enumeración\Búsqueda de formato.](./media/er-lookup-data-sources-img5.gif)

Puede configurar las reglas de búsqueda para el formato de ER seleccionado mediante la interfaz de usuario que se alinea automáticamente con la estructura de la fuente de datos configurada. Actualmente, esta interfaz de usuario requiere que para cada regla, especifique el valor devuelto como el formato de valor de enumeración de `List of taxation levels`, así como el código de impuestos como parámetro.

   ![Configure las reglas para la fuente de datos configurada.](./media/er-lookup-data-sources-img6.gif)

La siguiente ilustración muestra cómo la fuente de datos `Model.Data.Summary.LevelByLookup` del tipo **Campo calculado** se puede configurar para llamar a la fuente de datos de **búsqueda** configurada que proporciona los parámetros necesarios. Para procesar esta llamada en tiempo de ejecución, ER revisa la lista de reglas configuradas en la secuencia definida para ubicar la primera regla que satisface las condiciones proporcionadas. En este ejemplo, es la regla que contiene el código de impuestos que coincide con el proporcionado. Como resultado, se encuentra la regla más adecuada y esta fuente de datos devuelve el valor de enumeración configurado para la regla encontrada.

> [!NOTE]
> Se lanza una excepción cuando no se encuentra una regla aplicable. Para evitar estas excepciones, configure reglas adicionales al final de la lista de reglas para manejar los casos en los que se proporciona un valor no configurado o ningún valor. Utilice las opciones **\*No en blanco**\* y **\*En blanco**\* en consecuencia.  
>
> ![Agregar una fuente de datos para llamar a la fuente de datos de búsqueda configurada.](./media/er-lookup-data-sources-img7.png)

Cuando configura la opción **Compañías cruzadas** como **Sí** para la fuente de datos de búsqueda editable, agrega un nuevo parámetro requerido **Empresa** al conjunto de parámetros de esta fuente de datos. El valor del parámetro **Empresa** debe especificarse en tiempo de ejecución cuando se llama a la fuente de datos de búsqueda. Cuando se especifica el código de la empresa en tiempo de ejecución, las reglas configuradas para esta empresa se utilizan para encontrar la regla más adecuada y se devuelve el valor correspondiente. La siguiente ilustración muestra cómo puede hacer esto y cómo se cambia el conjunto de parámetros de la fuente de datos editables.

   ![Revisión del origen de datos de búsqueda entre empresas de tipo de enumeración\Búsqueda de formato.](./media/er-lookup-data-sources-img8.gif)

> [!NOTE]
> Seleccione cada empresa por separado para configurar el conjunto de reglas para esta fuente de datos de búsqueda del formato ER editable. Se lanza una excepción en tiempo de ejecución cuando se llama a la búsqueda entre empresas con el código de la empresa para la que no se completó la configuración de búsqueda.
>
> Asegúrese de otorgar permisos a un usuario que ejecute el formato ER con la fuente de datos de **búsqueda** entre empresas para acceder a los datos de todas las empresas que están dentro del alcance de esta fuente de datos. De lo contrario, se lanza una excepción en tiempo de ejecución.

A partir de la versión 10.0.19, las capacidades ampliadas de las fuentes de datos de **búsqueda** están disponibles. Cuando configura la opción **Extendido** en **Sí** para la fuente de datos de búsqueda editable, la fuente de datos de búsqueda configurada se transforma en la fuente de datos estructurados que ofrece las capacidades adicionales para analizar el conjunto de reglas configurado. En la ilustración siguiente se muestra esta transformación.

   ![Revisión del origen de datos de búsqueda estructurado de tipo de enumeración\Búsqueda de formato.](./media/er-lookup-data-sources-img9.gif)

- El subelemento de **búsqueda** está diseñado como una función para encontrar la regla más apropiada del conjunto de reglas configurables según el conjunto de parámetros proporcionado.
- El subelemento **IsLookupResultSet** está diseñado como una función para aceptar el valor proporcionado de la fuente de datos de enumeración base y devolver el valor *booleano* de **True** cuando el conjunto de reglas contiene al menos una regla para la cual el valor de enumeración proporcionado se configuró como valor devuelto. Esta función devuelve el valor *Booleano* de **False** cuando no hay reglas configuradas para devolver el valor de enumeración proporcionado.
- El subelemento de **configuración** está diseñado como una función que devuelve el conjunto de reglas configuradas como registros de una lista de registros. Los valores devueltos y el conjunto de parámetros de las reglas configuradas se presentan en cada registro devuelto como campos de los tipos de datos relevantes:

    - El valor devuelto se presenta como campo **Resultado de la búsqueda**.
    - Los parámetros configurados se presentan como campos con nombres de parámetros (campo **Código** en este ejemplo).

Para obtener más información sobre cómo configurar el origen de datos de **búsqueda**, vea [Configure los formatos de ER para utilizar parámetros que se especifican por entidad jurídica](er-app-specific-parameters-configure-format.md). Para aprender a configurar las reglas de búsqueda, consulte [Configurar los parámetros de un formato ER por entidad legal](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar formatos de informes electrónicos para usar parámetros especificados por entidad jurídica](er-app-specific-parameters-configure-format.md)

[Configurar los parámetros de un formato de informes electrónicos por entidad jurídica](er-app-specific-parameters-set-up.md)
