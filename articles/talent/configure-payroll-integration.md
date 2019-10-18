---
title: Configurar la integración de nóminas entre Talent y Dayforce
description: Este tema explica cómo configurar la integración entre Microsoft Dynamics 365 Talent y Ceridian Dayforce de modo que pueda procesar un período de pago.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: ec1d14cb14ab709dfc1bead4be0785904efcce4e
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251048"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="de6de-103">Configurar la integración de nóminas entre Talent y Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="de6de-104">La integración entre Microsoft Dynamics 365 Talent y Ceridian Dayforce se basa en varios pasos de configuración que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="de6de-104">The integration between Microsoft Dynamics 365 Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="de6de-105">Debe configurar la integración en Talent y Dayforce para poder procesar un período de pago.</span><span class="sxs-lookup"><span data-stu-id="de6de-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="de6de-106">Cuando se utiliza un servicio como Dayforce para completar períodos de pago, debe habilitar la integración en Talent.</span><span class="sxs-lookup"><span data-stu-id="de6de-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="de6de-107">La integración necesita los datos específicos de Talent.</span><span class="sxs-lookup"><span data-stu-id="de6de-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="de6de-108">Por lo tanto, debe comprobar que los datos que se asignen a Dayforce se hayan configurado en Talent de una forma que admita la integración.</span><span class="sxs-lookup"><span data-stu-id="de6de-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="de6de-109">La integración utiliza las amplias categorías de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="de6de-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="de6de-110">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="de6de-110">Human resources data</span></span>
- <span data-ttu-id="de6de-111">Catos de compensación</span><span class="sxs-lookup"><span data-stu-id="de6de-111">Compensation data</span></span>
- <span data-ttu-id="de6de-112">Datos de nómina, como ciclos de pago, períodos de sueldo, y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="de6de-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="de6de-113">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="de6de-113">Worker data</span></span>

<span data-ttu-id="de6de-114">Este tema describe los pasos que debe seguir para habilitar la integración.</span><span class="sxs-lookup"><span data-stu-id="de6de-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="de6de-115">También explica los tipos de datos y los detalles de configuración que requiere la integración.</span><span class="sxs-lookup"><span data-stu-id="de6de-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="de6de-116">Habilitar la integración</span><span class="sxs-lookup"><span data-stu-id="de6de-116">Enable the integration</span></span>

<span data-ttu-id="de6de-117">En Talent, debe activar la integración y especificar información de configuración para conectarse a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="de6de-118">Si desea que la transacción de contabilidad general que se genera se importe en Microsoft Dynamics 365 Finance, también debe configurar una cuenta de almacenamiento de Microsoft Azure y especificar la cadena de conexión Azure Storage en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="de6de-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="de6de-119">Para activar la integración en Talent, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="de6de-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="de6de-120">En la página **Administración del sistema** , seleccione **Configuración de la integración**.</span><span class="sxs-lookup"><span data-stu-id="de6de-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="de6de-121">Permite especificar el extremo del Protocolo de transferencia de archivos (FTP) y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="de6de-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="de6de-122">Escriba el nombre de usuario y contraseña del usuario que accederá al extremo y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="de6de-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="de6de-123">Pruebe la conexión, como sea necesario, y establezca la opción **Habilitar la integración de nómina** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="de6de-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="de6de-124">Cuando está activada la integración, se crean el paquete y los archivos de exportación de datos, y se establece la frecuencia.</span><span class="sxs-lookup"><span data-stu-id="de6de-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="de6de-125">Puede cambiar esta frecuencia como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="de6de-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="de6de-126">Para obtener más información acerca de las cuentas de almacenamiento de Azure y las cadenas de conexión de Azure Storage, consulte los temas de Azure siguientes:</span><span class="sxs-lookup"><span data-stu-id="de6de-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="de6de-127">Acerca de las cuentas de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="de6de-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="de6de-128">Configurar las cadenas de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="de6de-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="de6de-129">Detalles técnicos cuando está habilitada la integración de nóminas</span><span class="sxs-lookup"><span data-stu-id="de6de-129">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="de6de-130">La activación de la integración de nóminas tiene dos efectos primarios:</span><span class="sxs-lookup"><span data-stu-id="de6de-130">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="de6de-131">Se crea un proyecto de exportación de datos con el nombre "Exportación de la integración de nóminas".</span><span class="sxs-lookup"><span data-stu-id="de6de-131">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="de6de-132">Este proyecto contiene las entidades y los campos necesarios para la integración de nóminas.</span><span class="sxs-lookup"><span data-stu-id="de6de-132">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="de6de-133">Para examinar el proyecto, vaya **Administración del sistema**, seleccione el icono **Administración de datos** y abra el proyecto de datos de la lista de proyectos.</span><span class="sxs-lookup"><span data-stu-id="de6de-133">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="de6de-134">Este trabajo por lotes ejecuta el proyecto de exportación de datos, cifra el paquete de datos resultante y transfiere el archivo del paquete de datos al extremo de SFTP configurado en la pantalla **Configuración de la integración**.</span><span class="sxs-lookup"><span data-stu-id="de6de-134">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="de6de-135">El paquete de datos transferido al extremo de SFTP se cifra mediante una clave que es única para el paquete.</span><span class="sxs-lookup"><span data-stu-id="de6de-135">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="de6de-136">La clave está en Azure Key Vault, a la que solo puede acceder Ceridian.</span><span class="sxs-lookup"><span data-stu-id="de6de-136">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="de6de-137">No es posible descifrar y examinar el contenido del paquete de datos.</span><span class="sxs-lookup"><span data-stu-id="de6de-137">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="de6de-138">Si tiene que examinar el contenido del paquete de datos, debe exportar manualmente el proyecto de datos "Exportación de la integración de nóminas", descargarlo y abrirlo.</span><span class="sxs-lookup"><span data-stu-id="de6de-138">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="de6de-139">La exportación manual aplicará cifrado o transferirá el paquete.</span><span class="sxs-lookup"><span data-stu-id="de6de-139">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="de6de-140">Configurar los datos</span><span class="sxs-lookup"><span data-stu-id="de6de-140">Configure your data</span></span> 

<span data-ttu-id="de6de-141">Para procesar las nóminas, debe configurar los datos de recursos humanos en Talent.</span><span class="sxs-lookup"><span data-stu-id="de6de-141">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="de6de-142">Debe configurar datos de organización, como los trabajos y los puestos, así como las prestaciones y la información de compensación.</span><span class="sxs-lookup"><span data-stu-id="de6de-142">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="de6de-143">Esta información proporciona la información de empleo, pago y deducciones que se necesita para producir el sueldo del empleado.</span><span class="sxs-lookup"><span data-stu-id="de6de-143">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="de6de-144">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="de6de-144">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="de6de-145">Beneficios</span><span class="sxs-lookup"><span data-stu-id="de6de-145">Benefits</span></span> 

<span data-ttu-id="de6de-146">Recursos humanos ofrece herramientas para la configuración y el mantenimiento de prestaciones, deducciones y los planes de compensación de los trabajadores que una organización ofrece o procesa para sus trabajadores.</span><span class="sxs-lookup"><span data-stu-id="de6de-146">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="de6de-147">Al crear las prestaciones, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-147">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="de6de-148">Planes de prestaciones</span><span class="sxs-lookup"><span data-stu-id="de6de-148">Benefit plans</span></span>

- <span data-ttu-id="de6de-149">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-149">Plan (required)</span></span>
- <span data-ttu-id="de6de-150">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-150">Type (required)</span></span>
- <span data-ttu-id="de6de-151">Impacto de nómina (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-151">Payroll impact (required)</span></span>
- <span data-ttu-id="de6de-152">Recuperar atrasos</span><span class="sxs-lookup"><span data-stu-id="de6de-152">Recover arrears</span></span>
- <span data-ttu-id="de6de-153">Método de deducción</span><span class="sxs-lookup"><span data-stu-id="de6de-153">Deduction method</span></span>
- <span data-ttu-id="de6de-154">Prioridad de deducción</span><span class="sxs-lookup"><span data-stu-id="de6de-154">Deduction priority</span></span>
- <span data-ttu-id="de6de-155">Período de límite</span><span class="sxs-lookup"><span data-stu-id="de6de-155">Limit period</span></span>
- <span data-ttu-id="de6de-156">Importe límite</span><span class="sxs-lookup"><span data-stu-id="de6de-156">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="de6de-157">Beneficios</span><span class="sxs-lookup"><span data-stu-id="de6de-157">Benefits</span></span>

- <span data-ttu-id="de6de-158">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-158">Plan (required)</span></span>
- <span data-ttu-id="de6de-159">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-159">Type (required)</span></span>
- <span data-ttu-id="de6de-160">Opción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-160">Option (required)</span></span>
- <span data-ttu-id="de6de-161">Identificador de prestación (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-161">Benefit ID (required)</span></span>
- <span data-ttu-id="de6de-162">Frecuencia</span><span class="sxs-lookup"><span data-stu-id="de6de-162">Frequency</span></span>
- <span data-ttu-id="de6de-163">Base</span><span class="sxs-lookup"><span data-stu-id="de6de-163">Basis</span></span>
- <span data-ttu-id="de6de-164">Importe o índice</span><span class="sxs-lookup"><span data-stu-id="de6de-164">Amount or rate</span></span>
- <span data-ttu-id="de6de-165">Código de ganancias</span><span class="sxs-lookup"><span data-stu-id="de6de-165">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="de6de-166">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="de6de-166">Supported frequencies</span></span> 

- <span data-ttu-id="de6de-167">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="de6de-167">Weekly</span></span>
- <span data-ttu-id="de6de-168">Quincenal</span><span class="sxs-lookup"><span data-stu-id="de6de-168">Bi-weekly</span></span>
- <span data-ttu-id="de6de-169">Bimensual</span><span class="sxs-lookup"><span data-stu-id="de6de-169">Semi-monthly</span></span>
- <span data-ttu-id="de6de-170">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="de6de-170">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="de6de-171">Bases admitidas</span><span class="sxs-lookup"><span data-stu-id="de6de-171">Supported bases</span></span> 

- <span data-ttu-id="de6de-172">Importe fijo</span><span class="sxs-lookup"><span data-stu-id="de6de-172">Fixed amount</span></span>
- <span data-ttu-id="de6de-173">Porcentaje de ganancias</span><span class="sxs-lookup"><span data-stu-id="de6de-173">Percent of earnings</span></span>
- <span data-ttu-id="de6de-174">Horas productivas</span><span class="sxs-lookup"><span data-stu-id="de6de-174">Productive hours</span></span>

<span data-ttu-id="de6de-175">Dayforce crea las deducciones siguientes, según el impacto de nómina que hay definido en el plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="de6de-175">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="de6de-176">Selección en Talent</span><span class="sxs-lookup"><span data-stu-id="de6de-176">Selection in Talent</span></span>        | <span data-ttu-id="de6de-177">Resultado en Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-177">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="de6de-178">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="de6de-178">None</span></span>                       | <span data-ttu-id="de6de-179">No se crea ninguna deducción.</span><span class="sxs-lookup"><span data-stu-id="de6de-179">No deduction is created.</span></span>                      |
| <span data-ttu-id="de6de-180">Solo deducción</span><span class="sxs-lookup"><span data-stu-id="de6de-180">Deduction only</span></span>             | <span data-ttu-id="de6de-181">Se crea una deducción del empleado.</span><span class="sxs-lookup"><span data-stu-id="de6de-181">An employee deduction is created.</span></span>             |
| <span data-ttu-id="de6de-182">Solo contribución</span><span class="sxs-lookup"><span data-stu-id="de6de-182">Contribution only</span></span>          | <span data-ttu-id="de6de-183">Se crea una deducción del empresario.</span><span class="sxs-lookup"><span data-stu-id="de6de-183">An employer deduction is created.</span></span>             |
| <span data-ttu-id="de6de-184">Deducción y contribución</span><span class="sxs-lookup"><span data-stu-id="de6de-184">Deduction and contribution</span></span> | <span data-ttu-id="de6de-185">Se crean las deducciones del empleado y del empresario.</span><span class="sxs-lookup"><span data-stu-id="de6de-185">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="de6de-186">Para obtener más información sobre cómo definir y administrar un programa de prestaciones, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="de6de-186">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="de6de-187">Proporcionar un programa de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="de6de-187">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="de6de-188">Crear una nueva prestación</span><span class="sxs-lookup"><span data-stu-id="de6de-188">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="de6de-189">Definir reglas y directivas de idoneidad para prestaciones</span><span class="sxs-lookup"><span data-stu-id="de6de-189">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="de6de-190">Inscribir y quitar prestaciones para trabajadores</span><span class="sxs-lookup"><span data-stu-id="de6de-190">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="de6de-191">Compensación</span><span class="sxs-lookup"><span data-stu-id="de6de-191">Compensation</span></span> 

<span data-ttu-id="de6de-192">La gestión de compensaciones se usa para controlar la entrega de salarios base y primas.</span><span class="sxs-lookup"><span data-stu-id="de6de-192">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="de6de-193">El sueldo base fijo de un empleado y los aumentos por méritos se controlan mediante planes de compensación fijos.</span><span class="sxs-lookup"><span data-stu-id="de6de-193">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="de6de-194">El pago de incentivos, como los pagos de bonificación, las primas por rendimiento, las acciones y las concesiones, así como también las primas ocasionales, se controlan a través de planes de compensación variable.</span><span class="sxs-lookup"><span data-stu-id="de6de-194">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="de6de-195">Dayforce utiliza la información de compensación para calcular la tarifa por hora o anual de un empleado.</span><span class="sxs-lookup"><span data-stu-id="de6de-195">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="de6de-196">Se requieren planes de compensación fija y conversiones de índice salarial.</span><span class="sxs-lookup"><span data-stu-id="de6de-196">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="de6de-197">Los empleados deben estar asociados a un plan de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="de6de-197">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="de6de-198">Para obtener más información acerca de los panes de compensación, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="de6de-198">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="de6de-199">Crear planes de compensación fija</span><span class="sxs-lookup"><span data-stu-id="de6de-199">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="de6de-200">Crear planes de compensación variable</span><span class="sxs-lookup"><span data-stu-id="de6de-200">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="de6de-201">Desarrollar planes y estructura de salarios o compensaciones</span><span class="sxs-lookup"><span data-stu-id="de6de-201">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="de6de-202">Procesar compensaciones</span><span class="sxs-lookup"><span data-stu-id="de6de-202">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="de6de-203">Definición del proceso de compensación y el cálculo de resultados</span><span class="sxs-lookup"><span data-stu-id="de6de-203">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="de6de-204">Inscribir a un empleado en un plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="de6de-204">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="de6de-205">Inscribir a un empleado en un plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="de6de-205">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="de6de-206">Trabajos</span><span class="sxs-lookup"><span data-stu-id="de6de-206">Jobs</span></span> 

<span data-ttu-id="de6de-207">Un trabajo es un conjunto de las tareas y responsabilidades que deberá cumplir la persona que realiza un trabajo.</span><span class="sxs-lookup"><span data-stu-id="de6de-207">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="de6de-208">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="de6de-208">For more information, see the following topics:</span></span>

- [<span data-ttu-id="de6de-209">Configurar los componentes de un trabajo</span><span class="sxs-lookup"><span data-stu-id="de6de-209">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="de6de-210">Definir nuevos trabajos</span><span class="sxs-lookup"><span data-stu-id="de6de-210">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="de6de-211">Puestos</span><span class="sxs-lookup"><span data-stu-id="de6de-211">Positions</span></span>

<span data-ttu-id="de6de-212">Un puesto es un caso individual de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="de6de-212">A position is an individual instance of a job.</span></span> <span data-ttu-id="de6de-213">Por ejemplo, el puesto "Director de ventas (Este)" es uno de los puestos asociados al trabajo "Director de ventas".</span><span class="sxs-lookup"><span data-stu-id="de6de-213">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="de6de-214">Un puesto existe en un departamento.</span><span class="sxs-lookup"><span data-stu-id="de6de-214">A position exists in a department.</span></span> <span data-ttu-id="de6de-215">Solo un trabajador puede asociarse solo a cada puesto.</span><span class="sxs-lookup"><span data-stu-id="de6de-215">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="de6de-216">Tenga en cuenta los siguientes datos y configuración al configurar los puestos:</span><span class="sxs-lookup"><span data-stu-id="de6de-216">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="de6de-217">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-217">Position (required)</span></span>
- <span data-ttu-id="de6de-218">Descripción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-218">Description (required)</span></span>
- <span data-ttu-id="de6de-219">Trabajo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-219">Job (required)</span></span>
- <span data-ttu-id="de6de-220">Departamento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-220">Department (required)</span></span>
- <span data-ttu-id="de6de-221">Tipo de puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-221">Position type (required)</span></span>
- <span data-ttu-id="de6de-222">Equivalente de jornada completa</span><span class="sxs-lookup"><span data-stu-id="de6de-222">Full-time equivalent</span></span>
- <span data-ttu-id="de6de-223">Horas ordinarias anuales (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-223">Annual regular hours (required)</span></span>
- <span data-ttu-id="de6de-224">Pagado por la entidad jurídica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-224">Paid by legal entity (required)</span></span>
- <span data-ttu-id="de6de-225">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-225">Pay cycle (required)</span></span>
- <span data-ttu-id="de6de-226">Dimensión financiera predeterminada – Centro de coste (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-226">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="de6de-227">Asignación de trabajador – Trabajador, inicio de la asignación, final de la asignación, código de motivo</span><span class="sxs-lookup"><span data-stu-id="de6de-227">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="de6de-228">Si varios puestos en el mismo departamento están asociados al mismo trabajo, se consolidan en un solo puesto en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-228">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="de6de-229">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="de6de-229">For more information, see the following topics:</span></span>

- [<span data-ttu-id="de6de-230">Organizar los recursos mediante departamentos, trabajos y puestos</span><span class="sxs-lookup"><span data-stu-id="de6de-230">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="de6de-231">Configurar puestos</span><span class="sxs-lookup"><span data-stu-id="de6de-231">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="de6de-232">Departamentos</span><span class="sxs-lookup"><span data-stu-id="de6de-232">Departments</span></span>

<span data-ttu-id="de6de-233">Un departamneto es una unidad operativa que representa una categoría o un área funcional de la organización.</span><span class="sxs-lookup"><span data-stu-id="de6de-233">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="de6de-234">Un departamento es responsable de un área específica de la organización, como ventas, contabilidad o recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="de6de-234">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="de6de-235">Puede usar departamentos para informar sobre las áreas funcionales.</span><span class="sxs-lookup"><span data-stu-id="de6de-235">You can use departments to report on functional areas.</span></span> <span data-ttu-id="de6de-236">Los departamentos pueden tener responsabilidad de pérdidas y ganancias.</span><span class="sxs-lookup"><span data-stu-id="de6de-236">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="de6de-237">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="de6de-237">For more information, see the following topics:</span></span>

- [<span data-ttu-id="de6de-238">Crear un departamento y asociarlo a la jerarquía de departamentos</span><span class="sxs-lookup"><span data-stu-id="de6de-238">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="de6de-239">Definir nuevos departamentos</span><span class="sxs-lookup"><span data-stu-id="de6de-239">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="de6de-240">Ciclos y períodos de pago</span><span class="sxs-lookup"><span data-stu-id="de6de-240">Pay cycles and pay periods</span></span>

<span data-ttu-id="de6de-241">Un ciclo de pago determina la frecuencia con la que se ejecuta el cálculo de nómina y los días específicos en los que se paga a los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="de6de-241">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="de6de-242">Por ejemplo, un ciclo de pago puede ser mensual y a los empleados se les podría pagar el último día del mes.</span><span class="sxs-lookup"><span data-stu-id="de6de-242">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="de6de-243">De forma alternativa, un ciclo de pago puede ser semanal y a los empleados se les podría pagar el martes después del final del período de pago.</span><span class="sxs-lookup"><span data-stu-id="de6de-243">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="de6de-244">Los ciclos de pago se asignan a los puestos para controlar cuándo se paga a los trabajadores en esos puestos.</span><span class="sxs-lookup"><span data-stu-id="de6de-244">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="de6de-245">Después de crear ciclos de pago, puede generar los períodos de pago para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="de6de-245">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="de6de-246">Cada período de pago incluye una fecha de pago predeterminada basada en la información que proporcione.</span><span class="sxs-lookup"><span data-stu-id="de6de-246">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="de6de-247">Sin embargo, puede modificar la fecha de pago predeterminada en un período de pago para permitir excepciones, por ejemplo, cuando la fecha de pago se encuentra en un día festivo.</span><span class="sxs-lookup"><span data-stu-id="de6de-247">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="de6de-248">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="de6de-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="de6de-249">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-249">Pay cycle (required)</span></span>
- <span data-ttu-id="de6de-250">Frecuencia del ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-250">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="de6de-251">Fecha de inicio del período (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-251">Period start date (first pay period required)</span></span>
- <span data-ttu-id="de6de-252">Fecha de pago predeterminado (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-252">Default payment date (first pay period required)</span></span>

<span data-ttu-id="de6de-253">Esta información se integra con Dayforce como grupos salariales y se separa por país o región para cada ciclo de pago.</span><span class="sxs-lookup"><span data-stu-id="de6de-253">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="de6de-254">Al menos se debe generar un período de sueldo antes de la integración.</span><span class="sxs-lookup"><span data-stu-id="de6de-254">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="de6de-255">Dayforce genera los calendarios de grupo salarial y las fechas de pago, en función de la fecha inicial del primer período de pago y la fecha de pago predeterminada que se configuran en Talent.</span><span class="sxs-lookup"><span data-stu-id="de6de-255">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="de6de-256">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="de6de-256">Earning codes</span></span>

<span data-ttu-id="de6de-257">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="de6de-257">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="de6de-258">Los códigos tienen distintos parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="de6de-258">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="de6de-259">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="de6de-259">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="de6de-260">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-260">Earning Code (required)</span></span>
- <span data-ttu-id="de6de-261">Descripción</span><span class="sxs-lookup"><span data-stu-id="de6de-261">Description</span></span>
- <span data-ttu-id="de6de-262">Unidad de medida</span><span class="sxs-lookup"><span data-stu-id="de6de-262">Unit of measure</span></span>
- <span data-ttu-id="de6de-263">Productivo</span><span class="sxs-lookup"><span data-stu-id="de6de-263">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="de6de-264">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="de6de-264">Worker data</span></span>

<span data-ttu-id="de6de-265">Los registros para los diferentes tipos de trabajadores que tiene son importantes para los sistemas de recursos humanos y nómina.</span><span class="sxs-lookup"><span data-stu-id="de6de-265">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="de6de-266">La información que se indique se puede utilizar para efectuar un seguimiento de los trabajadores y su información personal.</span><span class="sxs-lookup"><span data-stu-id="de6de-266">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="de6de-267">Puede mantener la información siguiente para los trabajadores:</span><span class="sxs-lookup"><span data-stu-id="de6de-267">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="de6de-268">**Básica**: permite mantener la información básica de un trabajador, como la información de contacto, información demográfica, información de identificación, información de familia, estado del servicio militar, información de expatriado y contactos personales y de emergencia.</span><span class="sxs-lookup"><span data-stu-id="de6de-268">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="de6de-269">**Empleo**: permite mantener la información sobre el empleo de un trabajador, como afiliación de la empresa u organización, asignación de puesto, fecha de inicio y finalización, idoneidad para el trabajo, condiciones de empleo, pensión, vacaciones y la información de reubicación.</span><span class="sxs-lookup"><span data-stu-id="de6de-269">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="de6de-270">**Bajas y ausencias**: permite mantener información sobre las ausencias de un trabajador, como calendarios de trabajo, transacciones de ausencia y configuración de ausencias.</span><span class="sxs-lookup"><span data-stu-id="de6de-270">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="de6de-271">**Compensación y nómina**: permite mantener la información sobre los planes de compensación y la información de nómina de un trabajador, como inscripción del plan, concesiones, desempeño, comisión, información fiscal, retiro y deducciones de sueldo.</span><span class="sxs-lookup"><span data-stu-id="de6de-271">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="de6de-272">Al introducir la información del trabajador, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-272">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="de6de-273">Información general</span><span class="sxs-lookup"><span data-stu-id="de6de-273">General information</span></span>

- <span data-ttu-id="de6de-274">Número de personal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-274">Personnel number (required)</span></span>
- <span data-ttu-id="de6de-275">Nombre (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-275">First name (required)</span></span>
- <span data-ttu-id="de6de-276">Apellido (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-276">Last name (required)</span></span>
- <span data-ttu-id="de6de-277">Segundo nombre</span><span class="sxs-lookup"><span data-stu-id="de6de-277">Middle name</span></span>
- <span data-ttu-id="de6de-278">Antigüedad</span><span class="sxs-lookup"><span data-stu-id="de6de-278">Seniority date</span></span>
- <span data-ttu-id="de6de-279">Conocido como</span><span class="sxs-lookup"><span data-stu-id="de6de-279">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="de6de-280">Información personal</span><span class="sxs-lookup"><span data-stu-id="de6de-280">Personal information</span></span>

- <span data-ttu-id="de6de-281">Estado civil (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-281">Marital status (required)</span></span>
- <span data-ttu-id="de6de-282">Fecha de nacimiento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-282">Birth date (required)</span></span>
- <span data-ttu-id="de6de-283">Sexo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-283">Gender (required)</span></span>
- <span data-ttu-id="de6de-284">Persona con discapacidades</span><span class="sxs-lookup"><span data-stu-id="de6de-284">Person with disabilities</span></span>
- <span data-ttu-id="de6de-285">País o región, nacionalidad (solo para México)</span><span class="sxs-lookup"><span data-stu-id="de6de-285">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="de6de-286">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="de6de-286">Address information</span></span>

- <span data-ttu-id="de6de-287">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-287">Primary (required)</span></span>
- <span data-ttu-id="de6de-288">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-288">Country/region (required)</span></span>
- <span data-ttu-id="de6de-289">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-289">Postal code (required)</span></span>
- <span data-ttu-id="de6de-290">Número de calle (obligatorio) (solo para México)</span><span class="sxs-lookup"><span data-stu-id="de6de-290">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="de6de-291">Complemento de edificio (solo para México)</span><span class="sxs-lookup"><span data-stu-id="de6de-291">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="de6de-292">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-292">City (required)</span></span>
- <span data-ttu-id="de6de-293">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-293">State (required)</span></span>
- <span data-ttu-id="de6de-294">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-294">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="de6de-295">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="de6de-295">Contact information</span></span> 

- <span data-ttu-id="de6de-296">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-296">Primary (required)</span></span>
- <span data-ttu-id="de6de-297">Número de contacto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-297">Contact number (required)</span></span>
- <span data-ttu-id="de6de-298">Extensión</span><span class="sxs-lookup"><span data-stu-id="de6de-298">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="de6de-299">Información de nómina y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="de6de-299">Payroll information and earning codes</span></span>

<span data-ttu-id="de6de-300">A los empleados se les pueden asignar ganancias específicas de una frecuencia determinada de pago y tener un método de pago preferido.</span><span class="sxs-lookup"><span data-stu-id="de6de-300">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="de6de-301">Los siguientes campos se utilizan en Dayforce para ayudar a garantizar que se usen las preferencias y valores.</span><span class="sxs-lookup"><span data-stu-id="de6de-301">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="de6de-302">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="de6de-302">Earning codes</span></span>

- <span data-ttu-id="de6de-303">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-303">Position (required)</span></span>
- <span data-ttu-id="de6de-304">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-304">Earning Code (required)</span></span>
- <span data-ttu-id="de6de-305">Frecuencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-305">Frequency (required)</span></span>
- <span data-ttu-id="de6de-306">Importe (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-306">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="de6de-307">Información de nómina</span><span class="sxs-lookup"><span data-stu-id="de6de-307">Payroll information</span></span>

- <span data-ttu-id="de6de-308">Método de pago</span><span class="sxs-lookup"><span data-stu-id="de6de-308">Payment Method</span></span>
- <span data-ttu-id="de6de-309">Región económica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-309">Economic Region (required)</span></span>
- <span data-ttu-id="de6de-310">Id. de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="de6de-310">Employee Benefits ID</span></span>
- <span data-ttu-id="de6de-311">Número de id. nacional (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-311">National ID Number (required)</span></span>
- <span data-ttu-id="de6de-312">Número de servicio militar</span><span class="sxs-lookup"><span data-stu-id="de6de-312">Military Service Number</span></span>
- <span data-ttu-id="de6de-313">Id. de turno (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-313">Shift ID (required)</span></span>
- <span data-ttu-id="de6de-314">Número de identificación fiscal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-314">Tax Number (required)</span></span>
- <span data-ttu-id="de6de-315">Id. de sindicato (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-315">Union ID (required)</span></span>
- <span data-ttu-id="de6de-316">Id. de día laborable (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-316">Work Day ID (required)</span></span>
- <span data-ttu-id="de6de-317">Número de permiso de trabajo</span><span class="sxs-lookup"><span data-stu-id="de6de-317">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="de6de-318">Para el método de pago, México admite **Efectivo**, **Cheque** (cheque físico de la empresa) y **Pago electrónico**.</span><span class="sxs-lookup"><span data-stu-id="de6de-318">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="de6de-319">Si no se especifica ningún método de pago, **Cheque** se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="de6de-319">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="de6de-320">Detalles del empleo</span><span class="sxs-lookup"><span data-stu-id="de6de-320">Employment details</span></span>

<span data-ttu-id="de6de-321">El historial de detalles de empleo se utiliza como información clave para derivar los estados de contratación, despido y recontratación de un empleado en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-321">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="de6de-322">Dayforce solo admite un registro de empleo activo a la vez.</span><span class="sxs-lookup"><span data-stu-id="de6de-322">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="de6de-323">Fecha de inicio de empleo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-323">Employment start date (required)</span></span>
- <span data-ttu-id="de6de-324">Fecha final del empleo</span><span class="sxs-lookup"><span data-stu-id="de6de-324">Employment end date</span></span>
- <span data-ttu-id="de6de-325">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="de6de-325">Start date</span></span>
- <span data-ttu-id="de6de-326">Fecha inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="de6de-326">Adjusted start date</span></span>
- <span data-ttu-id="de6de-327">Fecha de finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="de6de-327">Termination date (required upon termination)</span></span>
- <span data-ttu-id="de6de-328">Razón de la finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="de6de-328">Termination reason (required upon termination)</span></span>

<span data-ttu-id="de6de-329">Las fechas clave de un empleado se obtienen utilizando la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="de6de-329">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="de6de-330">Talent</span><span class="sxs-lookup"><span data-stu-id="de6de-330">Talent</span></span>                | <span data-ttu-id="de6de-331">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-331">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="de6de-332">Fecha de contratación más reciente</span><span class="sxs-lookup"><span data-stu-id="de6de-332">Most recent hire date</span></span> | <span data-ttu-id="de6de-333">Inicio de empleo del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="de6de-333">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="de6de-334">Fecha de finalización</span><span class="sxs-lookup"><span data-stu-id="de6de-334">Termination date</span></span>      | <span data-ttu-id="de6de-335">Fecha de finalización del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="de6de-335">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="de6de-336">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="de6de-336">Start date</span></span>            | <span data-ttu-id="de6de-337">Fecha de inicio ajustada, fecha de inicio o inicio de empleo del registro de historial de empleo inactivo actual</span><span class="sxs-lookup"><span data-stu-id="de6de-337">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="de6de-338">Fecha de contratación original</span><span class="sxs-lookup"><span data-stu-id="de6de-338">Original hire date</span></span>    | <span data-ttu-id="de6de-339">Inicio del empleo del registro del historial de empleo más temprano</span><span class="sxs-lookup"><span data-stu-id="de6de-339">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="de6de-340">Compensación</span><span class="sxs-lookup"><span data-stu-id="de6de-340">Compensation</span></span>

<span data-ttu-id="de6de-341">Un plan de compensación fija se debe asociar al puesto principal de cada empleado durante un período de empleo.</span><span class="sxs-lookup"><span data-stu-id="de6de-341">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="de6de-342">Este período comienza en la fecha de contratación del empleado (o la fecha de inicio del empleo) y continúa hasta la finalización.</span><span class="sxs-lookup"><span data-stu-id="de6de-342">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="de6de-343">Fecha de vigencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-343">Effective Date (required)</span></span>
- <span data-ttu-id="de6de-344">Fecha de expiración</span><span class="sxs-lookup"><span data-stu-id="de6de-344">Expiration date</span></span>
- <span data-ttu-id="de6de-345">Índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-345">Pay Rate (required)</span></span>
- <span data-ttu-id="de6de-346">Conversiones de índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-346">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="de6de-347">Equivalente anual (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-347">Annual equivalent (required)</span></span>
- <span data-ttu-id="de6de-348">Equivalente por hora (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-348">Hourly equivalent (required)</span></span>

<span data-ttu-id="de6de-349">Si un empleado por hora tiene varios puestos, se importa la compensación fija del puesto principal en Dayforce como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="de6de-349">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="de6de-350">En el caso de los puestos no principales, el índice por hora se guarda en el puesto correspondiente en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-350">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="de6de-351">Si un empleado a sueldo tiene varios puestos, se derivan el índice por hora acumulativa y el sueldo anual en todos los puestos activos y se utilizan como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="de6de-351">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="de6de-352">Números de identificación</span><span class="sxs-lookup"><span data-stu-id="de6de-352">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="de6de-353">Identificador de seguridad social</span><span class="sxs-lookup"><span data-stu-id="de6de-353">Social Security identifier</span></span> 

<span data-ttu-id="de6de-354">Cada empleado debe tener un identificador principal.</span><span class="sxs-lookup"><span data-stu-id="de6de-354">Every employee must have one primary identifier.</span></span> <span data-ttu-id="de6de-355">Este identificador debe ser de tipo de identificación **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="de6de-355">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="de6de-356">En Dayforce, se deriva automáticamente como el identificador de seguridad social del empleado que se requiere para ser contratado.</span><span class="sxs-lookup"><span data-stu-id="de6de-356">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="de6de-357">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-357">Primary (required)</span></span>
- <span data-ttu-id="de6de-358">Tipo de identificación = "Nº de SS"</span><span class="sxs-lookup"><span data-stu-id="de6de-358">Identification Type = "SSN"</span></span>
- <span data-ttu-id="de6de-359">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="de6de-359">Issued Date</span></span>
- <span data-ttu-id="de6de-360">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="de6de-360">Expiration Date</span></span>

<span data-ttu-id="de6de-361">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="de6de-361">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="de6de-362">Sin embargo, solo el registro que está marcado como **Principal** está integrado en Dayforce, independientemente de si el número está activo o caducado.</span><span class="sxs-lookup"><span data-stu-id="de6de-362">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="de6de-363">Cuentas bancarias y desembolsos</span><span class="sxs-lookup"><span data-stu-id="de6de-363">Bank accounts and disbursements</span></span>

<span data-ttu-id="de6de-364">La información de cuenta bancaria válida se debe especificar para cualquier empleado que elija recibir el pago por transferencias de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="de6de-364">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="de6de-365">Talent</span><span class="sxs-lookup"><span data-stu-id="de6de-365">Talent</span></span>                         | <span data-ttu-id="de6de-366">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-366">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="de6de-367">Número de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-367">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="de6de-368">Código SWIFT (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-368">SWIFT code (required)</span></span>          | <span data-ttu-id="de6de-369">Campo **Identificador del banco** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="de6de-369">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="de6de-370">Número de sucursal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-370">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="de6de-371">Tipo de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-371">Bank account type (required)</span></span>   | <span data-ttu-id="de6de-372">Campo **Tipo de cuenta** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="de6de-372">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="de6de-373">Los valores admitidos incluyen **Comprobación** y **Nómina**.</span><span class="sxs-lookup"><span data-stu-id="de6de-373">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="de6de-374">Los empleados que elijan que se les pague a través de transferencia bancaria deben proporcionar un vínculo a una cuenta de remanente que esté en una entidad legal que tenga su dirección principal en México y esté asociada con una cuenta bancaria válida de un banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="de6de-374">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="de6de-375">Todas las demás cuentas no remanentes se ignoran.</span><span class="sxs-lookup"><span data-stu-id="de6de-375">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="de6de-376">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="de6de-376">Address information</span></span>

<span data-ttu-id="de6de-377">Cada empleado debe tener una ubicación principal.</span><span class="sxs-lookup"><span data-stu-id="de6de-377">Every employee must have one primary location.</span></span> <span data-ttu-id="de6de-378">En Dayforce, esta ubicación se usa para determinar la residencia principal del empleado para impuestos.</span><span class="sxs-lookup"><span data-stu-id="de6de-378">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="de6de-379">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-379">Primary (required)</span></span>
- <span data-ttu-id="de6de-380">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-380">Country/region (required)</span></span>
- <span data-ttu-id="de6de-381">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-381">Zip/postal code (required)</span></span>
- <span data-ttu-id="de6de-382">Calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-382">Street (required)</span></span>
- <span data-ttu-id="de6de-383">Número de calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-383">Street Number (required)</span></span>
- <span data-ttu-id="de6de-384">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="de6de-384">Building Complement</span></span>
- <span data-ttu-id="de6de-385">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-385">City (required)</span></span>
- <span data-ttu-id="de6de-386">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-386">State (required)</span></span>
- <span data-ttu-id="de6de-387">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-387">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="de6de-388">Configure los datos para generar nóminas en Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="de6de-388">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="de6de-389">Si va a generar el sueldo de los empleados en Estados Unidos y Canadá, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="de6de-389">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="de6de-390">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="de6de-390">Departments are required on positions.</span></span>
- <span data-ttu-id="de6de-391">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="de6de-391">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="de6de-392">Puede configurar Talent para requerir que los puestos especifiquen un departamento.</span><span class="sxs-lookup"><span data-stu-id="de6de-392">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="de6de-393">Para ello, vaya a **Puestos compartidos de recursos humanos > Puestos > Requerir departamentos en puestos**.</span><span class="sxs-lookup"><span data-stu-id="de6de-393">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="de6de-394">Recomendamos que este valor se aplique para la integración.</span><span class="sxs-lookup"><span data-stu-id="de6de-394">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="de6de-395">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="de6de-395">Job types</span></span>

<span data-ttu-id="de6de-396">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="de6de-396">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="de6de-397">Los tipos de trabajo son obligatorios para procesar la nómina en Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="de6de-397">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="de6de-398">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="de6de-398">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="de6de-399">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="de6de-399">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="de6de-400">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="de6de-400">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="de6de-401">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="de6de-401">Job type</span></span>   | <span data-ttu-id="de6de-402">Descripción</span><span class="sxs-lookup"><span data-stu-id="de6de-402">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="de6de-403">Por hora</span><span class="sxs-lookup"><span data-stu-id="de6de-403">Hourly</span></span>     | <span data-ttu-id="de6de-404">Por hora</span><span class="sxs-lookup"><span data-stu-id="de6de-404">Hourly</span></span>      |
| <span data-ttu-id="de6de-405">Asalariado</span><span class="sxs-lookup"><span data-stu-id="de6de-405">Salaried</span></span>   | <span data-ttu-id="de6de-406">Asalariado</span><span class="sxs-lookup"><span data-stu-id="de6de-406">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="de6de-407">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="de6de-407">Position types</span></span> 

<span data-ttu-id="de6de-408">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="de6de-408">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="de6de-409">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="de6de-409">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="de6de-410">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="de6de-410">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="de6de-411">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="de6de-411">Position type</span></span>   | <span data-ttu-id="de6de-412">Descripción</span><span class="sxs-lookup"><span data-stu-id="de6de-412">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="de6de-413">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="de6de-413">Full-time</span></span>       | <span data-ttu-id="de6de-414">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="de6de-414">Full time employee</span></span> |
| <span data-ttu-id="de6de-415">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="de6de-415">Part-time</span></span>       | <span data-ttu-id="de6de-416">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="de6de-416">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="de6de-417">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="de6de-417">Reason codes</span></span>

<span data-ttu-id="de6de-418">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="de6de-418">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="de6de-419">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="de6de-419">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="de6de-420">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="de6de-420">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="de6de-421">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="de6de-421">Reason code</span></span>    | <span data-ttu-id="de6de-422">Descripción</span><span class="sxs-lookup"><span data-stu-id="de6de-422">Description</span></span>      | <span data-ttu-id="de6de-423">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="de6de-423">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="de6de-424">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="de6de-424">RESIGNATION</span></span>    | <span data-ttu-id="de6de-425">Dimisión</span><span class="sxs-lookup"><span data-stu-id="de6de-425">Resignation</span></span>      | <span data-ttu-id="de6de-426">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-426">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-427">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="de6de-427">TERMINATION</span></span>    | <span data-ttu-id="de6de-428">Finalización</span><span class="sxs-lookup"><span data-stu-id="de6de-428">Termination</span></span>      | <span data-ttu-id="de6de-429">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-429">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-430">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="de6de-430">RETIREMENT</span></span>     | <span data-ttu-id="de6de-431">Jubilación</span><span class="sxs-lookup"><span data-stu-id="de6de-431">Retirement</span></span>       | <span data-ttu-id="de6de-432">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-432">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-433">OTHER</span><span class="sxs-lookup"><span data-stu-id="de6de-433">OTHER</span></span>          | <span data-ttu-id="de6de-434">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="de6de-434">Other Reasons</span></span>    | <span data-ttu-id="de6de-435">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-435">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-436">MUERTE</span><span class="sxs-lookup"><span data-stu-id="de6de-436">DEATH</span></span>          | <span data-ttu-id="de6de-437">Muerte</span><span class="sxs-lookup"><span data-stu-id="de6de-437">Death</span></span>            | <span data-ttu-id="de6de-438">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-438">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-439">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="de6de-439">LEAVEOFABSENCE</span></span> | <span data-ttu-id="de6de-440">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="de6de-440">Leave of Absence</span></span> | <span data-ttu-id="de6de-441">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-441">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-442">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="de6de-442">CONTRACTEND</span></span>    | <span data-ttu-id="de6de-443">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="de6de-443">End of Contract</span></span>  | <span data-ttu-id="de6de-444">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-444">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-445">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="de6de-445">SALARYCHANGE</span></span>   | <span data-ttu-id="de6de-446">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="de6de-446">Change of Salary</span></span> | <span data-ttu-id="de6de-447">Compensación</span><span class="sxs-lookup"><span data-stu-id="de6de-447">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="de6de-448">Estado civil</span><span class="sxs-lookup"><span data-stu-id="de6de-448">Marital status</span></span>

<span data-ttu-id="de6de-449">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="de6de-449">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="de6de-450">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-450">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="de6de-451">Talent</span><span class="sxs-lookup"><span data-stu-id="de6de-451">Talent</span></span>                 | <span data-ttu-id="de6de-452">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-452">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="de6de-453">Casado/a</span><span class="sxs-lookup"><span data-stu-id="de6de-453">Married</span></span>                | <span data-ttu-id="de6de-454">Casado/a</span><span class="sxs-lookup"><span data-stu-id="de6de-454">Married</span></span>              |
| <span data-ttu-id="de6de-455">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="de6de-455">Single</span></span>                 | <span data-ttu-id="de6de-456">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="de6de-456">Single</span></span>               |
| <span data-ttu-id="de6de-457">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="de6de-457">Widowed</span></span>                | <span data-ttu-id="de6de-458">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="de6de-458">Widowed</span></span>              |
| <span data-ttu-id="de6de-459">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="de6de-459">Divorced</span></span>               | <span data-ttu-id="de6de-460">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="de6de-460">Divorced</span></span>             |
| <span data-ttu-id="de6de-461">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="de6de-461">Registered Partnership</span></span> | <span data-ttu-id="de6de-462">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="de6de-462">Domestic Partnership</span></span> |
| <span data-ttu-id="de6de-463">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="de6de-463">None</span></span>                   | <span data-ttu-id="de6de-464">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="de6de-464">None</span></span>                 |
| <span data-ttu-id="de6de-465">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="de6de-465">Cohabiting</span></span>             | <span data-ttu-id="de6de-466">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="de6de-466">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="de6de-467">Género</span><span class="sxs-lookup"><span data-stu-id="de6de-467">Gender</span></span>

<span data-ttu-id="de6de-468">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="de6de-468">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="de6de-469">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-469">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="de6de-470">Talent</span><span class="sxs-lookup"><span data-stu-id="de6de-470">Talent</span></span>       | <span data-ttu-id="de6de-471">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-471">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="de6de-472">Hombre</span><span class="sxs-lookup"><span data-stu-id="de6de-472">Male</span></span>         | <span data-ttu-id="de6de-473">Hombre</span><span class="sxs-lookup"><span data-stu-id="de6de-473">Male</span></span>            |
| <span data-ttu-id="de6de-474">Mujer</span><span class="sxs-lookup"><span data-stu-id="de6de-474">Female</span></span>       | <span data-ttu-id="de6de-475">Mujer</span><span class="sxs-lookup"><span data-stu-id="de6de-475">Female</span></span>          |
| <span data-ttu-id="de6de-476">No específico</span><span class="sxs-lookup"><span data-stu-id="de6de-476">Non-specific</span></span> | <span data-ttu-id="de6de-477">*No admitido*</span><span class="sxs-lookup"><span data-stu-id="de6de-477">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="de6de-478">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="de6de-478">Earning codes</span></span>

<span data-ttu-id="de6de-479">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="de6de-479">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="de6de-480">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="de6de-480">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="de6de-481">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="de6de-481">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="de6de-482">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="de6de-482">Supported frequencies</span></span>

- <span data-ttu-id="de6de-483">Todas</span><span class="sxs-lookup"><span data-stu-id="de6de-483">All</span></span>
- <span data-ttu-id="de6de-484">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="de6de-484">EVERYPAY</span></span>
- <span data-ttu-id="de6de-485">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="de6de-485">EACHPAYPERIOD</span></span>
- <span data-ttu-id="de6de-486">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="de6de-486">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="de6de-487">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="de6de-487">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="de6de-488">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-488">1OFMTH</span></span>
- <span data-ttu-id="de6de-489">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-489">LASTOFMTH</span></span>
- <span data-ttu-id="de6de-490">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-490">2OFMTH</span></span>
- <span data-ttu-id="de6de-491">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-491">3OFMTH</span></span>
- <span data-ttu-id="de6de-492">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-492">4OFMTH</span></span>
- <span data-ttu-id="de6de-493">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-493">5OFMTH</span></span>
- <span data-ttu-id="de6de-494">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-494">1N2OFMTH</span></span>
- <span data-ttu-id="de6de-495">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-495">3N4OFMTH</span></span>
- <span data-ttu-id="de6de-496">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-496">1N3OFMTH</span></span>
- <span data-ttu-id="de6de-497">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-497">1N4OFMTH</span></span>
- <span data-ttu-id="de6de-498">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-498">2N3OFMTH</span></span>
- <span data-ttu-id="de6de-499">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-499">2N4OFMTH</span></span>
- <span data-ttu-id="de6de-500">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-500">1N2N3OFMTH</span></span>
- <span data-ttu-id="de6de-501">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-501">1N2N4OFMTH</span></span>
- <span data-ttu-id="de6de-502">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-502">1N3N4OFMTH</span></span>
- <span data-ttu-id="de6de-503">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-503">2N3N4OFMTH</span></span>
- <span data-ttu-id="de6de-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="de6de-505">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="de6de-505">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="de6de-506">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="de6de-506">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="de6de-507">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="de6de-507">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="de6de-508">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="de6de-508">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="de6de-509">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="de6de-509">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="de6de-510">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="de6de-510">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="de6de-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="de6de-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="de6de-512">Direcciones</span><span class="sxs-lookup"><span data-stu-id="de6de-512">Addresses</span></span>

<span data-ttu-id="de6de-513">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="de6de-513">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="de6de-514">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="de6de-514">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="de6de-515">Talent</span><span class="sxs-lookup"><span data-stu-id="de6de-515">Talent</span></span>          | <span data-ttu-id="de6de-516">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-516">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="de6de-517">País/región</span><span class="sxs-lookup"><span data-stu-id="de6de-517">Country/Region</span></span>  | <span data-ttu-id="de6de-518">Código de país</span><span class="sxs-lookup"><span data-stu-id="de6de-518">Country Code</span></span>          |
| <span data-ttu-id="de6de-519">Código postal</span><span class="sxs-lookup"><span data-stu-id="de6de-519">Zip/Postal Code</span></span> | <span data-ttu-id="de6de-520">Código postal</span><span class="sxs-lookup"><span data-stu-id="de6de-520">Postal Code</span></span>           |
| <span data-ttu-id="de6de-521">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="de6de-521">State</span></span>           | <span data-ttu-id="de6de-522">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="de6de-522">State Code</span></span>            |
| <span data-ttu-id="de6de-523">Población</span><span class="sxs-lookup"><span data-stu-id="de6de-523">City</span></span>            | <span data-ttu-id="de6de-524">Población</span><span class="sxs-lookup"><span data-stu-id="de6de-524">City</span></span>                  |
| <span data-ttu-id="de6de-525">Comarca</span><span class="sxs-lookup"><span data-stu-id="de6de-525">County</span></span>          | <span data-ttu-id="de6de-526">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="de6de-526">County (Municipality)</span></span> |
| <span data-ttu-id="de6de-527">Calle</span><span class="sxs-lookup"><span data-stu-id="de6de-527">Street</span></span>          | <span data-ttu-id="de6de-528">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="de6de-528">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="de6de-529">Regiones de impuestos</span><span class="sxs-lookup"><span data-stu-id="de6de-529">Tax regions</span></span>

<span data-ttu-id="de6de-530">Las regiones de impuestos se usan para determinar los impuestos correspondientes que se deben aplicar durante la generación de nómina.</span><span class="sxs-lookup"><span data-stu-id="de6de-530">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="de6de-531">Las regiones de impuestos se asignan a Dayforce como direcciones de ubicación.</span><span class="sxs-lookup"><span data-stu-id="de6de-531">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="de6de-532">La región de impuestos predeterminada se debe asociar al puesto activo del trabajador.</span><span class="sxs-lookup"><span data-stu-id="de6de-532">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="de6de-533">Región de impuestos (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-533">Tax region (required)</span></span>
- <span data-ttu-id="de6de-534">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-534">Country/Region (required)</span></span>
- <span data-ttu-id="de6de-535">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-535">State (required)</span></span>
- <span data-ttu-id="de6de-536">Comarca</span><span class="sxs-lookup"><span data-stu-id="de6de-536">County</span></span> 
- <span data-ttu-id="de6de-537">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="de6de-537">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="de6de-538">Configurar los datos para generar nóminas en México</span><span class="sxs-lookup"><span data-stu-id="de6de-538">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="de6de-539">Si va a generar el sueldo de los empleados en México, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="de6de-539">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="de6de-540">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="de6de-540">Departments are required on positions.</span></span>
- <span data-ttu-id="de6de-541">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="de6de-541">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="de6de-542">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="de6de-542">Job types</span></span>

<span data-ttu-id="de6de-543">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="de6de-543">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="de6de-544">Los tipos de trabajo son obligatorios para procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="de6de-544">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="de6de-545">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="de6de-545">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="de6de-546">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="de6de-546">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="de6de-547">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="de6de-547">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="de6de-548">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="de6de-548">Job type</span></span>   | <span data-ttu-id="de6de-549">Descripción</span><span class="sxs-lookup"><span data-stu-id="de6de-549">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="de6de-550">Por hora</span><span class="sxs-lookup"><span data-stu-id="de6de-550">Hourly</span></span>     | <span data-ttu-id="de6de-551">MX Por hora</span><span class="sxs-lookup"><span data-stu-id="de6de-551">MX Hourly</span></span>   |
| <span data-ttu-id="de6de-552">Asalariado</span><span class="sxs-lookup"><span data-stu-id="de6de-552">Salaried</span></span>   | <span data-ttu-id="de6de-553">MX Asalariado</span><span class="sxs-lookup"><span data-stu-id="de6de-553">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="de6de-554">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="de6de-554">Position types</span></span> 

<span data-ttu-id="de6de-555">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="de6de-555">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="de6de-556">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="de6de-556">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="de6de-557">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="de6de-557">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="de6de-558">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="de6de-558">Position type</span></span>   | <span data-ttu-id="de6de-559">Descripción</span><span class="sxs-lookup"><span data-stu-id="de6de-559">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="de6de-560">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="de6de-560">Full-time</span></span>       | <span data-ttu-id="de6de-561">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="de6de-561">Full time employee</span></span> |
| <span data-ttu-id="de6de-562">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="de6de-562">Part-time</span></span>       | <span data-ttu-id="de6de-563">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="de6de-563">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="de6de-564">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="de6de-564">Reason codes</span></span>

<span data-ttu-id="de6de-565">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="de6de-565">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="de6de-566">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="de6de-566">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="de6de-567">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="de6de-567">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="de6de-568">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="de6de-568">Reason code</span></span>            | <span data-ttu-id="de6de-569">Descripción</span><span class="sxs-lookup"><span data-stu-id="de6de-569">Description</span></span>                    | <span data-ttu-id="de6de-570">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="de6de-570">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="de6de-571">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="de6de-571">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="de6de-572">Salida antes de la primera nómina</span><span class="sxs-lookup"><span data-stu-id="de6de-572">Departure before first payroll</span></span> | <span data-ttu-id="de6de-573">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-573">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-574">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="de6de-574">RESIGNATION</span></span>            | <span data-ttu-id="de6de-575">Dimisión</span><span class="sxs-lookup"><span data-stu-id="de6de-575">Resignation</span></span>                    | <span data-ttu-id="de6de-576">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-576">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-577">PENSION</span><span class="sxs-lookup"><span data-stu-id="de6de-577">PENSION</span></span>                | <span data-ttu-id="de6de-578">Pensión</span><span class="sxs-lookup"><span data-stu-id="de6de-578">Pension</span></span>                        | <span data-ttu-id="de6de-579">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-579">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-580">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="de6de-580">TERMINATION</span></span>            | <span data-ttu-id="de6de-581">Finalización</span><span class="sxs-lookup"><span data-stu-id="de6de-581">Termination</span></span>                    | <span data-ttu-id="de6de-582">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-582">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-583">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="de6de-583">RETIREMENT</span></span>             | <span data-ttu-id="de6de-584">Jubilación</span><span class="sxs-lookup"><span data-stu-id="de6de-584">Retirement</span></span>                     | <span data-ttu-id="de6de-585">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-585">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-586">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="de6de-586">ABSENTEE</span></span>               | <span data-ttu-id="de6de-587">Ausente</span><span class="sxs-lookup"><span data-stu-id="de6de-587">Absentee</span></span>                       | <span data-ttu-id="de6de-588">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-588">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-589">OTHER</span><span class="sxs-lookup"><span data-stu-id="de6de-589">OTHER</span></span>                  | <span data-ttu-id="de6de-590">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="de6de-590">Other Reasons</span></span>                  | <span data-ttu-id="de6de-591">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-591">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-592">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="de6de-592">CLOSURE</span></span>                | <span data-ttu-id="de6de-593">Cierre de operaciones</span><span class="sxs-lookup"><span data-stu-id="de6de-593">Business Closure</span></span>               | <span data-ttu-id="de6de-594">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-594">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-595">MUERTE</span><span class="sxs-lookup"><span data-stu-id="de6de-595">DEATH</span></span>                  | <span data-ttu-id="de6de-596">Muerte</span><span class="sxs-lookup"><span data-stu-id="de6de-596">Death</span></span>                          | <span data-ttu-id="de6de-597">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-597">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-598">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="de6de-598">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="de6de-599">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="de6de-599">Leave of Absence</span></span>               | <span data-ttu-id="de6de-600">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-600">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-601">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="de6de-601">CONTRACTEND</span></span>            | <span data-ttu-id="de6de-602">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="de6de-602">End of Contract</span></span>                | <span data-ttu-id="de6de-603">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="de6de-603">Terminate worker</span></span>     |
| <span data-ttu-id="de6de-604">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="de6de-604">SALARYCHANGE</span></span>           | <span data-ttu-id="de6de-605">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="de6de-605">Change of Salary</span></span>               | <span data-ttu-id="de6de-606">Compensación</span><span class="sxs-lookup"><span data-stu-id="de6de-606">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="de6de-607">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="de6de-607">Terms of employment</span></span>

<span data-ttu-id="de6de-608">Las condiciones laborales se usan para crear categorías de condiciones laborales.</span><span class="sxs-lookup"><span data-stu-id="de6de-608">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="de6de-609">Las condiciones se asignan a Dayforce como valores de indicador de empleo.</span><span class="sxs-lookup"><span data-stu-id="de6de-609">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="de6de-610">Las siguientes condiciones laborales y descripciones son obligatorias.</span><span class="sxs-lookup"><span data-stu-id="de6de-610">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="de6de-611">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="de6de-611">Terms of employment</span></span>   | <span data-ttu-id="de6de-612">Descripción</span><span class="sxs-lookup"><span data-stu-id="de6de-612">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="de6de-613">Normal</span><span class="sxs-lookup"><span data-stu-id="de6de-613">Regular</span></span>               | <span data-ttu-id="de6de-614">Normal</span><span class="sxs-lookup"><span data-stu-id="de6de-614">Regular</span></span>     |
| <span data-ttu-id="de6de-615">Directo</span><span class="sxs-lookup"><span data-stu-id="de6de-615">Direct</span></span>                | <span data-ttu-id="de6de-616">Directo</span><span class="sxs-lookup"><span data-stu-id="de6de-616">Direct</span></span>      |
| <span data-ttu-id="de6de-617">Prácticas</span><span class="sxs-lookup"><span data-stu-id="de6de-617">Internship</span></span>            | <span data-ttu-id="de6de-618">Prácticas</span><span class="sxs-lookup"><span data-stu-id="de6de-618">Internship</span></span>  |
| <span data-ttu-id="de6de-619">Permanente</span><span class="sxs-lookup"><span data-stu-id="de6de-619">Permanent</span></span>             | <span data-ttu-id="de6de-620">Permanente</span><span class="sxs-lookup"><span data-stu-id="de6de-620">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="de6de-621">Estado civil</span><span class="sxs-lookup"><span data-stu-id="de6de-621">Marital status</span></span>

<span data-ttu-id="de6de-622">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="de6de-622">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="de6de-623">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-623">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="de6de-624">Talent</span><span class="sxs-lookup"><span data-stu-id="de6de-624">Talent</span></span>                 | <span data-ttu-id="de6de-625">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-625">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="de6de-626">Casado/a</span><span class="sxs-lookup"><span data-stu-id="de6de-626">Married</span></span>                | <span data-ttu-id="de6de-627">Casado/a</span><span class="sxs-lookup"><span data-stu-id="de6de-627">Married</span></span>                   |
| <span data-ttu-id="de6de-628">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="de6de-628">Single</span></span>                 | <span data-ttu-id="de6de-629">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="de6de-629">Single</span></span>                    |
| <span data-ttu-id="de6de-630">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="de6de-630">Widowed</span></span>                | <span data-ttu-id="de6de-631">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="de6de-631">Widowed</span></span>                   |
| <span data-ttu-id="de6de-632">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="de6de-632">Divorced</span></span>               | <span data-ttu-id="de6de-633">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="de6de-633">Divorced</span></span>                  |
| <span data-ttu-id="de6de-634">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="de6de-634">Registered Partnership</span></span> | <span data-ttu-id="de6de-635">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="de6de-635">Domestic Partnership</span></span>      |
| <span data-ttu-id="de6de-636">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="de6de-636">None</span></span>                   | <span data-ttu-id="de6de-637">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="de6de-637">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="de6de-638">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="de6de-638">Cohabiting</span></span>             | <span data-ttu-id="de6de-639">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="de6de-639">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="de6de-640">Género</span><span class="sxs-lookup"><span data-stu-id="de6de-640">Gender</span></span>

<span data-ttu-id="de6de-641">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="de6de-641">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="de6de-642">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-642">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="de6de-643">Talent</span><span class="sxs-lookup"><span data-stu-id="de6de-643">Talent</span></span>       | <span data-ttu-id="de6de-644">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-644">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="de6de-645">Hombre</span><span class="sxs-lookup"><span data-stu-id="de6de-645">Male</span></span>         | <span data-ttu-id="de6de-646">Hombre</span><span class="sxs-lookup"><span data-stu-id="de6de-646">Male</span></span>                      |
| <span data-ttu-id="de6de-647">Mujer</span><span class="sxs-lookup"><span data-stu-id="de6de-647">Female</span></span>       | <span data-ttu-id="de6de-648">Mujer</span><span class="sxs-lookup"><span data-stu-id="de6de-648">Female</span></span>                    |
| <span data-ttu-id="de6de-649">No específico</span><span class="sxs-lookup"><span data-stu-id="de6de-649">Non-specific</span></span> | <span data-ttu-id="de6de-650">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="de6de-650">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="de6de-651">Método de pago</span><span class="sxs-lookup"><span data-stu-id="de6de-651">Payment method</span></span>

<span data-ttu-id="de6de-652">Los métodos de pago ofrecen al empleado y la empresa una forma de describir cómo se pagará a los empleados.</span><span class="sxs-lookup"><span data-stu-id="de6de-652">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="de6de-653">Los métodos de pago se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="de6de-653">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="de6de-654">En la siguiente tabla se muestra cómo los métodos de pago se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-654">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="de6de-655">Talent</span><span class="sxs-lookup"><span data-stu-id="de6de-655">Talent</span></span>             | <span data-ttu-id="de6de-656">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-656">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="de6de-657">Efectivo</span><span class="sxs-lookup"><span data-stu-id="de6de-657">Cash</span></span>               | <span data-ttu-id="de6de-658">Efectivo</span><span class="sxs-lookup"><span data-stu-id="de6de-658">Cash</span></span>                      |
| <span data-ttu-id="de6de-659">Pago electrónico</span><span class="sxs-lookup"><span data-stu-id="de6de-659">Electronic Payment</span></span> | <span data-ttu-id="de6de-660">Transferir</span><span class="sxs-lookup"><span data-stu-id="de6de-660">Transfer</span></span>                  |
| <span data-ttu-id="de6de-661">Comprobación</span><span class="sxs-lookup"><span data-stu-id="de6de-661">Check</span></span>              | <span data-ttu-id="de6de-662">Cheque</span><span class="sxs-lookup"><span data-stu-id="de6de-662">Cheque</span></span>                    |
| <span data-ttu-id="de6de-663">Efecto bancario</span><span class="sxs-lookup"><span data-stu-id="de6de-663">Bank Draft</span></span>         | <span data-ttu-id="de6de-664">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="de6de-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="de6de-665">Otras</span><span class="sxs-lookup"><span data-stu-id="de6de-665">Other</span></span>              | <span data-ttu-id="de6de-666">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="de6de-666">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="de6de-667">Tipo de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="de6de-667">Bank account type</span></span>

<span data-ttu-id="de6de-668">Los tipos de cuenta bancaria se usan para los pagos electrónicos a los empleados.</span><span class="sxs-lookup"><span data-stu-id="de6de-668">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="de6de-669">Los tipos de cuenta bancaria se asignan a Dayforce como información de cuenta de transferencia.</span><span class="sxs-lookup"><span data-stu-id="de6de-669">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="de6de-670">Los tipos de cuenta bancaria se convierten, según proceda, en los valores aceptados en la integración.</span><span class="sxs-lookup"><span data-stu-id="de6de-670">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="de6de-671">Talent</span><span class="sxs-lookup"><span data-stu-id="de6de-671">Talent</span></span>            | <span data-ttu-id="de6de-672">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-672">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="de6de-673">Cuenta corriente</span><span class="sxs-lookup"><span data-stu-id="de6de-673">Checking Account</span></span>  | <span data-ttu-id="de6de-674">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="de6de-674">CheckingAccount</span></span>           |
| <span data-ttu-id="de6de-675">Cuenta de nómina</span><span class="sxs-lookup"><span data-stu-id="de6de-675">Payroll Account</span></span>   | <span data-ttu-id="de6de-676">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="de6de-676">PayrollAccount</span></span>            |
| <span data-ttu-id="de6de-677">Cuenta de ahorros</span><span class="sxs-lookup"><span data-stu-id="de6de-677">Savings Account</span></span>   | <span data-ttu-id="de6de-678">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="de6de-678">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="de6de-679">Cuenta de BankGirot</span><span class="sxs-lookup"><span data-stu-id="de6de-679">BankGirot account</span></span> | <span data-ttu-id="de6de-680">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="de6de-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="de6de-681">Cuenta de PlusGirot</span><span class="sxs-lookup"><span data-stu-id="de6de-681">PlusGirot account</span></span> | <span data-ttu-id="de6de-682">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="de6de-682">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="de6de-683">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="de6de-683">Earning codes</span></span>

<span data-ttu-id="de6de-684">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="de6de-684">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="de6de-685">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="de6de-685">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="de6de-686">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="de6de-686">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="de6de-687">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="de6de-687">Supported frequencies</span></span>

- <span data-ttu-id="de6de-688">Todas</span><span class="sxs-lookup"><span data-stu-id="de6de-688">All</span></span>
- <span data-ttu-id="de6de-689">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="de6de-689">EVERYPAY</span></span>
- <span data-ttu-id="de6de-690">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="de6de-690">EACHPAYPERIOD</span></span>
- <span data-ttu-id="de6de-691">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="de6de-691">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="de6de-692">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="de6de-692">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="de6de-693">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-693">1OFMTH</span></span>
- <span data-ttu-id="de6de-694">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-694">LASTOFMTH</span></span>
- <span data-ttu-id="de6de-695">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-695">2OFMTH</span></span>
- <span data-ttu-id="de6de-696">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-696">3OFMTH</span></span>
- <span data-ttu-id="de6de-697">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-697">4OFMTH</span></span>
- <span data-ttu-id="de6de-698">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-698">5OFMTH</span></span>
- <span data-ttu-id="de6de-699">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-699">1N2OFMTH</span></span>
- <span data-ttu-id="de6de-700">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-700">3N4OFMTH</span></span>
- <span data-ttu-id="de6de-701">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-701">1N3OFMTH</span></span>
- <span data-ttu-id="de6de-702">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-702">1N4OFMTH</span></span>
- <span data-ttu-id="de6de-703">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-703">2N3OFMTH</span></span>
- <span data-ttu-id="de6de-704">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-704">2N4OFMTH</span></span>
- <span data-ttu-id="de6de-705">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-705">1N2N3OFMTH</span></span>
- <span data-ttu-id="de6de-706">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-706">1N2N4OFMTH</span></span>
- <span data-ttu-id="de6de-707">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-707">1N3N4OFMTH</span></span>
- <span data-ttu-id="de6de-708">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-708">2N3N4OFMTH</span></span>
- <span data-ttu-id="de6de-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de6de-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="de6de-710">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="de6de-710">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="de6de-711">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="de6de-711">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="de6de-712">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="de6de-712">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="de6de-713">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="de6de-713">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="de6de-714">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="de6de-714">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="de6de-715">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="de6de-715">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="de6de-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="de6de-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="de6de-717">Direcciones</span><span class="sxs-lookup"><span data-stu-id="de6de-717">Addresses</span></span>

<span data-ttu-id="de6de-718">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="de6de-718">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="de6de-719">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="de6de-719">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="de6de-720">Talent</span><span class="sxs-lookup"><span data-stu-id="de6de-720">Talent</span></span>              | <span data-ttu-id="de6de-721">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de6de-721">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="de6de-722">País/región</span><span class="sxs-lookup"><span data-stu-id="de6de-722">Country/Region</span></span>      | <span data-ttu-id="de6de-723">Código de país</span><span class="sxs-lookup"><span data-stu-id="de6de-723">Country Code</span></span>          |
| <span data-ttu-id="de6de-724">Código postal</span><span class="sxs-lookup"><span data-stu-id="de6de-724">Zip/Postal Code</span></span>     | <span data-ttu-id="de6de-725">Código postal</span><span class="sxs-lookup"><span data-stu-id="de6de-725">Postal Code</span></span>           |
| <span data-ttu-id="de6de-726">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="de6de-726">State</span></span>               | <span data-ttu-id="de6de-727">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="de6de-727">State Code</span></span>            |
| <span data-ttu-id="de6de-728">Población</span><span class="sxs-lookup"><span data-stu-id="de6de-728">City</span></span>                | <span data-ttu-id="de6de-729">Población</span><span class="sxs-lookup"><span data-stu-id="de6de-729">City</span></span>                  |
| <span data-ttu-id="de6de-730">Comarca</span><span class="sxs-lookup"><span data-stu-id="de6de-730">County</span></span>              | <span data-ttu-id="de6de-731">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="de6de-731">County (Municipality)</span></span> |
| <span data-ttu-id="de6de-732">Calle</span><span class="sxs-lookup"><span data-stu-id="de6de-732">Street</span></span>              | <span data-ttu-id="de6de-733">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="de6de-733">Address Line 1</span></span>        |
| <span data-ttu-id="de6de-734">Número de calle</span><span class="sxs-lookup"><span data-stu-id="de6de-734">Street Number</span></span>       | <span data-ttu-id="de6de-735">Línea de dirección 2</span><span class="sxs-lookup"><span data-stu-id="de6de-735">Address Line 2</span></span>        |
| <span data-ttu-id="de6de-736">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="de6de-736">Building Complement</span></span> | <span data-ttu-id="de6de-737">Línea de dirección 5</span><span class="sxs-lookup"><span data-stu-id="de6de-737">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="de6de-738">Número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="de6de-738">Passport number</span></span>

<span data-ttu-id="de6de-739">Los empleados pueden declarar la información del pasaporte.</span><span class="sxs-lookup"><span data-stu-id="de6de-739">Employees can declare passport information.</span></span> <span data-ttu-id="de6de-740">Esta información es del tipo de identificación **Pasaporte** y se integra en Dayforce como parte de la información específica de México de un empleado.</span><span class="sxs-lookup"><span data-stu-id="de6de-740">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="de6de-741">Tipo de identificación = "Pasaporte"</span><span class="sxs-lookup"><span data-stu-id="de6de-741">Identification Type = "Passport"</span></span>
- <span data-ttu-id="de6de-742">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="de6de-742">Issued Date</span></span>
- <span data-ttu-id="de6de-743">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="de6de-743">Expiration Date</span></span>

<span data-ttu-id="de6de-744">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Pasaporte**.</span><span class="sxs-lookup"><span data-stu-id="de6de-744">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="de6de-745">Sin embargo, solo la entrada de pasaporte activa actual se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-745">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="de6de-746">Si todas las entradas de pasaporte han caducado, el pasaporte que se emitió más recientemente se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de6de-746">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
