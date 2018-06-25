---
title: "Importar catálogo de proveedores"
description: "En este tema se describe el proceso para importar datos de catálogos de proveedores."
author: mkirknel
manager: AnnBe
ms.date: 03/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendProspectiveVendorRegistrationRequests
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 
ms.search.region: Global
ms.search.industry: 
ms.author: mkirknel
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: ac7754bd6361ad74f7ab4d564ae3114dd4b9f165
ms.openlocfilehash: caf801ea27ade63c24bb0907313e7f8294c50702
ms.contentlocale: es-es
ms.lasthandoff: 04/26/2018

---

# <a name="import-vendor-catalogs"></a><span data-ttu-id="d677f-103">Importar catálogo de proveedores</span><span class="sxs-lookup"><span data-stu-id="d677f-103">Import vendor catalogs</span></span>
[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a><span data-ttu-id="d677f-104">Importación de catálogos de proveedores</span><span class="sxs-lookup"><span data-stu-id="d677f-104">Vendor catalogs import</span></span>

<span data-ttu-id="d677f-105">En Microsoft Dynamics 365 for Finance and Operations, los encargados de compras pueden crear y mantener catálogos que los empleados de las empresas pueden utilizar cuando piden servicios y artículos para su uso interno.</span><span class="sxs-lookup"><span data-stu-id="d677f-105">In Microsoft Dynamics 365 for Finance and Operations, purchasing professionals can create and maintain catalogs for company employees to use when they order items and services for internal use.</span></span> <span data-ttu-id="d677f-106">Para crear un catálogo de compras, puede agregar los artículos y servicios que desea poner a disposición de los empleados, ya sea importando los datos del catálogo de productos o agregando manualmente los datos del catálogo de productos al producto maestro.</span><span class="sxs-lookup"><span data-stu-id="d677f-106">To create a procurement catalog, you can add the items and services that you want to make available to employees, either by importing the product catalog data or by manually adding the product catalog data to the product master.</span></span> 

<span data-ttu-id="d677f-107">Puede cargar los datos del catálogo enviados por un proveedor del cliente de Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d677f-107">You can upload catalog data submitted by a vendor from the Microsoft Dynamics 365 client.</span></span>

<span data-ttu-id="d677f-108">Los datos de producto que le envía un proveedor, con el formato de un archivo de solicitud de mantenimiento del catálogo (CMR), debe estar en formato de archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d677f-108">The product data that a vendor submits to you, in the form of a catalog maintenance request (CMR) file, must be in XML file format.</span></span> <span data-ttu-id="d677f-109">El archivo de CMR debe contener los detalles de los productos que el proveedor proporciona a su compañía.</span><span class="sxs-lookup"><span data-stu-id="d677f-109">The CMR file should contain the details for the products that the vendor supplies to your company.</span></span>

## <a name="import-vendor-catalog-data"></a><span data-ttu-id="d677f-110">Importar datos de catálogos de proveedores</span><span class="sxs-lookup"><span data-stu-id="d677f-110">Import vendor catalog data</span></span>

<span data-ttu-id="d677f-111">Para importar datos de catálogos de proveedores, debe completar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d677f-111">To import vendor catalog data, you must complete the following tasks:</span></span>

1.  <span data-ttu-id="d677f-112">Configure un proyecto en el espacio de trabajo de administración de datos donde ha definido sus reglas de asignación de datos.</span><span class="sxs-lookup"><span data-stu-id="d677f-112">Set up a project in the Data management workspace where you have defined your data mapping rules.</span></span> <span data-ttu-id="d677f-113">Seleccione **Administración de datos** y luego seleccione **Configurar roles para proyectos de datos**.</span><span class="sxs-lookup"><span data-stu-id="d677f-113">Select **Data management** and then select **Set up roles for data projects**.</span></span> 

2.  <span data-ttu-id="d677f-114">Configurar una jerarquía de categorías de compras y asignar sus proveedores a categorías de compras.</span><span class="sxs-lookup"><span data-stu-id="d677f-114">Set up a procurement category hierarchy, and assign your vendors to procurement categories.</span></span> <span data-ttu-id="d677f-115">Si usa códigos de mercancías, agregue los códigos de mercancías a las categorías de compra.</span><span class="sxs-lookup"><span data-stu-id="d677f-115">If you use commodity codes, add the commodity codes to the procurement categories.</span></span> <span data-ttu-id="d677f-116">Para obtener información sobre la configuración de una jerarquía de categorías de compras, consulte [Configurar una jerarquía de categorías de compras](../procurement/tasks/set-up-procurement-category-hierarchy.md)</span><span class="sxs-lookup"><span data-stu-id="d677f-116">For information about setting up a procurement category hierarchy, see [Set up a procurement category hierarchy](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span></span>

3.  <span data-ttu-id="d677f-117">Configurar el proveedor para la importación de catálogos.</span><span class="sxs-lookup"><span data-stu-id="d677f-117">Configure the vendor for catalog import.</span></span> <span data-ttu-id="d677f-118">Seleccione un proveedor y, a continuación, seleccione **Adquisición** > **Configurar** > **Configurar proveedor para importación de catálogo**.</span><span class="sxs-lookup"><span data-stu-id="d677f-118">Select a vendor, and then select **Procurement** > **Set up** > **Configure vendor for catalog import**.</span></span>

4.  <span data-ttu-id="d677f-119">Configurar el flujo de trabajo para la importación de catálogos.</span><span class="sxs-lookup"><span data-stu-id="d677f-119">Configure workflow for catalog import.</span></span> <span data-ttu-id="d677f-120">Cree una plantilla del archivo de CMR y compártala con el proveedor.</span><span class="sxs-lookup"><span data-stu-id="d677f-120">Create a CMR file template and share this with your vendor.</span></span>

5.  <span data-ttu-id="d677f-121">Seleccione **Adquisición y abastecimiento** \> **Común** \> **Catálogos** \> **Catálogos de proveedores** para crear un catálogo de proveedores.</span><span class="sxs-lookup"><span data-stu-id="d677f-121">Select **Procurement and sourcing** \> **Common** \> **Catalogs** \> **Vendor catalogs** to create a vendor catalog.</span></span> <span data-ttu-id="d677f-122">Los archivos de solicitud de mantenimiento del catálogo (CMR) que recibe del proveedor se agrupan en este catálogo.</span><span class="sxs-lookup"><span data-stu-id="d677f-122">The catalog maintenance request (CMR) files that you receive from your vendor are grouped in this catalog.</span></span> 

6.  <span data-ttu-id="d677f-123">Cargar el archivo de CMR.</span><span class="sxs-lookup"><span data-stu-id="d677f-123">Upload the CMR file.</span></span>

7.  <span data-ttu-id="d677f-124">Revisar, aprobar o rechazar los productos del catálogo de proveedores.</span><span class="sxs-lookup"><span data-stu-id="d677f-124">Review, approve, or reject the products in the vendor catalog.</span></span> <span data-ttu-id="d677f-125">Los productos se asignan automáticamente a las categorías de compras de Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d677f-125">The products are automatically mapped to the procurement categories in Dynamics 365 for Finance and Operations.</span></span> 
    
<span data-ttu-id="d677f-126">Los productos aprobados se agregan al producto maestro y se liberan en las entidades jurídicas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="d677f-126">Approved products are added to the product master and are released to the selected legal entities.</span></span> <span data-ttu-id="d677f-127">Solo se pueden agregar productos aprobados al catálogo de compras.</span><span class="sxs-lookup"><span data-stu-id="d677f-127">Only approved products can be added to the procurement catalog.</span></span>

## <a name="generate-a-catalog-import-file-template"></a><span data-ttu-id="d677f-128">Generar una plantilla del archivo de importación de catálogos</span><span class="sxs-lookup"><span data-stu-id="d677f-128">Generate a catalog import file template</span></span>

<span data-ttu-id="d677f-129">La plantilla del archivo de importación de catálogos es un archivo XSD que se usa para crear un archivo de CMR para los productos de un proveedor.</span><span class="sxs-lookup"><span data-stu-id="d677f-129">The catalog import file template is an XSD file that you use to create a CMR file for a vendor’s products.</span></span> <span data-ttu-id="d677f-130">Puede usar el archivo de CMR para crear un nuevo catálogo, o sustituir o modificar un catálogo existente.</span><span class="sxs-lookup"><span data-stu-id="d677f-130">You can use the CMR file to create a new catalog, replace an existing catalog, or modify an existing catalog.</span></span>

1.  <span data-ttu-id="d677f-131">Seleccione **Adquisición y abastecimiento** \> **Catálogos** \> **Catálogos de proveedores** y haga doble clic en el catálogo con el que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="d677f-131">Select **Procurement and sourcing** \> **Catalogs** \> **Vendor catalogs** and double-click the catalog that you want to work with.</span></span>

2.  <span data-ttu-id="d677f-132">Descargue una plantilla actual de importación de catálogos (archivo XSD).</span><span class="sxs-lookup"><span data-stu-id="d677f-132">Download a current catalog import template (XSD file).</span></span> <span data-ttu-id="d677f-133">En la página **Actualizar catálogo**, en el **Panel de acciones**, en la pestaña **Catálogos**, en el grupo **Información relacionada** , haga clic en **Generar plantilla de catálogo** y seleccione **Categoría de compras**.</span><span class="sxs-lookup"><span data-stu-id="d677f-133">On the **Update catalog** page, on the **Action Pane**, on the **Catalogs** tab, in the **Related information** group, click **Generate catalog template** and select **Procurement category**.</span></span>

    -   <span data-ttu-id="d677f-134">Con la opción **Categoría de compras** puede generar una plantilla de catálogo que incluya las categorías de compras en las que el proveedor tenga autorización para proporcionar sus productos.</span><span class="sxs-lookup"><span data-stu-id="d677f-134">With the **Procurement category** option you can generate a catalog template that includes the procurement categories in which the vendor is authorized to provide products.</span></span>

3. <span data-ttu-id="d677f-135">En el cuadro de diálogo **Guardar como**, seleccione la ubicación en la que desea almacenar la plantilla del archivo de catálogo y guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="d677f-135">In the **Save as** dialog box, select the location where you want to store the catalog file template and save the file.</span></span>

<span data-ttu-id="d677f-136">Para obtener más información y ver ejemplos, consulte esta entrada de blog: [Catálogos de proveedor en Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span><span class="sxs-lookup"><span data-stu-id="d677f-136">For more information and for examples, refer to this blog post: [Vendor catalogs in Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span></span>
