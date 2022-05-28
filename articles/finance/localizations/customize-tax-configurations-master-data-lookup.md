---
title: Personalizar las configuraciones de impuestos para la búsqueda de datos maestros
description: Este tema explica cómo personalizar las configuraciones de impuestos para ampliar la funcionalidad de búsqueda de datos maestros.
author: kai-cloud
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 69541316ad4c6c4bb404ea142844ce596b5502b9
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689139"
---
# <a name="customize-tax-configurations-for-master-data-lookup"></a>Personalizar las configuraciones de impuestos para la búsqueda de datos maestros

[!include [banner](../includes/banner.md)]

Siga los pasos en este tema para personalizar las configuraciones de impuestos y ampliar la funcionalidad de búsqueda de datos maestros.

## <a name="import-a-tax-configuration-provided-by-microsoft"></a>Importar una configuración de impuestos proporcionada por Microsoft

1. En Regulatory Configuration Service (RCS), en el área de trabajo **Informes electrónicos**, seleccione el proveedor de configuración de **Microsoft**.
2. Seleccione **Repositorios**.
3. Seleccione **Global** y luego seleccione **Abierto**.
4. Seleccione una configuración de impuestos, como **Configuración de cálculo de impuestos**, y luego, en la pestaña **Versiones**, seleccione una versión.
5. Seleccione **Importar**.

> [!NOTE]
> Por defecto, se importa el modelo de asignación Dataverse. Si recibe mensajes de advertencia durante el proceso de importación de la configuración, habilite las entidades virtuales en Dataverse. Para obtener más información, [Consulte las entidades virtuales de Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="create-a-customized-data-model-configuration"></a>Crear un modelo personalizado de configuración de datos

1. En el área de trabajo **Informes electrónicos**, seleccione **Configuraciones de impuestos**, y luego seleccione la configuración del modelo de datos que extender. Por ejemplo, seleccione **Modelo de datos de cálculo de impuestos**.
2. Seleccionar **Crear configuración**.
3. Seleccione **Modelo de documento imponible derivado de Nombre: Modelo de datos de cálculo de impuestos, Microsoft**.
4. En el campo **Nombre**, escriba **Modelo de datos de personalización**.
5. Seleccionar **Crear configuración**.

## <a name="create-customized-reference-models"></a>Crear modelos de referencia personalizados

1. En la página **Configuraciones de impuestos**, seleccione **Modelo de datos de personalización** y luego seleccione **Diseñador**.
2. Seleccione el botón de puntos suspensivos (**...**) y, a continuación, seleccione la vista **Modelo de referencia**.

    [![Modelo de referencia.](./media/pic2.png)](./media/pic2.png)

3. Crear el modelo de referencia personalizado. El modelo personalizado es un modelo raíz. La entidad personalizada es una lista de registros. El campo personalizado es un campo de cadena que desea utilizar en la búsqueda. Si es necesario, puede añadir más campos.
4. Seleccione el botón de puntos suspensivos (**...**) y, a continuación, seleccione la vista **Documento imponible**.
5. Seleccione el atributo que se vinculará al modelo de referencia personalizado. Por ejemplo, seleccione **Atributo personalizado** y luego siga estos pasos:

    1. Seleccione **Seleccionar modelo de referencia**.
    2. Seleccione **Modelo de personalización** y, a continuación, seleccione **Aceptar**. El nombre del modelo de referencia se actualiza al valor del campo **Clave natural**.

        [![Cuadro de diálogo Seleccionar modelo de referencia.](./media/pic5.png)](./media/pic5.png)

    3. Seleccione **Guardar** y, a continuación, seleccione **Completar**.

## <a name="create-a-customized-model-mapping-configuration"></a>Crear un modelo personalizado de configuración de asignación

1. En el área de trabajo **Informes electrónicos**, seleccione **Configuraciones de impuestos**, y luego seleccione la configuración del **modelo de asignación Dataverse**.
2. En el campo **Valor predeterminado de la asignación de modelo** seleccione **No**.
3. Seleccionar **Crear configuración**.
4. Seleccione **Asignación de modelo de documento imponible derivado de Nombre: Asignación de modelo de datos Dataverse, Microsoft**.
5. En el campo **Nombre**, escriba **Asignación de modelo de personalización**.
6. En el campo **Modelo de destino**, seleccione el modelo de datos **Modelo de datos de personalización**.
7. Seleccionar **Crear configuración**.

    [![Cuadro de diálogo desplegable Crear configuración.](./media/pic6.png)](./media/pic6.png)

8. Seleccione **Mapeo del modelo de personalización** y establezca el campo **Aplicación conectada** a la conexión que se creó en el paso 8 en [Configurar un entorno para la búsqueda de datos maestros](tax-service-set-up-environment-master-data-lookup.md).
9. Establezca el campo **Valor predeterminado para la asignación de modelo** en **Sí**.

## <a name="create-customized-model-mappings"></a>Cree asignaciones de modelos personalizadas

1. En la página **Configuraciones de impuestos**, seleccione **Asignación del modelo de personalización**.
2. Seleccione **Diseñador** y, a continuación, seleccione **Modelo de personalización**.

    [![Modelo de personalización.](./media/pic8.png)](./media/pic8.png)

## <a name="map-a-model-mapping-to-a-dataverse-entity"></a>Mapear una asignación de modelo a una entidad Dataverse

1. En la página **Diseñador de asignación de modelo**, seleccione **Modelo de personalización** y luego seleccione **Diseñador**.
2. En el árbol **Tipos de origen de datos**, seleccione **Tabla Dataverse**.
3. En la pestaña **Orígenes de datos**, seleccione **Agregar raíz**.
4. En el campo **Nombre**, introduzca **Dataverse personalizado**.
5. En el segundo campo **Nombre**, seleccione una entidad.
6. Seleccione **Aceptar**.

    [![Cuadro de diálogo Propiedades del origen de datos de tabla.](./media/pic9.png)](./media/pic9.png)

7. Seleccione **Dataverse personalizado** y **Entidad personalizada** y luego seleccione **Enlazar**.

    [![Enlace de entidad personalizado y Dataverse personalizado.](./media/pic10.png)](./media/pic10.png)

8. En **Dataverse personalizado** y **Campo personalizado**, seleccione un campo y luego seleccione **Enlazar**.

    [![Enlace de campo personalizado y Dataverse personalizado.](./media/pic11.png)](./media/pic11.png)

9. Seleccione **Guardar** y, a continuación, seleccione **Completar**.

## <a name="create-a-customized-tax-configuration"></a>Crear una configuración de impuestos personalizada

1. En el área de trabajo **Informes electrónicos**, seleccione **Configuraciones de impuestos**, y luego seleccione **Configuración del cálculo de impuestos**.
2. Seleccionar **Crear configuración**.
3. Seleccione **Configuración del servicio de impuestos derivada de Nombre: Configuración de cálculo de impuestos, Microsoft**.
4. En el campo **Nombre**, escriba **Configuración de personalización**.
5. Seleccionar **Crear configuración**.
6. Seleccione **Configuración de personalización** y, a continuación, seleccione **Diseñador**.
7. En el campo **Modelo de datos**, seleccione **Modelo de datos de personalización**.
8. En el campo **Versión del modelo de datos**, seleccione la versión del modelo de datos correspondiente.

    [![Sección de propiedades.](./media/pic13.png)](./media/pic13.png)

9. Seleccione **Completar**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
