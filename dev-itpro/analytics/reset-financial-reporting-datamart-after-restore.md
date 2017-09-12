---
title: "Restablecer el data mart de informes financieros después de restablecer una base de datos"
description: "Este tema describe cómo restablecer el data mart de informes financieros después de restaurar una base de datos de Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 9953d2f29a67b35f4bb43f577df1c4d910e379a1
ms.openlocfilehash: 08a420a776f47119a5dc47f9119545aa448ffdbd
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a><span data-ttu-id="ab8c8-103">Restablecer el data mart de informes financieros después de restablecer una base de datos</span><span class="sxs-lookup"><span data-stu-id="ab8c8-103">Reset the financial reporting data mart after restoring a database</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ab8c8-104">Este tema describe cómo restablecer el data mart de informes financieros después de restaurar una base de datos de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-104">This topic describes how to reset the financial reporting data mart after restoring a Microsoft Dynamics 365 for Finance and Operations database.</span></span>

<span data-ttu-id="ab8c8-105">Si se restablece la base de datos de Finance and Operations desde una copia de seguridad o copia de la base de datos de otro entorno, debe seguir los pasos de este tema para garantizar que el informe financiero data mart usa correctamente la base de datos restaurada de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-105">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this topic to ensure that the financial reporting data mart is correctly using the restored Finance and Operations database.</span></span> 
<!--If you have questions about resetting the financial reporting data mart for a reason outside of restoring a Finance and Operations database, refer to the [Resetting the Management Reporter data mart](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) for more information. -->
> [!Note] 
> <span data-ttu-id="ab8c8-106">Los pasos de este proceso se admiten para la versión de mayo de 2016 de Dynamics 365 for Operation (compilación de la aplicación 7.0.1265.23014 y compilación de informe financiero 7.0.10000.4) y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-106">The steps in this process are supported for Dynamics 365 for Operation May 2016 release (App build 7.0.1265.23014 and financial reporting build 7.0.10000.4) and newer releases.</span></span> <span data-ttu-id="ab8c8-107">Si tiene una versión anterior de Finance and Operations, contacte con nuestro equipo de soporte técnico para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-107">If you have an earlier release of Finance and Operations, contact our Support team for assistance.</span></span>

## <a name="export-report-definitions"></a><span data-ttu-id="ab8c8-108">Exportar las definiciones de informe</span><span class="sxs-lookup"><span data-stu-id="ab8c8-108">Export report definitions</span></span>
<span data-ttu-id="ab8c8-109">En primer lugar, exporte los diseños de informe que se encuentran en el Diseñador de informes, mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ab8c8-109">First, export the report designs located in the Report Designer, using the following steps:</span></span>

1.  <span data-ttu-id="ab8c8-110">En el Diseñador de informes, vaya a **Empresa** &gt; **Grupos de bloque de creación**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-110">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="ab8c8-111">Seleccione el grupo de bloque de creación para exportar y haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-111">Select the building block group to export, and click **Export**.</span></span> 
    > [!Note] 
    > <span data-ttu-id="ab8c8-112">Para Finance and Operations, se admite solo un grupo de bloque de creación, **Predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-112">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
3.  <span data-ttu-id="ab8c8-113">Seleccione las definiciones del informe que quiere exportar:</span><span class="sxs-lookup"><span data-stu-id="ab8c8-113">Select the report definitions to export:</span></span>
    -   <span data-ttu-id="ab8c8-114">Para exportar todas las definiciones de informes y los loques de creación asociados, haga clic en **Seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-114">To export all your report definitions and the associated building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="ab8c8-115">Para exportar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, haga clic en la pestaña apropiada y, a continuación, seleccione los artículos que se exportarán.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-115">To export specific reports, rows, columns, trees, or dimension sets, click the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="ab8c8-116">Mantenga presionada la tecla CTRL para seleccionar varios elementos en una pestaña.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-116">Press and hold the Ctrl key to select multiple items in a tab.</span></span> <span data-ttu-id="ab8c8-117">Cuando selecciona informes para exportar, se seleccionan las filas, columnas, organigramas y conjuntos de dimensión asociados.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-117">When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4.  <span data-ttu-id="ab8c8-118">Haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-118">Click **Export**.</span></span>
5.  <span data-ttu-id="ab8c8-119">Escriba un nombre de archivo y seleccione una ubicación segura en la que desea guardar las definiciones de informe exportadas.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-119">Enter a file name and select a secure location where you want to save the exported report definitions.</span></span>
6.  <span data-ttu-id="ab8c8-120">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-120">Click **Save**.</span></span>

<span data-ttu-id="ab8c8-121">El archivo se puede copiar o cargar en una ubicación segura, lo que permite importarlo a otro entorno en otra hora.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-121">The file can be copied or uploaded to a secure location, allowing it to be imported into a different environment at another time.</span></span> <span data-ttu-id="ab8c8-122">La información sobre el uso de una cuenta de almacenamiento de Microsoft Azure puede ser encontrada en la sección sobre [datos de la transferencia con el programa de línea de comandos de AzCopy](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="ab8c8-122">Information about using a Microsoft Azure storage account can be found in [Transfer data with the AzCopy Command-Line Utility](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy).</span></span> 
> [!NOTE]
> <span data-ttu-id="ab8c8-123">Microsoft no proporciona una cuenta de almacenamiento como parte del contrato de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-123">Microsoft doesn’t provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="ab8c8-124">Debe comprar una cuenta almacenamiento o utilizar una cuenta de almacenamiento de una suscripción de Azure independiente.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-124">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span> 
> [!WARNING]
> <span data-ttu-id="ab8c8-125">Tenga en cuenta el comportamiento de la unidad D en Azure Virtual Machines.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-125">Be aware of the behavior of the D drive on Azure Virtual Machines.</span></span> <span data-ttu-id="ab8c8-126">No retenga sus grupos exportados del bloque de creación aquí permanentemente.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-126">Do not keep your exported building block groups here permanently.</span></span> <span data-ttu-id="ab8c8-127">Para obtener más información acerca de unidades temporales, vea la sección sobre [entendiendo la unidad temporal de Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="ab8c8-127">For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

## <a name="stop-services"></a><span data-ttu-id="ab8c8-128">Detener servicios</span><span class="sxs-lookup"><span data-stu-id="ab8c8-128">Stop services</span></span>
<span data-ttu-id="ab8c8-129">Use Escritorio remoto para conectarse con todos los equipos del entorno y detener los servicios siguientes de Windows mediante services.msc:</span><span class="sxs-lookup"><span data-stu-id="ab8c8-129">Use Remote Desktop to connect to all the computers in the environment and stop the following Windows services by using services.msc:</span></span>

-   <span data-ttu-id="ab8c8-130">Servicio de publicación de la World Wide Web (en todos los equipos AOS)</span><span class="sxs-lookup"><span data-stu-id="ab8c8-130">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="ab8c8-131">Servicio de administración por lotes de Microsoft Dynamics 365 for Finance and Operations (solo en equipos AOS que no son privados)</span><span class="sxs-lookup"><span data-stu-id="ab8c8-131">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="ab8c8-132">Servicio de proceso de Management Reporter 2012 (en equipos de BI solamente)</span><span class="sxs-lookup"><span data-stu-id="ab8c8-132">Management Reporter 2012 Process Service (on BI computers only)</span></span>

<span data-ttu-id="ab8c8-133">Estos servicios tendrán conexiones abiertas con la base de datos de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-133">These services will have open connections to the Finance and Operations database.</span></span>

## <a name="reset"></a><span data-ttu-id="ab8c8-134">Restablecer</span><span class="sxs-lookup"><span data-stu-id="ab8c8-134">Reset</span></span>
#### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="ab8c8-135">Localice y descargue el último paquete de MinorVersionDataUpgrade.zip</span><span class="sxs-lookup"><span data-stu-id="ab8c8-135">Locate and download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="ab8c8-136">Localice el último paquete de MinorVersionDataUpgrade.zip mediante las instrucciones que se encuentran en la sección de [Descarga del paquete desplegable de la última actualización de datos](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package).</span><span class="sxs-lookup"><span data-stu-id="ab8c8-136">Locate the latest MinorVersionDataUpgrade.zip package using the directions found in [Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package).</span></span> <span data-ttu-id="ab8c8-137">Las instrucciones explican cómo encontrar y descargar la versión correcta del paquete de actualización de datos.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-137">The directions explain how to locate and download the correct version of the data upgrade package.</span></span> <span data-ttu-id="ab8c8-138">No se requiere una actualización para descargar el paquete de MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-138">An upgrade is not required to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="ab8c8-139">Sólo necesita completar los pasos de la sección “Descarga del paquete desplegable de la última actualización de datos” sin realizar ningún otro paso del artículo para recuperar una copia del paquete de MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-139">You only need to complete the steps in the “Download the latest data upgrade deployable package” section without performing any of the other steps in the article to retrieve a copy of the MinorVersionDataUpgrade.zip package.</span></span>

#### <a name="execute-scripts-against-finance-and-operations-database"></a><span data-ttu-id="ab8c8-140">Ejecute las secuencias de comandos en la base de datos de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ab8c8-140">Execute scripts against Finance and Operations database</span></span>

<span data-ttu-id="ab8c8-141">Ejecute las secuencias de comandos siguientes en la base de datos de Finance and Operations (no en la base de datos del informe financiero).</span><span class="sxs-lookup"><span data-stu-id="ab8c8-141">Run the following scripts against the Finance and Operations database (not against the financial reporting database).</span></span>

-   <span data-ttu-id="ab8c8-142">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="ab8c8-142">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
-   <span data-ttu-id="ab8c8-143">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="ab8c8-143">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="ab8c8-144">Estas secuencias de comandos garantizan que la configuración de usuarios, roles y seguimiento de cambios sea correcta.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-144">These scripts ensure that the users, roles, and change tracking settings are correct.</span></span>

#### <a name="execute-powershell-command-to-reset-database"></a><span data-ttu-id="ab8c8-145">Ejecute el comando PowerShell para restablecer la base de datos</span><span class="sxs-lookup"><span data-stu-id="ab8c8-145">Execute PowerShell command to reset database</span></span>

<span data-ttu-id="ab8c8-146">Ejecute el siguiente comando, directamente en el equipo AOS, para restablecer la integración entre Finance and Operations y el informe financiero:</span><span class="sxs-lookup"><span data-stu-id="ab8c8-146">Execute the following command, directly on the AOS computer, to reset the integration between Finance and Operations and financial reporting:</span></span>

1.  <span data-ttu-id="ab8c8-147">Abra Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-147">Open Windows PowerShell as Administrator.</span></span>
2.  <span data-ttu-id="ab8c8-148">Ejecute F:</span><span class="sxs-lookup"><span data-stu-id="ab8c8-148">Execute: F:</span></span>
3.  <span data-ttu-id="ab8c8-149">Ejecute: cd F:\\MRApplicationService\\MRInstallDirectory</span><span class="sxs-lookup"><span data-stu-id="ab8c8-149">Execute: cd F:\\MRApplicationService\\MRInstallDirectory</span></span>
4.  <span data-ttu-id="ab8c8-150">Ejecute: Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1</span><span class="sxs-lookup"><span data-stu-id="ab8c8-150">Execute: Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1</span></span>
5.  <span data-ttu-id="ab8c8-151">Ejecute: Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;mi motivo para restablecer&gt;”</span><span class="sxs-lookup"><span data-stu-id="ab8c8-151">Execute: Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;my reason for resetting&gt;”</span></span>
    -   <span data-ttu-id="ab8c8-152">Se le solicitará que introduzca “Y” para confirmar.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-152">You will be asked to enter “Y” to confirm.</span></span>

<span data-ttu-id="ab8c8-153">Explicación de parámetros:</span><span class="sxs-lookup"><span data-stu-id="ab8c8-153">Explanation of parameters:</span></span>

-   <span data-ttu-id="ab8c8-154">Los valores válidos para el motivo son: SERVICING, BADDATA, OTHER.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-154">The valid values for -Reason are: SERVICING, BADDATA, OTHER.</span></span>
-   <span data-ttu-id="ab8c8-155">El parámetro ReasonDetail es de texto libre.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-155">The -ReasonDetail parameter is free text.</span></span>
-   <span data-ttu-id="ab8c8-156">El motivo y reasonDetail se registrarán en telemetría/seguimiento del entorno.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-156">The reason and reasonDetail will be recorded in telemetry/environment monitoring.</span></span>

## <a name="start-services"></a><span data-ttu-id="ab8c8-157">Iniciar los servicios</span><span class="sxs-lookup"><span data-stu-id="ab8c8-157">Start services</span></span>
<span data-ttu-id="ab8c8-158">Use services.msc para reiniciar los servicios que ha detenido anteriormente:</span><span class="sxs-lookup"><span data-stu-id="ab8c8-158">Use services.msc to restart the services that you stopped earlier:</span></span>

-   <span data-ttu-id="ab8c8-159">Servicio de publicación de la World Wide Web (en todos los equipos AOS)</span><span class="sxs-lookup"><span data-stu-id="ab8c8-159">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="ab8c8-160">Servicio de administración por lotes de Microsoft Dynamics 365 for Finance and Operations (solo en equipos AOS que no son privados)</span><span class="sxs-lookup"><span data-stu-id="ab8c8-160">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="ab8c8-161">Servicio de proceso de Management Reporter 2012 (en equipos de BI solamente)</span><span class="sxs-lookup"><span data-stu-id="ab8c8-161">Management Reporter 2012 Process Service (on BI computers only)</span></span>

## <a name="import-report-definitions"></a><span data-ttu-id="ab8c8-162">Importar las definiciones de informe</span><span class="sxs-lookup"><span data-stu-id="ab8c8-162">Import report definitions</span></span>
<span data-ttu-id="ab8c8-163">Importe sus diseños de informe del Diseñador de informes, mediante el archivo creado durante la exportación:</span><span class="sxs-lookup"><span data-stu-id="ab8c8-163">Import your report designs from the Report Designer, using the file created during the export:</span></span>

1.  <span data-ttu-id="ab8c8-164">En el Diseñador de informes, vaya a **Empresa** &gt; **Grupos de bloque de creación**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-164">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="ab8c8-165">Seleccione el grupo de bloque de creación para exportar y haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-165">Select the building block group to export, and click **Export**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="ab8c8-166">Para Finance and Operations, se admite solo un grupo de bloque de creación, **Predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-166">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="ab8c8-167">Seleccione el bloque de creación **Predeterminado** y haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-167">Select the **Default** building block and click **Import**.</span></span>
4.  <span data-ttu-id="ab8c8-168">Seleccione el archivo que contiene las definiciones de informe exportadas y haga clic **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-168">Select the file containing the exported report definitions and click **Open**.</span></span>
5.  <span data-ttu-id="ab8c8-169">En el cuadro de diálogo Importar, seleccione las definiciones del informe que desea importar:</span><span class="sxs-lookup"><span data-stu-id="ab8c8-169">In the Import dialog box, select the report definitions to import:</span></span>
    -   <span data-ttu-id="ab8c8-170">Para importar todas las definiciones de informes y los bloques de creación asociados, haga clic en **Seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-170">To import all the report definitions and the supporting building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="ab8c8-171">Para importar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, seleccione los informes, filas, columnas, orgnaigramas o conjuntos de dimensiones que desea importar.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-171">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6.  <span data-ttu-id="ab8c8-172">Haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="ab8c8-172">Click **Import**.</span></span>





