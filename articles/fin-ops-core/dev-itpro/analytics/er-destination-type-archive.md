---
title: Tipo de destino de ER de archivo
description: Este artículo proporciona información sobre cómo configurar un destino de archivo para cada componente FOLDER o FILE de un informe electrónico (ER).
author: kfend
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 97423
ms.assetid: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: d907bf391c0629d62da489cea90a05eabaf69ef1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285467"
---
# <a name="archive-er-destination-type"></a>Tipo de destino de ER de archivo

[!include [banner](../includes/banner.md)]

Puede configurar un destino de archivo para cada componente **Carpeta** o **Archivo** de un formato de informe electrónico (ER) que está configurado para generar documentos salientes. Según la configuración de destino, un documento generado se almacena como archivo adjunto de un registro de la lista de trabajos de ER. Para ver los resultados vaya a **Administración de organización** \> **Informes electrónicos** \> **Trabajos de informes electrónicos**.

Puede utilizar esta opción para enviar el documento generado a una carpeta de Microsoft SharePoint o Microsoft Azure Storage. Establezca **Habilitada** en **Sí** para enviar la salida a un destino que se define por el tipo de documento seleccionado. Solo los tipos de documento donde el grupo se establece en **Archivo** están disponibles para su selección. Defina los [tipos](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) de documento en **Administración de la organización** \> **Administración de documentos** \> **Tipos de documento**. La configuración de destinos de ER es la misma que la configuración para el sistema de administración de documentos.

[![Página de tipos de documento.](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

La ubicación determina dónde se guarda el archivo. Una vez que se habilite el destino de **Archivado**, los resultados se pueden guardar en el archivo de trabajo. Puede ver los resultados en **Administración de organización** \> **Informes electrónicos** \> **Trabajos archivados de informes electrónicos**.

> [!NOTE]
> Seleccione un tipo de documento para el archivo de trabajo en **Administración de organización** \> **Áreas de trabajo** \> **Informes electrónicos** \> **Parámetros de informes electrónicos**. Para obtener más información, consulte [Configurar el marco de informes electrónicos (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).

## <a name="sharepoint"></a>SharePoint

Puede guardar un archivo en una carpeta de SharePoint designada. Para definir el servidor de SharePoint predeterminado, vaya a **Administración de la organización** \> **Administración de documentos** \> **Parámetros de la administración de documentos**. En la pestaña **SharePoint**, configure la carpeta SharePoint. Luego, puede seleccionarla como carpeta donde se guardará la salida ER. La ubicación de **SharePoint** debe seleccionarse en este tipo de documento.

[![Selección de una carpeta de SharePoint.](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Almacenamiento de Azure

Cuando se establece la ubicación del tipo de documento en **Almacenamiento de Azure**, puede guardar un archivo en el Almacenamiento de Azure.

> [!NOTE] 
> El marco de ER almacena permanentemente archivos en Azure Blob Storage, a diferencia del marco de administración de datos que aplica la política de retención de siete días para los documentos que deben procesarse. Para más información, consulte [API para obtener el estado del mensaje](../data-entities/recurring-integrations.md#api-for-getting-message-status) y [API de verificación de estado](../data-entities/data-management-api.md#status-check-api). Los archivos relacionados con ER se almacenarán en Azure Blob Storage como archivos adjuntos de los registros de la tabla de la aplicación durante el tiempo que sea necesario. Se eliminará un solo archivo de Azure Blob Storage junto con el registro de la tabla de aplicación al que se adjuntó este archivo.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)
- [Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)
- [Configurar la gestión de documentos](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
