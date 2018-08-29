---
title: "Configurar la integración de nóminas entre Talent y Dayforce"
description: "Este tema explica cómo configurar la integración entre Microsoft Dynamics 365 for Talent y Ceridian Dayforce de modo que pueda procesar un período de pago."
author: jcart1106
manager: AnnBe
ms.date: 07/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: fcddf82cffb9f0ba94b83eb21809b810585ebc9e
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="e38b8-103">Configurar la integración de nóminas entre Talent y Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e38b8-104">La integración entre Microsoft Dynamics 365 for Talent y Ceridian Dayforce se basa en varios pasos de configuración que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="e38b8-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="e38b8-105">Debe configurar la integración en Talent y Dayforce para poder procesar un período de pago.</span><span class="sxs-lookup"><span data-stu-id="e38b8-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="e38b8-106">Cuando se utiliza un servicio como Dayforce para completar períodos de pago, debe habilitar la integración en Talent.</span><span class="sxs-lookup"><span data-stu-id="e38b8-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="e38b8-107">La integración necesita los datos específicos de Talent.</span><span class="sxs-lookup"><span data-stu-id="e38b8-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="e38b8-108">Por lo tanto, debe comprobar que los datos que se asignen a Dayforce se hayan configurado en Talent de una forma que admita la integración.</span><span class="sxs-lookup"><span data-stu-id="e38b8-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="e38b8-109">La integración utiliza las amplias categorías de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e38b8-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="e38b8-110">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="e38b8-110">Human resources data</span></span>
- <span data-ttu-id="e38b8-111">Catos de compensación</span><span class="sxs-lookup"><span data-stu-id="e38b8-111">Compensation data</span></span>
- <span data-ttu-id="e38b8-112">Datos de nómina, como ciclos de pago, períodos de sueldo, y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="e38b8-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="e38b8-113">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="e38b8-113">Worker data</span></span>

<span data-ttu-id="e38b8-114">Este tema describe los pasos que debe seguir para habilitar la integración.</span><span class="sxs-lookup"><span data-stu-id="e38b8-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="e38b8-115">También explica los tipos de datos y los detalles de configuración que requiere la integración.</span><span class="sxs-lookup"><span data-stu-id="e38b8-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="e38b8-116">Habilitar la integración</span><span class="sxs-lookup"><span data-stu-id="e38b8-116">Enable the integration</span></span>

<span data-ttu-id="e38b8-117">En Talent, debe activar la integración y especificar información de configuración para conectarse a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="e38b8-118">Si desea que la transacción de contabilidad general que se genera se importe en Microsoft Dynamics 365 for Finance and Operations, también debe configurar una cuenta de almacenamiento de Microsoft Azure y especificar la cadena de conexión Azure Storage en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e38b8-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="e38b8-119">Para activar la integración en Talent, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e38b8-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="e38b8-120">En la página **Administración del sistema** , seleccione **Configuración de la integración**.</span><span class="sxs-lookup"><span data-stu-id="e38b8-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="e38b8-121">Permite especificar el extremo del Protocolo de transferencia de archivos (FTP) y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="e38b8-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="e38b8-122">Escriba el nombre de usuario y contraseña del usuario que accederá al extremo y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="e38b8-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="e38b8-123">Pruebe la conexión, como sea necesario, y establezca la opción **Habilitar la integración de nómina** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e38b8-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="e38b8-124">Cuando está activada la integración, se crean el paquete y los archivos de exportación de datos, y se establece la frecuencia.</span><span class="sxs-lookup"><span data-stu-id="e38b8-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="e38b8-125">Puede cambiar esta frecuencia como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e38b8-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="e38b8-126">Para obtener más información acerca de las cuentas de almacenamiento de Azure y las cadenas de conexión de Azure Storage, consulte los temas de Azure siguientes:</span><span class="sxs-lookup"><span data-stu-id="e38b8-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="e38b8-127">Acerca de las cuentas de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="e38b8-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="e38b8-128">Configurar las cadenas de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="e38b8-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="e38b8-129">Configurar los datos</span><span class="sxs-lookup"><span data-stu-id="e38b8-129">Configure your data</span></span> 

<span data-ttu-id="e38b8-130">Para procesar las nóminas, debe configurar los datos de recursos humanos en Talent.</span><span class="sxs-lookup"><span data-stu-id="e38b8-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="e38b8-131">Debe configurar datos de organización, como los trabajos y los puestos, así como las prestaciones y la información de compensación.</span><span class="sxs-lookup"><span data-stu-id="e38b8-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="e38b8-132">Esta información proporciona la información de empleo, pago y deducciones que se necesita para producir el sueldo del empleado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="e38b8-133">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="e38b8-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="e38b8-134">Beneficios</span><span class="sxs-lookup"><span data-stu-id="e38b8-134">Benefits</span></span> 

<span data-ttu-id="e38b8-135">Recursos humanos ofrece herramientas para la configuración y el mantenimiento de prestaciones, deducciones y los planes de compensación de los trabajadores que una organización ofrece o procesa para sus trabajadores.</span><span class="sxs-lookup"><span data-stu-id="e38b8-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="e38b8-136">Al crear las prestaciones, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="e38b8-137">Planes de prestaciones</span><span class="sxs-lookup"><span data-stu-id="e38b8-137">Benefit plans</span></span>

- <span data-ttu-id="e38b8-138">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-138">Plan (required)</span></span>
- <span data-ttu-id="e38b8-139">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-139">Type (required)</span></span>
- <span data-ttu-id="e38b8-140">Impacto de nómina (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-140">Payroll impact (required)</span></span>
- <span data-ttu-id="e38b8-141">Recuperar atrasos</span><span class="sxs-lookup"><span data-stu-id="e38b8-141">Recover arrears</span></span>
- <span data-ttu-id="e38b8-142">Método de deducción</span><span class="sxs-lookup"><span data-stu-id="e38b8-142">Deduction method</span></span>
- <span data-ttu-id="e38b8-143">Prioridad de deducción</span><span class="sxs-lookup"><span data-stu-id="e38b8-143">Deduction priority</span></span>
- <span data-ttu-id="e38b8-144">Período de límite</span><span class="sxs-lookup"><span data-stu-id="e38b8-144">Limit period</span></span>
- <span data-ttu-id="e38b8-145">Importe límite</span><span class="sxs-lookup"><span data-stu-id="e38b8-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="e38b8-146">Beneficios</span><span class="sxs-lookup"><span data-stu-id="e38b8-146">Benefits</span></span>

- <span data-ttu-id="e38b8-147">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-147">Plan (required)</span></span>
- <span data-ttu-id="e38b8-148">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-148">Type (required)</span></span>
- <span data-ttu-id="e38b8-149">Opción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-149">Option (required)</span></span>
- <span data-ttu-id="e38b8-150">Identificador de prestación (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-150">Benefit ID (required)</span></span>
- <span data-ttu-id="e38b8-151">Frecuencia</span><span class="sxs-lookup"><span data-stu-id="e38b8-151">Frequency</span></span>
- <span data-ttu-id="e38b8-152">Base</span><span class="sxs-lookup"><span data-stu-id="e38b8-152">Basis</span></span>
- <span data-ttu-id="e38b8-153">Importe o índice</span><span class="sxs-lookup"><span data-stu-id="e38b8-153">Amount or rate</span></span>
- <span data-ttu-id="e38b8-154">Código de ganancias</span><span class="sxs-lookup"><span data-stu-id="e38b8-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="e38b8-155">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="e38b8-155">Supported frequencies</span></span> 

- <span data-ttu-id="e38b8-156">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="e38b8-156">Weekly</span></span>
- <span data-ttu-id="e38b8-157">Quincenal</span><span class="sxs-lookup"><span data-stu-id="e38b8-157">Bi-weekly</span></span>
- <span data-ttu-id="e38b8-158">Bimensual</span><span class="sxs-lookup"><span data-stu-id="e38b8-158">Semi-monthly</span></span>
- <span data-ttu-id="e38b8-159">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="e38b8-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="e38b8-160">Bases admitidas</span><span class="sxs-lookup"><span data-stu-id="e38b8-160">Supported bases</span></span> 

- <span data-ttu-id="e38b8-161">Importe fijo</span><span class="sxs-lookup"><span data-stu-id="e38b8-161">Fixed amount</span></span>
- <span data-ttu-id="e38b8-162">Porcentaje de ganancias</span><span class="sxs-lookup"><span data-stu-id="e38b8-162">Percent of earnings</span></span>
- <span data-ttu-id="e38b8-163">Horas productivas</span><span class="sxs-lookup"><span data-stu-id="e38b8-163">Productive hours</span></span>

<span data-ttu-id="e38b8-164">Dayforce crea las deducciones siguientes, según el impacto de nómina que hay definido en el plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="e38b8-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="e38b8-165">Selección en Talent</span><span class="sxs-lookup"><span data-stu-id="e38b8-165">Selection in Talent</span></span>        | <span data-ttu-id="e38b8-166">Resultado en Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="e38b8-167">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="e38b8-167">None</span></span>                       | <span data-ttu-id="e38b8-168">No se crea ninguna deducción.</span><span class="sxs-lookup"><span data-stu-id="e38b8-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="e38b8-169">Solo deducción</span><span class="sxs-lookup"><span data-stu-id="e38b8-169">Deduction only</span></span>             | <span data-ttu-id="e38b8-170">Se crea una deducción del empleado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="e38b8-171">Solo contribución</span><span class="sxs-lookup"><span data-stu-id="e38b8-171">Contribution only</span></span>          | <span data-ttu-id="e38b8-172">Se crea una deducción del empresario.</span><span class="sxs-lookup"><span data-stu-id="e38b8-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="e38b8-173">Deducción y contribución</span><span class="sxs-lookup"><span data-stu-id="e38b8-173">Deduction and contribution</span></span> | <span data-ttu-id="e38b8-174">Se crean las deducciones del empleado y del empresario.</span><span class="sxs-lookup"><span data-stu-id="e38b8-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="e38b8-175">Para obtener más información sobre cómo definir y administrar un programa de prestaciones, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="e38b8-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="e38b8-176">Proporcionar un programa de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="e38b8-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="e38b8-177">Crear una nueva prestación</span><span class="sxs-lookup"><span data-stu-id="e38b8-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="e38b8-178">Definir reglas y directivas de idoneidad para prestaciones</span><span class="sxs-lookup"><span data-stu-id="e38b8-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="e38b8-179">Inscribir y quitar prestaciones para trabajadores</span><span class="sxs-lookup"><span data-stu-id="e38b8-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="e38b8-180">Compensación</span><span class="sxs-lookup"><span data-stu-id="e38b8-180">Compensation</span></span> 

<span data-ttu-id="e38b8-181">La gestión de compensaciones se usa para controlar la entrega de salarios base y primas.</span><span class="sxs-lookup"><span data-stu-id="e38b8-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="e38b8-182">El sueldo base fijo de un empleado y los aumentos por méritos se controlan mediante planes de compensación fijos.</span><span class="sxs-lookup"><span data-stu-id="e38b8-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="e38b8-183">El pago de incentivos, como los pagos de bonificación, las primas por rendimiento, las acciones y las concesiones, así como también las primas ocasionales, se controlan a través de planes de compensación variable.</span><span class="sxs-lookup"><span data-stu-id="e38b8-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="e38b8-184">Dayforce utiliza la información de compensación para calcular la tarifa por hora o anual de un empleado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="e38b8-185">Se requieren planes de compensación fija y conversiones de índice salarial.</span><span class="sxs-lookup"><span data-stu-id="e38b8-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="e38b8-186">Los empleados deben estar asociados a un plan de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="e38b8-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="e38b8-187">Para obtener más información acerca de los panes de compensación, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="e38b8-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="e38b8-188">Crear planes de compensación fija</span><span class="sxs-lookup"><span data-stu-id="e38b8-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="e38b8-189">Crear planes de compensación variable</span><span class="sxs-lookup"><span data-stu-id="e38b8-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="e38b8-190">Desarrollar planes y estructura de salarios o compensaciones</span><span class="sxs-lookup"><span data-stu-id="e38b8-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="e38b8-191">Procesar compensaciones</span><span class="sxs-lookup"><span data-stu-id="e38b8-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="e38b8-192">Definición del proceso de compensación y el cálculo de resultados</span><span class="sxs-lookup"><span data-stu-id="e38b8-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="e38b8-193">Inscribir a un empleado en un plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="e38b8-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="e38b8-194">Inscribir a un empleado en un plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="e38b8-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="e38b8-195">Trabajos</span><span class="sxs-lookup"><span data-stu-id="e38b8-195">Jobs</span></span> 

<span data-ttu-id="e38b8-196">Un trabajo es un conjunto de las tareas y responsabilidades que deberá cumplir la persona que realiza un trabajo.</span><span class="sxs-lookup"><span data-stu-id="e38b8-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="e38b8-197">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="e38b8-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="e38b8-198">Configurar los componentes de un trabajo</span><span class="sxs-lookup"><span data-stu-id="e38b8-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="e38b8-199">Definir nuevos trabajos</span><span class="sxs-lookup"><span data-stu-id="e38b8-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="e38b8-200">Puestos</span><span class="sxs-lookup"><span data-stu-id="e38b8-200">Positions</span></span>

<span data-ttu-id="e38b8-201">Un puesto es un caso individual de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="e38b8-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="e38b8-202">Por ejemplo, el puesto "Director de ventas (Este)" es uno de los puestos asociados al trabajo "Director de ventas".</span><span class="sxs-lookup"><span data-stu-id="e38b8-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="e38b8-203">Un puesto existe en un departamento.</span><span class="sxs-lookup"><span data-stu-id="e38b8-203">A position exists in a department.</span></span> <span data-ttu-id="e38b8-204">Solo un trabajador puede asociarse solo a cada puesto.</span><span class="sxs-lookup"><span data-stu-id="e38b8-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="e38b8-205">Tenga en cuenta los siguientes datos y configuración al configurar los puestos:</span><span class="sxs-lookup"><span data-stu-id="e38b8-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="e38b8-206">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-206">Position (required)</span></span>
- <span data-ttu-id="e38b8-207">Descripción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-207">Description (required)</span></span>
- <span data-ttu-id="e38b8-208">Trabajo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-208">Job (required)</span></span>
- <span data-ttu-id="e38b8-209">Departamento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-209">Department (required)</span></span>
- <span data-ttu-id="e38b8-210">Tipo de puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-210">Position type (required)</span></span>
- <span data-ttu-id="e38b8-211">Equivalente de jornada completa</span><span class="sxs-lookup"><span data-stu-id="e38b8-211">Full-time equivalent</span></span>
- <span data-ttu-id="e38b8-212">Horas ordinarias anuales (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="e38b8-213">Pagado por la entidad jurídica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="e38b8-214">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-214">Pay cycle (required)</span></span>
- <span data-ttu-id="e38b8-215">Dimensión financiera predeterminada – Centro de coste (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="e38b8-216">Asignación de trabajador – Trabajador, inicio de la asignación, final de la asignación, código de motivo</span><span class="sxs-lookup"><span data-stu-id="e38b8-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="e38b8-217">Si varios puestos en el mismo departamento están asociados al mismo trabajo, se consolidan en un solo puesto en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="e38b8-218">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="e38b8-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="e38b8-219">Organizar los recursos mediante departamentos, trabajos y puestos</span><span class="sxs-lookup"><span data-stu-id="e38b8-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="e38b8-220">Configurar puestos</span><span class="sxs-lookup"><span data-stu-id="e38b8-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="e38b8-221">Departamentos</span><span class="sxs-lookup"><span data-stu-id="e38b8-221">Departments</span></span>

<span data-ttu-id="e38b8-222">Un departamneto es una unidad operativa que representa una categoría o un área funcional de la organización.</span><span class="sxs-lookup"><span data-stu-id="e38b8-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="e38b8-223">Un departamento es responsable de un área específica de la organización, como ventas, contabilidad o recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="e38b8-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="e38b8-224">Puede usar departamentos para informar sobre las áreas funcionales.</span><span class="sxs-lookup"><span data-stu-id="e38b8-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="e38b8-225">Los departamentos pueden tener responsabilidad de pérdidas y ganancias.</span><span class="sxs-lookup"><span data-stu-id="e38b8-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="e38b8-226">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="e38b8-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="e38b8-227">Crear un departamento y asociarlo a la jerarquía de departamentos</span><span class="sxs-lookup"><span data-stu-id="e38b8-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="e38b8-228">Definir nuevos departamentos</span><span class="sxs-lookup"><span data-stu-id="e38b8-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="e38b8-229">Ciclos y períodos de pago</span><span class="sxs-lookup"><span data-stu-id="e38b8-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="e38b8-230">Un ciclo de pago determina la frecuencia con la que se ejecuta el cálculo de nómina y los días específicos en los que se paga a los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="e38b8-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="e38b8-231">Por ejemplo, un ciclo de pago puede ser mensual y a los empleados se les podría pagar el último día del mes.</span><span class="sxs-lookup"><span data-stu-id="e38b8-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="e38b8-232">De forma alternativa, un ciclo de pago puede ser semanal y a los empleados se les podría pagar el martes después del final del período de pago.</span><span class="sxs-lookup"><span data-stu-id="e38b8-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="e38b8-233">Los ciclos de pago se asignan a los puestos para controlar cuándo se paga a los trabajadores en esos puestos.</span><span class="sxs-lookup"><span data-stu-id="e38b8-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="e38b8-234">Después de crear ciclos de pago, puede generar los períodos de pago para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="e38b8-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="e38b8-235">Cada período de pago incluye una fecha de pago predeterminada basada en la información que proporcione.</span><span class="sxs-lookup"><span data-stu-id="e38b8-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="e38b8-236">Sin embargo, puede modificar la fecha de pago predeterminada en un período de pago para permitir excepciones, por ejemplo, cuando la fecha de pago se encuentra en un día festivo.</span><span class="sxs-lookup"><span data-stu-id="e38b8-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="e38b8-237">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="e38b8-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="e38b8-238">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-238">Pay cycle (required)</span></span>
- <span data-ttu-id="e38b8-239">Frecuencia del ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="e38b8-240">Fecha de inicio del período (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="e38b8-241">Fecha de pago predeterminado (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="e38b8-242">Esta información se integra con Dayforce como grupos salariales y se separa por país o región para cada ciclo de pago.</span><span class="sxs-lookup"><span data-stu-id="e38b8-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="e38b8-243">Al menos se debe generar un período de sueldo antes de la integración.</span><span class="sxs-lookup"><span data-stu-id="e38b8-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="e38b8-244">Dayforce genera los calendarios de grupo salarial y las fechas de pago, en función de la fecha inicial del primer período de pago y la fecha de pago predeterminada que se configuran en Talent.</span><span class="sxs-lookup"><span data-stu-id="e38b8-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="e38b8-245">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="e38b8-245">Earning codes</span></span>

<span data-ttu-id="e38b8-246">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="e38b8-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="e38b8-247">Los códigos tienen distintos parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="e38b8-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="e38b8-248">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="e38b8-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="e38b8-249">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-249">Earning Code (required)</span></span>
- <span data-ttu-id="e38b8-250">Descripción</span><span class="sxs-lookup"><span data-stu-id="e38b8-250">Description</span></span>
- <span data-ttu-id="e38b8-251">Unidad de medida</span><span class="sxs-lookup"><span data-stu-id="e38b8-251">Unit of measure</span></span>
- <span data-ttu-id="e38b8-252">Productivo</span><span class="sxs-lookup"><span data-stu-id="e38b8-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="e38b8-253">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="e38b8-253">Worker data</span></span>

<span data-ttu-id="e38b8-254">Los registros para los diferentes tipos de trabajadores que tiene son importantes para los sistemas de recursos humanos y nómina.</span><span class="sxs-lookup"><span data-stu-id="e38b8-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="e38b8-255">La información que se indique se puede utilizar para efectuar un seguimiento de los trabajadores y su información personal.</span><span class="sxs-lookup"><span data-stu-id="e38b8-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="e38b8-256">Puede mantener la información siguiente para los trabajadores:</span><span class="sxs-lookup"><span data-stu-id="e38b8-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="e38b8-257">**Básica**: permite mantener la información básica de un trabajador, como la información de contacto, información demográfica, información de identificación, información de familia, estado del servicio militar, información de expatriado y contactos personales y de emergencia.</span><span class="sxs-lookup"><span data-stu-id="e38b8-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="e38b8-258">**Empleo**: permite mantener la información sobre el empleo de un trabajador, como afiliación de la empresa u organización, asignación de puesto, fecha de inicio y finalización, idoneidad para el trabajo, condiciones de empleo, pensión, vacaciones y la información de reubicación.</span><span class="sxs-lookup"><span data-stu-id="e38b8-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="e38b8-259">**Bajas y ausencias**: permite mantener información sobre las ausencias de un trabajador, como calendarios de trabajo, transacciones de ausencia y configuración de ausencias.</span><span class="sxs-lookup"><span data-stu-id="e38b8-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="e38b8-260">**Compensación y nómina**: permite mantener la información sobre los planes de compensación y la información de nómina de un trabajador, como inscripción del plan, concesiones, desempeño, comisión, información fiscal, retiro y deducciones de sueldo.</span><span class="sxs-lookup"><span data-stu-id="e38b8-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="e38b8-261">Al introducir la información del trabajador, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="e38b8-262">Información general</span><span class="sxs-lookup"><span data-stu-id="e38b8-262">General information</span></span>

- <span data-ttu-id="e38b8-263">Número de personal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-263">Personnel number (required)</span></span>
- <span data-ttu-id="e38b8-264">Nombre (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-264">First name (required)</span></span>
- <span data-ttu-id="e38b8-265">Apellido (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-265">Last name (required)</span></span>
- <span data-ttu-id="e38b8-266">Segundo nombre</span><span class="sxs-lookup"><span data-stu-id="e38b8-266">Middle name</span></span>
- <span data-ttu-id="e38b8-267">Antigüedad</span><span class="sxs-lookup"><span data-stu-id="e38b8-267">Seniority date</span></span>
- <span data-ttu-id="e38b8-268">Conocido como</span><span class="sxs-lookup"><span data-stu-id="e38b8-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="e38b8-269">Información personal</span><span class="sxs-lookup"><span data-stu-id="e38b8-269">Personal information</span></span>

- <span data-ttu-id="e38b8-270">Estado civil (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-270">Marital status (required)</span></span>
- <span data-ttu-id="e38b8-271">Fecha de nacimiento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-271">Birth date (required)</span></span>
- <span data-ttu-id="e38b8-272">Sexo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-272">Gender (required)</span></span>
- <span data-ttu-id="e38b8-273">Persona con discapacidades</span><span class="sxs-lookup"><span data-stu-id="e38b8-273">Person with disabilities</span></span>
- <span data-ttu-id="e38b8-274">País o región, nacionalidad (solo para México)</span><span class="sxs-lookup"><span data-stu-id="e38b8-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="e38b8-275">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="e38b8-275">Address information</span></span>

- <span data-ttu-id="e38b8-276">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-276">Primary (required)</span></span>
- <span data-ttu-id="e38b8-277">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-277">Country/region (required)</span></span>
- <span data-ttu-id="e38b8-278">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-278">Postal code (required)</span></span>
- <span data-ttu-id="e38b8-279">Número de calle (obligatorio) (solo para México)</span><span class="sxs-lookup"><span data-stu-id="e38b8-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="e38b8-280">Complemento de edificio (solo para México)</span><span class="sxs-lookup"><span data-stu-id="e38b8-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="e38b8-281">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-281">City (required)</span></span>
- <span data-ttu-id="e38b8-282">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-282">State (required)</span></span>
- <span data-ttu-id="e38b8-283">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="e38b8-284">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="e38b8-284">Contact information</span></span> 

- <span data-ttu-id="e38b8-285">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-285">Primary (required)</span></span>
- <span data-ttu-id="e38b8-286">Número de contacto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-286">Contact number (required)</span></span>
- <span data-ttu-id="e38b8-287">Extensión</span><span class="sxs-lookup"><span data-stu-id="e38b8-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="e38b8-288">Información de nómina y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="e38b8-288">Payroll information and earning codes</span></span>

<span data-ttu-id="e38b8-289">A los empleados se les pueden asignar ganancias específicas de una frecuencia determinada de pago y tener un método de pago preferido.</span><span class="sxs-lookup"><span data-stu-id="e38b8-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="e38b8-290">Los siguientes campos se utilizan en Dayforce para ayudar a garantizar que se usen las preferencias y valores.</span><span class="sxs-lookup"><span data-stu-id="e38b8-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="e38b8-291">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="e38b8-291">Earning codes</span></span>

- <span data-ttu-id="e38b8-292">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-292">Position (required)</span></span>
- <span data-ttu-id="e38b8-293">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-293">Earning Code (required)</span></span>
- <span data-ttu-id="e38b8-294">Frecuencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-294">Frequency (required)</span></span>
- <span data-ttu-id="e38b8-295">Importe (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="e38b8-296">Información de nómina</span><span class="sxs-lookup"><span data-stu-id="e38b8-296">Payroll information</span></span>

- <span data-ttu-id="e38b8-297">Método de pago</span><span class="sxs-lookup"><span data-stu-id="e38b8-297">Payment Method</span></span>
- <span data-ttu-id="e38b8-298">Región económica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-298">Economic Region (required)</span></span>
- <span data-ttu-id="e38b8-299">Id. de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="e38b8-299">Employee Benefits ID</span></span>
- <span data-ttu-id="e38b8-300">Número de id. nacional (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-300">National ID Number (required)</span></span>
- <span data-ttu-id="e38b8-301">Número de servicio militar</span><span class="sxs-lookup"><span data-stu-id="e38b8-301">Military Service Number</span></span>
- <span data-ttu-id="e38b8-302">Id. de turno (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-302">Shift ID (required)</span></span>
- <span data-ttu-id="e38b8-303">Número de identificación fiscal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-303">Tax Number (required)</span></span>
- <span data-ttu-id="e38b8-304">Id. de sindicato (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-304">Union ID (required)</span></span>
- <span data-ttu-id="e38b8-305">Id. de día laborable (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-305">Work Day ID (required)</span></span>
- <span data-ttu-id="e38b8-306">Número de permiso de trabajo</span><span class="sxs-lookup"><span data-stu-id="e38b8-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="e38b8-307">Para el método de pago, México admite **Efectivo**, **Cheque** (cheque físico de la empresa) y **Pago electrónico**.</span><span class="sxs-lookup"><span data-stu-id="e38b8-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="e38b8-308">Si no se especifica ningún método de pago, **Cheque** se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e38b8-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="e38b8-309">Detalles del empleo</span><span class="sxs-lookup"><span data-stu-id="e38b8-309">Employment details</span></span>

<span data-ttu-id="e38b8-310">El historial de detalles de empleo se utiliza como información clave para derivar los estados de contratación, despido y recontratación de un empleado en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="e38b8-311">Dayforce solo admite un registro de empleo activo a la vez.</span><span class="sxs-lookup"><span data-stu-id="e38b8-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="e38b8-312">Fecha de inicio de empleo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-312">Employment start date (required)</span></span>
- <span data-ttu-id="e38b8-313">Fecha final del empleo</span><span class="sxs-lookup"><span data-stu-id="e38b8-313">Employment end date</span></span>
- <span data-ttu-id="e38b8-314">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="e38b8-314">Start date</span></span>
- <span data-ttu-id="e38b8-315">Fecha inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="e38b8-315">Adjusted start date</span></span>
- <span data-ttu-id="e38b8-316">Fecha de finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="e38b8-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="e38b8-317">Razón de la finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="e38b8-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="e38b8-318">Las fechas clave de un empleado se obtienen utilizando la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="e38b8-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="e38b8-319">Talent</span><span class="sxs-lookup"><span data-stu-id="e38b8-319">Talent</span></span>                | <span data-ttu-id="e38b8-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e38b8-321">Fecha de contratación más reciente</span><span class="sxs-lookup"><span data-stu-id="e38b8-321">Most recent hire date</span></span> | <span data-ttu-id="e38b8-322">Inicio de empleo del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="e38b8-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="e38b8-323">Fecha de finalización</span><span class="sxs-lookup"><span data-stu-id="e38b8-323">Termination date</span></span>      | <span data-ttu-id="e38b8-324">Fecha de finalización del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="e38b8-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="e38b8-325">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="e38b8-325">Start date</span></span>            | <span data-ttu-id="e38b8-326">Fecha de inicio ajustada, fecha de inicio o inicio de empleo del registro de historial de empleo inactivo actual</span><span class="sxs-lookup"><span data-stu-id="e38b8-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="e38b8-327">Fecha de contratación original</span><span class="sxs-lookup"><span data-stu-id="e38b8-327">Original hire date</span></span>    | <span data-ttu-id="e38b8-328">Inicio del empleo del registro del historial de empleo más temprano</span><span class="sxs-lookup"><span data-stu-id="e38b8-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="e38b8-329">Compensación</span><span class="sxs-lookup"><span data-stu-id="e38b8-329">Compensation</span></span>

<span data-ttu-id="e38b8-330">Un plan de compensación fija se debe asociar al puesto principal de cada empleado durante un período de empleo.</span><span class="sxs-lookup"><span data-stu-id="e38b8-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="e38b8-331">Este período comienza en la fecha de contratación del empleado (o la fecha de inicio del empleo) y continúa hasta la finalización.</span><span class="sxs-lookup"><span data-stu-id="e38b8-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="e38b8-332">Fecha de vigencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-332">Effective Date (required)</span></span>
- <span data-ttu-id="e38b8-333">Fecha de expiración</span><span class="sxs-lookup"><span data-stu-id="e38b8-333">Expiration date</span></span>
- <span data-ttu-id="e38b8-334">Índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-334">Pay Rate (required)</span></span>
- <span data-ttu-id="e38b8-335">Conversiones de índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="e38b8-336">Equivalente anual (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="e38b8-337">Equivalente por hora (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="e38b8-338">Si un empleado por hora tiene varios puestos, se importa la compensación fija del puesto principal en Dayforce como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="e38b8-339">En el caso de los puestos no principales, el índice por hora se guarda en el puesto correspondiente en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="e38b8-340">Si un empleado a sueldo tiene varios puestos, se derivan el índice por hora acumulativa y el sueldo anual en todos los puestos activos y se utilizan como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="e38b8-341">Números de identificación</span><span class="sxs-lookup"><span data-stu-id="e38b8-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="e38b8-342">Identificador de seguridad social</span><span class="sxs-lookup"><span data-stu-id="e38b8-342">Social Security identifier</span></span> 

<span data-ttu-id="e38b8-343">Cada empleado debe tener un identificador principal.</span><span class="sxs-lookup"><span data-stu-id="e38b8-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="e38b8-344">Este identificador debe ser de tipo de identificación **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="e38b8-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="e38b8-345">En Dayforce, se deriva automáticamente como el identificador de seguridad social del empleado que se requiere para ser contratado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="e38b8-346">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-346">Primary (required)</span></span>
- <span data-ttu-id="e38b8-347">Tipo de identificación = "Nº de SS"</span><span class="sxs-lookup"><span data-stu-id="e38b8-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="e38b8-348">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="e38b8-348">Issued Date</span></span>
- <span data-ttu-id="e38b8-349">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="e38b8-349">Expiration Date</span></span>

<span data-ttu-id="e38b8-350">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="e38b8-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="e38b8-351">Sin embargo, solo el registro que está marcado como **Principal** está integrado en Dayforce, independientemente de si el número está activo o caducado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="e38b8-352">Cuentas bancarias y desembolsos</span><span class="sxs-lookup"><span data-stu-id="e38b8-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="e38b8-353">La información de cuenta bancaria válida se debe especificar para cualquier empleado que elija recibir el pago por transferencias de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="e38b8-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="e38b8-354">Talent</span><span class="sxs-lookup"><span data-stu-id="e38b8-354">Talent</span></span>                         | <span data-ttu-id="e38b8-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e38b8-356">Número de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="e38b8-357">Código SWIFT (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-357">SWIFT code (required)</span></span>          | <span data-ttu-id="e38b8-358">Campo **Identificador del banco** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="e38b8-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="e38b8-359">Número de sucursal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="e38b8-360">Tipo de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-360">Bank account type (required)</span></span>   | <span data-ttu-id="e38b8-361">Campo **Tipo de cuenta** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="e38b8-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="e38b8-362">Los valores admitidos incluyen **Comprobación** y **Nómina**.</span><span class="sxs-lookup"><span data-stu-id="e38b8-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="e38b8-363">Los empleados que elijan que se les pague a través de transferencia bancaria deben proporcionar un vínculo a una cuenta de remanente que esté en una entidad legal que tenga su dirección principal en México y esté asociada con una cuenta bancaria válida de un banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="e38b8-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="e38b8-364">Todas las demás cuentas no remanentes se ignoran.</span><span class="sxs-lookup"><span data-stu-id="e38b8-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="e38b8-365">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="e38b8-365">Address information</span></span>

<span data-ttu-id="e38b8-366">Cada empleado debe tener una ubicación principal.</span><span class="sxs-lookup"><span data-stu-id="e38b8-366">Every employee must have one primary location.</span></span> <span data-ttu-id="e38b8-367">En Dayforce, esta ubicación se usa para determinar la residencia principal del empleado para impuestos.</span><span class="sxs-lookup"><span data-stu-id="e38b8-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="e38b8-368">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-368">Primary (required)</span></span>
- <span data-ttu-id="e38b8-369">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-369">Country/region (required)</span></span>
- <span data-ttu-id="e38b8-370">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="e38b8-371">Calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-371">Street (required)</span></span>
- <span data-ttu-id="e38b8-372">Número de calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-372">Street Number (required)</span></span>
- <span data-ttu-id="e38b8-373">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="e38b8-373">Building Complement</span></span>
- <span data-ttu-id="e38b8-374">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-374">City (required)</span></span>
- <span data-ttu-id="e38b8-375">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-375">State (required)</span></span>
- <span data-ttu-id="e38b8-376">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="e38b8-377">Configure los datos para generar nóminas en Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="e38b8-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="e38b8-378">Si va a generar el sueldo de los empleados en Estados Unidos y Canadá, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="e38b8-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="e38b8-379">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="e38b8-379">Departments are required on positions.</span></span>
- <span data-ttu-id="e38b8-380">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e38b8-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="e38b8-381">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="e38b8-381">Job types</span></span>

<span data-ttu-id="e38b8-382">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="e38b8-382">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="e38b8-383">Los tipos de trabajo son obligatorios para procesar la nómina en Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="e38b8-383">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="e38b8-384">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="e38b8-384">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="e38b8-385">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-385">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="e38b8-386">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="e38b8-386">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="e38b8-387">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e38b8-387">Job type</span></span>   | <span data-ttu-id="e38b8-388">Descripción</span><span class="sxs-lookup"><span data-stu-id="e38b8-388">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="e38b8-389">Por hora</span><span class="sxs-lookup"><span data-stu-id="e38b8-389">Hourly</span></span>     | <span data-ttu-id="e38b8-390">Por hora</span><span class="sxs-lookup"><span data-stu-id="e38b8-390">Hourly</span></span>      |
| <span data-ttu-id="e38b8-391">Asalariado</span><span class="sxs-lookup"><span data-stu-id="e38b8-391">Salaried</span></span>   | <span data-ttu-id="e38b8-392">Asalariado</span><span class="sxs-lookup"><span data-stu-id="e38b8-392">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="e38b8-393">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="e38b8-393">Position types</span></span> 

<span data-ttu-id="e38b8-394">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="e38b8-394">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="e38b8-395">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="e38b8-395">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="e38b8-396">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="e38b8-396">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="e38b8-397">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="e38b8-397">Position type</span></span>   | <span data-ttu-id="e38b8-398">Descripción</span><span class="sxs-lookup"><span data-stu-id="e38b8-398">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="e38b8-399">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="e38b8-399">Full-time</span></span>       | <span data-ttu-id="e38b8-400">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="e38b8-400">Full time employee</span></span> |
| <span data-ttu-id="e38b8-401">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="e38b8-401">Part-time</span></span>       | <span data-ttu-id="e38b8-402">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="e38b8-402">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="e38b8-403">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="e38b8-403">Reason codes</span></span>

<span data-ttu-id="e38b8-404">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-404">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="e38b8-405">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="e38b8-405">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="e38b8-406">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="e38b8-406">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="e38b8-407">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="e38b8-407">Reason code</span></span>    | <span data-ttu-id="e38b8-408">Descripción</span><span class="sxs-lookup"><span data-stu-id="e38b8-408">Description</span></span>      | <span data-ttu-id="e38b8-409">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="e38b8-409">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="e38b8-410">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="e38b8-410">RESIGNATION</span></span>    | <span data-ttu-id="e38b8-411">Dimisión</span><span class="sxs-lookup"><span data-stu-id="e38b8-411">Resignation</span></span>      | <span data-ttu-id="e38b8-412">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-412">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-413">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="e38b8-413">TERMINATION</span></span>    | <span data-ttu-id="e38b8-414">Finalización</span><span class="sxs-lookup"><span data-stu-id="e38b8-414">Termination</span></span>      | <span data-ttu-id="e38b8-415">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-415">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-416">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="e38b8-416">RETIREMENT</span></span>     | <span data-ttu-id="e38b8-417">Jubilación</span><span class="sxs-lookup"><span data-stu-id="e38b8-417">Retirement</span></span>       | <span data-ttu-id="e38b8-418">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-418">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-419">OTHER</span><span class="sxs-lookup"><span data-stu-id="e38b8-419">OTHER</span></span>          | <span data-ttu-id="e38b8-420">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="e38b8-420">Other Reasons</span></span>    | <span data-ttu-id="e38b8-421">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-421">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-422">MUERTE</span><span class="sxs-lookup"><span data-stu-id="e38b8-422">DEATH</span></span>          | <span data-ttu-id="e38b8-423">Muerte</span><span class="sxs-lookup"><span data-stu-id="e38b8-423">Death</span></span>            | <span data-ttu-id="e38b8-424">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-424">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-425">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="e38b8-425">LEAVEOFABSENCE</span></span> | <span data-ttu-id="e38b8-426">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="e38b8-426">Leave of Absence</span></span> | <span data-ttu-id="e38b8-427">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-427">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-428">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="e38b8-428">CONTRACTEND</span></span>    | <span data-ttu-id="e38b8-429">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="e38b8-429">End of Contract</span></span>  | <span data-ttu-id="e38b8-430">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-430">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-431">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="e38b8-431">SALARYCHANGE</span></span>   | <span data-ttu-id="e38b8-432">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="e38b8-432">Change of Salary</span></span> | <span data-ttu-id="e38b8-433">Compensación</span><span class="sxs-lookup"><span data-stu-id="e38b8-433">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="e38b8-434">Estado civil</span><span class="sxs-lookup"><span data-stu-id="e38b8-434">Marital status</span></span>

<span data-ttu-id="e38b8-435">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="e38b8-435">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="e38b8-436">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-436">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="e38b8-437">Talent</span><span class="sxs-lookup"><span data-stu-id="e38b8-437">Talent</span></span>                 | <span data-ttu-id="e38b8-438">Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-438">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="e38b8-439">Casado/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-439">Married</span></span>                | <span data-ttu-id="e38b8-440">Casado/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-440">Married</span></span>              |
| <span data-ttu-id="e38b8-441">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-441">Single</span></span>                 | <span data-ttu-id="e38b8-442">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-442">Single</span></span>               |
| <span data-ttu-id="e38b8-443">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-443">Widowed</span></span>                | <span data-ttu-id="e38b8-444">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-444">Widowed</span></span>              |
| <span data-ttu-id="e38b8-445">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-445">Divorced</span></span>               | <span data-ttu-id="e38b8-446">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-446">Divorced</span></span>             |
| <span data-ttu-id="e38b8-447">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="e38b8-447">Registered Partnership</span></span> | <span data-ttu-id="e38b8-448">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="e38b8-448">Domestic Partnership</span></span> |
| <span data-ttu-id="e38b8-449">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="e38b8-449">None</span></span>                   | <span data-ttu-id="e38b8-450">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="e38b8-450">None</span></span>                 |
| <span data-ttu-id="e38b8-451">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="e38b8-451">Cohabiting</span></span>             | <span data-ttu-id="e38b8-452">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="e38b8-452">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="e38b8-453">Género</span><span class="sxs-lookup"><span data-stu-id="e38b8-453">Gender</span></span>

<span data-ttu-id="e38b8-454">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="e38b8-454">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="e38b8-455">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-455">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="e38b8-456">Talent</span><span class="sxs-lookup"><span data-stu-id="e38b8-456">Talent</span></span>       | <span data-ttu-id="e38b8-457">Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-457">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="e38b8-458">Hombre</span><span class="sxs-lookup"><span data-stu-id="e38b8-458">Male</span></span>         | <span data-ttu-id="e38b8-459">Hombre</span><span class="sxs-lookup"><span data-stu-id="e38b8-459">Male</span></span>            |
| <span data-ttu-id="e38b8-460">Mujer</span><span class="sxs-lookup"><span data-stu-id="e38b8-460">Female</span></span>       | <span data-ttu-id="e38b8-461">Mujer</span><span class="sxs-lookup"><span data-stu-id="e38b8-461">Female</span></span>          |
| <span data-ttu-id="e38b8-462">No específico</span><span class="sxs-lookup"><span data-stu-id="e38b8-462">Non-specific</span></span> | <span data-ttu-id="e38b8-463">*No admitido*</span><span class="sxs-lookup"><span data-stu-id="e38b8-463">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="e38b8-464">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="e38b8-464">Earning codes</span></span>

<span data-ttu-id="e38b8-465">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="e38b8-465">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="e38b8-466">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="e38b8-466">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="e38b8-467">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="e38b8-467">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="e38b8-468">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="e38b8-468">Supported frequencies</span></span>

- <span data-ttu-id="e38b8-469">Todas</span><span class="sxs-lookup"><span data-stu-id="e38b8-469">All</span></span>
- <span data-ttu-id="e38b8-470">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="e38b8-470">EVERYPAY</span></span>
- <span data-ttu-id="e38b8-471">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="e38b8-471">EACHPAYPERIOD</span></span>
- <span data-ttu-id="e38b8-472">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="e38b8-472">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="e38b8-473">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="e38b8-473">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="e38b8-474">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-474">1OFMTH</span></span>
- <span data-ttu-id="e38b8-475">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-475">LASTOFMTH</span></span>
- <span data-ttu-id="e38b8-476">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-476">2OFMTH</span></span>
- <span data-ttu-id="e38b8-477">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-477">3OFMTH</span></span>
- <span data-ttu-id="e38b8-478">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-478">4OFMTH</span></span>
- <span data-ttu-id="e38b8-479">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-479">5OFMTH</span></span>
- <span data-ttu-id="e38b8-480">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-480">1N2OFMTH</span></span>
- <span data-ttu-id="e38b8-481">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-481">3N4OFMTH</span></span>
- <span data-ttu-id="e38b8-482">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-482">1N3OFMTH</span></span>
- <span data-ttu-id="e38b8-483">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-483">1N4OFMTH</span></span>
- <span data-ttu-id="e38b8-484">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-484">2N3OFMTH</span></span>
- <span data-ttu-id="e38b8-485">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-485">2N4OFMTH</span></span>
- <span data-ttu-id="e38b8-486">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-486">1N2N3OFMTH</span></span>
- <span data-ttu-id="e38b8-487">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-487">1N2N4OFMTH</span></span>
- <span data-ttu-id="e38b8-488">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-488">1N3N4OFMTH</span></span>
- <span data-ttu-id="e38b8-489">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-489">2N3N4OFMTH</span></span>
- <span data-ttu-id="e38b8-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="e38b8-491">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="e38b8-491">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="e38b8-492">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="e38b8-492">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="e38b8-493">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="e38b8-493">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="e38b8-494">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="e38b8-494">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="e38b8-495">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="e38b8-495">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="e38b8-496">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="e38b8-496">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="e38b8-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="e38b8-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="e38b8-498">Direcciones</span><span class="sxs-lookup"><span data-stu-id="e38b8-498">Addresses</span></span>

<span data-ttu-id="e38b8-499">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="e38b8-499">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="e38b8-500">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-500">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="e38b8-501">Talent</span><span class="sxs-lookup"><span data-stu-id="e38b8-501">Talent</span></span>          | <span data-ttu-id="e38b8-502">Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-502">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="e38b8-503">País/región</span><span class="sxs-lookup"><span data-stu-id="e38b8-503">Country/Region</span></span>  | <span data-ttu-id="e38b8-504">Código de país</span><span class="sxs-lookup"><span data-stu-id="e38b8-504">Country Code</span></span>          |
| <span data-ttu-id="e38b8-505">Código postal</span><span class="sxs-lookup"><span data-stu-id="e38b8-505">Zip/Postal Code</span></span> | <span data-ttu-id="e38b8-506">Código postal</span><span class="sxs-lookup"><span data-stu-id="e38b8-506">Postal Code</span></span>           |
| <span data-ttu-id="e38b8-507">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="e38b8-507">State</span></span>           | <span data-ttu-id="e38b8-508">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="e38b8-508">State Code</span></span>            |
| <span data-ttu-id="e38b8-509">Población</span><span class="sxs-lookup"><span data-stu-id="e38b8-509">City</span></span>            | <span data-ttu-id="e38b8-510">Población</span><span class="sxs-lookup"><span data-stu-id="e38b8-510">City</span></span>                  |
| <span data-ttu-id="e38b8-511">Comarca</span><span class="sxs-lookup"><span data-stu-id="e38b8-511">County</span></span>          | <span data-ttu-id="e38b8-512">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-512">County (Municipality)</span></span> |
| <span data-ttu-id="e38b8-513">Calle</span><span class="sxs-lookup"><span data-stu-id="e38b8-513">Street</span></span>          | <span data-ttu-id="e38b8-514">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="e38b8-514">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="e38b8-515">Regiones de impuestos</span><span class="sxs-lookup"><span data-stu-id="e38b8-515">Tax regions</span></span>

<span data-ttu-id="e38b8-516">Las regiones de impuestos se usan para determinar los impuestos correspondientes que se deben aplicar durante la generación de nómina.</span><span class="sxs-lookup"><span data-stu-id="e38b8-516">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="e38b8-517">Las regiones de impuestos se asignan a Dayforce como direcciones de ubicación.</span><span class="sxs-lookup"><span data-stu-id="e38b8-517">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="e38b8-518">La región de impuestos predeterminada se debe asociar al puesto activo del trabajador.</span><span class="sxs-lookup"><span data-stu-id="e38b8-518">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="e38b8-519">Región de impuestos (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-519">Tax region (required)</span></span>
- <span data-ttu-id="e38b8-520">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-520">Country/Region (required)</span></span>
- <span data-ttu-id="e38b8-521">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-521">State (required)</span></span>
- <span data-ttu-id="e38b8-522">Comarca</span><span class="sxs-lookup"><span data-stu-id="e38b8-522">County</span></span> 
- <span data-ttu-id="e38b8-523">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-523">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="e38b8-524">Configurar los datos para generar nóminas en México</span><span class="sxs-lookup"><span data-stu-id="e38b8-524">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="e38b8-525">Si va a generar el sueldo de los empleados en México, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="e38b8-525">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="e38b8-526">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="e38b8-526">Departments are required on positions.</span></span>
- <span data-ttu-id="e38b8-527">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e38b8-527">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="e38b8-528">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="e38b8-528">Job types</span></span>

<span data-ttu-id="e38b8-529">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="e38b8-529">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="e38b8-530">Los tipos de trabajo son obligatorios para procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="e38b8-530">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="e38b8-531">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="e38b8-531">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="e38b8-532">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-532">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="e38b8-533">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="e38b8-533">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="e38b8-534">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e38b8-534">Job type</span></span>   | <span data-ttu-id="e38b8-535">Descripción</span><span class="sxs-lookup"><span data-stu-id="e38b8-535">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="e38b8-536">Por hora</span><span class="sxs-lookup"><span data-stu-id="e38b8-536">Hourly</span></span>     | <span data-ttu-id="e38b8-537">MX Por hora</span><span class="sxs-lookup"><span data-stu-id="e38b8-537">MX Hourly</span></span>   |
| <span data-ttu-id="e38b8-538">Asalariado</span><span class="sxs-lookup"><span data-stu-id="e38b8-538">Salaried</span></span>   | <span data-ttu-id="e38b8-539">MX Asalariado</span><span class="sxs-lookup"><span data-stu-id="e38b8-539">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="e38b8-540">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="e38b8-540">Position types</span></span> 

<span data-ttu-id="e38b8-541">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="e38b8-541">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="e38b8-542">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="e38b8-542">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="e38b8-543">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="e38b8-543">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="e38b8-544">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="e38b8-544">Position type</span></span>   | <span data-ttu-id="e38b8-545">Descripción</span><span class="sxs-lookup"><span data-stu-id="e38b8-545">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="e38b8-546">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="e38b8-546">Full-time</span></span>       | <span data-ttu-id="e38b8-547">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="e38b8-547">Full time employee</span></span> |
| <span data-ttu-id="e38b8-548">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="e38b8-548">Part-time</span></span>       | <span data-ttu-id="e38b8-549">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="e38b8-549">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="e38b8-550">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="e38b8-550">Reason codes</span></span>

<span data-ttu-id="e38b8-551">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-551">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="e38b8-552">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="e38b8-552">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="e38b8-553">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="e38b8-553">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="e38b8-554">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="e38b8-554">Reason code</span></span>            | <span data-ttu-id="e38b8-555">Descripción</span><span class="sxs-lookup"><span data-stu-id="e38b8-555">Description</span></span>                    | <span data-ttu-id="e38b8-556">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="e38b8-556">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="e38b8-557">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="e38b8-557">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="e38b8-558">Salida antes de la primera nómina</span><span class="sxs-lookup"><span data-stu-id="e38b8-558">Departure before first payroll</span></span> | <span data-ttu-id="e38b8-559">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-559">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-560">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="e38b8-560">RESIGNATION</span></span>            | <span data-ttu-id="e38b8-561">Dimisión</span><span class="sxs-lookup"><span data-stu-id="e38b8-561">Resignation</span></span>                    | <span data-ttu-id="e38b8-562">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-562">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-563">PENSION</span><span class="sxs-lookup"><span data-stu-id="e38b8-563">PENSION</span></span>                | <span data-ttu-id="e38b8-564">Pensión</span><span class="sxs-lookup"><span data-stu-id="e38b8-564">Pension</span></span>                        | <span data-ttu-id="e38b8-565">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-565">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-566">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="e38b8-566">TERMINATION</span></span>            | <span data-ttu-id="e38b8-567">Finalización</span><span class="sxs-lookup"><span data-stu-id="e38b8-567">Termination</span></span>                    | <span data-ttu-id="e38b8-568">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-568">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-569">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="e38b8-569">RETIREMENT</span></span>             | <span data-ttu-id="e38b8-570">Jubilación</span><span class="sxs-lookup"><span data-stu-id="e38b8-570">Retirement</span></span>                     | <span data-ttu-id="e38b8-571">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-571">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-572">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="e38b8-572">ABSENTEE</span></span>               | <span data-ttu-id="e38b8-573">Ausente</span><span class="sxs-lookup"><span data-stu-id="e38b8-573">Absentee</span></span>                       | <span data-ttu-id="e38b8-574">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-574">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-575">OTHER</span><span class="sxs-lookup"><span data-stu-id="e38b8-575">OTHER</span></span>                  | <span data-ttu-id="e38b8-576">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="e38b8-576">Other Reasons</span></span>                  | <span data-ttu-id="e38b8-577">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-577">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-578">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="e38b8-578">CLOSURE</span></span>                | <span data-ttu-id="e38b8-579">Cierre de operaciones</span><span class="sxs-lookup"><span data-stu-id="e38b8-579">Business Closure</span></span>               | <span data-ttu-id="e38b8-580">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-580">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-581">MUERTE</span><span class="sxs-lookup"><span data-stu-id="e38b8-581">DEATH</span></span>                  | <span data-ttu-id="e38b8-582">Muerte</span><span class="sxs-lookup"><span data-stu-id="e38b8-582">Death</span></span>                          | <span data-ttu-id="e38b8-583">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-583">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-584">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="e38b8-584">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="e38b8-585">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="e38b8-585">Leave of Absence</span></span>               | <span data-ttu-id="e38b8-586">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-586">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-587">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="e38b8-587">CONTRACTEND</span></span>            | <span data-ttu-id="e38b8-588">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="e38b8-588">End of Contract</span></span>                | <span data-ttu-id="e38b8-589">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="e38b8-589">Terminate worker</span></span>     |
| <span data-ttu-id="e38b8-590">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="e38b8-590">SALARYCHANGE</span></span>           | <span data-ttu-id="e38b8-591">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="e38b8-591">Change of Salary</span></span>               | <span data-ttu-id="e38b8-592">Compensación</span><span class="sxs-lookup"><span data-stu-id="e38b8-592">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="e38b8-593">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="e38b8-593">Terms of employment</span></span>

<span data-ttu-id="e38b8-594">Las condiciones laborales se usan para crear categorías de condiciones laborales.</span><span class="sxs-lookup"><span data-stu-id="e38b8-594">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="e38b8-595">Las condiciones se asignan a Dayforce como valores de indicador de empleo.</span><span class="sxs-lookup"><span data-stu-id="e38b8-595">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="e38b8-596">Las siguientes condiciones laborales y descripciones son obligatorias.</span><span class="sxs-lookup"><span data-stu-id="e38b8-596">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="e38b8-597">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="e38b8-597">Terms of employment</span></span>   | <span data-ttu-id="e38b8-598">Descripción</span><span class="sxs-lookup"><span data-stu-id="e38b8-598">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="e38b8-599">Normal</span><span class="sxs-lookup"><span data-stu-id="e38b8-599">Regular</span></span>               | <span data-ttu-id="e38b8-600">Normal</span><span class="sxs-lookup"><span data-stu-id="e38b8-600">Regular</span></span>     |
| <span data-ttu-id="e38b8-601">Directo</span><span class="sxs-lookup"><span data-stu-id="e38b8-601">Direct</span></span>                | <span data-ttu-id="e38b8-602">Directo</span><span class="sxs-lookup"><span data-stu-id="e38b8-602">Direct</span></span>      |
| <span data-ttu-id="e38b8-603">Prácticas</span><span class="sxs-lookup"><span data-stu-id="e38b8-603">Internship</span></span>            | <span data-ttu-id="e38b8-604">Prácticas</span><span class="sxs-lookup"><span data-stu-id="e38b8-604">Internship</span></span>  |
| <span data-ttu-id="e38b8-605">Permanente</span><span class="sxs-lookup"><span data-stu-id="e38b8-605">Permanent</span></span>             | <span data-ttu-id="e38b8-606">Permanente</span><span class="sxs-lookup"><span data-stu-id="e38b8-606">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="e38b8-607">Estado civil</span><span class="sxs-lookup"><span data-stu-id="e38b8-607">Marital status</span></span>

<span data-ttu-id="e38b8-608">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="e38b8-608">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="e38b8-609">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-609">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="e38b8-610">Talent</span><span class="sxs-lookup"><span data-stu-id="e38b8-610">Talent</span></span>                 | <span data-ttu-id="e38b8-611">Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-611">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="e38b8-612">Casado/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-612">Married</span></span>                | <span data-ttu-id="e38b8-613">Casado/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-613">Married</span></span>                   |
| <span data-ttu-id="e38b8-614">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-614">Single</span></span>                 | <span data-ttu-id="e38b8-615">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-615">Single</span></span>                    |
| <span data-ttu-id="e38b8-616">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-616">Widowed</span></span>                | <span data-ttu-id="e38b8-617">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-617">Widowed</span></span>                   |
| <span data-ttu-id="e38b8-618">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-618">Divorced</span></span>               | <span data-ttu-id="e38b8-619">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="e38b8-619">Divorced</span></span>                  |
| <span data-ttu-id="e38b8-620">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="e38b8-620">Registered Partnership</span></span> | <span data-ttu-id="e38b8-621">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="e38b8-621">Domestic Partnership</span></span>      |
| <span data-ttu-id="e38b8-622">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="e38b8-622">None</span></span>                   | <span data-ttu-id="e38b8-623">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="e38b8-623">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="e38b8-624">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="e38b8-624">Cohabiting</span></span>             | <span data-ttu-id="e38b8-625">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="e38b8-625">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="e38b8-626">Género</span><span class="sxs-lookup"><span data-stu-id="e38b8-626">Gender</span></span>

<span data-ttu-id="e38b8-627">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="e38b8-627">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="e38b8-628">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-628">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="e38b8-629">Talent</span><span class="sxs-lookup"><span data-stu-id="e38b8-629">Talent</span></span>       | <span data-ttu-id="e38b8-630">Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-630">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="e38b8-631">Hombre</span><span class="sxs-lookup"><span data-stu-id="e38b8-631">Male</span></span>         | <span data-ttu-id="e38b8-632">Hombre</span><span class="sxs-lookup"><span data-stu-id="e38b8-632">Male</span></span>                      |
| <span data-ttu-id="e38b8-633">Mujer</span><span class="sxs-lookup"><span data-stu-id="e38b8-633">Female</span></span>       | <span data-ttu-id="e38b8-634">Mujer</span><span class="sxs-lookup"><span data-stu-id="e38b8-634">Female</span></span>                    |
| <span data-ttu-id="e38b8-635">No específico</span><span class="sxs-lookup"><span data-stu-id="e38b8-635">Non-specific</span></span> | <span data-ttu-id="e38b8-636">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="e38b8-636">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="e38b8-637">Método de pago</span><span class="sxs-lookup"><span data-stu-id="e38b8-637">Payment method</span></span>

<span data-ttu-id="e38b8-638">Los métodos de pago ofrecen al empleado y la empresa una forma de describir cómo se pagará a los empleados.</span><span class="sxs-lookup"><span data-stu-id="e38b8-638">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="e38b8-639">Los métodos de pago se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="e38b8-639">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="e38b8-640">En la siguiente tabla se muestra cómo los métodos de pago se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-640">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="e38b8-641">Talent</span><span class="sxs-lookup"><span data-stu-id="e38b8-641">Talent</span></span>             | <span data-ttu-id="e38b8-642">Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-642">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="e38b8-643">Efectivo</span><span class="sxs-lookup"><span data-stu-id="e38b8-643">Cash</span></span>               | <span data-ttu-id="e38b8-644">Efectivo</span><span class="sxs-lookup"><span data-stu-id="e38b8-644">Cash</span></span>                      |
| <span data-ttu-id="e38b8-645">Pago electrónico</span><span class="sxs-lookup"><span data-stu-id="e38b8-645">Electronic Payment</span></span> | <span data-ttu-id="e38b8-646">Transferir</span><span class="sxs-lookup"><span data-stu-id="e38b8-646">Transfer</span></span>                  |
| <span data-ttu-id="e38b8-647">Comprobación</span><span class="sxs-lookup"><span data-stu-id="e38b8-647">Check</span></span>              | <span data-ttu-id="e38b8-648">Cheque</span><span class="sxs-lookup"><span data-stu-id="e38b8-648">Cheque</span></span>                    |
| <span data-ttu-id="e38b8-649">Efecto bancario</span><span class="sxs-lookup"><span data-stu-id="e38b8-649">Bank Draft</span></span>         | <span data-ttu-id="e38b8-650">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="e38b8-650">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="e38b8-651">Otras</span><span class="sxs-lookup"><span data-stu-id="e38b8-651">Other</span></span>              | <span data-ttu-id="e38b8-652">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="e38b8-652">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="e38b8-653">Tipo de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="e38b8-653">Bank account type</span></span>

<span data-ttu-id="e38b8-654">Los tipos de cuenta bancaria se usan para los pagos electrónicos a los empleados.</span><span class="sxs-lookup"><span data-stu-id="e38b8-654">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="e38b8-655">Los tipos de cuenta bancaria se asignan a Dayforce como información de cuenta de transferencia.</span><span class="sxs-lookup"><span data-stu-id="e38b8-655">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="e38b8-656">Los tipos de cuenta bancaria se convierten, según proceda, en los valores aceptados en la integración.</span><span class="sxs-lookup"><span data-stu-id="e38b8-656">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="e38b8-657">Talent</span><span class="sxs-lookup"><span data-stu-id="e38b8-657">Talent</span></span>            | <span data-ttu-id="e38b8-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-658">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="e38b8-659">Cuenta corriente</span><span class="sxs-lookup"><span data-stu-id="e38b8-659">Checking Account</span></span>  | <span data-ttu-id="e38b8-660">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="e38b8-660">CheckingAccount</span></span>           |
| <span data-ttu-id="e38b8-661">Cuenta de nómina</span><span class="sxs-lookup"><span data-stu-id="e38b8-661">Payroll Account</span></span>   | <span data-ttu-id="e38b8-662">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="e38b8-662">PayrollAccount</span></span>            |
| <span data-ttu-id="e38b8-663">Cuenta de ahorros</span><span class="sxs-lookup"><span data-stu-id="e38b8-663">Savings Account</span></span>   | <span data-ttu-id="e38b8-664">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="e38b8-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="e38b8-665">Cuenta de BankGirot</span><span class="sxs-lookup"><span data-stu-id="e38b8-665">BankGirot account</span></span> | <span data-ttu-id="e38b8-666">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="e38b8-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="e38b8-667">Cuenta de PlusGirot</span><span class="sxs-lookup"><span data-stu-id="e38b8-667">PlusGirot account</span></span> | <span data-ttu-id="e38b8-668">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="e38b8-668">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="e38b8-669">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="e38b8-669">Earning codes</span></span>

<span data-ttu-id="e38b8-670">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="e38b8-670">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="e38b8-671">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="e38b8-671">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="e38b8-672">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="e38b8-672">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="e38b8-673">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="e38b8-673">Supported frequencies</span></span>

- <span data-ttu-id="e38b8-674">Todas</span><span class="sxs-lookup"><span data-stu-id="e38b8-674">All</span></span>
- <span data-ttu-id="e38b8-675">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="e38b8-675">EVERYPAY</span></span>
- <span data-ttu-id="e38b8-676">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="e38b8-676">EACHPAYPERIOD</span></span>
- <span data-ttu-id="e38b8-677">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="e38b8-677">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="e38b8-678">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="e38b8-678">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="e38b8-679">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-679">1OFMTH</span></span>
- <span data-ttu-id="e38b8-680">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-680">LASTOFMTH</span></span>
- <span data-ttu-id="e38b8-681">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-681">2OFMTH</span></span>
- <span data-ttu-id="e38b8-682">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-682">3OFMTH</span></span>
- <span data-ttu-id="e38b8-683">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-683">4OFMTH</span></span>
- <span data-ttu-id="e38b8-684">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-684">5OFMTH</span></span>
- <span data-ttu-id="e38b8-685">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-685">1N2OFMTH</span></span>
- <span data-ttu-id="e38b8-686">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-686">3N4OFMTH</span></span>
- <span data-ttu-id="e38b8-687">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-687">1N3OFMTH</span></span>
- <span data-ttu-id="e38b8-688">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-688">1N4OFMTH</span></span>
- <span data-ttu-id="e38b8-689">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-689">2N3OFMTH</span></span>
- <span data-ttu-id="e38b8-690">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-690">2N4OFMTH</span></span>
- <span data-ttu-id="e38b8-691">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-691">1N2N3OFMTH</span></span>
- <span data-ttu-id="e38b8-692">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-692">1N2N4OFMTH</span></span>
- <span data-ttu-id="e38b8-693">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-693">1N3N4OFMTH</span></span>
- <span data-ttu-id="e38b8-694">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-694">2N3N4OFMTH</span></span>
- <span data-ttu-id="e38b8-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="e38b8-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="e38b8-696">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="e38b8-696">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="e38b8-697">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="e38b8-697">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="e38b8-698">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="e38b8-698">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="e38b8-699">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="e38b8-699">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="e38b8-700">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="e38b8-700">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="e38b8-701">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="e38b8-701">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="e38b8-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="e38b8-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="e38b8-703">Direcciones</span><span class="sxs-lookup"><span data-stu-id="e38b8-703">Addresses</span></span>

<span data-ttu-id="e38b8-704">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="e38b8-704">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="e38b8-705">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-705">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="e38b8-706">Talent</span><span class="sxs-lookup"><span data-stu-id="e38b8-706">Talent</span></span>              | <span data-ttu-id="e38b8-707">Dayforce</span><span class="sxs-lookup"><span data-stu-id="e38b8-707">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="e38b8-708">País/región</span><span class="sxs-lookup"><span data-stu-id="e38b8-708">Country/Region</span></span>      | <span data-ttu-id="e38b8-709">Código de país</span><span class="sxs-lookup"><span data-stu-id="e38b8-709">Country Code</span></span>          |
| <span data-ttu-id="e38b8-710">Código postal</span><span class="sxs-lookup"><span data-stu-id="e38b8-710">Zip/Postal Code</span></span>     | <span data-ttu-id="e38b8-711">Código postal</span><span class="sxs-lookup"><span data-stu-id="e38b8-711">Postal Code</span></span>           |
| <span data-ttu-id="e38b8-712">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="e38b8-712">State</span></span>               | <span data-ttu-id="e38b8-713">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="e38b8-713">State Code</span></span>            |
| <span data-ttu-id="e38b8-714">Población</span><span class="sxs-lookup"><span data-stu-id="e38b8-714">City</span></span>                | <span data-ttu-id="e38b8-715">Población</span><span class="sxs-lookup"><span data-stu-id="e38b8-715">City</span></span>                  |
| <span data-ttu-id="e38b8-716">Comarca</span><span class="sxs-lookup"><span data-stu-id="e38b8-716">County</span></span>              | <span data-ttu-id="e38b8-717">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="e38b8-717">County (Municipality)</span></span> |
| <span data-ttu-id="e38b8-718">Calle</span><span class="sxs-lookup"><span data-stu-id="e38b8-718">Street</span></span>              | <span data-ttu-id="e38b8-719">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="e38b8-719">Address Line 1</span></span>        |
| <span data-ttu-id="e38b8-720">Número de calle</span><span class="sxs-lookup"><span data-stu-id="e38b8-720">Street Number</span></span>       | <span data-ttu-id="e38b8-721">Línea de dirección 2</span><span class="sxs-lookup"><span data-stu-id="e38b8-721">Address Line 2</span></span>        |
| <span data-ttu-id="e38b8-722">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="e38b8-722">Building Complement</span></span> | <span data-ttu-id="e38b8-723">Línea de dirección 5</span><span class="sxs-lookup"><span data-stu-id="e38b8-723">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="e38b8-724">Número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="e38b8-724">Passport number</span></span>

<span data-ttu-id="e38b8-725">Los empleados pueden declarar la información del pasaporte.</span><span class="sxs-lookup"><span data-stu-id="e38b8-725">Employees can declare passport information.</span></span> <span data-ttu-id="e38b8-726">Esta información es del tipo de identificación **Pasaporte** y se integra en Dayforce como parte de la información específica de México de un empleado.</span><span class="sxs-lookup"><span data-stu-id="e38b8-726">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="e38b8-727">Tipo de identificación = "Pasaporte"</span><span class="sxs-lookup"><span data-stu-id="e38b8-727">Identification Type = "Passport"</span></span>
- <span data-ttu-id="e38b8-728">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="e38b8-728">Issued Date</span></span>
- <span data-ttu-id="e38b8-729">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="e38b8-729">Expiration Date</span></span>

<span data-ttu-id="e38b8-730">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Pasaporte**.</span><span class="sxs-lookup"><span data-stu-id="e38b8-730">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="e38b8-731">Sin embargo, solo la entrada de pasaporte activa actual se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-731">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="e38b8-732">Si todas las entradas de pasaporte han caducado, el pasaporte que se emitió más recientemente se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="e38b8-732">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>

