---
title: "Restablecer el data mart de informes financieros después de restablecer una base de datos"
description: "Este tema describe cómo restablecer el data mart de informes financieros después de restaurar una base de datos de Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6e3f78fb2f6528449d2a411225cd0e14ca33443e
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a><span data-ttu-id="778fe-103">Restablecer el data mart de informes financieros después de restablecer una base de datos</span><span class="sxs-lookup"><span data-stu-id="778fe-103">Reset the financial reporting data mart after restoring a database</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="778fe-104">Este tema describe cómo restablecer el data mart de informes financieros después de restaurar una base de datos de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="778fe-104">This topic describes how to reset the financial reporting data mart after restoring a Microsoft Dynamics 365 for Finance and Operations database.</span></span>

<span data-ttu-id="778fe-105">Si se restablece la base de datos de Finance and Operations desde una copia de seguridad o copia de la base de datos de otro entorno, debe seguir los pasos de este tema para garantizar que el informe financiero data mart usa correctamente la base de datos restaurada de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="778fe-105">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this topic to ensure that the financial reporting data mart is correctly using the restored Finance and Operations database.</span></span> 
> [!Note] 
> <span data-ttu-id="778fe-106">Los pasos de este proceso se admiten para la versión de mayo de 2016 de Dynamics 365 for Operation (compilación de la aplicación 7.0.1265.23014 y compilación de informe financiero 7.0.10000.4) y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="778fe-106">The steps in this process are supported for Dynamics 365 for Operation May 2016 release (App build 7.0.1265.23014 and financial reporting build 7.0.10000.4) and newer releases.</span></span> <span data-ttu-id="778fe-107">Si tiene una versión anterior de Finance and Operations, contacte con nuestro equipo de soporte técnico para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="778fe-107">If you have an earlier release of Finance and Operations, contact our Support team for assistance.</span></span>

## <a name="export-report-definitions"></a><span data-ttu-id="778fe-108">Exportar las definiciones de informe</span><span class="sxs-lookup"><span data-stu-id="778fe-108">Export report definitions</span></span>
<span data-ttu-id="778fe-109">En primer lugar, exporte los diseños de informe que se encuentran en el Diseñador de informes, mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="778fe-109">First, export the report designs located in the Report Designer, using the following steps:</span></span>

1.  <span data-ttu-id="778fe-110">En el Diseñador de informes, vaya a **Empresa** &gt; **Grupos de bloque de creación**.</span><span class="sxs-lookup"><span data-stu-id="778fe-110">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="778fe-111">Seleccione el grupo de bloque de creación para exportar y haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="778fe-111">Select the building block group to export, and click **Export**.</span></span> 

    > [!Note] 
    > <span data-ttu-id="778fe-112">Para Finance and Operations, se admite solo un grupo de bloque de creación, **Predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="778fe-112">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="778fe-113">Seleccione las definiciones del informe que quiere exportar:</span><span class="sxs-lookup"><span data-stu-id="778fe-113">Select the report definitions to export:</span></span>
    -   <span data-ttu-id="778fe-114">Para exportar todas las definiciones de informes y los loques de creación asociados, haga clic en **Seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="778fe-114">To export all your report definitions and the associated building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="778fe-115">Para exportar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, haga clic en la pestaña apropiada y, a continuación, seleccione los artículos que se exportarán.</span><span class="sxs-lookup"><span data-stu-id="778fe-115">To export specific reports, rows, columns, trees, or dimension sets, click the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="778fe-116">Mantenga presionada la tecla Ctrl para seleccionar varios artículos en una pestaña. Al seleccionar los informes para exportar, las filas, columnas, árboles y conjuntos de dimensiones asociados se seleccionan también.</span><span class="sxs-lookup"><span data-stu-id="778fe-116">Press and hold the Ctrl key to select multiple items in a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4.  <span data-ttu-id="778fe-117">Haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="778fe-117">Click **Export**.</span></span>
5.  <span data-ttu-id="778fe-118">Escriba un nombre de archivo y seleccione una ubicación segura en la que desea guardar las definiciones de informe exportadas.</span><span class="sxs-lookup"><span data-stu-id="778fe-118">Enter a file name and select a secure location where you want to save the exported report definitions.</span></span>
6.  <span data-ttu-id="778fe-119">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="778fe-119">Click **Save**.</span></span>

<span data-ttu-id="778fe-120">El archivo se puede copiar o cargar en una ubicación segura, lo que permite importarlo a otro entorno en otra hora.</span><span class="sxs-lookup"><span data-stu-id="778fe-120">The file can be copied or uploaded to a secure location, allowing it to be imported into a different environment at another time.</span></span> <span data-ttu-id="778fe-121">La información sobre el uso de una cuenta de almacenamiento de Microsoft Azure puede ser encontrada en la sección sobre [datos de la transferencia con el programa de línea de comandos de AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="778fe-121">Information about using a Microsoft Azure storage account can be found in [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span> 
> [!NOTE]
> <span data-ttu-id="778fe-122">Microsoft no proporciona una cuenta de almacenamiento como parte del contrato de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="778fe-122">Microsoft doesn’t provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="778fe-123">Debe comprar una cuenta almacenamiento o utilizar una cuenta de almacenamiento de una suscripción de Azure independiente.</span><span class="sxs-lookup"><span data-stu-id="778fe-123">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span> 
> [!WARNING]
> <span data-ttu-id="778fe-124">Tenga en cuenta el comportamiento de la unidad D en Azure Virtual Machines.</span><span class="sxs-lookup"><span data-stu-id="778fe-124">Be aware of the behavior of the D drive on Azure Virtual Machines.</span></span> <span data-ttu-id="778fe-125">No retenga sus grupos exportados del bloque de creación aquí permanentemente.</span><span class="sxs-lookup"><span data-stu-id="778fe-125">Do not keep your exported building block groups here permanently.</span></span> <span data-ttu-id="778fe-126">Para obtener más información acerca de unidades temporales, vea la sección sobre [entendiendo la unidad temporal de Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="778fe-126">For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

## <a name="stop-services"></a><span data-ttu-id="778fe-127">Detener servicios</span><span class="sxs-lookup"><span data-stu-id="778fe-127">Stop services</span></span>
<span data-ttu-id="778fe-128">Use Escritorio remoto para conectarse con todos los equipos del entorno y detener los servicios siguientes de Windows mediante services.msc:</span><span class="sxs-lookup"><span data-stu-id="778fe-128">Use Remote Desktop to connect to all the computers in the environment and stop the following Windows services by using services.msc:</span></span>

-   <span data-ttu-id="778fe-129">Servicio de publicación de la World Wide Web (en todos los equipos AOS)</span><span class="sxs-lookup"><span data-stu-id="778fe-129">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="778fe-130">Servicio de administración por lotes de Microsoft Dynamics 365 for Finance and Operations (solo en equipos AOS que no son privados)</span><span class="sxs-lookup"><span data-stu-id="778fe-130">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="778fe-131">Servicio de proceso de Management Reporter 2012 (en equipos de BI solamente)</span><span class="sxs-lookup"><span data-stu-id="778fe-131">Management Reporter 2012 Process Service (on BI computers only)</span></span>

<span data-ttu-id="778fe-132">Estos servicios tendrán conexiones abiertas con la base de datos de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="778fe-132">These services will have open connections to the Finance and Operations database.</span></span>

## <a name="reset"></a><span data-ttu-id="778fe-133">Restablecer</span><span class="sxs-lookup"><span data-stu-id="778fe-133">Reset</span></span>
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="778fe-134">Localice y descargue el último paquete de MinorVersionDataUpgrade.zip</span><span class="sxs-lookup"><span data-stu-id="778fe-134">Locate and download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="778fe-135">Localice el último paquete de MinorVersionDataUpgrade.zip mediante las instrucciones que se encuentran en la sección de [Descarga del paquete desplegable de la última actualización de datos](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="778fe-135">Locate the latest MinorVersionDataUpgrade.zip package using the directions found in [Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="778fe-136">Las instrucciones explican cómo encontrar y descargar la versión correcta del paquete de actualización de datos.</span><span class="sxs-lookup"><span data-stu-id="778fe-136">The directions explain how to locate and download the correct version of the data upgrade package.</span></span> <span data-ttu-id="778fe-137">No se requiere una actualización para descargar el paquete de MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="778fe-137">An upgrade is not required to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="778fe-138">Sólo necesita completar los pasos de la sección “Descarga del paquete desplegable de la última actualización de datos” sin realizar ningún otro paso del artículo para recuperar una copia del paquete de MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="778fe-138">You only need to complete the steps in the “Download the latest data upgrade deployable package” section without performing any of the other steps in the article to retrieve a copy of the MinorVersionDataUpgrade.zip package.</span></span>

### <a name="execute-scripts-against-finance-and-operations-database"></a><span data-ttu-id="778fe-139">Ejecute las secuencias de comandos en la base de datos de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="778fe-139">Execute scripts against Finance and Operations database</span></span>

<span data-ttu-id="778fe-140">Ejecute las secuencias de comandos siguientes en la base de datos de Finance and Operations (no en la base de datos del informe financiero).</span><span class="sxs-lookup"><span data-stu-id="778fe-140">Run the following scripts against the Finance and Operations database (not against the financial reporting database).</span></span>

-   <span data-ttu-id="778fe-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="778fe-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
-   <span data-ttu-id="778fe-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="778fe-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="778fe-143">Estas secuencias de comandos garantizan que la configuración de usuarios, roles y seguimiento de cambios sea correcta.</span><span class="sxs-lookup"><span data-stu-id="778fe-143">These scripts ensure that the users, roles, and change tracking settings are correct.</span></span>

### <a name="execute-powershell-command-to-reset-database"></a><span data-ttu-id="778fe-144">Ejecute el comando PowerShell para restablecer la base de datos</span><span class="sxs-lookup"><span data-stu-id="778fe-144">Execute PowerShell command to reset database</span></span>

<span data-ttu-id="778fe-145">En el equipo de Microsoft Dynamics AX Application Object Server (AOS), ejecute los siguientes comandos en PowerShell como administrador para restablecer la integración entre Finance and Operations y el informe financiero:</span><span class="sxs-lookup"><span data-stu-id="778fe-145">On the AOS computer, execute the following commands in PowerShell as an Administrator to reset the integration between Finance and Operations and financial reporting:</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> <span data-ttu-id="778fe-146">Una vez ejecutados los comandos, se le solicitará que introduzca “Y” para confirmar.</span><span class="sxs-lookup"><span data-stu-id="778fe-146">After executing the commands, you will be asked to enter “Y” to confirm.</span></span>

<span data-ttu-id="778fe-147">Explicación de parámetros:</span><span class="sxs-lookup"><span data-stu-id="778fe-147">Explanation of parameters:</span></span>

-   <span data-ttu-id="778fe-148">Los valores válidos para el motivo son: SERVICING, BADDATA, OTHER.</span><span class="sxs-lookup"><span data-stu-id="778fe-148">The valid values for -Reason are: SERVICING, BADDATA, OTHER.</span></span>
-   <span data-ttu-id="778fe-149">El parámetro ReasonDetail es de texto libre.</span><span class="sxs-lookup"><span data-stu-id="778fe-149">The -ReasonDetail parameter is free text.</span></span>
-   <span data-ttu-id="778fe-150">El motivo y reasonDetail se registrarán en telemetría/seguimiento del entorno.</span><span class="sxs-lookup"><span data-stu-id="778fe-150">The reason and reasonDetail will be recorded in telemetry/environment monitoring.</span></span>

## <a name="start-services"></a><span data-ttu-id="778fe-151">Iniciar los servicios</span><span class="sxs-lookup"><span data-stu-id="778fe-151">Start services</span></span>
<span data-ttu-id="778fe-152">Use services.msc para reiniciar los servicios que ha detenido anteriormente:</span><span class="sxs-lookup"><span data-stu-id="778fe-152">Use services.msc to restart the services that you stopped earlier:</span></span>

-   <span data-ttu-id="778fe-153">Servicio de publicación de la World Wide Web (en todos los equipos AOS)</span><span class="sxs-lookup"><span data-stu-id="778fe-153">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="778fe-154">Servicio de administración por lotes de Microsoft Dynamics 365 for Finance and Operations (solo en equipos AOS que no son privados)</span><span class="sxs-lookup"><span data-stu-id="778fe-154">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="778fe-155">Servicio de proceso de Management Reporter 2012 (en equipos de BI solamente)</span><span class="sxs-lookup"><span data-stu-id="778fe-155">Management Reporter 2012 Process Service (on BI computers only)</span></span>

## <a name="import-report-definitions"></a><span data-ttu-id="778fe-156">Importar las definiciones de informe</span><span class="sxs-lookup"><span data-stu-id="778fe-156">Import report definitions</span></span>
<span data-ttu-id="778fe-157">Importe sus diseños de informe del Diseñador de informes, mediante el archivo creado durante la exportación:</span><span class="sxs-lookup"><span data-stu-id="778fe-157">Import your report designs from the Report Designer, using the file created during the export:</span></span>

1.  <span data-ttu-id="778fe-158">En el Diseñador de informes, vaya a **Empresa** &gt; **Grupos de bloque de creación**.</span><span class="sxs-lookup"><span data-stu-id="778fe-158">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="778fe-159">Seleccione el grupo de bloque de creación para exportar y haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="778fe-159">Select the building block group to export, and click **Export**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="778fe-160">Para Finance and Operations, se admite solo un grupo de bloque de creación, **Predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="778fe-160">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="778fe-161">Seleccione el bloque de creación **Predeterminado** y haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="778fe-161">Select the **Default** building block and click **Import**.</span></span>
4.  <span data-ttu-id="778fe-162">Seleccione el archivo que contiene las definiciones de informe exportadas y haga clic **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="778fe-162">Select the file containing the exported report definitions and click **Open**.</span></span>
5.  <span data-ttu-id="778fe-163">En el cuadro de diálogo Importar, seleccione las definiciones del informe que desea importar:</span><span class="sxs-lookup"><span data-stu-id="778fe-163">In the Import dialog box, select the report definitions to import:</span></span>
    -   <span data-ttu-id="778fe-164">Para importar todas las definiciones de informes y los bloques de creación asociados, haga clic en **Seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="778fe-164">To import all the report definitions and the supporting building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="778fe-165">Para importar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, seleccione los informes, filas, columnas, orgnaigramas o conjuntos de dimensiones que desea importar.</span><span class="sxs-lookup"><span data-stu-id="778fe-165">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6.  <span data-ttu-id="778fe-166">Haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="778fe-166">Click **Import**.</span></span>





