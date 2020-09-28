---
title: Tipo de destino de ER de archivo
description: Este tema proporciona información sobre cómo configurar un destino de archivo para cada componente FOLDER o FILE de un formato de informe electrónico (ER) que está configurado para generar documentos salientes.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8797a68507a5116c6adbf1f2d805838fa507958c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745594"
---
# <a name="archive-destination"></a>Destino de archivo

[!include [banner](../includes/banner.md)]

Puede configurar un destino de archivo para cada componente FOLDER o FILE de un formato de informe electrónico (ER) que está configurado para generar documentos salientes. Según la configuración de destino, un documento generado se almacena como archivo adjunto de un registro de la lista de trabajos de ER.

Puede utilizar esta opción para enviar el documento generado a una carpeta de Microsoft SharePoint o Microsoft Azure Storage. Establezca **Habilitada** en **Sí** para enviar la salida a un destino que se define por el tipo de documento seleccionado. Solo los tipos de documento donde el grupo se establece en **Archivo** están disponibles para su selección. Defina los [tipos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) de documento en **Administración de la organización** \> **Administración de documentos** \> **Tipos de documento**. La configuración de destinos de ER es la misma que la configuración para el sistema de administración de documentos.

[![Página de tipos de documento](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

La ubicación determina dónde se guarda el archivo. Una vez que se habilite el destino de **Archivado**, los resultados se pueden guardar en el archivo de trabajo. Puede ver los resultados en **Administración de organización** \> **Informes electrónicos** \> **Trabajos archivados de informes electrónicos**.

> [!NOTE]
> Seleccione un tipo de documento para el archivo de trabajo en **Administración de organización** \> **Áreas de trabajo** \> **Informes electrónicos** \> **Parámetros de informes electrónicos**. Para obtener más información, consulte [Configurar el marco de informes electrónicos (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).

## <a name="sharepoint"></a>SharePoint

Puede guardar un archivo en una carpeta de SharePoint designada. Para definir el servidor de SharePoint predeterminado, vaya a **Administración de la organización** \> **Administración de documentos** \> **Parámetros de la administración de documentos**. En la pestaña **SharePoint**, configure la carpeta SharePoint. Luego, puede seleccionarla como carpeta donde se guardará la salida ER. La ubicación de **SharePoint** debe seleccionarse en este tipo de documento.

[![Selección de una carpeta de SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Almacenamiento de Azure

Cuando se establece la ubicación del tipo de documento en **Almacenamiento de Azure**, puede guardar un archivo en el Almacenamiento de Azure.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)
- [Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)
- [Configurar la gestión de documentos](../../fin-ops/organization-administration/configure-document-management.md)
