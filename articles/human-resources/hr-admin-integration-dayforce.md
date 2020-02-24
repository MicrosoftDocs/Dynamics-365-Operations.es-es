---
title: Configurar la integración con Dayforce
description: La integración entre Microsoft Dynamics 365 Human Resources y Ceridian Dayforce se basa en varios pasos de configuración que se describen en este artículo. Debe configurar la integración en Human Resources y Dayforce para poder procesar un período de pago.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85e7274b0e9c130e5c3426fd1fff98410f93e49a
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010422"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="81494-104">Configurar la integración con Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-104">Configure integration with Dayforce</span></span>

<span data-ttu-id="81494-105">La integración entre Microsoft Dynamics 365 Human Resources y Ceridian Dayforce se basa en varios pasos de configuración que se describen en este artículo.</span><span class="sxs-lookup"><span data-stu-id="81494-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="81494-106">Debe configurar la integración en Human Resources y Dayforce para poder procesar un período de pago.</span><span class="sxs-lookup"><span data-stu-id="81494-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="81494-107">Cuando se utiliza un servicio como Dayforce para completar períodos de pago, debe habilitar la integración en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="81494-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="81494-108">La integración necesita los datos específicos de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="81494-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="81494-109">Por lo tanto, debe comprobar que los datos que se asignen a Dayforce se hayan configurado en Human Resources de una forma que admita la integración.</span><span class="sxs-lookup"><span data-stu-id="81494-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="81494-110">La integración utiliza las amplias categorías de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="81494-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="81494-111">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-111">Human resources data</span></span>
- <span data-ttu-id="81494-112">Catos de compensación</span><span class="sxs-lookup"><span data-stu-id="81494-112">Compensation data</span></span>
- <span data-ttu-id="81494-113">Datos de nómina, como ciclos de pago, períodos de sueldo, y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="81494-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="81494-114">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="81494-114">Worker data</span></span>

<span data-ttu-id="81494-115">Este artículo describe los pasos que debe seguir para habilitar la integración.</span><span class="sxs-lookup"><span data-stu-id="81494-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="81494-116">También explica los tipos de datos y los detalles de configuración que requiere la integración.</span><span class="sxs-lookup"><span data-stu-id="81494-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="81494-117">Habilitar la integración</span><span class="sxs-lookup"><span data-stu-id="81494-117">Enable the integration</span></span>

<span data-ttu-id="81494-118">En Human Resources, debe activar la integración y especificar información de configuración para conectarse a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="81494-119">Si desea que la transacción de contabilidad general que se genera se importe en Microsoft Dynamics 365 Finance, también debe configurar una cuenta de almacenamiento de Microsoft Azure y especificar la cadena de conexión Azure Storage en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="81494-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="81494-120">Para activar la integración en Human Resources, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="81494-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="81494-121">En la página **Administración del sistema** , seleccione **Configuración de la integración**.</span><span class="sxs-lookup"><span data-stu-id="81494-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="81494-122">Permite especificar el extremo del Protocolo de transferencia de archivos (FTP) y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="81494-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="81494-123">Escriba el nombre de usuario y contraseña del usuario que accederá al extremo y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="81494-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="81494-124">Pruebe la conexión, como sea necesario, y establezca la opción **Habilitar la integración de nómina** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="81494-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="81494-125">Cuando está activada la integración, se crean el paquete y los archivos de exportación de datos, y se establece la frecuencia.</span><span class="sxs-lookup"><span data-stu-id="81494-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="81494-126">Puede cambiar esta frecuencia como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="81494-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="81494-127">Para obtener más información acerca de las cuentas de almacenamiento de Azure y las cadenas de conexión de Azure Storage, consulte los artículos de Azure siguientes:</span><span class="sxs-lookup"><span data-stu-id="81494-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="81494-128">Acerca de las cuentas de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="81494-128">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="81494-129">Configurar las cadenas de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="81494-129">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="81494-130">Detalles técnicos cuando está habilitada la integración de nóminas</span><span class="sxs-lookup"><span data-stu-id="81494-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="81494-131">La activación de la integración de nóminas tiene dos efectos primarios:</span><span class="sxs-lookup"><span data-stu-id="81494-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="81494-132">Se crea un proyecto de exportación de datos con el nombre "Exportación de la integración de nóminas".</span><span class="sxs-lookup"><span data-stu-id="81494-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="81494-133">Este proyecto contiene las entidades y los campos necesarios para la integración de nóminas.</span><span class="sxs-lookup"><span data-stu-id="81494-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="81494-134">Para examinar el proyecto, vaya **Administración del sistema**, seleccione el icono **Administración de datos** y abra el proyecto de datos de la lista de proyectos.</span><span class="sxs-lookup"><span data-stu-id="81494-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="81494-135">Este trabajo por lotes ejecuta el proyecto de exportación de datos, cifra el paquete de datos resultante y transfiere el archivo del paquete de datos al extremo de SFTP configurado en la pantalla **Configuración de la integración**.</span><span class="sxs-lookup"><span data-stu-id="81494-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="81494-136">El paquete de datos transferido al extremo de SFTP se cifra mediante una clave que es única para el paquete.</span><span class="sxs-lookup"><span data-stu-id="81494-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="81494-137">La clave está en Azure Key Vault, a la que solo puede acceder Ceridian.</span><span class="sxs-lookup"><span data-stu-id="81494-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="81494-138">No es posible descifrar y examinar el contenido del paquete de datos.</span><span class="sxs-lookup"><span data-stu-id="81494-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="81494-139">Si tiene que examinar el contenido del paquete de datos, debe exportar manualmente el proyecto de datos "Exportación de la integración de nóminas", descargarlo y abrirlo.</span><span class="sxs-lookup"><span data-stu-id="81494-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="81494-140">La exportación manual aplicará cifrado o transferirá el paquete.</span><span class="sxs-lookup"><span data-stu-id="81494-140">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="81494-141">Configurar los datos</span><span class="sxs-lookup"><span data-stu-id="81494-141">Configure your data</span></span> 

<span data-ttu-id="81494-142">Para procesar las nóminas, debe configurar los datos de recursos humanos en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="81494-142">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="81494-143">Debe configurar datos de organización, como los trabajos y los puestos, así como las prestaciones y la información de compensación.</span><span class="sxs-lookup"><span data-stu-id="81494-143">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="81494-144">Esta información proporciona la información de empleo, pago y deducciones que se necesita para producir el sueldo del empleado.</span><span class="sxs-lookup"><span data-stu-id="81494-144">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="81494-145">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-145">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="81494-146">Beneficios</span><span class="sxs-lookup"><span data-stu-id="81494-146">Benefits</span></span> 

<span data-ttu-id="81494-147">Recursos humanos ofrece herramientas para la configuración y el mantenimiento de prestaciones, deducciones y los planes de compensación de los trabajadores que una organización ofrece o procesa para sus trabajadores.</span><span class="sxs-lookup"><span data-stu-id="81494-147">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="81494-148">Al crear las prestaciones, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-148">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="81494-149">Planes de prestaciones</span><span class="sxs-lookup"><span data-stu-id="81494-149">Benefit plans</span></span>

- <span data-ttu-id="81494-150">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-150">Plan (required)</span></span>
- <span data-ttu-id="81494-151">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-151">Type (required)</span></span>
- <span data-ttu-id="81494-152">Impacto de nómina (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-152">Payroll impact (required)</span></span>
- <span data-ttu-id="81494-153">Recuperar atrasos</span><span class="sxs-lookup"><span data-stu-id="81494-153">Recover arrears</span></span>
- <span data-ttu-id="81494-154">Método de deducción</span><span class="sxs-lookup"><span data-stu-id="81494-154">Deduction method</span></span>
- <span data-ttu-id="81494-155">Prioridad de deducción</span><span class="sxs-lookup"><span data-stu-id="81494-155">Deduction priority</span></span>
- <span data-ttu-id="81494-156">Período de límite</span><span class="sxs-lookup"><span data-stu-id="81494-156">Limit period</span></span>
- <span data-ttu-id="81494-157">Importe límite</span><span class="sxs-lookup"><span data-stu-id="81494-157">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="81494-158">Beneficios</span><span class="sxs-lookup"><span data-stu-id="81494-158">Benefits</span></span>

- <span data-ttu-id="81494-159">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-159">Plan (required)</span></span>
- <span data-ttu-id="81494-160">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-160">Type (required)</span></span>
- <span data-ttu-id="81494-161">Opción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-161">Option (required)</span></span>
- <span data-ttu-id="81494-162">Identificador de prestación (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-162">Benefit ID (required)</span></span>
- <span data-ttu-id="81494-163">Frecuencia</span><span class="sxs-lookup"><span data-stu-id="81494-163">Frequency</span></span>
- <span data-ttu-id="81494-164">Base</span><span class="sxs-lookup"><span data-stu-id="81494-164">Basis</span></span>
- <span data-ttu-id="81494-165">Importe o índice</span><span class="sxs-lookup"><span data-stu-id="81494-165">Amount or rate</span></span>
- <span data-ttu-id="81494-166">Código de ganancias</span><span class="sxs-lookup"><span data-stu-id="81494-166">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="81494-167">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="81494-167">Supported frequencies</span></span> 

- <span data-ttu-id="81494-168">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="81494-168">Weekly</span></span>
- <span data-ttu-id="81494-169">Quincenal</span><span class="sxs-lookup"><span data-stu-id="81494-169">Bi-weekly</span></span>
- <span data-ttu-id="81494-170">Bimensual</span><span class="sxs-lookup"><span data-stu-id="81494-170">Semi-monthly</span></span>
- <span data-ttu-id="81494-171">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="81494-171">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="81494-172">Bases admitidas</span><span class="sxs-lookup"><span data-stu-id="81494-172">Supported bases</span></span> 

- <span data-ttu-id="81494-173">Importe fijo</span><span class="sxs-lookup"><span data-stu-id="81494-173">Fixed amount</span></span>
- <span data-ttu-id="81494-174">Porcentaje de ganancias</span><span class="sxs-lookup"><span data-stu-id="81494-174">Percent of earnings</span></span>
- <span data-ttu-id="81494-175">Horas productivas</span><span class="sxs-lookup"><span data-stu-id="81494-175">Productive hours</span></span>

<span data-ttu-id="81494-176">Dayforce crea las deducciones siguientes, según el impacto de nómina que hay definido en el plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="81494-176">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="81494-177">Selección en Human Resources</span><span class="sxs-lookup"><span data-stu-id="81494-177">Selection in Human Resources</span></span>        | <span data-ttu-id="81494-178">Resultado en Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-178">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="81494-179">Ninguno</span><span class="sxs-lookup"><span data-stu-id="81494-179">None</span></span>                       | <span data-ttu-id="81494-180">No se crea ninguna deducción.</span><span class="sxs-lookup"><span data-stu-id="81494-180">No deduction is created.</span></span>                      |
| <span data-ttu-id="81494-181">Solo deducción</span><span class="sxs-lookup"><span data-stu-id="81494-181">Deduction only</span></span>             | <span data-ttu-id="81494-182">Se crea una deducción del empleado.</span><span class="sxs-lookup"><span data-stu-id="81494-182">An employee deduction is created.</span></span>             |
| <span data-ttu-id="81494-183">Solo contribución</span><span class="sxs-lookup"><span data-stu-id="81494-183">Contribution only</span></span>          | <span data-ttu-id="81494-184">Se crea una deducción del empresario.</span><span class="sxs-lookup"><span data-stu-id="81494-184">An employer deduction is created.</span></span>             |
| <span data-ttu-id="81494-185">Deducción y contribución</span><span class="sxs-lookup"><span data-stu-id="81494-185">Deduction and contribution</span></span> | <span data-ttu-id="81494-186">Se crean las deducciones del empleado y del empresario.</span><span class="sxs-lookup"><span data-stu-id="81494-186">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="81494-187">Para obtener más información sobre cómo definir y administrar un programa de prestaciones, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="81494-187">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="81494-188">Proporcionar un programa de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="81494-188">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="81494-189">Crear un nuevo beneficio</span><span class="sxs-lookup"><span data-stu-id="81494-189">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="81494-190">Definir reglas y directivas de idoneidad para prestaciones</span><span class="sxs-lookup"><span data-stu-id="81494-190">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="81494-191">Inscribir y quitar prestaciones para trabajadores</span><span class="sxs-lookup"><span data-stu-id="81494-191">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="81494-192">Compensación</span><span class="sxs-lookup"><span data-stu-id="81494-192">Compensation</span></span> 

<span data-ttu-id="81494-193">La gestión de compensaciones se usa para controlar la entrega de salarios base y primas.</span><span class="sxs-lookup"><span data-stu-id="81494-193">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="81494-194">El sueldo base fijo de un empleado y los aumentos por méritos se controlan mediante planes de compensación fijos.</span><span class="sxs-lookup"><span data-stu-id="81494-194">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="81494-195">El pago de incentivos, como los pagos de bonificación, las primas por rendimiento, las acciones y las concesiones, así como también las primas ocasionales, se controlan a través de planes de compensación variable.</span><span class="sxs-lookup"><span data-stu-id="81494-195">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="81494-196">Dayforce utiliza la información de compensación para calcular la tarifa por hora o anual de un empleado.</span><span class="sxs-lookup"><span data-stu-id="81494-196">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="81494-197">Se requieren planes de compensación fija y conversiones de índice salarial.</span><span class="sxs-lookup"><span data-stu-id="81494-197">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="81494-198">Los empleados deben estar asociados a un plan de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="81494-198">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="81494-199">Para obtener más información acerca de los panes de compensación, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="81494-199">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="81494-200">Crear planes de compensación fija</span><span class="sxs-lookup"><span data-stu-id="81494-200">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="81494-201">Crear planes de compensación variable</span><span class="sxs-lookup"><span data-stu-id="81494-201">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="81494-202">Desarrollar planes y estructura de salarios o compensaciones</span><span class="sxs-lookup"><span data-stu-id="81494-202">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="81494-203">Procesar compensaciones</span><span class="sxs-lookup"><span data-stu-id="81494-203">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="81494-204">Definición del proceso de compensación y el cálculo de resultados</span><span class="sxs-lookup"><span data-stu-id="81494-204">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="81494-205">Inscribir a un empleado en un plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="81494-205">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="81494-206">Inscribir a un empleado en un plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="81494-206">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="81494-207">Trabajos</span><span class="sxs-lookup"><span data-stu-id="81494-207">Jobs</span></span> 

<span data-ttu-id="81494-208">Un trabajo es un conjunto de las tareas y responsabilidades que deberá cumplir la persona que realiza un trabajo.</span><span class="sxs-lookup"><span data-stu-id="81494-208">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="81494-209">Para obtener más información, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="81494-209">For more information, see the following articles:</span></span>

- [<span data-ttu-id="81494-210">Configurar los componentes de un trabajo</span><span class="sxs-lookup"><span data-stu-id="81494-210">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="81494-211">Definir nuevos trabajos</span><span class="sxs-lookup"><span data-stu-id="81494-211">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="81494-212">Puestos</span><span class="sxs-lookup"><span data-stu-id="81494-212">Positions</span></span>

<span data-ttu-id="81494-213">Un puesto es un caso individual de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="81494-213">A position is an individual instance of a job.</span></span> <span data-ttu-id="81494-214">Por ejemplo, el puesto "Director de ventas (Este)" es uno de los puestos asociados al trabajo "Director de ventas".</span><span class="sxs-lookup"><span data-stu-id="81494-214">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="81494-215">Un puesto existe en un departamento.</span><span class="sxs-lookup"><span data-stu-id="81494-215">A position exists in a department.</span></span> <span data-ttu-id="81494-216">Solo un trabajador puede asociarse solo a cada puesto.</span><span class="sxs-lookup"><span data-stu-id="81494-216">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="81494-217">Tenga en cuenta los siguientes datos y configuración al configurar los puestos:</span><span class="sxs-lookup"><span data-stu-id="81494-217">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="81494-218">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-218">Position (required)</span></span>
- <span data-ttu-id="81494-219">Descripción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-219">Description (required)</span></span>
- <span data-ttu-id="81494-220">Trabajo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-220">Job (required)</span></span>
- <span data-ttu-id="81494-221">Departamento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-221">Department (required)</span></span>
- <span data-ttu-id="81494-222">Tipo de puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-222">Position type (required)</span></span>
- <span data-ttu-id="81494-223">Equivalente de jornada completa</span><span class="sxs-lookup"><span data-stu-id="81494-223">Full-time equivalent</span></span>
- <span data-ttu-id="81494-224">Horas ordinarias anuales (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-224">Annual regular hours (required)</span></span>
- <span data-ttu-id="81494-225">Pagado por la entidad jurídica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-225">Paid by legal entity (required)</span></span>
- <span data-ttu-id="81494-226">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-226">Pay cycle (required)</span></span>
- <span data-ttu-id="81494-227">Dimensión financiera predeterminada – Centro de coste (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-227">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="81494-228">Asignación de trabajador – Trabajador, inicio de la asignación, final de la asignación, código de motivo</span><span class="sxs-lookup"><span data-stu-id="81494-228">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="81494-229">Si varios puestos en el mismo departamento están asociados al mismo trabajo, se consolidan en un solo puesto en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-229">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="81494-230">Para obtener más información, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="81494-230">For more information, see the following articles:</span></span>

- [<span data-ttu-id="81494-231">Organizar los recursos mediante departamentos, trabajos y puestos</span><span class="sxs-lookup"><span data-stu-id="81494-231">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="81494-232">Configurar puestos</span><span class="sxs-lookup"><span data-stu-id="81494-232">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="81494-233">Departamentos</span><span class="sxs-lookup"><span data-stu-id="81494-233">Departments</span></span>

<span data-ttu-id="81494-234">Un departamneto es una unidad operativa que representa una categoría o un área funcional de la organización.</span><span class="sxs-lookup"><span data-stu-id="81494-234">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="81494-235">Un departamento es responsable de un área específica de la organización, como ventas, contabilidad o recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="81494-235">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="81494-236">Puede usar departamentos para informar sobre las áreas funcionales.</span><span class="sxs-lookup"><span data-stu-id="81494-236">You can use departments to report on functional areas.</span></span> <span data-ttu-id="81494-237">Los departamentos pueden tener responsabilidad de pérdidas y ganancias.</span><span class="sxs-lookup"><span data-stu-id="81494-237">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="81494-238">Para obtener más información, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="81494-238">For more information, see the following articles:</span></span>

- [<span data-ttu-id="81494-239">Crear un departamento y asociarlo a la jerarquía del departamento</span><span class="sxs-lookup"><span data-stu-id="81494-239">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="81494-240">Definir nuevos departamentos</span><span class="sxs-lookup"><span data-stu-id="81494-240">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="81494-241">Ciclos y períodos de pago</span><span class="sxs-lookup"><span data-stu-id="81494-241">Pay cycles and pay periods</span></span>

<span data-ttu-id="81494-242">Un ciclo de pago determina la frecuencia con la que se ejecuta el cálculo de nómina y los días específicos en los que se paga a los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="81494-242">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="81494-243">Por ejemplo, un ciclo de pago puede ser mensual y a los empleados se les podría pagar el último día del mes.</span><span class="sxs-lookup"><span data-stu-id="81494-243">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="81494-244">De forma alternativa, un ciclo de pago puede ser semanal y a los empleados se les podría pagar el martes después del final del período de pago.</span><span class="sxs-lookup"><span data-stu-id="81494-244">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="81494-245">Los ciclos de pago se asignan a los puestos para controlar cuándo se paga a los trabajadores en esos puestos.</span><span class="sxs-lookup"><span data-stu-id="81494-245">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="81494-246">Después de crear ciclos de pago, puede generar los períodos de pago para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="81494-246">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="81494-247">Cada período de pago incluye una fecha de pago predeterminada basada en la información que proporcione.</span><span class="sxs-lookup"><span data-stu-id="81494-247">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="81494-248">Sin embargo, puede modificar la fecha de pago predeterminada en un período de pago para permitir excepciones, por ejemplo, cuando la fecha de pago se encuentra en un día festivo.</span><span class="sxs-lookup"><span data-stu-id="81494-248">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="81494-249">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="81494-249">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="81494-250">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-250">Pay cycle (required)</span></span>
- <span data-ttu-id="81494-251">Frecuencia del ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-251">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="81494-252">Fecha de inicio del período (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-252">Period start date (first pay period required)</span></span>
- <span data-ttu-id="81494-253">Fecha de pago predeterminado (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-253">Default payment date (first pay period required)</span></span>

<span data-ttu-id="81494-254">Esta información se integra con Dayforce como grupos salariales y se separa por país o región para cada ciclo de pago.</span><span class="sxs-lookup"><span data-stu-id="81494-254">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="81494-255">Al menos se debe generar un período de sueldo antes de la integración.</span><span class="sxs-lookup"><span data-stu-id="81494-255">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="81494-256">Dayforce genera los calendarios de grupo salarial y las fechas de pago, en función de la fecha inicial del primer período de pago y la fecha de pago predeterminada que se configuran en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="81494-256">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="81494-257">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="81494-257">Earning codes</span></span>

<span data-ttu-id="81494-258">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="81494-258">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="81494-259">Los códigos tienen distintos parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="81494-259">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="81494-260">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="81494-260">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="81494-261">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-261">Earning Code (required)</span></span>
- <span data-ttu-id="81494-262">Descripción</span><span class="sxs-lookup"><span data-stu-id="81494-262">Description</span></span>
- <span data-ttu-id="81494-263">Unidad de medida</span><span class="sxs-lookup"><span data-stu-id="81494-263">Unit of measure</span></span>
- <span data-ttu-id="81494-264">Productivo</span><span class="sxs-lookup"><span data-stu-id="81494-264">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="81494-265">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="81494-265">Worker data</span></span>

<span data-ttu-id="81494-266">Los registros para los diferentes tipos de trabajadores que tiene son importantes para los sistemas de recursos humanos y nómina.</span><span class="sxs-lookup"><span data-stu-id="81494-266">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="81494-267">La información que se indique se puede utilizar para efectuar un seguimiento de los trabajadores y su información personal.</span><span class="sxs-lookup"><span data-stu-id="81494-267">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="81494-268">Puede mantener la información siguiente para los trabajadores:</span><span class="sxs-lookup"><span data-stu-id="81494-268">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="81494-269">**Básica**: permite mantener la información básica de un trabajador, como la información de contacto, información demográfica, información de identificación, información de familia, estado del servicio militar, información de expatriado y contactos personales y de emergencia.</span><span class="sxs-lookup"><span data-stu-id="81494-269">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="81494-270">**Empleo**: permite mantener la información sobre el empleo de un trabajador, como afiliación de la empresa u organización, asignación de puesto, fecha de inicio y finalización, idoneidad para el trabajo, condiciones de empleo, pensión, vacaciones y la información de reubicación.</span><span class="sxs-lookup"><span data-stu-id="81494-270">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="81494-271">**Bajas y ausencias**: permite mantener información sobre las ausencias de un trabajador, como calendarios de trabajo, transacciones de ausencia y configuración de ausencias.</span><span class="sxs-lookup"><span data-stu-id="81494-271">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="81494-272">**Compensación y nómina**: permite mantener la información sobre los planes de compensación y la información de nómina de un trabajador, como inscripción del plan, concesiones, desempeño, comisión, información fiscal, retiro y deducciones de sueldo.</span><span class="sxs-lookup"><span data-stu-id="81494-272">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="81494-273">Al introducir la información del trabajador, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-273">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="81494-274">Información general</span><span class="sxs-lookup"><span data-stu-id="81494-274">General information</span></span>

- <span data-ttu-id="81494-275">Número de personal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-275">Personnel number (required)</span></span>
- <span data-ttu-id="81494-276">Nombre (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-276">First name (required)</span></span>
- <span data-ttu-id="81494-277">Apellido (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-277">Last name (required)</span></span>
- <span data-ttu-id="81494-278">Segundo nombre</span><span class="sxs-lookup"><span data-stu-id="81494-278">Middle name</span></span>
- <span data-ttu-id="81494-279">Antigüedad</span><span class="sxs-lookup"><span data-stu-id="81494-279">Seniority date</span></span>
- <span data-ttu-id="81494-280">Conocido como</span><span class="sxs-lookup"><span data-stu-id="81494-280">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="81494-281">Información personal</span><span class="sxs-lookup"><span data-stu-id="81494-281">Personal information</span></span>

- <span data-ttu-id="81494-282">Estado civil (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-282">Marital status (required)</span></span>
- <span data-ttu-id="81494-283">Fecha de nacimiento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-283">Birth date (required)</span></span>
- <span data-ttu-id="81494-284">Sexo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-284">Gender (required)</span></span>
- <span data-ttu-id="81494-285">Persona con discapacidades</span><span class="sxs-lookup"><span data-stu-id="81494-285">Person with disabilities</span></span>
- <span data-ttu-id="81494-286">País o región, nacionalidad (solo para México)</span><span class="sxs-lookup"><span data-stu-id="81494-286">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="81494-287">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="81494-287">Address information</span></span>

- <span data-ttu-id="81494-288">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-288">Primary (required)</span></span>
- <span data-ttu-id="81494-289">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-289">Country/region (required)</span></span>
- <span data-ttu-id="81494-290">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-290">Postal code (required)</span></span>
- <span data-ttu-id="81494-291">Número de calle (obligatorio) (solo para México)</span><span class="sxs-lookup"><span data-stu-id="81494-291">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="81494-292">Complemento de edificio (solo para México)</span><span class="sxs-lookup"><span data-stu-id="81494-292">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="81494-293">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-293">City (required)</span></span>
- <span data-ttu-id="81494-294">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-294">State (required)</span></span>
- <span data-ttu-id="81494-295">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-295">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="81494-296">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="81494-296">Contact information</span></span> 

- <span data-ttu-id="81494-297">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-297">Primary (required)</span></span>
- <span data-ttu-id="81494-298">Número de contacto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-298">Contact number (required)</span></span>
- <span data-ttu-id="81494-299">Extensión</span><span class="sxs-lookup"><span data-stu-id="81494-299">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="81494-300">Información de nómina y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="81494-300">Payroll information and earning codes</span></span>

<span data-ttu-id="81494-301">A los empleados se les pueden asignar ganancias específicas de una frecuencia determinada de pago y tener un método de pago preferido.</span><span class="sxs-lookup"><span data-stu-id="81494-301">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="81494-302">Los siguientes campos se utilizan en Dayforce para ayudar a garantizar que se usen las preferencias y valores.</span><span class="sxs-lookup"><span data-stu-id="81494-302">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="81494-303">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="81494-303">Earning codes</span></span>

- <span data-ttu-id="81494-304">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-304">Position (required)</span></span>
- <span data-ttu-id="81494-305">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-305">Earning Code (required)</span></span>
- <span data-ttu-id="81494-306">Frecuencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-306">Frequency (required)</span></span>
- <span data-ttu-id="81494-307">Importe (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-307">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="81494-308">Información de nómina</span><span class="sxs-lookup"><span data-stu-id="81494-308">Payroll information</span></span>

- <span data-ttu-id="81494-309">Método de pago</span><span class="sxs-lookup"><span data-stu-id="81494-309">Payment Method</span></span>
- <span data-ttu-id="81494-310">Región económica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-310">Economic Region (required)</span></span>
- <span data-ttu-id="81494-311">Id. de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="81494-311">Employee Benefits ID</span></span>
- <span data-ttu-id="81494-312">Número de id. nacional (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-312">National ID Number (required)</span></span>
- <span data-ttu-id="81494-313">Número de servicio militar</span><span class="sxs-lookup"><span data-stu-id="81494-313">Military Service Number</span></span>
- <span data-ttu-id="81494-314">Id. de turno (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-314">Shift ID (required)</span></span>
- <span data-ttu-id="81494-315">Número de identificación fiscal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-315">Tax Number (required)</span></span>
- <span data-ttu-id="81494-316">Id. de sindicato (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-316">Union ID (required)</span></span>
- <span data-ttu-id="81494-317">Id. de día laborable (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-317">Work Day ID (required)</span></span>
- <span data-ttu-id="81494-318">Número de permiso de trabajo</span><span class="sxs-lookup"><span data-stu-id="81494-318">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="81494-319">Para el método de pago, México admite **Efectivo**, **Cheque** (cheque físico de la empresa) y **Pago electrónico**.</span><span class="sxs-lookup"><span data-stu-id="81494-319">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="81494-320">Si no se especifica ningún método de pago, **Cheque** se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="81494-320">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="81494-321">Detalles del empleo</span><span class="sxs-lookup"><span data-stu-id="81494-321">Employment details</span></span>

<span data-ttu-id="81494-322">El historial de detalles de empleo se utiliza como información clave para derivar los estados de contratación, despido y recontratación de un empleado en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-322">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="81494-323">Dayforce solo admite un registro de empleo activo a la vez.</span><span class="sxs-lookup"><span data-stu-id="81494-323">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="81494-324">Fecha de inicio de empleo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-324">Employment start date (required)</span></span>
- <span data-ttu-id="81494-325">Fecha final del empleo</span><span class="sxs-lookup"><span data-stu-id="81494-325">Employment end date</span></span>
- <span data-ttu-id="81494-326">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="81494-326">Start date</span></span>
- <span data-ttu-id="81494-327">Fecha inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="81494-327">Adjusted start date</span></span>
- <span data-ttu-id="81494-328">Fecha de finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="81494-328">Termination date (required upon termination)</span></span>
- <span data-ttu-id="81494-329">Razón de la finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="81494-329">Termination reason (required upon termination)</span></span>

<span data-ttu-id="81494-330">Las fechas clave de un empleado se obtienen utilizando la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="81494-330">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="81494-331">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-331">Human Resources</span></span>                | <span data-ttu-id="81494-332">Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-332">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="81494-333">Fecha de contratación más reciente</span><span class="sxs-lookup"><span data-stu-id="81494-333">Most recent hire date</span></span> | <span data-ttu-id="81494-334">Inicio de empleo del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="81494-334">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="81494-335">Fecha de finalización</span><span class="sxs-lookup"><span data-stu-id="81494-335">Termination date</span></span>      | <span data-ttu-id="81494-336">Fecha de finalización del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="81494-336">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="81494-337">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="81494-337">Start date</span></span>            | <span data-ttu-id="81494-338">Fecha de inicio ajustada, fecha de inicio o inicio de empleo del registro de historial de empleo inactivo actual</span><span class="sxs-lookup"><span data-stu-id="81494-338">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="81494-339">Fecha de contratación original</span><span class="sxs-lookup"><span data-stu-id="81494-339">Original hire date</span></span>    | <span data-ttu-id="81494-340">Inicio del empleo del registro del historial de empleo más temprano</span><span class="sxs-lookup"><span data-stu-id="81494-340">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="81494-341">Compensación</span><span class="sxs-lookup"><span data-stu-id="81494-341">Compensation</span></span>

<span data-ttu-id="81494-342">Un plan de compensación fija se debe asociar al puesto principal de cada empleado durante un período de empleo.</span><span class="sxs-lookup"><span data-stu-id="81494-342">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="81494-343">Este período comienza en la fecha de contratación del empleado (o la fecha de inicio del empleo) y continúa hasta la finalización.</span><span class="sxs-lookup"><span data-stu-id="81494-343">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="81494-344">Fecha de vigencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-344">Effective Date (required)</span></span>
- <span data-ttu-id="81494-345">Fecha de expiración</span><span class="sxs-lookup"><span data-stu-id="81494-345">Expiration date</span></span>
- <span data-ttu-id="81494-346">Índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-346">Pay Rate (required)</span></span>
- <span data-ttu-id="81494-347">Conversiones de índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-347">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="81494-348">Equivalente anual (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-348">Annual equivalent (required)</span></span>
- <span data-ttu-id="81494-349">Equivalente por hora (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-349">Hourly equivalent (required)</span></span>

<span data-ttu-id="81494-350">Si un empleado por hora tiene varios puestos, se importa la compensación fija del puesto principal en Dayforce como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="81494-350">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="81494-351">En el caso de los puestos no principales, el índice por hora se guarda en el puesto correspondiente en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-351">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="81494-352">Si un empleado a sueldo tiene varios puestos, se derivan el índice por hora acumulativa y el sueldo anual en todos los puestos activos y se utilizan como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="81494-352">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="81494-353">Números de identificación</span><span class="sxs-lookup"><span data-stu-id="81494-353">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="81494-354">Identificador de seguridad social</span><span class="sxs-lookup"><span data-stu-id="81494-354">Social Security identifier</span></span> 

<span data-ttu-id="81494-355">Cada empleado debe tener un identificador principal.</span><span class="sxs-lookup"><span data-stu-id="81494-355">Every employee must have one primary identifier.</span></span> <span data-ttu-id="81494-356">Este identificador debe ser de tipo de identificación **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="81494-356">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="81494-357">En Dayforce, se deriva automáticamente como el identificador de seguridad social del empleado que se requiere para ser contratado.</span><span class="sxs-lookup"><span data-stu-id="81494-357">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="81494-358">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-358">Primary (required)</span></span>
- <span data-ttu-id="81494-359">Tipo de identificación = "Nº de SS"</span><span class="sxs-lookup"><span data-stu-id="81494-359">Identification Type = "SSN"</span></span>
- <span data-ttu-id="81494-360">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="81494-360">Issued Date</span></span>
- <span data-ttu-id="81494-361">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="81494-361">Expiration Date</span></span>

<span data-ttu-id="81494-362">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="81494-362">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="81494-363">Sin embargo, solo el registro que está marcado como **Principal** está integrado en Dayforce, independientemente de si el número está activo o caducado.</span><span class="sxs-lookup"><span data-stu-id="81494-363">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="81494-364">Cuentas bancarias y desembolsos</span><span class="sxs-lookup"><span data-stu-id="81494-364">Bank accounts and disbursements</span></span>

<span data-ttu-id="81494-365">La información de cuenta bancaria válida se debe especificar para cualquier empleado que elija recibir el pago por transferencias de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="81494-365">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="81494-366">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-366">Human Resources</span></span>                         | <span data-ttu-id="81494-367">Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-367">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="81494-368">Número de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-368">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="81494-369">Código SWIFT (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-369">SWIFT code (required)</span></span>          | <span data-ttu-id="81494-370">Campo **Identificador del banco** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="81494-370">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="81494-371">Número de sucursal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-371">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="81494-372">Tipo de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-372">Bank account type (required)</span></span>   | <span data-ttu-id="81494-373">Campo **Tipo de cuenta** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="81494-373">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="81494-374">Los valores admitidos incluyen **Comprobación** y **Nómina**.</span><span class="sxs-lookup"><span data-stu-id="81494-374">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="81494-375">Los empleados que elijan que se les pague a través de transferencia bancaria deben proporcionar un vínculo a una cuenta de remanente que esté en una entidad legal que tenga su dirección principal en México y esté asociada con una cuenta bancaria válida de un banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="81494-375">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="81494-376">Todas las demás cuentas no remanentes se ignoran.</span><span class="sxs-lookup"><span data-stu-id="81494-376">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="81494-377">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="81494-377">Address information</span></span>

<span data-ttu-id="81494-378">Cada empleado debe tener una ubicación principal.</span><span class="sxs-lookup"><span data-stu-id="81494-378">Every employee must have one primary location.</span></span> <span data-ttu-id="81494-379">En Dayforce, esta ubicación se usa para determinar la residencia principal del empleado para impuestos.</span><span class="sxs-lookup"><span data-stu-id="81494-379">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="81494-380">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-380">Primary (required)</span></span>
- <span data-ttu-id="81494-381">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-381">Country/region (required)</span></span>
- <span data-ttu-id="81494-382">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-382">Zip/postal code (required)</span></span>
- <span data-ttu-id="81494-383">Calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-383">Street (required)</span></span>
- <span data-ttu-id="81494-384">Número de calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-384">Street Number (required)</span></span>
- <span data-ttu-id="81494-385">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="81494-385">Building Complement</span></span>
- <span data-ttu-id="81494-386">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-386">City (required)</span></span>
- <span data-ttu-id="81494-387">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-387">State (required)</span></span>
- <span data-ttu-id="81494-388">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-388">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="81494-389">Configure los datos para generar nóminas en Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="81494-389">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="81494-390">Si va a generar el sueldo de los empleados en Estados Unidos y Canadá, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="81494-390">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="81494-391">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="81494-391">Departments are required on positions.</span></span>
- <span data-ttu-id="81494-392">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="81494-392">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="81494-393">Puede configurar Human Resources para requerir que los puestos especifiquen un departamento.</span><span class="sxs-lookup"><span data-stu-id="81494-393">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="81494-394">Para ello, vaya a **Puestos compartidos de recursos humanos > Puestos > Requerir departamentos en puestos**.</span><span class="sxs-lookup"><span data-stu-id="81494-394">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="81494-395">Recomendamos que este valor se aplique para la integración.</span><span class="sxs-lookup"><span data-stu-id="81494-395">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="81494-396">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="81494-396">Job types</span></span>

<span data-ttu-id="81494-397">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="81494-397">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="81494-398">Los tipos de trabajo son obligatorios para procesar la nómina en Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="81494-398">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="81494-399">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="81494-399">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="81494-400">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="81494-400">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="81494-401">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="81494-401">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="81494-402">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="81494-402">Job type</span></span>   | <span data-ttu-id="81494-403">Descripción</span><span class="sxs-lookup"><span data-stu-id="81494-403">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="81494-404">Por hora</span><span class="sxs-lookup"><span data-stu-id="81494-404">Hourly</span></span>     | <span data-ttu-id="81494-405">Por hora</span><span class="sxs-lookup"><span data-stu-id="81494-405">Hourly</span></span>      |
| <span data-ttu-id="81494-406">Asalariado</span><span class="sxs-lookup"><span data-stu-id="81494-406">Salaried</span></span>   | <span data-ttu-id="81494-407">Asalariado</span><span class="sxs-lookup"><span data-stu-id="81494-407">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="81494-408">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="81494-408">Position types</span></span> 

<span data-ttu-id="81494-409">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="81494-409">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="81494-410">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="81494-410">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="81494-411">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="81494-411">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="81494-412">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="81494-412">Position type</span></span>   | <span data-ttu-id="81494-413">Descripción</span><span class="sxs-lookup"><span data-stu-id="81494-413">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="81494-414">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="81494-414">Full-time</span></span>       | <span data-ttu-id="81494-415">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="81494-415">Full time employee</span></span> |
| <span data-ttu-id="81494-416">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="81494-416">Part-time</span></span>       | <span data-ttu-id="81494-417">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="81494-417">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="81494-418">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="81494-418">Reason codes</span></span>

<span data-ttu-id="81494-419">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="81494-419">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="81494-420">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="81494-420">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="81494-421">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="81494-421">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="81494-422">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="81494-422">Reason code</span></span>    | <span data-ttu-id="81494-423">Descripción</span><span class="sxs-lookup"><span data-stu-id="81494-423">Description</span></span>      | <span data-ttu-id="81494-424">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="81494-424">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="81494-425">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="81494-425">RESIGNATION</span></span>    | <span data-ttu-id="81494-426">Dimisión</span><span class="sxs-lookup"><span data-stu-id="81494-426">Resignation</span></span>      | <span data-ttu-id="81494-427">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-427">Terminate worker</span></span>     |
| <span data-ttu-id="81494-428">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="81494-428">TERMINATION</span></span>    | <span data-ttu-id="81494-429">Finalización</span><span class="sxs-lookup"><span data-stu-id="81494-429">Termination</span></span>      | <span data-ttu-id="81494-430">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-430">Terminate worker</span></span>     |
| <span data-ttu-id="81494-431">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="81494-431">RETIREMENT</span></span>     | <span data-ttu-id="81494-432">Jubilación</span><span class="sxs-lookup"><span data-stu-id="81494-432">Retirement</span></span>       | <span data-ttu-id="81494-433">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-433">Terminate worker</span></span>     |
| <span data-ttu-id="81494-434">OTHER</span><span class="sxs-lookup"><span data-stu-id="81494-434">OTHER</span></span>          | <span data-ttu-id="81494-435">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="81494-435">Other Reasons</span></span>    | <span data-ttu-id="81494-436">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-436">Terminate worker</span></span>     |
| <span data-ttu-id="81494-437">MUERTE</span><span class="sxs-lookup"><span data-stu-id="81494-437">DEATH</span></span>          | <span data-ttu-id="81494-438">Muerte</span><span class="sxs-lookup"><span data-stu-id="81494-438">Death</span></span>            | <span data-ttu-id="81494-439">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-439">Terminate worker</span></span>     |
| <span data-ttu-id="81494-440">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="81494-440">LEAVEOFABSENCE</span></span> | <span data-ttu-id="81494-441">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="81494-441">Leave of Absence</span></span> | <span data-ttu-id="81494-442">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-442">Terminate worker</span></span>     |
| <span data-ttu-id="81494-443">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="81494-443">CONTRACTEND</span></span>    | <span data-ttu-id="81494-444">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="81494-444">End of Contract</span></span>  | <span data-ttu-id="81494-445">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-445">Terminate worker</span></span>     |
| <span data-ttu-id="81494-446">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="81494-446">SALARYCHANGE</span></span>   | <span data-ttu-id="81494-447">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="81494-447">Change of Salary</span></span> | <span data-ttu-id="81494-448">Compensación</span><span class="sxs-lookup"><span data-stu-id="81494-448">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="81494-449">Estado civil</span><span class="sxs-lookup"><span data-stu-id="81494-449">Marital status</span></span>

<span data-ttu-id="81494-450">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="81494-450">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="81494-451">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-451">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="81494-452">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-452">Human Resources</span></span>                 | <span data-ttu-id="81494-453">Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-453">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="81494-454">Casado/a</span><span class="sxs-lookup"><span data-stu-id="81494-454">Married</span></span>                | <span data-ttu-id="81494-455">Casado/a</span><span class="sxs-lookup"><span data-stu-id="81494-455">Married</span></span>              |
| <span data-ttu-id="81494-456">Único</span><span class="sxs-lookup"><span data-stu-id="81494-456">Single</span></span>                 | <span data-ttu-id="81494-457">Único</span><span class="sxs-lookup"><span data-stu-id="81494-457">Single</span></span>               |
| <span data-ttu-id="81494-458">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="81494-458">Widowed</span></span>                | <span data-ttu-id="81494-459">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="81494-459">Widowed</span></span>              |
| <span data-ttu-id="81494-460">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="81494-460">Divorced</span></span>               | <span data-ttu-id="81494-461">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="81494-461">Divorced</span></span>             |
| <span data-ttu-id="81494-462">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="81494-462">Registered Partnership</span></span> | <span data-ttu-id="81494-463">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="81494-463">Domestic Partnership</span></span> |
| <span data-ttu-id="81494-464">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="81494-464">None</span></span>                   | <span data-ttu-id="81494-465">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="81494-465">None</span></span>                 |
| <span data-ttu-id="81494-466">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="81494-466">Cohabiting</span></span>             | <span data-ttu-id="81494-467">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="81494-467">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="81494-468">Género</span><span class="sxs-lookup"><span data-stu-id="81494-468">Gender</span></span>

<span data-ttu-id="81494-469">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="81494-469">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="81494-470">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-470">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="81494-471">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-471">Human Resources</span></span>       | <span data-ttu-id="81494-472">Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-472">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="81494-473">Masculino</span><span class="sxs-lookup"><span data-stu-id="81494-473">Male</span></span>         | <span data-ttu-id="81494-474">Masculino</span><span class="sxs-lookup"><span data-stu-id="81494-474">Male</span></span>            |
| <span data-ttu-id="81494-475">Femenino</span><span class="sxs-lookup"><span data-stu-id="81494-475">Female</span></span>       | <span data-ttu-id="81494-476">Femenino</span><span class="sxs-lookup"><span data-stu-id="81494-476">Female</span></span>          |
| <span data-ttu-id="81494-477">No específico</span><span class="sxs-lookup"><span data-stu-id="81494-477">Non-specific</span></span> | <span data-ttu-id="81494-478">*No admitido*</span><span class="sxs-lookup"><span data-stu-id="81494-478">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="81494-479">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="81494-479">Earning codes</span></span>

<span data-ttu-id="81494-480">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="81494-480">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="81494-481">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="81494-481">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="81494-482">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="81494-482">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="81494-483">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="81494-483">Supported frequencies</span></span>

- <span data-ttu-id="81494-484">Todas</span><span class="sxs-lookup"><span data-stu-id="81494-484">All</span></span>
- <span data-ttu-id="81494-485">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="81494-485">EVERYPAY</span></span>
- <span data-ttu-id="81494-486">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="81494-486">EACHPAYPERIOD</span></span>
- <span data-ttu-id="81494-487">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="81494-487">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="81494-488">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="81494-488">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="81494-489">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-489">1OFMTH</span></span>
- <span data-ttu-id="81494-490">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-490">LASTOFMTH</span></span>
- <span data-ttu-id="81494-491">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-491">2OFMTH</span></span>
- <span data-ttu-id="81494-492">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-492">3OFMTH</span></span>
- <span data-ttu-id="81494-493">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-493">4OFMTH</span></span>
- <span data-ttu-id="81494-494">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-494">5OFMTH</span></span>
- <span data-ttu-id="81494-495">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-495">1N2OFMTH</span></span>
- <span data-ttu-id="81494-496">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-496">3N4OFMTH</span></span>
- <span data-ttu-id="81494-497">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-497">1N3OFMTH</span></span>
- <span data-ttu-id="81494-498">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-498">1N4OFMTH</span></span>
- <span data-ttu-id="81494-499">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-499">2N3OFMTH</span></span>
- <span data-ttu-id="81494-500">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-500">2N4OFMTH</span></span>
- <span data-ttu-id="81494-501">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-501">1N2N3OFMTH</span></span>
- <span data-ttu-id="81494-502">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-502">1N2N4OFMTH</span></span>
- <span data-ttu-id="81494-503">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-503">1N3N4OFMTH</span></span>
- <span data-ttu-id="81494-504">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-504">2N3N4OFMTH</span></span>
- <span data-ttu-id="81494-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="81494-506">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="81494-506">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="81494-507">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="81494-507">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="81494-508">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="81494-508">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="81494-509">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="81494-509">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="81494-510">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="81494-510">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="81494-511">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="81494-511">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="81494-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="81494-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="81494-513">Direcciones</span><span class="sxs-lookup"><span data-stu-id="81494-513">Addresses</span></span>

<span data-ttu-id="81494-514">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="81494-514">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="81494-515">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="81494-515">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="81494-516">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-516">Human Resources</span></span>          | <span data-ttu-id="81494-517">Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-517">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="81494-518">País/región</span><span class="sxs-lookup"><span data-stu-id="81494-518">Country/Region</span></span>  | <span data-ttu-id="81494-519">Código de país</span><span class="sxs-lookup"><span data-stu-id="81494-519">Country Code</span></span>          |
| <span data-ttu-id="81494-520">Código postal</span><span class="sxs-lookup"><span data-stu-id="81494-520">Zip/Postal Code</span></span> | <span data-ttu-id="81494-521">Código postal</span><span class="sxs-lookup"><span data-stu-id="81494-521">Postal Code</span></span>           |
| <span data-ttu-id="81494-522">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="81494-522">State</span></span>           | <span data-ttu-id="81494-523">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="81494-523">State Code</span></span>            |
| <span data-ttu-id="81494-524">Población</span><span class="sxs-lookup"><span data-stu-id="81494-524">City</span></span>            | <span data-ttu-id="81494-525">Población</span><span class="sxs-lookup"><span data-stu-id="81494-525">City</span></span>                  |
| <span data-ttu-id="81494-526">Comarca</span><span class="sxs-lookup"><span data-stu-id="81494-526">County</span></span>          | <span data-ttu-id="81494-527">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="81494-527">County (Municipality)</span></span> |
| <span data-ttu-id="81494-528">Calle</span><span class="sxs-lookup"><span data-stu-id="81494-528">Street</span></span>          | <span data-ttu-id="81494-529">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="81494-529">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="81494-530">Regiones de impuestos</span><span class="sxs-lookup"><span data-stu-id="81494-530">Tax regions</span></span>

<span data-ttu-id="81494-531">Las regiones de impuestos se usan para determinar los impuestos correspondientes que se deben aplicar durante la generación de nómina.</span><span class="sxs-lookup"><span data-stu-id="81494-531">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="81494-532">Las regiones de impuestos se asignan a Dayforce como direcciones de ubicación.</span><span class="sxs-lookup"><span data-stu-id="81494-532">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="81494-533">La región de impuestos predeterminada se debe asociar al puesto activo del trabajador.</span><span class="sxs-lookup"><span data-stu-id="81494-533">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="81494-534">Región de impuestos (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-534">Tax region (required)</span></span>
- <span data-ttu-id="81494-535">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-535">Country/Region (required)</span></span>
- <span data-ttu-id="81494-536">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-536">State (required)</span></span>
- <span data-ttu-id="81494-537">Comarca</span><span class="sxs-lookup"><span data-stu-id="81494-537">County</span></span> 
- <span data-ttu-id="81494-538">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="81494-538">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="81494-539">Configurar los datos para generar nóminas en México</span><span class="sxs-lookup"><span data-stu-id="81494-539">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="81494-540">Si va a generar el sueldo de los empleados en México, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="81494-540">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="81494-541">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="81494-541">Departments are required on positions.</span></span>
- <span data-ttu-id="81494-542">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="81494-542">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="81494-543">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="81494-543">Job types</span></span>

<span data-ttu-id="81494-544">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="81494-544">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="81494-545">Los tipos de trabajo son obligatorios para procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="81494-545">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="81494-546">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="81494-546">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="81494-547">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="81494-547">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="81494-548">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="81494-548">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="81494-549">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="81494-549">Job type</span></span>   | <span data-ttu-id="81494-550">Descripción</span><span class="sxs-lookup"><span data-stu-id="81494-550">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="81494-551">Por hora</span><span class="sxs-lookup"><span data-stu-id="81494-551">Hourly</span></span>     | <span data-ttu-id="81494-552">MX Por hora</span><span class="sxs-lookup"><span data-stu-id="81494-552">MX Hourly</span></span>   |
| <span data-ttu-id="81494-553">Asalariado</span><span class="sxs-lookup"><span data-stu-id="81494-553">Salaried</span></span>   | <span data-ttu-id="81494-554">MX Asalariado</span><span class="sxs-lookup"><span data-stu-id="81494-554">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="81494-555">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="81494-555">Position types</span></span> 

<span data-ttu-id="81494-556">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="81494-556">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="81494-557">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="81494-557">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="81494-558">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="81494-558">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="81494-559">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="81494-559">Position type</span></span>   | <span data-ttu-id="81494-560">Descripción</span><span class="sxs-lookup"><span data-stu-id="81494-560">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="81494-561">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="81494-561">Full-time</span></span>       | <span data-ttu-id="81494-562">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="81494-562">Full time employee</span></span> |
| <span data-ttu-id="81494-563">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="81494-563">Part-time</span></span>       | <span data-ttu-id="81494-564">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="81494-564">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="81494-565">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="81494-565">Reason codes</span></span>

<span data-ttu-id="81494-566">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="81494-566">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="81494-567">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="81494-567">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="81494-568">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="81494-568">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="81494-569">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="81494-569">Reason code</span></span>            | <span data-ttu-id="81494-570">Descripción</span><span class="sxs-lookup"><span data-stu-id="81494-570">Description</span></span>                    | <span data-ttu-id="81494-571">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="81494-571">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="81494-572">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="81494-572">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="81494-573">Salida antes de la primera nómina</span><span class="sxs-lookup"><span data-stu-id="81494-573">Departure before first payroll</span></span> | <span data-ttu-id="81494-574">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-574">Terminate worker</span></span>     |
| <span data-ttu-id="81494-575">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="81494-575">RESIGNATION</span></span>            | <span data-ttu-id="81494-576">Dimisión</span><span class="sxs-lookup"><span data-stu-id="81494-576">Resignation</span></span>                    | <span data-ttu-id="81494-577">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-577">Terminate worker</span></span>     |
| <span data-ttu-id="81494-578">PENSION</span><span class="sxs-lookup"><span data-stu-id="81494-578">PENSION</span></span>                | <span data-ttu-id="81494-579">Pensión</span><span class="sxs-lookup"><span data-stu-id="81494-579">Pension</span></span>                        | <span data-ttu-id="81494-580">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-580">Terminate worker</span></span>     |
| <span data-ttu-id="81494-581">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="81494-581">TERMINATION</span></span>            | <span data-ttu-id="81494-582">Finalización</span><span class="sxs-lookup"><span data-stu-id="81494-582">Termination</span></span>                    | <span data-ttu-id="81494-583">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-583">Terminate worker</span></span>     |
| <span data-ttu-id="81494-584">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="81494-584">RETIREMENT</span></span>             | <span data-ttu-id="81494-585">Jubilación</span><span class="sxs-lookup"><span data-stu-id="81494-585">Retirement</span></span>                     | <span data-ttu-id="81494-586">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-586">Terminate worker</span></span>     |
| <span data-ttu-id="81494-587">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="81494-587">ABSENTEE</span></span>               | <span data-ttu-id="81494-588">Ausente</span><span class="sxs-lookup"><span data-stu-id="81494-588">Absentee</span></span>                       | <span data-ttu-id="81494-589">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-589">Terminate worker</span></span>     |
| <span data-ttu-id="81494-590">OTHER</span><span class="sxs-lookup"><span data-stu-id="81494-590">OTHER</span></span>                  | <span data-ttu-id="81494-591">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="81494-591">Other Reasons</span></span>                  | <span data-ttu-id="81494-592">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-592">Terminate worker</span></span>     |
| <span data-ttu-id="81494-593">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="81494-593">CLOSURE</span></span>                | <span data-ttu-id="81494-594">Cierre de operaciones</span><span class="sxs-lookup"><span data-stu-id="81494-594">Business Closure</span></span>               | <span data-ttu-id="81494-595">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-595">Terminate worker</span></span>     |
| <span data-ttu-id="81494-596">MUERTE</span><span class="sxs-lookup"><span data-stu-id="81494-596">DEATH</span></span>                  | <span data-ttu-id="81494-597">Muerte</span><span class="sxs-lookup"><span data-stu-id="81494-597">Death</span></span>                          | <span data-ttu-id="81494-598">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-598">Terminate worker</span></span>     |
| <span data-ttu-id="81494-599">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="81494-599">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="81494-600">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="81494-600">Leave of Absence</span></span>               | <span data-ttu-id="81494-601">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-601">Terminate worker</span></span>     |
| <span data-ttu-id="81494-602">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="81494-602">CONTRACTEND</span></span>            | <span data-ttu-id="81494-603">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="81494-603">End of Contract</span></span>                | <span data-ttu-id="81494-604">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="81494-604">Terminate worker</span></span>     |
| <span data-ttu-id="81494-605">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="81494-605">SALARYCHANGE</span></span>           | <span data-ttu-id="81494-606">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="81494-606">Change of Salary</span></span>               | <span data-ttu-id="81494-607">Compensación</span><span class="sxs-lookup"><span data-stu-id="81494-607">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="81494-608">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="81494-608">Terms of employment</span></span>

<span data-ttu-id="81494-609">Las condiciones laborales se usan para crear categorías de condiciones laborales.</span><span class="sxs-lookup"><span data-stu-id="81494-609">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="81494-610">Las condiciones se asignan a Dayforce como valores de indicador de empleo.</span><span class="sxs-lookup"><span data-stu-id="81494-610">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="81494-611">Las siguientes condiciones laborales y descripciones son obligatorias.</span><span class="sxs-lookup"><span data-stu-id="81494-611">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="81494-612">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="81494-612">Terms of employment</span></span>   | <span data-ttu-id="81494-613">Descripción</span><span class="sxs-lookup"><span data-stu-id="81494-613">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="81494-614">Normal</span><span class="sxs-lookup"><span data-stu-id="81494-614">Regular</span></span>               | <span data-ttu-id="81494-615">Normal</span><span class="sxs-lookup"><span data-stu-id="81494-615">Regular</span></span>     |
| <span data-ttu-id="81494-616">Directo</span><span class="sxs-lookup"><span data-stu-id="81494-616">Direct</span></span>                | <span data-ttu-id="81494-617">Directo</span><span class="sxs-lookup"><span data-stu-id="81494-617">Direct</span></span>      |
| <span data-ttu-id="81494-618">Prácticas</span><span class="sxs-lookup"><span data-stu-id="81494-618">Internship</span></span>            | <span data-ttu-id="81494-619">Prácticas</span><span class="sxs-lookup"><span data-stu-id="81494-619">Internship</span></span>  |
| <span data-ttu-id="81494-620">Permanente</span><span class="sxs-lookup"><span data-stu-id="81494-620">Permanent</span></span>             | <span data-ttu-id="81494-621">Permanente</span><span class="sxs-lookup"><span data-stu-id="81494-621">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="81494-622">Estado civil</span><span class="sxs-lookup"><span data-stu-id="81494-622">Marital status</span></span>

<span data-ttu-id="81494-623">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="81494-623">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="81494-624">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-624">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="81494-625">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-625">Human Resources</span></span>                 | <span data-ttu-id="81494-626">Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-626">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="81494-627">Casado/a</span><span class="sxs-lookup"><span data-stu-id="81494-627">Married</span></span>                | <span data-ttu-id="81494-628">Casado/a</span><span class="sxs-lookup"><span data-stu-id="81494-628">Married</span></span>                   |
| <span data-ttu-id="81494-629">Único</span><span class="sxs-lookup"><span data-stu-id="81494-629">Single</span></span>                 | <span data-ttu-id="81494-630">Único</span><span class="sxs-lookup"><span data-stu-id="81494-630">Single</span></span>                    |
| <span data-ttu-id="81494-631">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="81494-631">Widowed</span></span>                | <span data-ttu-id="81494-632">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="81494-632">Widowed</span></span>                   |
| <span data-ttu-id="81494-633">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="81494-633">Divorced</span></span>               | <span data-ttu-id="81494-634">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="81494-634">Divorced</span></span>                  |
| <span data-ttu-id="81494-635">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="81494-635">Registered Partnership</span></span> | <span data-ttu-id="81494-636">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="81494-636">Domestic Partnership</span></span>      |
| <span data-ttu-id="81494-637">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="81494-637">None</span></span>                   | <span data-ttu-id="81494-638">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="81494-638">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="81494-639">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="81494-639">Cohabiting</span></span>             | <span data-ttu-id="81494-640">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="81494-640">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="81494-641">Género</span><span class="sxs-lookup"><span data-stu-id="81494-641">Gender</span></span>

<span data-ttu-id="81494-642">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="81494-642">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="81494-643">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-643">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="81494-644">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-644">Human Resources</span></span>       | <span data-ttu-id="81494-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-645">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="81494-646">Masculino</span><span class="sxs-lookup"><span data-stu-id="81494-646">Male</span></span>         | <span data-ttu-id="81494-647">Masculino</span><span class="sxs-lookup"><span data-stu-id="81494-647">Male</span></span>                      |
| <span data-ttu-id="81494-648">Femenino</span><span class="sxs-lookup"><span data-stu-id="81494-648">Female</span></span>       | <span data-ttu-id="81494-649">Femenino</span><span class="sxs-lookup"><span data-stu-id="81494-649">Female</span></span>                    |
| <span data-ttu-id="81494-650">No específico</span><span class="sxs-lookup"><span data-stu-id="81494-650">Non-specific</span></span> | <span data-ttu-id="81494-651">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="81494-651">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="81494-652">Método de pago</span><span class="sxs-lookup"><span data-stu-id="81494-652">Payment method</span></span>

<span data-ttu-id="81494-653">Los métodos de pago ofrecen al empleado y la empresa una forma de describir cómo se pagará a los empleados.</span><span class="sxs-lookup"><span data-stu-id="81494-653">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="81494-654">Los métodos de pago se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="81494-654">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="81494-655">En la siguiente tabla se muestra cómo los métodos de pago se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-655">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="81494-656">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-656">Human Resources</span></span>             | <span data-ttu-id="81494-657">Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-657">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="81494-658">Efectivo</span><span class="sxs-lookup"><span data-stu-id="81494-658">Cash</span></span>               | <span data-ttu-id="81494-659">Efectivo</span><span class="sxs-lookup"><span data-stu-id="81494-659">Cash</span></span>                      |
| <span data-ttu-id="81494-660">Pago electrónico</span><span class="sxs-lookup"><span data-stu-id="81494-660">Electronic Payment</span></span> | <span data-ttu-id="81494-661">Transferir</span><span class="sxs-lookup"><span data-stu-id="81494-661">Transfer</span></span>                  |
| <span data-ttu-id="81494-662">Comprobación</span><span class="sxs-lookup"><span data-stu-id="81494-662">Check</span></span>              | <span data-ttu-id="81494-663">Cheque</span><span class="sxs-lookup"><span data-stu-id="81494-663">Cheque</span></span>                    |
| <span data-ttu-id="81494-664">Efecto bancario</span><span class="sxs-lookup"><span data-stu-id="81494-664">Bank Draft</span></span>         | <span data-ttu-id="81494-665">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="81494-665">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="81494-666">Otras</span><span class="sxs-lookup"><span data-stu-id="81494-666">Other</span></span>              | <span data-ttu-id="81494-667">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="81494-667">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="81494-668">Tipo de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="81494-668">Bank account type</span></span>

<span data-ttu-id="81494-669">Los tipos de cuenta bancaria se usan para los pagos electrónicos a los empleados.</span><span class="sxs-lookup"><span data-stu-id="81494-669">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="81494-670">Los tipos de cuenta bancaria se asignan a Dayforce como información de cuenta de transferencia.</span><span class="sxs-lookup"><span data-stu-id="81494-670">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="81494-671">Los tipos de cuenta bancaria se convierten, según proceda, en los valores aceptados en la integración.</span><span class="sxs-lookup"><span data-stu-id="81494-671">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="81494-672">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-672">Human Resources</span></span>            | <span data-ttu-id="81494-673">Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-673">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="81494-674">Cuenta corriente</span><span class="sxs-lookup"><span data-stu-id="81494-674">Checking Account</span></span>  | <span data-ttu-id="81494-675">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="81494-675">CheckingAccount</span></span>           |
| <span data-ttu-id="81494-676">Cuenta de nómina</span><span class="sxs-lookup"><span data-stu-id="81494-676">Payroll Account</span></span>   | <span data-ttu-id="81494-677">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="81494-677">PayrollAccount</span></span>            |
| <span data-ttu-id="81494-678">Cuenta de ahorros</span><span class="sxs-lookup"><span data-stu-id="81494-678">Savings Account</span></span>   | <span data-ttu-id="81494-679">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="81494-679">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="81494-680">Cuenta de BankGirot</span><span class="sxs-lookup"><span data-stu-id="81494-680">BankGirot account</span></span> | <span data-ttu-id="81494-681">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="81494-681">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="81494-682">Cuenta de PlusGirot</span><span class="sxs-lookup"><span data-stu-id="81494-682">PlusGirot account</span></span> | <span data-ttu-id="81494-683">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="81494-683">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="81494-684">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="81494-684">Earning codes</span></span>

<span data-ttu-id="81494-685">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="81494-685">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="81494-686">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="81494-686">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="81494-687">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="81494-687">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="81494-688">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="81494-688">Supported frequencies</span></span>

- <span data-ttu-id="81494-689">Todas</span><span class="sxs-lookup"><span data-stu-id="81494-689">All</span></span>
- <span data-ttu-id="81494-690">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="81494-690">EVERYPAY</span></span>
- <span data-ttu-id="81494-691">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="81494-691">EACHPAYPERIOD</span></span>
- <span data-ttu-id="81494-692">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="81494-692">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="81494-693">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="81494-693">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="81494-694">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-694">1OFMTH</span></span>
- <span data-ttu-id="81494-695">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-695">LASTOFMTH</span></span>
- <span data-ttu-id="81494-696">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-696">2OFMTH</span></span>
- <span data-ttu-id="81494-697">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-697">3OFMTH</span></span>
- <span data-ttu-id="81494-698">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-698">4OFMTH</span></span>
- <span data-ttu-id="81494-699">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-699">5OFMTH</span></span>
- <span data-ttu-id="81494-700">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-700">1N2OFMTH</span></span>
- <span data-ttu-id="81494-701">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-701">3N4OFMTH</span></span>
- <span data-ttu-id="81494-702">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-702">1N3OFMTH</span></span>
- <span data-ttu-id="81494-703">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-703">1N4OFMTH</span></span>
- <span data-ttu-id="81494-704">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-704">2N3OFMTH</span></span>
- <span data-ttu-id="81494-705">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-705">2N4OFMTH</span></span>
- <span data-ttu-id="81494-706">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-706">1N2N3OFMTH</span></span>
- <span data-ttu-id="81494-707">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-707">1N2N4OFMTH</span></span>
- <span data-ttu-id="81494-708">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-708">1N3N4OFMTH</span></span>
- <span data-ttu-id="81494-709">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-709">2N3N4OFMTH</span></span>
- <span data-ttu-id="81494-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="81494-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="81494-711">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="81494-711">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="81494-712">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="81494-712">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="81494-713">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="81494-713">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="81494-714">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="81494-714">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="81494-715">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="81494-715">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="81494-716">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="81494-716">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="81494-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="81494-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="81494-718">Direcciones</span><span class="sxs-lookup"><span data-stu-id="81494-718">Addresses</span></span>

<span data-ttu-id="81494-719">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="81494-719">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="81494-720">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="81494-720">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="81494-721">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="81494-721">Human Resources</span></span>              | <span data-ttu-id="81494-722">Dayforce</span><span class="sxs-lookup"><span data-stu-id="81494-722">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="81494-723">País/región</span><span class="sxs-lookup"><span data-stu-id="81494-723">Country/Region</span></span>      | <span data-ttu-id="81494-724">Código de país</span><span class="sxs-lookup"><span data-stu-id="81494-724">Country Code</span></span>          |
| <span data-ttu-id="81494-725">Código postal</span><span class="sxs-lookup"><span data-stu-id="81494-725">Zip/Postal Code</span></span>     | <span data-ttu-id="81494-726">Código postal</span><span class="sxs-lookup"><span data-stu-id="81494-726">Postal Code</span></span>           |
| <span data-ttu-id="81494-727">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="81494-727">State</span></span>               | <span data-ttu-id="81494-728">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="81494-728">State Code</span></span>            |
| <span data-ttu-id="81494-729">Población</span><span class="sxs-lookup"><span data-stu-id="81494-729">City</span></span>                | <span data-ttu-id="81494-730">Población</span><span class="sxs-lookup"><span data-stu-id="81494-730">City</span></span>                  |
| <span data-ttu-id="81494-731">Comarca</span><span class="sxs-lookup"><span data-stu-id="81494-731">County</span></span>              | <span data-ttu-id="81494-732">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="81494-732">County (Municipality)</span></span> |
| <span data-ttu-id="81494-733">Calle</span><span class="sxs-lookup"><span data-stu-id="81494-733">Street</span></span>              | <span data-ttu-id="81494-734">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="81494-734">Address Line 1</span></span>        |
| <span data-ttu-id="81494-735">Número de calle</span><span class="sxs-lookup"><span data-stu-id="81494-735">Street Number</span></span>       | <span data-ttu-id="81494-736">Línea de dirección 2</span><span class="sxs-lookup"><span data-stu-id="81494-736">Address Line 2</span></span>        |
| <span data-ttu-id="81494-737">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="81494-737">Building Complement</span></span> | <span data-ttu-id="81494-738">Línea de dirección 5</span><span class="sxs-lookup"><span data-stu-id="81494-738">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="81494-739">Número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="81494-739">Passport number</span></span>

<span data-ttu-id="81494-740">Los empleados pueden declarar la información del pasaporte.</span><span class="sxs-lookup"><span data-stu-id="81494-740">Employees can declare passport information.</span></span> <span data-ttu-id="81494-741">Esta información es del tipo de identificación **Pasaporte** y se integra en Dayforce como parte de la información específica de México de un empleado.</span><span class="sxs-lookup"><span data-stu-id="81494-741">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="81494-742">Tipo de identificación = "Pasaporte"</span><span class="sxs-lookup"><span data-stu-id="81494-742">Identification Type = "Passport"</span></span>
- <span data-ttu-id="81494-743">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="81494-743">Issued Date</span></span>
- <span data-ttu-id="81494-744">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="81494-744">Expiration Date</span></span>

<span data-ttu-id="81494-745">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Pasaporte**.</span><span class="sxs-lookup"><span data-stu-id="81494-745">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="81494-746">Sin embargo, solo la entrada de pasaporte activa actual se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-746">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="81494-747">Si todas las entradas de pasaporte han caducado, el pasaporte que se emitió más recientemente se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="81494-747">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>

