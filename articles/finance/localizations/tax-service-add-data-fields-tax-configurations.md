---
title: Agregar campos de datos en configuraciones de impuestos
description: Este tema explica cómo personalizar las configuraciones de impuestos agregando campos de datos.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 197a2d1605dd39188841aba02a71d228c7138c54
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921198"
---
# <a name="add-data-fields-in-tax-configurations"></a><span data-ttu-id="89cd2-103">Agregar campos de datos en configuraciones de impuestos</span><span class="sxs-lookup"><span data-stu-id="89cd2-103">Add data fields in tax configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89cd2-104">Este tema explica cómo personalizar las configuraciones de impuestos mediante el uso de [campos de datos que se agregan en la integración de impuestos](tax-service-add-data-fields-tax-integration-by-extension.md).</span><span class="sxs-lookup"><span data-stu-id="89cd2-104">This topic explains how to customize tax configurations by using [data fields that are added in the tax integration](tax-service-add-data-fields-tax-integration-by-extension.md).</span></span>

## <a name="customize-the-tax-data-model"></a><span data-ttu-id="89cd2-105">Personalizar el modelo de datos de impuestos</span><span class="sxs-lookup"><span data-stu-id="89cd2-105">Customize the tax data model</span></span>

1. <span data-ttu-id="89cd2-106">En Microsoft Dynamics 365 Finance, vaya a **Informes electrónicos** \> **Configuraciones de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-106">In Microsoft Dynamics 365 Finance, go to **Electronic Reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="89cd2-107">En el árbol de configuración, seleccione **Modelo de datos fiscales: Europa**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-107">In the configuration tree, select **Tax Data Model - Europe**.</span></span> <span data-ttu-id="89cd2-108">Luego, en el panel de acciones, seleccione **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-108">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="89cd2-109">En el cuadro de diálogo desplegable, seleccione la opción **Modelo de documento imponible derivado de Nombre: Modelo de datos fiscales - Europa, Microsoft**, introduzca un nombre para el nuevo modelo de datos de impuestos y luego seleccione **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-109">In the drop-down dialog box, select the **Taxable document model derived from Name: Tax Data Model -- Europe, Microsoft** option, enter a name for the new tax data model, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="89cd2-110">Seleccione el modelo de datos de impuestos que acaba de crear y luego, en el panel de acciones, seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-110">Select the tax data model that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="89cd2-111">Expanda el árbol del modelo de datos, seleccione **Líneas** y luego seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-111">Expand the data model tree, select **Lines**, and then select **New**.</span></span>
6. <span data-ttu-id="89cd2-112">En el cuadro de diálogo **Crear nodo**, introduzca un nombre, especifique el tipo de artículo y luego seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-112">In the **Create node** dialog box, enter a name, specify the item type, and then select **Add**.</span></span>
7. <span data-ttu-id="89cd2-113">Agregue las columnas requeridas.</span><span class="sxs-lookup"><span data-stu-id="89cd2-113">Add any required columns.</span></span>
8. <span data-ttu-id="89cd2-114">En el panel de acciones, seleccione **Guardar** y luego seleccione **Completo**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-114">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="89cd2-115">Cierre la página y vea la versión completa de su modelo de datos fiscales.</span><span class="sxs-lookup"><span data-stu-id="89cd2-115">Close the page, and view the completed version of your tax data model.</span></span>

## <a name="customize-the-tax-configuration"></a><span data-ttu-id="89cd2-116">Personalizar la configuración de impuestos</span><span class="sxs-lookup"><span data-stu-id="89cd2-116">Customize the tax configuration</span></span>

1. <span data-ttu-id="89cd2-117">En Finance, vaya a **Informes electrónicos** \> **Configuraciones de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-117">In Finance, go to **Electronic reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="89cd2-118">En el árbol de configuración, seleccione **Configuración de impuestos: Europa**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-118">In the configuration tree, select **Tax Configuration -- Europe**.</span></span> <span data-ttu-id="89cd2-119">Luego, en el panel de acciones, seleccione **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-119">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="89cd2-120">En el cuadro de diálogo desplegable, seleccione la opción **Configuración de servicio de impuestos derivada de Nombre: Configuración de impuestos, Europa, Microsoft**, introduzca un nombre para la nueva configuración de impuestos y luego seleccione **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-120">In the drop-down dialog box, select the **Tax service configuration derived from Name: Tax Configuration -- Europe, Microsoft** option, enter a name for the new tax configuration, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="89cd2-121">Seleccione la configuración de impuestos que acaba de crear y luego, en el panel de acciones, seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-121">Select the tax configuration that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="89cd2-122">En la sección **Propiedades**, en el campo **Modelo de datos**, seleccione el modelo de datos de impuestos personalizado que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="89cd2-122">In the **Properties** section, in the **Data model** field, select the customized tax data model that you created earlier.</span></span>
6. <span data-ttu-id="89cd2-123">En el campo **Versión del modelo de datos**, seleccione la versión completa del modelo de datos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="89cd2-123">In the **Data model version** field, select the completed version of the tax data model.</span></span>
7. <span data-ttu-id="89cd2-124">Seleccione **Agregar** y agregue las medidas tributarias requeridas.</span><span class="sxs-lookup"><span data-stu-id="89cd2-124">Select **Add**, and add the required tax measures.</span></span>
8. <span data-ttu-id="89cd2-125">En el panel de acciones, seleccione **Guardar** y luego seleccione **Completo**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-125">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="89cd2-126">Cierre la página y vea la versión completa de su configuración de impuestos.</span><span class="sxs-lookup"><span data-stu-id="89cd2-126">Close page, and view the completed version of your tax configuration.</span></span>

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a><span data-ttu-id="89cd2-127">Implementar funciones de impuestos en la configuración de impuestos personalizada</span><span class="sxs-lookup"><span data-stu-id="89cd2-127">Implement tax features in the customized tax configuration</span></span>

1. <span data-ttu-id="89cd2-128">En el servicio de configuración regulatoria (RCS), vaya a **Características de globalización** \> **Impuesto**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-128">In Regulatory Configuration Service (RCS), go to **Globalization Features** \> **Tax**.</span></span>
2. <span data-ttu-id="89cd2-129">Seleccione **Agregar**, introduzca información sobre la nueva función y luego seleccione **Crear característica**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-129">Select **Add**, enter information about the new feature, and then select **Create feature**.</span></span>
3. <span data-ttu-id="89cd2-130">En la pestaña **Versiones**, seleccione la característica y luego elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-130">On the **Versions** tab, select the feature, and then select **Edit**.</span></span>
4. <span data-ttu-id="89cd2-131">En la pestaña **General**, en el campo **Versión de configuración**, seleccione la configuración y la versión de impuestos personalizadas.</span><span class="sxs-lookup"><span data-stu-id="89cd2-131">On the **General** tab, in the **Configuration version** field, select the customized tax configuration and version.</span></span>
5. <span data-ttu-id="89cd2-132">En el cuadro de diálogo **Administrar columnas**, seleccione el encabezado y las columnas de línea que desea incluir en su medida de impuestos personalizada, y luego seleccione el botón de flecha hacia la derecha para agregarlos a la lista **Columnas seleccionadas**.</span><span class="sxs-lookup"><span data-stu-id="89cd2-132">In the **Manage columns** dialog box, select the header and line columns that you want to include in your customized tax measure, and then select the right arrow button to add them to the **Selected columns** list.</span></span>
