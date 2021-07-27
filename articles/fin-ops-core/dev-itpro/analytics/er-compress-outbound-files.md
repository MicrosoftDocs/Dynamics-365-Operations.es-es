---
title: Comprimir documentos grandes que se generan en informes electrónicos
description: Este tema explica cómo comprimir documentos grandes generados por un formato de informes electrónicos (ER).
author: NickSelin
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERFormatDestinationTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 5b58a9345b83219296a3570e7bf653ef8624b7a1
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6357651"
---
# <a name="compress-large-documents-that-are-generated-in-electronic-reporting"></a>Comprimir documentos grandes que se generan en informes electrónicos 

[!include [banner](../includes/banner.md)]

Puedes usar el [Marco de informes electrónicos (ER)](general-electronic-reporting.md) para configurar una solución que obtenga datos transaccionales para generar un documento saliente. Este documento generado puede ser bastante grande. Cuando se genera este tipo de documento, se usa la memoria del [Servidor de objetos de aplicación (AOS)](../dev-tools/access-instances.md#location-of-packages-source-code-and-other-aos-configurations) para retenerlo. En algún momento, el documento debe descargarse de su aplicación de Microsoft Dynamics 365 Finance. Actualmente, el tamaño máximo de un solo documento que se genera en ER está limitado a 2 gigabytes (GB). Además, Finance actualmente [limita](https://fix.lcs.dynamics.com/Issue/Details?kb=4569432&bugId=453907&dbType=3) el tamaño de un archivo descargado a 1 GB. Por lo tanto, debe configurar una solución de ER que reduzca la probabilidad de que se excedan estas limitaciones y que reciba una excepción **La transmisión fue demasiado larga** o **Desbordamiento o subdesbordamiento en la operación aritmética**.

Cuando configura una solución, puede ajustar su formato de ER en el diseñador de operaciones agregando un elemento raíz del tipo **Carpeta** para comprimir el contenido generado por cualquiera de sus elementos anidados. La compresión funciona "justo a tiempo", por lo que se puede reducir el uso máximo de memoria y el tamaño del archivo que se descargará.

> [!NOTE]
> La compresión de archivos requiere un porcentaje adicional del uso de la CPU.

Para obtener más información acerca de este enfoque, complete el ejemplo de este tema.

## <a name="example-compress-an-outbound-document"></a>Ejemplo: comprimir un documento saliente

Este ejemplo muestra cómo un usuario asignado al rol **Administrador de sistema** o **Consultor funcional de informes electrónicos** puede configurar un formato ER para comprimir un documento generado.

### <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar los procedimientos en este tema, debe completar los siguientes pasos:

1. [Activar un proveedor de configuración](er-defer-xml-element.md#activate-a-configuration-provider).
2. [Importar las configuraciones de ER de ejemplo](er-defer-xml-element.md#import-the-sample-er-configurations).
3. [Revisar el formato importado](er-defer-xml-element.md#review-the-imported-format).

> [!NOTE]
> Actualmente, la estructura del formato comienza desde el elemento **Informe** del tipo **Archivo** y contiene elementos XML. Por lo tanto, se generará un documento saliente en formato XML y no se utilizará compresión.

### <a name="generate-an-er-format-to-get-an-uncompressed-document"></a>Genere un formato ER para obtener un documento sin comprimir

1. [Ejecutar el formato importado](er-defer-xml-element.md#run-the-imported-format).
2. Observe que el tamaño del documento generado en formato XML es de 3 kilobytes (KB).

    ![Vista previa del documento saliente sin comprimir.](./media/er-compress-outbound-files1.png)

### <a name="modify-the-format-to-compress-the-generated-output"></a>Modificar el formato para comprimir la salida generada

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones, expanda **Modelo para aprender elementos aplazados**.
3. Seleccione la configuración **Formato para aprender elementos XML aplazados**.
4. Seleccione **Diseñador** para modificar la estructura del formato.
5. En la página **Diseñador de formato**, en la pestaña **Formato**, seleccione **Agregar raíz** para agregar un elemento de formato de raíz.
6. En el cuadro de diálogo **Agregar**, seleccione **Común\\Carpeta**.
7. Seleccione **Aceptar** para confirmar la adición del nuevo elemento raíz.
8. Seleccione **Guardar**.

> [!NOTE]
> La estructura del formato parte del elemento del tipo **Carpeta**. Este elemento generará una salida como un archivo comprimido (zip). Cuando un documento generado por el elemento **Informe** se coloca en un archivo zip saliente, su contenido se comprimirá para reducir el tamaño del archivo saliente.

### <a name="generate-an-er-format-to-get-a-compressed-document"></a>Genere un formato ER para obtener un documento comprimido

1. En la página **Diseñador de formato**, seleccione **Ejecutar**.
2. Descargue el archivo zip que ofrece el navegador web y ábralo para su revisión.
3. Observe que el tamaño del documento generado en formato ZIP es de 1 KB.

    > [!NOTE] 
    > La tasa de compresión del archivo XML que contiene este archivo zip es del 87 por ciento. La relación de compresión depende de los datos que se comprimen.

    ![Vista previa del documento saliente comprimido.](./media/er-compress-outbound-files2.png)

> [!NOTE]
> Si el [destino](electronic-reporting-destinations.md) de ER está configurado para el elemento de formato que genera la salida (el elemento **Informe** en este ejemplo), se omitirá la compresión de la salida.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)

[Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)

[Aplazar la ejecución de elementos de XML en formatos de informes electrónicos](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]