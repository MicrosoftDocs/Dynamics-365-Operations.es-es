---
title: Almacenamiento de copia de seguridad de las plantillas de ER
description: Este tema explica cómo utilizar el almacenamiento de copia de seguridad de los informes electrónicos (ER) para recuperar plantillas.
author: NickSelin
manager: AnnBe
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-13
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 136a81e661590d7af879e816c1142de85fb72e06
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681409"
---
# <a name="backup-storage-of-er-templates"></a>Almacenamiento de copia de seguridad de las plantillas de ER

[!include [banner](../includes/banner.md)]

La [Visión general del marco de informes electrónicos (ER)](general-electronic-reporting.md) permite a los usuarios de la empresa configurar formatos para documentos de salida en función de los requisitos legales de diversos países o regiones. Los formatos de ER configurados pueden usar plantillas predefinidas para generar documentos salientes en distintos formatos, como libros Microsoft Excel , documentos Microsoft Word , o documentos PDF. Las plantillas se rellenan con los datos que necesita el flujo de datos configurado para los documentos generados.

Cada formato configurado se puede publicar como parte de una solución de ER. Cada solución de ER se puede exportar a partir de una instancia de Finance and Operations e importarse a otra instancia.

El marco de ER usa [Configurar la gestión de documentos](../../fin-ops/organization-administration/configure-document-management.md) para conservar las plantillas necesarias para la instancia actual de Finance and Operations. En función de la configuración del marco de ER, el Blob Storage de Microsoft Azure o una carpeta de Microsoft SharePoint se pueden seleccionar como la ubicación de almacenamiento principal físico para las plantillas. (Para obtener más información, consulte [Configurar el marco de informes electrónicos (ER)](electronic-reporting-er-configure-parameters.md)). La tabla DocuValue contiene un registro individual para cada plantilla. En cada registro, el campo **AccessInformation** almacena la ruta del archivo de una plantilla ubicado en la ubicación de almacenamiento configurada.

Al gestionar las instancias de Finance and Operations, es posible que desee migrar la instancia actual a otra ubicación. Por ejemplo, puede migrar la instancia de producción a un nuevo entorno de espacio aislado. Si configuró el marco de ER para almacenar plantillas en Blob storage, la tabla DocuValue en el nuevo entorno aislado se refiere a la instancia de Blob storage del entorno de producción. Sin embargo, no se puede acceder a esta instancia desde el entorno aislado, ya que el proceso de migración no admite la migración de artefactos en Blob storage. Por lo tanto, si intenta ejecutar un formato de ER que use una plantilla para generar documentos empresariales, se producirá una excepción, y se le notificará que falta la plantilla. También se le guía para usar la herramienta de limpieza del ER y después volver a importar la configuración del formato de ER que contiene la plantilla. Dado que puede que tenga varias configuraciones de formato de ER, este proceso puede ser largo.

La característica de almacenamiento de copia de seguridad de las plantillas de ER puede ayudarle a crear sus plantillas de modo que están siempre disponibles para generar documentos empresariales.

> [!NOTE]
> Esta función se puede utilizar solo si Blob storage se ha seleccionado como la ubicación de almacenamiento físico de las plantillas de ER.

## <a name="automated-recovery-and-notification"></a>Recuperación automatizada y notificación

Para esta función, cada plantilla de una nueva configuración de formato de ER en el entorno actual se guarda automáticamente en la ubicación de almacenamiento de copia de seguridad (la tabla de base de datos de ERDocuDatabaseStorage) cuando los eventos siguientes se producen:

- Importa una nueva configuración del formato de ER que contiene una plantilla.
- Completa el borrador de versión de una configuración del formato de ER que contiene una plantilla.

Las copias de seguridad de plantillas se migran a una nueva instancia de Finance and Operations como parte de la base de datos de la aplicación.

Si una plantilla de un formato de ER se requiere para la generación de documentos salientes, para procesar pagos de proveedor incluidas la generación de avisos de pago y informes de control, por ejemplo, pero la plantilla requerida no se encuentra en la ubicación de almacenamiento principal, los eventos siguientes se producen:

- Si la plantilla estará disponible en la ubicación de almacenamiento de copia de seguridad, se toma automáticamente de la ubicación de almacenamiento de copia de seguridad, se restablece a la ubicación de almacenamiento principal, y se usa para la ejecución actual.
- Se avisa a todos los usuarios asignados al rol **Desarrollador de informes electrónicos** o **Administrador del sistema** acerca del problema de la falta de la plantilla a través del centro de acción. El mensaje que aparece depende del valor del parámetro **Ejecutar automáticamente el procedimiento de restablecer las plantillas rotas en lote**:

    - Si este parámetro se establece en **Desactivado**, el mensaje recomienda que comience el proceso por lotes para corregir automáticamente emisiones similares para otras plantillas de configuración del formato de ER. El mensaje incluye un vínculo que podrá usar para iniciar el proceso por lotes.
    - Si este parámetro se establece en **Activado**, el mensaje le notifica que se ha detectado un problema de falta de plantillas, y que un nuevo proceso por lotes, **Restaurar plantillas rotas desde la copia de seguridad interna de la base de datos**, se ha programado automáticamente. Este proceso por lotes corregirá automáticamente problemas similares para otras plantillas.

Para configurar el parámetro **Ejecutar automáticamente el procedimiento de restablecer las plantillas rotas por lotes**, complete los pasos siguientes:

1. En Finance and Operations, abra la página **Administración de la organización \> Informes electrónicos \> Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. En el cuadro de diálogo **Parámetros de usuario** , establezca el valor necesario para el parámetro **Ejecutar automáticamente el procedimiento de restablecer las plantillas rotas por lotes**.

> [!NOTE]
> Este parámetro se define como usuario de aplicación y específico de la empresa registrada.

![Página de configuraciones de ER](./media/GER-BackupTemplates-1.png)

La ilustración siguiente muestra un ejemplo del mensaje que se genera cuando el parámetro **Ejecutar automáticamente el procedimiento de restablecer las plantillas rotas por lotes** se establece en **Activado**.

![Página del diario de pagos a proveedores](./media/GER-BackupTemplates-2.png)

La ilustración siguiente muestra el proceso por lotes **Restaurar plantillas rotas desde la copia de seguridad interna de la base de datos** en la página **trabajo por lotes**.

![Página de trabajos por lotes](./media/GER-BackupTemplates-3.png)

El registro de la ejecución del proceso por lotes **Restaurar plantillas rotas desde la copia de seguridad interna de la base de datos** completado incluye información acerca de las plantillas que se han restablecido desde la ubicación de almacenamiento de copia de seguridad a la ubicación de almacenamiento principal.

![Página del historial de trabajos por lotes](./media/GER-BackupTemplates-4.png)

De forma predeterminada, el proceso de crear automáticamente las copias de seguridad de las plantillas que residen en configuraciones de formato de ER está activado. Para detener el crear copias de seguridad de plantillas, establezca la opción **Detener la creación de copias de seguridad de plantillas** en **Sí** en la pestaña **Archivos adjuntos** de la página **Parámetros de informes electrónicos**. Puede abrir esta página desde el espacio de trabajo **Informes electrónicos**.

Si establece la opción **Detener la creación de copias de seguridad de plantillas** en **Sí** y no desea conservar las copias de seguridad que se realizaron anteriormente de plantillas, seleccione **Borrar almacenamiento de copia de seguridad** en la página **Parámetros de informes electrónico**.

Si ha actualizado el entorno a Finance and Operations, versión 10.0.5 (octubre de 2019), y desea migrar a un nuevo entorno que incluye las configuraciones del formato de ER que pueden ejecutarse, seleccione **Rellenar el almacenamiento de copia de seguridad** en la página **Parámetros de informes electrónicos** antes de que se produzca la migración. Este botón inicia el proceso de crear las copias de seguridad de todas las plantillas disponibles, para que se puedan almacenar en la ubicación de almacenamiento de copia de seguridad de ER para plantillas.

![Página de parámetros de informes electrónicos](./media/GER-BackupTemplates-5.png)

## <a name="manual-recovery"></a>Recuperación manual

Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Restaurar plantillas estropeadas** para iniciar manualmente el proceso de restauración de plantillas ER desde la ubicación de almacenamiento de respaldo a la ubicación de almacenamiento principal. Antes de comenzar este proceso, en la página **Restaurar plantillas estropeadas** puede especificar si se realizará de forma interactiva, o el proceso por lotes se programará para esto.

## <a name="supported-deployments"></a>Implementaciones compatibles

En Finance and Operations, versión 10.0.5, el almacenamiento de copia de seguridad de la función de plantillas de ER solo está disponible en las implementaciones en la nube.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)

[Configurar el marco de informes electrónicos (ER)](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]