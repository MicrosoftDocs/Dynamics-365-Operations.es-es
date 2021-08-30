---
title: Limpieza de migración de ER
description: Este tema explica cómo puede usar la función de limpieza de migración de ER para resolver problemas con las plantillas de ER.
author: NickSelin
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, ERParameters, ERMigrationCleanup
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: d437bed9b9873f82bcd047e85245bd2a8c66fb3572c06660f29fc19f66aebae1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723150"
---
# <a name="er-migration-cleanup"></a>Limpieza de migración de ER 

[!include[banner](../includes/banner.md)]

Al gestionar las instancias de Finance, es posible que desee migrar su instancia actual a otra ubicación. Por ejemplo, puede migrar la instancia de producción a un nuevo entorno de espacio aislado. Si configuró el marco de informes electrónicos (ER) para almacenar plantillas en Microsoft Azure, la tabla **DocuValue** del nuevo entorno aislado se refiere a la instancia de Almacenamiento de blob del entorno de producción. Sin embargo, no se puede acceder a esta instancia desde el entorno aislado, ya que el proceso de migración no admite la migración de artefactos en Almacenamiento de blob. Por el contrario, se espera que, en el nuevo entorno de sandbox, se refiera a la instancia de Blob Storage en el entorno de sandbox que aún no obtiene las plantillas ER.

Si intenta ejecutar un formato de ER que use una plantilla para generar documentos empresariales, se producirá una excepción, y se le notificará de que falta la plantilla. También se le guía para usar la herramienta de limpieza de migración de ER para eliminar y después volver a importar la configuración del formato de ER que contiene la plantilla.

[![Ejecución de un formato ER.](./media/er-migration-cleanup-run.png)](./media/er-migration-cleanup-run.png)

Recibirá un error similar si navega hasta la página **Configuraciones** (**Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**) y, en el árbol de configuraciones, intente eliminar una configuración de formato ER que use una plantilla.

[![Eliminación de un formato ER.](./media/er-migration-cleanup-delete.png)](./media/er-migration-cleanup-delete.png)

Complete los siguientes pasos para resolver problemas con las plantillas de ER a las que no puede acceder.

1.  Vaya a la página **Administración de la organización** \> **Periódico** \> **Limpieza de migración**.
2.  Seleccione una configuración de formato ER que no se pueda ejecutar o eliminar.
3.  Seleccione **Eliminar**.
4.  Confirme la eliminación de la configuración de formato ER seleccionada.
5.  [Importe](download-electronic-reporting-configuration-lcs.md) la configuración de formato ER eliminada a la instancia actual de Finance.

## <a name="applicability"></a>Aplicabilidad

> [Importante] La opción **Limpieza de migración** está dirigida solo a configuraciones de formato ER que contienen plantillas ER no accesibles. Cuando elimina una configuración de formato ER utilizando la opción **Limpieza de migración**, ER elimina las plantillas relacionadas con los artefactos de configuración en la única base de datos de la aplicación. La existencia de los archivos físicos apropiados en Almacenamiento de blob no está validada. En cambio, se supone que no hay ninguno. Por lo tanto, no use la opción **Limpieza de migración** como alternativa a la opción de eliminación de configuración ER en la página **Configuraciones**. Use la opción **Limpieza de migración** solo cuando no funcione correctamente la opción de eliminación de configuración ER en la página **Configuraciones**.
>
> Si usa la opción **Limpieza de migración** para eliminar una configuración de formato ER cuando la plantilla referida esté disponible en el Almacenamiento de blob, solo se eliminan los artefactos de configuración de la base de datos de la aplicación. El archivo físico de la plantilla en el Almacenamiento de blob permanece. La sobrescritura de archivos en el Almacenamiento de blob ya no está permitida. Para obtener más información, consulte [KB4557217](https://fix.lcs.dynamics.com/Issue/Details?kb=4557217). Además, ya no podrá volver a importar las configuraciones eliminadas mediante la limpieza de migración en este entorno. Para resolver este problema, debe encontrar el archivo correspondiente en Almacenamiento de blob y eliminarlo manualmente.

[![Importación de un formato ER.](./media/er-migration-cleanup-import.png)](./media/er-migration-cleanup-import.png)

Puede ocurrir un problema similar si migra la instancia de la aplicación a otra ubicación que se ha utilizado como destino de migración más de una vez y para la cual el Almacenamiento de blob ya contiene archivos de plantilla ER.

Dado que puede tener varias configuraciones de formato de ER, este proceso puede ser largo. Por lo tanto, es preferible el uso de la función [Almacenamiento de respaldo de plantillas ER](er-backup-storage-templates.md) para recuperar automáticamente plantillas con referencias rotas.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]