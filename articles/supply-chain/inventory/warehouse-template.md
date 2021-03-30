---
title: Configurar un almacén mediante una plantilla de configuración de almacén
description: Este tema explica cómo configurar un almacén mediante una plantilla de configuración de almacén.
author: perlynne
manager: tfehr
ms.date: 11/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportEnhanced, DMFDefinitionGroupTemplate, DMFEntityTemplateDefinitionLoadDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 7bf69ccec59f2c540d71d44347bd99dc2378dc4c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224987"
---
# <a name="set-up-a-warehouse-by-using-a-warehouse-configuration-template"></a>Configurar un almacén mediante una plantilla de configuración de almacén

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar un almacén mediante una plantilla de configuración de almacén. Existen varias plantillas de configuración predefinidas que puede usar. Para obtener información sobre cómo usar estas plantillas, vea [Plantillas de datos de configuración](../../dev-itpro/data-entities/configuration-data-templates.md).

## <a name="scenarios-where-configuration-templates-can-be-helpful"></a>Situaciones de ejemplo donde las plantillas de configuración pueden ser útiles

Las plantillas de configuración pueden ser útiles en diversos escenarios. A continuación se incluyen algunos ejemplos:

- Ha completado y probado una configuración en un entorno de prueba y ahora se desea copiar la configuración en un entorno de producción.
- Desea extender la configuración del almacén a varias entidades jurídicas o crear un nuevo almacén en la misma entidad jurídica.
- Desea prepararse rápidamente para una demostración de la funcionalidad de almacén.
- Desea que los artículos existentes y los almacenes utilicen la funcionalidad de Gestión de almacenes en lugar de la funcionalidad en Gestión del inventario.

Este tema se centra en estos primeros escenarios. Muestra cómo puede usar una plantilla de configuración para copiar una configuración desde un entorno de prueba a un entorno de producción.

## <a name="copy-a-configuration-setup-from-a-test-environment-to-a-production-environment"></a>Copiar una configuración desde un entorno de prueba a un entorno de producción

Para este escenario, la configuración para un almacén y algunos procesos de transacción ya existen en un entorno de prueba. Ahora desea copiar la configuración para almacén del entorno de prueba a un entorno de producción.

> [!NOTE]
> Es importante que incluya otros datos de configuración relacionados al copiar una configuración. Por ejemplo, desea configurar productos copiando la configuración de un entorno de prueba. Sin embargo, no puede configurar una ubicación fija de recogida para un producto antes que el producto esté creado. Aunque las plantillas de configuración individuales no admiten este tipo de dependencia, hay plantillas de datos predeterminados que lo admiten. Es fácil incluir estas plantillas de datos predeterminados en un proceso de configuración.

### <a name="export-a-default-warehouse-template"></a>Exportar una plantilla de almacén predeterminado 

1. Abra el espacio trabajo **Administración de datos** .

    > [!NOTE]
    > Si usa este área de trabajo por primera vez, debe cargar todas las entidades de datos antes de continuar.

2. Seleccione el icono **Plantillas** y, a continuación seleccione **Cargar plantillas predeterminadas** para cargar las plantillas predeterminadas.

    > [!NOTE]
    > **Cargar plantillas predeterminadas** solo está disponible en la vista **Ampliada**. Seleccione **Parámetros del marco** y, a continuación, en el campo **Valores predeterminados de la vista**, seleccione **Vista ampliada**.

3. Una vez que las plantillas predeterminadas se cargan, puede cambiarlas de modo que coincidan con los requisitos empresariales.

    > [!NOTE]
    > Para cargar las plantillas predeterminadas y plantillas de importación, debe tener acceso de administrador del sistema. Este requisito ayuda a garantizar que todas las entidades se carguen correctamente en la plantilla.

4. Asegúrese de que se encuentra en la entidad legal de la que desea exportar datos específicos de la empresa.
5. En el área de trabajo, seleccione **Exportar**.
6. Cree un nuevo proyecto de exportación.
7. Seleccione **+ Agregar plantilla** y busque la plantilla del almacén predeterminada **400 - WMS**. Esta plantilla agrega entidades de datos para la configuración del almacén.

    > [!NOTE]
    > Si los datos que va a exportar se deben filtrar (por ejemplo, desea exportar únicamente los datos que estén relacionads con un almacén específico), debe evaluar cada entidad de datos y agregar el filtro mediante una consulta. Como alternativa, puede exportar todos los datos y luego eliminar los registros que no se requieren en los archivos de destino.

8. Seleccione **Exportar**. Se exportan los datos relacionados con todas las entidades de datos en el proyecto.

Puede descargar un archivo zip para el paquete de datos. Este archivo contiene todos los datos en el formato seleccionado (por ejemplo, formato Excel). Como se ha mencionado, algunos registros en los archivos del paquete de datos podrían tener que actualizarse antes de poder importarlos en el entorno de producción. Si actualiza un registro, asegúrese de no cambiar el nombre del archivo.

### <a name="import-a-warehouse-configuration-setup"></a>Importar una configuración de almacén

1. En el entorno de destino, asegúrese de que se encuentra en la empresa en la que desea importar los datos del almacén.

    > [!NOTE]
    > Antes de realizar la importación, debe identificar cualquier dependencia de datos. Por ejemplo, la plantilla **Administración de almacenes** incluye una entidad de datos que se llama **Códigos de disposición de almacén**. Esta entidad contiene los datos relacionados con la página de configuración **Códigos de disposición** (**Administración de almacenes** > **Configuración** > **Dispositivo móvil** > **Códigos de disposición**). Si una configuración existente ya gestiona el proceso de devolución para los pedidos de ventas, el campo **Código de disposición de devolución** contiene un valor. El código de disposición en este campo está relacionado con la entidad de los datos **Código de disposición**, que forma parte de la plantilla **Ventas y marketing**. Si los datos de la entidad de los datos **Código de disposición** no se importa antes de los datos del campo **Códigos de disposición de almacén**, la importación fallará.

2. En el espacio de trabajo **Administración de datos**, seleccione **Importación**.
3. Cree un nuevo proyecto de importación.
4. Seleccione **+ Agregar archivo** y cargue el archivo zip para el paquete de datos.
5. Seleccione **Importar**. En el vista **Ampliado**, puede usar la opción **Filtro** para obtener rápidamente una visión general de problemas que podrían producirse durante la importación.

El registro **Ejecución de la vista** proporciona información detallada acerca de cada entidad de datos que se importe. Puede usar la vista de datos provisional para obtener rápidamente los datos de destino. De esta manera, puede ver cómo se muestran los datos importados en las páginas relacionadas en la aplicación. Al utilizar las plantillas de datos predeterminadas, la secuencia de importación para cada entidad de datos funciona de la forma predefinida, para ayudar a garantizar que todos los datos dependiente se importen primero. Si las entidades personalizadas de los datos son parte del proyecto, debe asegurarse de que se ha definido la secuencia correcta. Para obtener más información, consulte [Plantillas de datos de configuración](../../dev-itpro/data-entities/configuration-data-templates.md).

Para obtener más información acerca de cómo usar la plantilla del almacén para copiar la configuración de un almacén de una empresa a una nueva empresa dentro de la misma instancia, vea este vídeo de 3 minutos en YouTube sobre [cómo usar una plantilla de almacén para copiar la configuración para Finance and Operations](https://www.youtube.com/watch?v=K2WIfFlqJYs).

## <a name="related-topic"></a>Tema relacionado

[Plantillas de datos de configuración](../../dev-itpro/data-entities/configuration-data-templates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]