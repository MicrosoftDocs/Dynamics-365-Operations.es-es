---
title: MX-00010 Definir parámetros para una factura electrónica
description: Este procedimiento muestra cómo configurar una factura electrónica y la cuenta de PAC para obtener la aprobación y el sello digital.
author: sndray
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EInvoiceCFDIPACTable_MX, EInvoiceParameters_MX, DigitalCertificateLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55afd9a45caabfb69d69e83008015bf8336dd011
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814904"
---
# <a name="mx-00010-set-parameters-for-an-electronic-invoice"></a><span data-ttu-id="362cc-103">MX-00010 Definir parámetros para una factura electrónica</span><span class="sxs-lookup"><span data-stu-id="362cc-103">MX-00010 Set parameters for an electronic invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="362cc-104">Este procedimiento muestra cómo configurar una factura electrónica y la cuenta de PAC para obtener la aprobación y el sello digital.</span><span class="sxs-lookup"><span data-stu-id="362cc-104">This procedure walks you through setting up an electronic invoice and the PAC account to get the approval and the digital stamp.</span></span> <span data-ttu-id="362cc-105">Este procedimiento solo se puede completar con entidades jurídicas con dirección principal en México.</span><span class="sxs-lookup"><span data-stu-id="362cc-105">This procedure can only be completed for a legal entity with a primary address in Mexico.</span></span> <span data-ttu-id="362cc-106">Este procedimiento se creó con los datos de demostración de la empresa MXMF.</span><span class="sxs-lookup"><span data-stu-id="362cc-106">This procedure was created using the demo data company MXMF.</span></span> <span data-ttu-id="362cc-107">Los certificados que se utilizan para cifrar el mensaje XML deben haberse instalado anteriormente, y el archivo XSD de esquema se debe haber copiado en la aplicación también antes de comenzar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="362cc-107">The certificates used to encrypt the XML message must be previously installed and the schema XSD file must be copied in the application as well before to start this procedure.</span></span>


## <a name="set-up-pac-accounts"></a><span data-ttu-id="362cc-108">Configuración de cuentas de PAC</span><span class="sxs-lookup"><span data-stu-id="362cc-108">Set up PAC accounts</span></span>
1. <span data-ttu-id="362cc-109">Vaya a Clientes > Facturas > Facturas electrónicas > Cuentas de PAC.</span><span class="sxs-lookup"><span data-stu-id="362cc-109">Go to Accounts receivable > Invoices > E-Invoices > PAC Accounts</span></span>
2. <span data-ttu-id="362cc-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="362cc-110">Click New.</span></span>
3. <span data-ttu-id="362cc-111">En el campo Cuenta de PAC, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="362cc-111">In the PAC account field, type a value.</span></span>
4. <span data-ttu-id="362cc-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="362cc-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="362cc-113">En el campo Número de RFC, escriba el número de RFC de su proveedor de PAC.</span><span class="sxs-lookup"><span data-stu-id="362cc-113">In the RFC number field, enter the RFC number of your PAC provider.</span></span>
6. <span data-ttu-id="362cc-114">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="362cc-114">Click Save.</span></span>
7. <span data-ttu-id="362cc-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="362cc-115">Click New.</span></span>
8. <span data-ttu-id="362cc-116">En el campo del entorno, seleccione el tipo de entorno desde dónde se ejecutan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="362cc-116">In the environment field, select the type of environment where the web services are run from.</span></span>
    * <span data-ttu-id="362cc-117">Consulte con su proveedor de PAC sobre la disponibilidad de entornos de prueba y producción.</span><span class="sxs-lookup"><span data-stu-id="362cc-117">Check with your PAC provider about the availability of Testing and Production environments.</span></span>  
9. <span data-ttu-id="362cc-118">En el campo Dirección de Internet, escriba la dirección del servicio web de su proveedor de PAC.</span><span class="sxs-lookup"><span data-stu-id="362cc-118">In the Internet address field, enter the web service address of your PAC provider.</span></span>
10. <span data-ttu-id="362cc-119">En el campo Servicio web, seleccione Solicitar sello.</span><span class="sxs-lookup"><span data-stu-id="362cc-119">In the Web service field, select 'Request stamp'.</span></span>
    * <span data-ttu-id="362cc-120">El servicio web de solicitud de sello se utiliza para solicitar la firma digital.</span><span class="sxs-lookup"><span data-stu-id="362cc-120">The request stamp web service is used to request the digital signature.</span></span>  
11. <span data-ttu-id="362cc-121">En el campo Nombre del método, especifique el nombre de la operación que se usa para solicitar la aprobación de una factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="362cc-121">In the Method name field, enter the name of operation used to request the approval of an electronic invoice.</span></span>
    * <span data-ttu-id="362cc-122">Póngase en contacto con su proveedor de PAC para obtener el nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="362cc-122">Contact your PAC provider to get the operation name.</span></span>  
12. <span data-ttu-id="362cc-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="362cc-123">Click New.</span></span>
13. <span data-ttu-id="362cc-124">En el campo Entorno, seleccione el tipo de entorno desde dónde se ejecutan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="362cc-124">In the environment field, select the type of environment where the web services are ran from</span></span>
    * <span data-ttu-id="362cc-125">Consulte con su proveedor de PAC sobre la disponibilidad de entornos de prueba y producción.</span><span class="sxs-lookup"><span data-stu-id="362cc-125">Check with your PAC provider about the availability of testing and production environments.</span></span>  
14. <span data-ttu-id="362cc-126">En el campo Dirección de Internet, escriba la dirección de los servicios web de su proveedor de PAC.</span><span class="sxs-lookup"><span data-stu-id="362cc-126">In the Internet address field, enter the web services address of your PAC provider.</span></span>
15. <span data-ttu-id="362cc-127">En el campo Servicio web, seleccione Cancelar.</span><span class="sxs-lookup"><span data-stu-id="362cc-127">In the Web service field, select 'Cancel'.</span></span>
16. <span data-ttu-id="362cc-128">En el campo Nombre del método, especifique el método usado para la operación de cancelación.</span><span class="sxs-lookup"><span data-stu-id="362cc-128">In the Method name field, enter the method used for Cancel operation.</span></span>
    * <span data-ttu-id="362cc-129">Este es el nombre de la operación que se usa en el proceso de servicios web para cancelar una factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="362cc-129">This is the name of operation used in the web services process to cancel an electronic invoice.</span></span> <span data-ttu-id="362cc-130">Póngase en contacto con su proveedor de PAC para obtener el nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="362cc-130">Contact your PAC provider to get the operation name.</span></span>  

## <a name="set-up-electronic-invoice-parameters"></a><span data-ttu-id="362cc-131">Configuración de parámetros de facturas electrónicas</span><span class="sxs-lookup"><span data-stu-id="362cc-131">Set up electronic invoice parameters</span></span>
1. <span data-ttu-id="362cc-132">Vaya a Clientes > Facturas > Facturas electrónicas > Parámetros de facturas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="362cc-132">Go to Accounts receivable > Invoices > E-Invoices > Electronic invoice parameters</span></span>
2. <span data-ttu-id="362cc-133">Active o desactive la casilla Habilitar CFDI (factura electrónica).</span><span class="sxs-lookup"><span data-stu-id="362cc-133">Select or clear the Enable CFDI (electronic invoice) check box.</span></span>
    * <span data-ttu-id="362cc-134">Para esta tarea, cambie el control deslizante a Sí.</span><span class="sxs-lookup"><span data-stu-id="362cc-134">For this task, change the slider to be 'Yes'.</span></span>  
3. <span data-ttu-id="362cc-135">En el campo Certificado, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="362cc-135">In the Certificate field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="362cc-136">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="362cc-136">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="362cc-137">En el campo Versión CFDI, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="362cc-137">In the CFDI version field, select an option.</span></span>
    * <span data-ttu-id="362cc-138">Puede comprobar la versión disponible actual del esquema CFDI en el sitio web de la administración pública.</span><span class="sxs-lookup"><span data-stu-id="362cc-138">You can check the current available version of CFDI schema on the government website.</span></span>  
6. <span data-ttu-id="362cc-139">En el campo Archivo de esquema XML de CFDI, especifique la ruta y el nombre de archivo de esquema XML de CFDI.</span><span class="sxs-lookup"><span data-stu-id="362cc-139">In the CFDI XML schema file field, enter the path and name of the CFDI XML Schema file.</span></span>
7. <span data-ttu-id="362cc-140">En el campo Entorno, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="362cc-140">In the Environment field, select an option.</span></span>
8. <span data-ttu-id="362cc-141">En el campo Certificado PAC, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="362cc-141">In the PAC certificate field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="362cc-142">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="362cc-142">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="362cc-143">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="362cc-143">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="362cc-144">En el campo Cuenta de PAC, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="362cc-144">In the PAC account field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="362cc-145">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="362cc-145">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="362cc-146">Active o desactive la casilla Enviar correo.</span><span class="sxs-lookup"><span data-stu-id="362cc-146">Select or clear the Send mail check box.</span></span>
14. <span data-ttu-id="362cc-147">En el campo Id. de correo electrónico, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="362cc-147">In the E-mail ID field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="362cc-148">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="362cc-148">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="362cc-149">Active o desactive la casilla Enviar archivo de informe: PDF.</span><span class="sxs-lookup"><span data-stu-id="362cc-149">Select or clear the Send report file - PDF check box.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]