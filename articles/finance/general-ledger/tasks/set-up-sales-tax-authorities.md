---
title: Configuración de las autoridades fiscales
description: Las autoridades fiscales son las entidades a las que tienen que notificarse y pagarse los impuestos cobrados.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eff67bc32eafea86d0ff582c56059c28706ed2a1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222247"
---
# <a name="set-up-sales-tax-authorities"></a><span data-ttu-id="312ca-103">Configuración de las autoridades fiscales</span><span class="sxs-lookup"><span data-stu-id="312ca-103">Set up sales tax authorities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="312ca-104">Las autoridades fiscales son las entidades a las que tienen que notificarse y pagarse los impuestos cobrados.</span><span class="sxs-lookup"><span data-stu-id="312ca-104">Sales tax authorities are entities to which collected sales tax needs to be reported and paid.</span></span> <span data-ttu-id="312ca-105">Puede pagar los impuestos a la autoridad directamente o a través de una cuenta de proveedor que cree para la autoridad fiscal.</span><span class="sxs-lookup"><span data-stu-id="312ca-105">You can pay sales taxes to the authority directly or through a vendor account that you create for the sales tax authority.</span></span> <span data-ttu-id="312ca-106">Si lo hace, la empresa puede usar sus rutinas de pago habituales para pagar a la autoridad fiscal puntualmente.</span><span class="sxs-lookup"><span data-stu-id="312ca-106">If you do this, the company can use its usual payment routines to pay the sales tax authority on time.</span></span> <span data-ttu-id="312ca-107">Si no configura la autoridad fiscal como proveedor, una persona deberá prepararle un pago manual en la fecha de vencimiento correspondiente.</span><span class="sxs-lookup"><span data-stu-id="312ca-107">If you do not set up the tax authority as a vendor, someone must prepare a manual payment to the tax authority on the appropriate due date.</span></span> <span data-ttu-id="312ca-108">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="312ca-108">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="312ca-109">Vaya a Impuestos >Impuestos indirectos >Impuestos >Autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="312ca-109">Go to Tax > Indirect taxes > Sales tax > Sales tax authorities.</span></span>
2. <span data-ttu-id="312ca-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="312ca-110">Click New.</span></span>
3. <span data-ttu-id="312ca-111">En el campo Autoridad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="312ca-111">In the Authority field, type a value.</span></span>
4. <span data-ttu-id="312ca-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="312ca-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="312ca-113">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="312ca-113">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="312ca-114">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="312ca-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="312ca-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="312ca-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="312ca-116">Seleccione el diseño del informe para su país o región si hay uno disponible.</span><span class="sxs-lookup"><span data-stu-id="312ca-116">Select the report layout for your country/region, if one is available.</span></span> <span data-ttu-id="312ca-117">Si los diseños de informe no se corresponden con los requisitos de la autoridad fiscal, use el diseño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="312ca-117">If the report layouts do not correspond to the requirements of the sales tax authority, use default layout.</span></span>
9. <span data-ttu-id="312ca-118">Especifique los valores en el formulario de redondeo y los campos Redondear para especificar cómo se debe redondear el importe total de impuestos que se debe pagar.</span><span class="sxs-lookup"><span data-stu-id="312ca-118">Enter values in the Rounding form and the Round-off fields to specify how the tax total amount to be paid should be rounded.</span></span> <span data-ttu-id="312ca-119">Las diferencias de redondeo se registrarán en la configuración de Cuentas para transacciones automáticas en contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="312ca-119">Any rounding differences will be posted to Accounts for automatic transactions set up in General ledger.</span></span>
10. <span data-ttu-id="312ca-120">En el campo Redondear, escriba un número</span><span class="sxs-lookup"><span data-stu-id="312ca-120">In the Round-off field, enter a number.</span></span>
11. <span data-ttu-id="312ca-121">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="312ca-121">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]