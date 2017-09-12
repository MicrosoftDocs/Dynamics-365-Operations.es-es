--- 
title: Configurar tipos de documentos I-9
description: "Este procedimiento muestra cómo ver y configurar los tipos de documentos que se usan para la verificación I-9."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 3b0e7f09994367f5683ed5c6d1f3b3ba3d550cc7
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-i-9-document-types"></a><span data-ttu-id="82898-103">Configurar tipos de documentos I-9</span><span class="sxs-lookup"><span data-stu-id="82898-103">Set up I-9 document types</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="82898-104">Este procedimiento muestra cómo ver y configurar los tipos de documentos que se usan para la verificación I-9.</span><span class="sxs-lookup"><span data-stu-id="82898-104">This procedure shows how to view and set up document types that are used for I-9 verification.</span></span> <span data-ttu-id="82898-105">Antes de configurar tipos de documentos I-9, también debe configurar las agencias emisoras y los tipos de identificación.</span><span class="sxs-lookup"><span data-stu-id="82898-105">Before you set up I-9 document types, you must also set up the issuing agencies and identification types.</span></span> <span data-ttu-id="82898-106">La empresa de datos de demostración utilizada para crear este procedimiento es USMF, la cual incluye ejemplos de agencias emisoras y de los tipos de identificación necesarios para completar el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="82898-106">The demo data company used to create this procedure is USMF, which includes examples of the issue agencies and identification types that are needed to complete the procedure.</span></span>

1. <span data-ttu-id="82898-107">Vaya a Recursos humanos > Trabajadores > I-9 > Tipos de documentos I-9.</span><span class="sxs-lookup"><span data-stu-id="82898-107">Go to Human resources > Workers > I-9 > I-9 document types.</span></span>
2. <span data-ttu-id="82898-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="82898-108">Click New.</span></span>
3. <span data-ttu-id="82898-109">En el campo Tipos de documento I-9, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="82898-109">In the I-9 document type field, type a value.</span></span>
    * <span data-ttu-id="82898-110">Ejemplo: Identificación escolar.</span><span class="sxs-lookup"><span data-stu-id="82898-110">Example: School ID.</span></span>  
4. <span data-ttu-id="82898-111">Seleccione el tipo de identificación.</span><span class="sxs-lookup"><span data-stu-id="82898-111">Select the identification type.</span></span>  <span data-ttu-id="82898-112">Ejemplo: Identificación escolar.</span><span class="sxs-lookup"><span data-stu-id="82898-112">Example:  School ID</span></span>
    * <span data-ttu-id="82898-113">Son ejemplos de tipos de identificación un número de la Seguridad Social (SSN), un número de visado, el número de pasaporte o el permiso de conducir.</span><span class="sxs-lookup"><span data-stu-id="82898-113">Examples of identification types include a Social Security number (SSN), visa number, passport ID, or driver's licence.</span></span>  
5. <span data-ttu-id="82898-114">Seleccione la lista de documentos I-9 utilizada para el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="82898-114">Select the I-9 document list that is used for the document type.</span></span>
    * <span data-ttu-id="82898-115">Como parte del proceso I-9, los empleados deben presentar documentación que muestre al empleador su identidad y su permiso de empleo.</span><span class="sxs-lookup"><span data-stu-id="82898-115">As part of the I-9 process, employees must present documentation that shows the employer their identity and employment authorization.</span></span> <span data-ttu-id="82898-116">El sitio web de los servicios de ciudadanía e inmigración de Estados Unidos contiene información relativa a los documentos aceptables y a qué lista pertenecen.</span><span class="sxs-lookup"><span data-stu-id="82898-116">The US Citizenship and Immigration Services website contains information about which documents are acceptable, and which list they belong to.</span></span>  <span data-ttu-id="82898-117">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="82898-117">http://www.uscis.gov</span></span>  
6. <span data-ttu-id="82898-118">En el campo Formulario, especifique el número de formulario oficial para el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="82898-118">In the Form field, Enter the official form number for the document type.</span></span> <span data-ttu-id="82898-119">Ejemplo: Identificación escolar.</span><span class="sxs-lookup"><span data-stu-id="82898-119">Example: School ID.</span></span>
    * <span data-ttu-id="82898-120">Los números de los formularios oficiales se pueden encontrar en el sitio web de los servicios de ciudadanía e inmigración de los EE. UU.</span><span class="sxs-lookup"><span data-stu-id="82898-120">The official form numbers can be found on the US Citizenship and Immigration Services website.</span></span>  <span data-ttu-id="82898-121">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="82898-121">http://www.uscis.gov</span></span>  
7. <span data-ttu-id="82898-122">Active o desactive la casilla Activo.</span><span class="sxs-lookup"><span data-stu-id="82898-122">Check or uncheck the Active checkbox.</span></span>
8. <span data-ttu-id="82898-123">En el campo Caducidad, defina la fecha en "2019-10-27".</span><span class="sxs-lookup"><span data-stu-id="82898-123">In the Expire field, set the date to '2019-10-27'.</span></span>
    * <span data-ttu-id="82898-124">La fecha de vencimiento es opcional.</span><span class="sxs-lookup"><span data-stu-id="82898-124">The expiration date is optional.</span></span>  
9. <span data-ttu-id="82898-125">Seleccione la agencia emisora del tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="82898-125">Select the agency that issued the document type.</span></span> <span data-ttu-id="82898-126">Ejemplo: Provincia/territorio</span><span class="sxs-lookup"><span data-stu-id="82898-126">Example: Province/territory</span></span>
10. <span data-ttu-id="82898-127">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="82898-127">Click Save.</span></span>


