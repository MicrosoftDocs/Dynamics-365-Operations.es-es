---
title: MX-00006 Configuración de un código de impuesto sobre las ventas
description: Los documentos financieros jurídicos, como declaraciones de impuestos o facturas electrónicas enviadas a las autoridades fiscales en México, deben contener distintos tipos de identificadores de registro de impuestos u otra información relacionada.
author: sndray
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxVatReportCategory_MX, TaxTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 144e1de7373c7c91687e88256d71eb7242c6a6c4
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139120"
---
# <a name="mx-00006-set-up-sales-tax-code"></a><span data-ttu-id="dd457-103">MX-00006 Configuración de un código de impuesto sobre las ventas</span><span class="sxs-lookup"><span data-stu-id="dd457-103">MX-00006 Set up sales tax code</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd457-104">Los documentos financieros jurídicos, como declaraciones de impuestos o facturas electrónicas enviadas a las autoridades fiscales en México, deben contener distintos tipos de identificadores de registro de impuestos u otra información relacionada.</span><span class="sxs-lookup"><span data-stu-id="dd457-104">Legal financial documents such as tax declarations or electronic invoices submitted to the tax authorities in Mexico must contain different types of tax registration IDs and other related information.</span></span> <span data-ttu-id="dd457-105">Esta guía detalla todos los pasos necesarios para completar la información sobre identificadores de registro en entidades jurídicas mexicanas.</span><span class="sxs-lookup"><span data-stu-id="dd457-105">This guide details all necessary steps to complete the information about registration IDs in Mexican legal entities.</span></span>

1. <span data-ttu-id="dd457-106">Vaya a Administración de la organización > Organizaciones > Entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="dd457-106">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="dd457-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="dd457-107">Click New.</span></span>
    * <span data-ttu-id="dd457-108">Si ha creado previamente su entidad jurídica mexicana, podrá editar una entidad jurídica existente en lugar de crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="dd457-108">If you have already created your Mexican legal entity, you can edit an existing legal entity instead of creating a new one.</span></span>  
3. <span data-ttu-id="dd457-109">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="dd457-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="dd457-110">En el campo Empresa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="dd457-110">In the Company field, type a value.</span></span>
5. <span data-ttu-id="dd457-111">En el campo País o Región, seleccione el código de país o región.</span><span class="sxs-lookup"><span data-stu-id="dd457-111">In the Country/region field, Select the Country/region code.</span></span>
6. <span data-ttu-id="dd457-112">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="dd457-112">Click OK.</span></span>
7. <span data-ttu-id="dd457-113">Expanda o contraiga la sección Números de registro.</span><span class="sxs-lookup"><span data-stu-id="dd457-113">Expand or collapse the Registration numbers section.</span></span>
8. <span data-ttu-id="dd457-114">En el campo Tipo de empresa, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="dd457-114">In the Company type field, select an option.</span></span>
9. <span data-ttu-id="dd457-115">En el campo Número de RFC, escriba el número de RFC de 12 caracteres de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="dd457-115">In the RFC number field, enter the 12-character RFC number of the legal entity.</span></span>
    * <span data-ttu-id="dd457-116">El número de Registro Federal del Contribuyentes (RFC) es el número de identificación fiscal asignado por las autoridades fiscales a una persona o una corporación.</span><span class="sxs-lookup"><span data-stu-id="dd457-116">Federal Registration for Taxpayers (RFC) number is the tax identification number assigned by tax authorities to a person or a corporation.</span></span> <span data-ttu-id="dd457-117">Microsoft Dynamics AX valida los identificadores de registro de impuestos según el formato especificado por las autoridades fiscales de México.</span><span class="sxs-lookup"><span data-stu-id="dd457-117">Microsoft Dynamics AX validates the tax registration IDs according to the format specified by tax authorities in Mexico.</span></span>  
10. <span data-ttu-id="dd457-118">En el campo Número de CURP, escriba el número de CURP de 18 caracteres de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="dd457-118">In the CURP number field, Enter the 18-character CURP number of the legal entity..</span></span>
    * <span data-ttu-id="dd457-119">El número de identificación de tarjeta fiscal único (CURP), que es el número de identificación fiscal asignado por las autoridades fiscales a una persona.</span><span class="sxs-lookup"><span data-stu-id="dd457-119">Unique Fiscal Card Identification (CURP) number which is the tax identification number assigned by the tax authorities to a person.</span></span>  <span data-ttu-id="dd457-120">Microsoft Dynamics AX valida los identificadores de registro de impuestos según el formato especificado por las autoridades fiscales de México.</span><span class="sxs-lookup"><span data-stu-id="dd457-120">Microsoft Dynamics AX validates the tax registration IDs according to the format specified by tax authorities in Mexico.</span></span>  <span data-ttu-id="dd457-121">Este campo es obligatorio cuando el campo RFC está vacío.</span><span class="sxs-lookup"><span data-stu-id="dd457-121">This is a mandatory field when the RFC field is empty.</span></span>  
11. <span data-ttu-id="dd457-122">En el campo Inscripción estatal, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="dd457-122">In the State inscription field, type a value.</span></span>
12. <span data-ttu-id="dd457-123">En el campo Representante legal, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="dd457-123">In the Legal representative field, type a value.</span></span>
13. <span data-ttu-id="dd457-124">En el campo RFC de representante legal, escriba el número de RFC de 12 caracteres del representante de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="dd457-124">In the Legal representative RFC field, Enter the 12-character RFC number of the legal entity representative..</span></span>
    * <span data-ttu-id="dd457-125">Microsoft Dynamics AX valida los identificadores de registro de impuestos según el formato especificado por las autoridades fiscales de México.</span><span class="sxs-lookup"><span data-stu-id="dd457-125">Microsoft Dynamics AX validates the tax registration IDs according to the format specified by tax authorities in Mexico.</span></span>  
14. <span data-ttu-id="dd457-126">En el campo CURP de representante legal, escriba el número de CURP de 12 caracteres del representante de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="dd457-126">In the Legal representative CURP field, Enter the 12-character CURP number of the legal entity representative..</span></span>
    * <span data-ttu-id="dd457-127">Microsoft Dynamics AX valida los identificadores de registro de impuestos según el formato especificado por las autoridades fiscales de México.</span><span class="sxs-lookup"><span data-stu-id="dd457-127">Microsoft Dynamics AX validates the tax registration IDs according to the format specified by tax authorities in Mexico.</span></span>  
15. <span data-ttu-id="dd457-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="dd457-128">Click Save.</span></span>

