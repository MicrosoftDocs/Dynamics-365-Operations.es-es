---
title: Documentos de activos
description: Este tema explica los documentos de activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f994e519e354a766a2437f182d2ade39155749b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216561"
---
# <a name="asset-documents"></a><span data-ttu-id="eb19c-103">Documentos de activos</span><span class="sxs-lookup"><span data-stu-id="eb19c-103">Asset documents</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="eb19c-104">Este tema explica los documentos de activos en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="eb19c-104">This topic explains asset documents in Asset Management.</span></span>

<span data-ttu-id="eb19c-105">En Administración de activos, puede configurar los documentos para que se relacionen automáticamente con los tipos de trabajo, los fabricantes de activos, los tipos de activos o los activos, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="eb19c-105">In Asset Management, you can set up documents so that they are automatically related to job types, asset manufacturers, asset types, or assets, for example.</span></span> <span data-ttu-id="eb19c-106">Esta funcionalidad es de utilidad cuando se publican versiones de documento actualizadas.</span><span class="sxs-lookup"><span data-stu-id="eb19c-106">This functionality is useful when updated document versions are released.</span></span> <span data-ttu-id="eb19c-107">En ese caso, solo tiene que colocar el documento actualizado en la ubicación estándar que se utiliza para los documentos de Supply Chain Management y vincular el documento al registro de documento de activo que ha creado.</span><span class="sxs-lookup"><span data-stu-id="eb19c-107">In that case, you just have to put the updated document in the standard location that you use for your Supply Chain Management documents, and attach the document to the asset document record that you've created.</span></span> <span data-ttu-id="eb19c-108">Después, el documento actualizado está accesible desde los elementos de menú **Todos los activos**, **Activos activos**, **Mis activos activos**, **Todas las órdenes de trabajo** y **Trabajos de orden de trabajo activos**.</span><span class="sxs-lookup"><span data-stu-id="eb19c-108">The updated document can then be accessed from the **All assets**, **Active assets**, **My active assets**, **All work orders**, and **Active work order jobs** menu items.</span></span> <span data-ttu-id="eb19c-109">El proceso para adjuntar documentos a un registro de documento de activo utiliza el sistema de control de documentos estándar.</span><span class="sxs-lookup"><span data-stu-id="eb19c-109">The process for attaching documents to an asset document record uses the standard document handling system.</span></span>

<span data-ttu-id="eb19c-110">**Ejemplo 1:** un documento relacionado con un tipo de trabajo puede describir un procedimiento para ese tipo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb19c-110">**Example 1:** A document that is related to a job type might describe a procedure for that job type.</span></span>

<span data-ttu-id="eb19c-111">**Ejemplo 2:** un documento relacionado con una combinación de tipo de activo, fabricante y modelo puede ser el manual estándar del modelo del fabricante del activo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="eb19c-111">**Example 2:** A document that is related to a combination of an asset type, manufacturer, and model might be the standard manual for the selected asset manufacturer model.</span></span>

## <a name="create-asset-document-relation"></a><span data-ttu-id="eb19c-112">Crear una relación de documento de activo</span><span class="sxs-lookup"><span data-stu-id="eb19c-112">Create asset document relation</span></span>

1. <span data-ttu-id="eb19c-113">Seleccione **Administración de activos** \> **Configuración** \> **Documentos de activos**.</span><span class="sxs-lookup"><span data-stu-id="eb19c-113">Select **Asset management** \> **Setup** \> **Asset documents**.</span></span>
2. <span data-ttu-id="eb19c-114">Seleccione **Nuevo** para crear un registro de documento de activo.</span><span class="sxs-lookup"><span data-stu-id="eb19c-114">Select **New** to create an asset document record.</span></span>
3. <span data-ttu-id="eb19c-115">En función de lo específica que desea que sea la relación, realice las selecciones relevantes en uno o más de los campos siguientes: **Tipo de activo**, **Fabricante**, **Modelo**, **Activo**, **Categoría de tipo de trabajo**, **Tipo de trabajo**, **Variante del tipo de trabajo** y **Requisito de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="eb19c-115">Depending on how specific you want the document relation to be, make relevant selections in one or more of the following fields: **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement**.</span></span> <span data-ttu-id="eb19c-116">Las opciones disponibles en **Variante del tipo de trabajo** y **Requisito de trabajo** dependen de la selección realizada en el campo **Tipo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="eb19c-116">The options that are available in the **Job type variant** and **Job requirement** fields depend on your selection in the **Job type** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb19c-117">Cuando el sistema busca documentos que deben estar relacionados con un activo o una orden trabajo, Administración de activos recorre todos los registros de documentos de activos para buscar una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="eb19c-117">When the system searches for documents that should be related to an asset or a work order, Asset Management goes through all asset document records to check for a possible match.</span></span> <span data-ttu-id="eb19c-118">Comprueba siempre primero la combinación más específica.</span><span class="sxs-lookup"><span data-stu-id="eb19c-118">It always checks the most specific combination first.</span></span> <span data-ttu-id="eb19c-119">Es decir, Administración de activos primero busca una coincidencia para el campo **Requisito de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="eb19c-119">In other words, Asset Management first checks for a match for the **Job requirement** field.</span></span> <span data-ttu-id="eb19c-120">Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Variante de tipo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="eb19c-120">If no match is found, it checks for a match for the **Job type variant** field.</span></span> <span data-ttu-id="eb19c-121">Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Tipo de trabajo**, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="eb19c-121">If no match is found, it checks for a match for the **Job type** field, and so on.</span></span> <span data-ttu-id="eb19c-122">Como puede ver en el diseño de la página **Documentos de activos**, este comportamiento significa que, para encontrar la combinación más específica, Administración de activos comprueba cada registro de derecha a izquierda en busca de una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="eb19c-122">As you can see in the layout of the **Asset documents** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="eb19c-123">Varios documentos pueden estar relacionados con un activo o una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb19c-123">Several documents might be related to an asset or a work order.</span></span> <span data-ttu-id="eb19c-124">Puede editar el nivel de servicio en una solicitud de mantenimiento o una orden de trabajo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="eb19c-124">You can edit the service level on a maintenance request or a work order as you require.</span></span>

4. <span data-ttu-id="eb19c-125">Seleccione **Archivos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="eb19c-125">Select **Attachments**.</span></span> <span data-ttu-id="eb19c-126">Aparece la página **Gestión de documentos** estándar.</span><span class="sxs-lookup"><span data-stu-id="eb19c-126">The standard **Document handling** page appears.</span></span>
5. <span data-ttu-id="eb19c-127">Configure los documentos o las notas que se deben vincular al registro de documento de activo.</span><span class="sxs-lookup"><span data-stu-id="eb19c-127">Set up the documents or notes that should be attached to the asset document record.</span></span> <span data-ttu-id="eb19c-128">Después de vincular documentos, el campo **Archivos adjuntos** muestra el número de documentos relacionados con el registro.</span><span class="sxs-lookup"><span data-stu-id="eb19c-128">After you attach documents, the **Attachments** field shows the number of documents that are related to the record.</span></span>
