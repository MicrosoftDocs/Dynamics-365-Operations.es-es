--- 
title: "Configurar parámetros para una factura electrónica (México)"
description: "Este procedimiento muestra cómo configurar una factura electrónica y la cuenta de PAC para obtener la aprobación y el sello digital."
author: sndray
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 88ee2f9b825027e2e2f6986dfd59382fefb9819d
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-parameters-for-an-electronic-invoice-mexico"></a><span data-ttu-id="efbc2-103">Configurar parámetros para una factura electrónica (México)</span><span class="sxs-lookup"><span data-stu-id="efbc2-103">Set parameters for an electronic invoice (Mexico)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="efbc2-104">Este procedimiento muestra cómo configurar una factura electrónica y la cuenta de PAC para obtener la aprobación y el sello digital.</span><span class="sxs-lookup"><span data-stu-id="efbc2-104">This procedure walks you through setting up an electronic invoice and the PAC account to get the approval and the digital stamp.</span></span> <span data-ttu-id="efbc2-105">Este procedimiento solo se puede completar con entidades jurídicas con dirección principal en México.</span><span class="sxs-lookup"><span data-stu-id="efbc2-105">This procedure can only be completed for a legal entity with a primary address in Mexico.</span></span> <span data-ttu-id="efbc2-106">Este procedimiento se creó con los datos de demostración de la empresa MXMF.</span><span class="sxs-lookup"><span data-stu-id="efbc2-106">This procedure was created using the demo data company MXMF.</span></span> <span data-ttu-id="efbc2-107">Los certificados que se utilizan para cifrar el mensaje XML deben haberse instalado anteriormente, y el archivo XSD de esquema se debe haber copiado en la aplicación también antes de comenzar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="efbc2-107">The certificates used to encrypt the XML message must be previously installed and the schema XSD file must be copied in the application as well before to start this procedure.</span></span>


## <a name="set-up-pac-accounts"></a><span data-ttu-id="efbc2-108">Configuración de cuentas de PAC</span><span class="sxs-lookup"><span data-stu-id="efbc2-108">Set up PAC accounts</span></span>
1. <span data-ttu-id="efbc2-109">Vaya a Clientes > Facturas > Facturas electrónicas > Cuentas de PAC.</span><span class="sxs-lookup"><span data-stu-id="efbc2-109">Go to Accounts receivable > Invoices > E-Invoices > PAC Accounts</span></span>
2. <span data-ttu-id="efbc2-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="efbc2-110">Click New.</span></span>
3. <span data-ttu-id="efbc2-111">En el campo Cuenta de PAC, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="efbc2-111">In the PAC account field, type a value.</span></span>
4. <span data-ttu-id="efbc2-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="efbc2-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="efbc2-113">En el campo Número de RFC, escriba el número de RFC de su proveedor de PAC.</span><span class="sxs-lookup"><span data-stu-id="efbc2-113">In the RFC number field, enter the RFC number of your PAC provider.</span></span>
6. <span data-ttu-id="efbc2-114">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="efbc2-114">Click Save.</span></span>
7. <span data-ttu-id="efbc2-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="efbc2-115">Click New.</span></span>
8. <span data-ttu-id="efbc2-116">En el campo del entorno, seleccione el tipo de entorno desde dónde se ejecutan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="efbc2-116">In the environment field, select the type of environment where the web services are run from.</span></span>
    * <span data-ttu-id="efbc2-117">Consulte con su proveedor de PAC sobre la disponibilidad de entornos de prueba y producción.</span><span class="sxs-lookup"><span data-stu-id="efbc2-117">Check with your PAC provider about the availability of Testing and Production environments.</span></span>  
9. <span data-ttu-id="efbc2-118">En el campo Dirección de Internet, escriba la dirección del servicio web de su proveedor de PAC.</span><span class="sxs-lookup"><span data-stu-id="efbc2-118">In the Internet address field, enter the web service address of your PAC provider.</span></span>
10. <span data-ttu-id="efbc2-119">En el campo Servicio web, seleccione Solicitar sello.</span><span class="sxs-lookup"><span data-stu-id="efbc2-119">In the Web service field, select 'Request stamp'.</span></span>
    * <span data-ttu-id="efbc2-120">El servicio web de solicitud de sello se utiliza para solicitar la firma digital.</span><span class="sxs-lookup"><span data-stu-id="efbc2-120">The request stamp web service is used to request the digital signature.</span></span>  
11. <span data-ttu-id="efbc2-121">En el campo Nombre del método, especifique el nombre de la operación que se usa para solicitar la aprobación de una factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="efbc2-121">In the Method name field, enter the name of operation used to request the approval of an electronic invoice.</span></span>
    * <span data-ttu-id="efbc2-122">Póngase en contacto con su proveedor de PAC para obtener el nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="efbc2-122">Contact your PAC provider to get the operation name.</span></span>  
12. <span data-ttu-id="efbc2-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="efbc2-123">Click New.</span></span>
13. <span data-ttu-id="efbc2-124">En el campo Entorno, seleccione el tipo de entorno desde dónde se ejecutan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="efbc2-124">In the environment field, select the type of environment where the web services are ran from</span></span>
    * <span data-ttu-id="efbc2-125">Consulte con su proveedor de PAC sobre la disponibilidad de entornos de prueba y producción.</span><span class="sxs-lookup"><span data-stu-id="efbc2-125">Check with your PAC provider about the availability of testing and production environments.</span></span>  
14. <span data-ttu-id="efbc2-126">En el campo Dirección de Internet, escriba la dirección de los servicios web de su proveedor de PAC.</span><span class="sxs-lookup"><span data-stu-id="efbc2-126">In the Internet address field, enter the web services address of your PAC provider.</span></span>
15. <span data-ttu-id="efbc2-127">En el campo Servicio web, seleccione Cancelar.</span><span class="sxs-lookup"><span data-stu-id="efbc2-127">In the Web service field, select 'Cancel'.</span></span>
16. <span data-ttu-id="efbc2-128">En el campo Nombre del método, especifique el método usado para la operación de cancelación.</span><span class="sxs-lookup"><span data-stu-id="efbc2-128">In the Method name field, enter the method used for Cancel operation.</span></span>
    * <span data-ttu-id="efbc2-129">Este es el nombre de la operación que se usa en el proceso de servicios web para cancelar una factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="efbc2-129">This is the name of operation used in the web services process to cancel an electronic invoice.</span></span> <span data-ttu-id="efbc2-130">Póngase en contacto con su proveedor de PAC para obtener el nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="efbc2-130">Contact your PAC provider to get the operation name.</span></span>  

## <a name="set-up-electronic-invoice-parameters"></a><span data-ttu-id="efbc2-131">Configuración de parámetros de facturas electrónicas</span><span class="sxs-lookup"><span data-stu-id="efbc2-131">Set up electronic invoice parameters</span></span>
1. <span data-ttu-id="efbc2-132">Vaya a Clientes > Facturas > Facturas electrónicas > Parámetros de facturas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="efbc2-132">Go to Accounts receivable > Invoices > E-Invoices > Electronic invoice parameters</span></span>
2. <span data-ttu-id="efbc2-133">Active o desactive la casilla Habilitar CFDI (factura electrónica).</span><span class="sxs-lookup"><span data-stu-id="efbc2-133">Select or clear the Enable CFDI (electronic invoice) check box.</span></span>
    * <span data-ttu-id="efbc2-134">Para esta tarea, cambie el control deslizante a Sí.</span><span class="sxs-lookup"><span data-stu-id="efbc2-134">For this task, change the slider to be 'Yes'.</span></span>  
3. <span data-ttu-id="efbc2-135">En el campo Certificado, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="efbc2-135">In the Certificate field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="efbc2-136">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="efbc2-136">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="efbc2-137">En el campo Versión CFDI, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="efbc2-137">In the CFDI version field, select an option.</span></span>
    * <span data-ttu-id="efbc2-138">Puede comprobar la versión disponible actual del esquema CFDI en el sitio web de la administración pública.</span><span class="sxs-lookup"><span data-stu-id="efbc2-138">You can check the current available version of CFDI schema on the government website.</span></span>  
6. <span data-ttu-id="efbc2-139">En el campo Archivo de esquema XML de CFDI, especifique la ruta y el nombre de archivo de esquema XML de CFDI.</span><span class="sxs-lookup"><span data-stu-id="efbc2-139">In the CFDI XML schema file field, enter the path and name of the CFDI XML Schema file.</span></span>
7. <span data-ttu-id="efbc2-140">En el campo Entorno, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="efbc2-140">In the Environment field, select an option.</span></span>
8. <span data-ttu-id="efbc2-141">En el campo Certificado PAC, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="efbc2-141">In the PAC certificate field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="efbc2-142">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="efbc2-142">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="efbc2-143">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="efbc2-143">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="efbc2-144">En el campo Cuenta de PAC, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="efbc2-144">In the PAC account field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="efbc2-145">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="efbc2-145">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="efbc2-146">Active o desactive la casilla Enviar correo.</span><span class="sxs-lookup"><span data-stu-id="efbc2-146">Select or clear the Send mail check box.</span></span>
14. <span data-ttu-id="efbc2-147">En el campo Id. de correo electrónico, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="efbc2-147">In the E-mail ID field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="efbc2-148">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="efbc2-148">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="efbc2-149">Active o desactive la casilla Enviar archivo de informe: PDF.</span><span class="sxs-lookup"><span data-stu-id="efbc2-149">Select or clear the Send report file - PDF check box.</span></span>


