---
title: Orígenes de datos entre empresas en informes electrónicos (ER)
description: En este tema se explica cómo puede usar orígenes de datos entre empresas en informes electrónicos (ER).
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERModelMappingDesigner, ERFormatMappingLegalEntityFilterTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 1a5c05b65c9022220056947471e95b703d923dc5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680839"
---
# <a name="cross-company-data-sources-in-electronic-reporting-er"></a>Orígenes de datos entre empresas en informes electrónicos (ER)

[!include[banner](../includes/banner.md)]

Puede diseñar formatos de informes electrónicos (ER) para generar documentos salientes en varios formato. Cuando se genera un documento, un formato de ER denomina orígenes de datos que se configuraron en una asignación correspondiente del modelo de ER. Para configurar el acceso a las tablas de la aplicación para la recuperación del registro, puede usar los orígenes de datos de ER del tipo **Registros de tabla**. Cuando la tabla de acceso es una tabla compartida (es decir, una tabla en la que los datos se guardan sin un identificador de empresa), este origen de datos devuelve todos los registros. Cuando la tabla de acceso es una tabla que depende de la empresa (es decir, una tabla en la que los datos se guardan por empresa), este origen de datos solo devuelve los registros que se han guardado para la empresa actual (es decir, el contexto de la empresa bajo la que el formato de ER se está ejecutando).

Cada origen de datos del tipo **Registros de tabla** en una asignación de modelo ahora se podrá marcar como origen de datos entre empresas. Por tanto, puede utilizar orígenes de datos del tipo **Registros de tabla** para acceder a datos entre empresas en tablas de la aplicación.

Si marca un origen de datos como entre empresas, se produce el siguiente comportamiento:

- Para un origen de datos que hace referencia a cualquier tabla compartida a excepción de CompanyInfo, el origen de datos devuelve todos los registros que existen en la tabla de referencia. 
- Para un origen de datos que hace referencia a la tabla CompanyInfo, aunque CompanyInfo sea una tabla compartida, el origen de datos devuelve los registros que contienen el identificador de una empresa del ámbito definido.
- Para cualquier tabla que depende de la empresa, el origen de datos devuelve los registros de la tabla de referencia que contienen el identificador de una empresa del ámbito definido.

En el cuadro de diálogo de consulta del sistema, cuando la opción **Pedir consulta** está activada para cualquier origen de datos que esté marcada como entre empresas, puede seleccionar manualmente una o más empresas para incluirlas en la pestaña **Intervalo de empresas** .

> [!IMPORTANT]
> Como otros filtros, el filtro de empresa se conserva como un valor utilizado por última vez para consultas cuando ejecute un formato de ER. El filtro no se modifica automáticamente si cambia el valor entre empresas para un origen de datos. Para utilizar un valor entre empresas diferente para otro origen de datos, elimine la correspondiente selección específica del usuario.

Para cada origen de datos que esté marcado como entre empresas, puede seleccionar los registros que desee utilizando las funciones **FILTRO** y **DONDE** en expresiones de ER. El campo **dataAreaID** se puede usar como un identificador de empresa. Actualmente, el campo **dataAreaID** se limita a los siguientes tipos de condiciones cuando se utiliza la función **FILTRO**:

- Solo se admiten las condiciones que tienen una única comparación del campo **dataAreaID**.
- Solo se permiten las comparaciones con expresiones que no dependen de elementos de la lista de registros.

Por tanto, la siguiente expresión es válida.

```ER Expression
FILTER (MyTable, MyTable.dataAreaID = $StringUserInputParameter)
While shown below expressions will not pass the validation:
FILTER (MyTable, MyTable.dataAreaID = MyTable2RecordsList.MyField)
FILTER (MyTable, 
    OR(
        MyTable.dataAreaID = $StringUserInputParameter1,
        MyTable.dataAreaID = $StringUserInputParameter2
    )
)
```

De forma predeterminada, el ámbito incluye todas las empresas de la aplicación actual. Sin embargo, puede estar limitado. Para limitar el ámbito de acceso a datos entre empresas para un único formato de ER, asigne una jerarquía organizativa específica para el formato. Cuando una jerarquía se define para un formato de ER, solo se devuelven los registros para las entidades jurídicas que están presentes en la jerarquía asignada, aunque el formato llama a orígenes de datos entre empresas. Cuando se define una referencia a una jerarquía que ya no existe para un formato de ER, se aplica el ámbito predeterminado y el formato llama a orígenes de datos entre empresas. En esta situación, se devuelven los registros para todas las empresas de la aplicación.

Tenga en cuenta que cuando se activa la opción **Usar borrador** para lo asignado a una única jerarquía organizativa del formato de ER, las entidades jurídicas de la versión de borrador de esta jerarquía se utilizarán para identificar el ámbito para orígenes de datos entre empresas. Si no existe la versión de borrador, las entidades jurídicas de la última versión publicada de esta jerarquía organizativa se utilizarán para esto.

Tenga en cuenta que cuando se desactiva la opción **Usar borrador** para lo asignado a una única jerarquía organizativa del formato de ER, las entidades jurídicas de la última versión publicada de esta jerarquía organizativa se utilizarán para identificar el ámbito para orígenes de datos entre empresas. La efectividad de la fecha de jerarquías organizativas no se admite aún en el marco de ER.

La jerarquía se puede asignar a un formato en una página específica a la que se puede acceder desde el espacio de trabajo de ER o mediante el elemento de menú **Administración de la organización \> Informes electrónicos \> Filtro de entidad jurídica para formatos**. Para acceder a la página, debe concederse al usuario el privilegio **Mantener filtros de la entidad jurídica para formatos** (ERMaintainFormatMappingLegalEntityFilters). Se aplica la restricción del ámbito de las entidades jurídicas basadas en jerarquías para el formato, además de la restricción que el usuario puede especificar manualmente en el cuadro de diálogo de consulta del sistema. La intersección de estas restricciones se utiliza cuando se ejecuta el formato.

Para obtener más información acerca de esta función, reproduzca la guía de tareas **ER Acceder a registros de tablas que dependen de la empresa en modo entre empresas**, que forma parte del proceso empresarial 7.5.4.3 Adquirir o desarrollar componentes de soluciones y servicios de TI (10677) y puede descargarse del [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Esta guía de tareas le guía por el proceso de configurar una asignación del modelo de ER y el formato de ER para acceder a las tablas de la aplicación en modo entre empresas.

Descargue los siguientes archivos para completar la guía de tareas:

- [Configuración del modelo de ER - CrossCompanyDataAccessModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [Configuración del formato de ER - CrossCompanyDataAccessFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]