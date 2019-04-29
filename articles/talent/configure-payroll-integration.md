---
title: Configurar la integración de nóminas entre Talent y Dayforce
description: Este tema explica cómo configurar la integración entre Microsoft Dynamics 365 for Talent y Ceridian Dayforce de modo que pueda procesar un período de pago.
author: andreabichsel
manager: AnnBe
ms.date: 03/26/2019
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
ms.openlocfilehash: 9a88bf61dbb12520b555ceb7363b1c646d95386e
ms.sourcegitcommit: 204e4554e409c39fbbf7b273ad138ce2809931a8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "898453"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="6381a-103">Configurar la integración de nóminas entre Talent y Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6381a-104">La integración entre Microsoft Dynamics 365 for Talent y Ceridian Dayforce se basa en varios pasos de configuración que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="6381a-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="6381a-105">Debe configurar la integración en Talent y Dayforce para poder procesar un período de pago.</span><span class="sxs-lookup"><span data-stu-id="6381a-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="6381a-106">Cuando se utiliza un servicio como Dayforce para completar períodos de pago, debe habilitar la integración en Talent.</span><span class="sxs-lookup"><span data-stu-id="6381a-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="6381a-107">La integración necesita los datos específicos de Talent.</span><span class="sxs-lookup"><span data-stu-id="6381a-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="6381a-108">Por lo tanto, debe comprobar que los datos que se asignen a Dayforce se hayan configurado en Talent de una forma que admita la integración.</span><span class="sxs-lookup"><span data-stu-id="6381a-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="6381a-109">La integración utiliza las amplias categorías de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6381a-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="6381a-110">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="6381a-110">Human resources data</span></span>
- <span data-ttu-id="6381a-111">Catos de compensación</span><span class="sxs-lookup"><span data-stu-id="6381a-111">Compensation data</span></span>
- <span data-ttu-id="6381a-112">Datos de nómina, como ciclos de pago, períodos de sueldo, y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="6381a-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="6381a-113">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="6381a-113">Worker data</span></span>

<span data-ttu-id="6381a-114">Este tema describe los pasos que debe seguir para habilitar la integración.</span><span class="sxs-lookup"><span data-stu-id="6381a-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="6381a-115">También explica los tipos de datos y los detalles de configuración que requiere la integración.</span><span class="sxs-lookup"><span data-stu-id="6381a-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="6381a-116">Habilitar la integración</span><span class="sxs-lookup"><span data-stu-id="6381a-116">Enable the integration</span></span>

<span data-ttu-id="6381a-117">En Talent, debe activar la integración y especificar información de configuración para conectarse a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="6381a-118">Si desea que la transacción de contabilidad general que se genera se importe en Microsoft Dynamics 365 for Finance and Operations, también debe configurar una cuenta de almacenamiento de Microsoft Azure y especificar la cadena de conexión Azure Storage en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6381a-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="6381a-119">Para activar la integración en Talent, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6381a-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="6381a-120">En la página **Administración del sistema** , seleccione **Configuración de la integración**.</span><span class="sxs-lookup"><span data-stu-id="6381a-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="6381a-121">Permite especificar el extremo del Protocolo de transferencia de archivos (FTP) y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="6381a-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="6381a-122">Escriba el nombre de usuario y contraseña del usuario que accederá al extremo y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="6381a-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="6381a-123">Pruebe la conexión, como sea necesario, y establezca la opción **Habilitar la integración de nómina** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6381a-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="6381a-124">Cuando está activada la integración, se crean el paquete y los archivos de exportación de datos, y se establece la frecuencia.</span><span class="sxs-lookup"><span data-stu-id="6381a-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="6381a-125">Puede cambiar esta frecuencia como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6381a-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="6381a-126">Para obtener más información acerca de las cuentas de almacenamiento de Azure y las cadenas de conexión de Azure Storage, consulte los temas de Azure siguientes:</span><span class="sxs-lookup"><span data-stu-id="6381a-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="6381a-127">Acerca de las cuentas de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="6381a-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="6381a-128">Configurar las cadenas de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="6381a-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="6381a-129">Configurar los datos</span><span class="sxs-lookup"><span data-stu-id="6381a-129">Configure your data</span></span> 

<span data-ttu-id="6381a-130">Para procesar las nóminas, debe configurar los datos de recursos humanos en Talent.</span><span class="sxs-lookup"><span data-stu-id="6381a-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="6381a-131">Debe configurar datos de organización, como los trabajos y los puestos, así como las prestaciones y la información de compensación.</span><span class="sxs-lookup"><span data-stu-id="6381a-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="6381a-132">Esta información proporciona la información de empleo, pago y deducciones que se necesita para producir el sueldo del empleado.</span><span class="sxs-lookup"><span data-stu-id="6381a-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="6381a-133">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="6381a-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="6381a-134">Beneficios</span><span class="sxs-lookup"><span data-stu-id="6381a-134">Benefits</span></span> 

<span data-ttu-id="6381a-135">Recursos humanos ofrece herramientas para la configuración y el mantenimiento de prestaciones, deducciones y los planes de compensación de los trabajadores que una organización ofrece o procesa para sus trabajadores.</span><span class="sxs-lookup"><span data-stu-id="6381a-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="6381a-136">Al crear las prestaciones, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="6381a-137">Planes de prestaciones</span><span class="sxs-lookup"><span data-stu-id="6381a-137">Benefit plans</span></span>

- <span data-ttu-id="6381a-138">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-138">Plan (required)</span></span>
- <span data-ttu-id="6381a-139">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-139">Type (required)</span></span>
- <span data-ttu-id="6381a-140">Impacto de nómina (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-140">Payroll impact (required)</span></span>
- <span data-ttu-id="6381a-141">Recuperar atrasos</span><span class="sxs-lookup"><span data-stu-id="6381a-141">Recover arrears</span></span>
- <span data-ttu-id="6381a-142">Método de deducción</span><span class="sxs-lookup"><span data-stu-id="6381a-142">Deduction method</span></span>
- <span data-ttu-id="6381a-143">Prioridad de deducción</span><span class="sxs-lookup"><span data-stu-id="6381a-143">Deduction priority</span></span>
- <span data-ttu-id="6381a-144">Período de límite</span><span class="sxs-lookup"><span data-stu-id="6381a-144">Limit period</span></span>
- <span data-ttu-id="6381a-145">Importe límite</span><span class="sxs-lookup"><span data-stu-id="6381a-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="6381a-146">Beneficios</span><span class="sxs-lookup"><span data-stu-id="6381a-146">Benefits</span></span>

- <span data-ttu-id="6381a-147">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-147">Plan (required)</span></span>
- <span data-ttu-id="6381a-148">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-148">Type (required)</span></span>
- <span data-ttu-id="6381a-149">Opción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-149">Option (required)</span></span>
- <span data-ttu-id="6381a-150">Identificador de prestación (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-150">Benefit ID (required)</span></span>
- <span data-ttu-id="6381a-151">Frecuencia</span><span class="sxs-lookup"><span data-stu-id="6381a-151">Frequency</span></span>
- <span data-ttu-id="6381a-152">Base</span><span class="sxs-lookup"><span data-stu-id="6381a-152">Basis</span></span>
- <span data-ttu-id="6381a-153">Importe o índice</span><span class="sxs-lookup"><span data-stu-id="6381a-153">Amount or rate</span></span>
- <span data-ttu-id="6381a-154">Código de ganancias</span><span class="sxs-lookup"><span data-stu-id="6381a-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="6381a-155">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="6381a-155">Supported frequencies</span></span> 

- <span data-ttu-id="6381a-156">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="6381a-156">Weekly</span></span>
- <span data-ttu-id="6381a-157">Quincenal</span><span class="sxs-lookup"><span data-stu-id="6381a-157">Bi-weekly</span></span>
- <span data-ttu-id="6381a-158">Bimensual</span><span class="sxs-lookup"><span data-stu-id="6381a-158">Semi-monthly</span></span>
- <span data-ttu-id="6381a-159">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="6381a-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="6381a-160">Bases admitidas</span><span class="sxs-lookup"><span data-stu-id="6381a-160">Supported bases</span></span> 

- <span data-ttu-id="6381a-161">Importe fijo</span><span class="sxs-lookup"><span data-stu-id="6381a-161">Fixed amount</span></span>
- <span data-ttu-id="6381a-162">Porcentaje de ganancias</span><span class="sxs-lookup"><span data-stu-id="6381a-162">Percent of earnings</span></span>
- <span data-ttu-id="6381a-163">Horas productivas</span><span class="sxs-lookup"><span data-stu-id="6381a-163">Productive hours</span></span>

<span data-ttu-id="6381a-164">Dayforce crea las deducciones siguientes, según el impacto de nómina que hay definido en el plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="6381a-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="6381a-165">Selección en Talent</span><span class="sxs-lookup"><span data-stu-id="6381a-165">Selection in Talent</span></span>        | <span data-ttu-id="6381a-166">Resultado en Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="6381a-167">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="6381a-167">None</span></span>                       | <span data-ttu-id="6381a-168">No se crea ninguna deducción.</span><span class="sxs-lookup"><span data-stu-id="6381a-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="6381a-169">Solo deducción</span><span class="sxs-lookup"><span data-stu-id="6381a-169">Deduction only</span></span>             | <span data-ttu-id="6381a-170">Se crea una deducción del empleado.</span><span class="sxs-lookup"><span data-stu-id="6381a-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="6381a-171">Solo contribución</span><span class="sxs-lookup"><span data-stu-id="6381a-171">Contribution only</span></span>          | <span data-ttu-id="6381a-172">Se crea una deducción del empresario.</span><span class="sxs-lookup"><span data-stu-id="6381a-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="6381a-173">Deducción y contribución</span><span class="sxs-lookup"><span data-stu-id="6381a-173">Deduction and contribution</span></span> | <span data-ttu-id="6381a-174">Se crean las deducciones del empleado y del empresario.</span><span class="sxs-lookup"><span data-stu-id="6381a-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="6381a-175">Para obtener más información sobre cómo definir y administrar un programa de prestaciones, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6381a-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="6381a-176">Proporcionar un programa de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="6381a-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="6381a-177">Crear una nueva prestación</span><span class="sxs-lookup"><span data-stu-id="6381a-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="6381a-178">Definir reglas y directivas de idoneidad para prestaciones</span><span class="sxs-lookup"><span data-stu-id="6381a-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="6381a-179">Inscribir y quitar prestaciones para trabajadores</span><span class="sxs-lookup"><span data-stu-id="6381a-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="6381a-180">Compensación</span><span class="sxs-lookup"><span data-stu-id="6381a-180">Compensation</span></span> 

<span data-ttu-id="6381a-181">La gestión de compensaciones se usa para controlar la entrega de salarios base y primas.</span><span class="sxs-lookup"><span data-stu-id="6381a-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="6381a-182">El sueldo base fijo de un empleado y los aumentos por méritos se controlan mediante planes de compensación fijos.</span><span class="sxs-lookup"><span data-stu-id="6381a-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="6381a-183">El pago de incentivos, como los pagos de bonificación, las primas por rendimiento, las acciones y las concesiones, así como también las primas ocasionales, se controlan a través de planes de compensación variable.</span><span class="sxs-lookup"><span data-stu-id="6381a-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="6381a-184">Dayforce utiliza la información de compensación para calcular la tarifa por hora o anual de un empleado.</span><span class="sxs-lookup"><span data-stu-id="6381a-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="6381a-185">Se requieren planes de compensación fija y conversiones de índice salarial.</span><span class="sxs-lookup"><span data-stu-id="6381a-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="6381a-186">Los empleados deben estar asociados a un plan de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="6381a-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="6381a-187">Para obtener más información acerca de los panes de compensación, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6381a-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="6381a-188">Crear planes de compensación fija</span><span class="sxs-lookup"><span data-stu-id="6381a-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="6381a-189">Crear planes de compensación variable</span><span class="sxs-lookup"><span data-stu-id="6381a-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="6381a-190">Desarrollar planes y estructura de salarios o compensaciones</span><span class="sxs-lookup"><span data-stu-id="6381a-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="6381a-191">Procesar compensaciones</span><span class="sxs-lookup"><span data-stu-id="6381a-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="6381a-192">Definición del proceso de compensación y el cálculo de resultados</span><span class="sxs-lookup"><span data-stu-id="6381a-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="6381a-193">Inscribir a un empleado en un plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="6381a-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="6381a-194">Inscribir a un empleado en un plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="6381a-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="6381a-195">Trabajos</span><span class="sxs-lookup"><span data-stu-id="6381a-195">Jobs</span></span> 

<span data-ttu-id="6381a-196">Un trabajo es un conjunto de las tareas y responsabilidades que deberá cumplir la persona que realiza un trabajo.</span><span class="sxs-lookup"><span data-stu-id="6381a-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="6381a-197">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6381a-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="6381a-198">Configurar los componentes de un trabajo</span><span class="sxs-lookup"><span data-stu-id="6381a-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="6381a-199">Definir nuevos trabajos</span><span class="sxs-lookup"><span data-stu-id="6381a-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="6381a-200">Puestos</span><span class="sxs-lookup"><span data-stu-id="6381a-200">Positions</span></span>

<span data-ttu-id="6381a-201">Un puesto es un caso individual de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="6381a-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="6381a-202">Por ejemplo, el puesto "Director de ventas (Este)" es uno de los puestos asociados al trabajo "Director de ventas".</span><span class="sxs-lookup"><span data-stu-id="6381a-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="6381a-203">Un puesto existe en un departamento.</span><span class="sxs-lookup"><span data-stu-id="6381a-203">A position exists in a department.</span></span> <span data-ttu-id="6381a-204">Solo un trabajador puede asociarse solo a cada puesto.</span><span class="sxs-lookup"><span data-stu-id="6381a-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="6381a-205">Tenga en cuenta los siguientes datos y configuración al configurar los puestos:</span><span class="sxs-lookup"><span data-stu-id="6381a-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="6381a-206">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-206">Position (required)</span></span>
- <span data-ttu-id="6381a-207">Descripción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-207">Description (required)</span></span>
- <span data-ttu-id="6381a-208">Trabajo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-208">Job (required)</span></span>
- <span data-ttu-id="6381a-209">Departamento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-209">Department (required)</span></span>
- <span data-ttu-id="6381a-210">Tipo de puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-210">Position type (required)</span></span>
- <span data-ttu-id="6381a-211">Equivalente de jornada completa</span><span class="sxs-lookup"><span data-stu-id="6381a-211">Full-time equivalent</span></span>
- <span data-ttu-id="6381a-212">Horas ordinarias anuales (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="6381a-213">Pagado por la entidad jurídica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="6381a-214">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-214">Pay cycle (required)</span></span>
- <span data-ttu-id="6381a-215">Dimensión financiera predeterminada – Centro de coste (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="6381a-216">Asignación de trabajador – Trabajador, inicio de la asignación, final de la asignación, código de motivo</span><span class="sxs-lookup"><span data-stu-id="6381a-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="6381a-217">Si varios puestos en el mismo departamento están asociados al mismo trabajo, se consolidan en un solo puesto en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="6381a-218">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6381a-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="6381a-219">Organizar los recursos mediante departamentos, trabajos y puestos</span><span class="sxs-lookup"><span data-stu-id="6381a-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="6381a-220">Configurar puestos</span><span class="sxs-lookup"><span data-stu-id="6381a-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="6381a-221">Departamentos</span><span class="sxs-lookup"><span data-stu-id="6381a-221">Departments</span></span>

<span data-ttu-id="6381a-222">Un departamneto es una unidad operativa que representa una categoría o un área funcional de la organización.</span><span class="sxs-lookup"><span data-stu-id="6381a-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="6381a-223">Un departamento es responsable de un área específica de la organización, como ventas, contabilidad o recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="6381a-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="6381a-224">Puede usar departamentos para informar sobre las áreas funcionales.</span><span class="sxs-lookup"><span data-stu-id="6381a-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="6381a-225">Los departamentos pueden tener responsabilidad de pérdidas y ganancias.</span><span class="sxs-lookup"><span data-stu-id="6381a-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="6381a-226">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6381a-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="6381a-227">Crear un departamento y asociarlo a la jerarquía de departamentos</span><span class="sxs-lookup"><span data-stu-id="6381a-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="6381a-228">Definir nuevos departamentos</span><span class="sxs-lookup"><span data-stu-id="6381a-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="6381a-229">Ciclos y períodos de pago</span><span class="sxs-lookup"><span data-stu-id="6381a-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="6381a-230">Un ciclo de pago determina la frecuencia con la que se ejecuta el cálculo de nómina y los días específicos en los que se paga a los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="6381a-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="6381a-231">Por ejemplo, un ciclo de pago puede ser mensual y a los empleados se les podría pagar el último día del mes.</span><span class="sxs-lookup"><span data-stu-id="6381a-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="6381a-232">De forma alternativa, un ciclo de pago puede ser semanal y a los empleados se les podría pagar el martes después del final del período de pago.</span><span class="sxs-lookup"><span data-stu-id="6381a-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="6381a-233">Los ciclos de pago se asignan a los puestos para controlar cuándo se paga a los trabajadores en esos puestos.</span><span class="sxs-lookup"><span data-stu-id="6381a-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="6381a-234">Después de crear ciclos de pago, puede generar los períodos de pago para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="6381a-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="6381a-235">Cada período de pago incluye una fecha de pago predeterminada basada en la información que proporcione.</span><span class="sxs-lookup"><span data-stu-id="6381a-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="6381a-236">Sin embargo, puede modificar la fecha de pago predeterminada en un período de pago para permitir excepciones, por ejemplo, cuando la fecha de pago se encuentra en un día festivo.</span><span class="sxs-lookup"><span data-stu-id="6381a-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="6381a-237">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="6381a-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="6381a-238">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-238">Pay cycle (required)</span></span>
- <span data-ttu-id="6381a-239">Frecuencia del ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="6381a-240">Fecha de inicio del período (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="6381a-241">Fecha de pago predeterminado (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="6381a-242">Esta información se integra con Dayforce como grupos salariales y se separa por país o región para cada ciclo de pago.</span><span class="sxs-lookup"><span data-stu-id="6381a-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="6381a-243">Al menos se debe generar un período de sueldo antes de la integración.</span><span class="sxs-lookup"><span data-stu-id="6381a-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="6381a-244">Dayforce genera los calendarios de grupo salarial y las fechas de pago, en función de la fecha inicial del primer período de pago y la fecha de pago predeterminada que se configuran en Talent.</span><span class="sxs-lookup"><span data-stu-id="6381a-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="6381a-245">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="6381a-245">Earning codes</span></span>

<span data-ttu-id="6381a-246">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="6381a-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="6381a-247">Los códigos tienen distintos parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="6381a-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="6381a-248">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="6381a-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="6381a-249">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-249">Earning Code (required)</span></span>
- <span data-ttu-id="6381a-250">Descripción</span><span class="sxs-lookup"><span data-stu-id="6381a-250">Description</span></span>
- <span data-ttu-id="6381a-251">Unidad de medida</span><span class="sxs-lookup"><span data-stu-id="6381a-251">Unit of measure</span></span>
- <span data-ttu-id="6381a-252">Productivo</span><span class="sxs-lookup"><span data-stu-id="6381a-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="6381a-253">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="6381a-253">Worker data</span></span>

<span data-ttu-id="6381a-254">Los registros para los diferentes tipos de trabajadores que tiene son importantes para los sistemas de recursos humanos y nómina.</span><span class="sxs-lookup"><span data-stu-id="6381a-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="6381a-255">La información que se indique se puede utilizar para efectuar un seguimiento de los trabajadores y su información personal.</span><span class="sxs-lookup"><span data-stu-id="6381a-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="6381a-256">Puede mantener la información siguiente para los trabajadores:</span><span class="sxs-lookup"><span data-stu-id="6381a-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="6381a-257">**Básica**: permite mantener la información básica de un trabajador, como la información de contacto, información demográfica, información de identificación, información de familia, estado del servicio militar, información de expatriado y contactos personales y de emergencia.</span><span class="sxs-lookup"><span data-stu-id="6381a-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="6381a-258">**Empleo**: permite mantener la información sobre el empleo de un trabajador, como afiliación de la empresa u organización, asignación de puesto, fecha de inicio y finalización, idoneidad para el trabajo, condiciones de empleo, pensión, vacaciones y la información de reubicación.</span><span class="sxs-lookup"><span data-stu-id="6381a-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="6381a-259">**Bajas y ausencias**: permite mantener información sobre las ausencias de un trabajador, como calendarios de trabajo, transacciones de ausencia y configuración de ausencias.</span><span class="sxs-lookup"><span data-stu-id="6381a-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="6381a-260">**Compensación y nómina**: permite mantener la información sobre los planes de compensación y la información de nómina de un trabajador, como inscripción del plan, concesiones, desempeño, comisión, información fiscal, retiro y deducciones de sueldo.</span><span class="sxs-lookup"><span data-stu-id="6381a-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="6381a-261">Al introducir la información del trabajador, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="6381a-262">Información general</span><span class="sxs-lookup"><span data-stu-id="6381a-262">General information</span></span>

- <span data-ttu-id="6381a-263">Número de personal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-263">Personnel number (required)</span></span>
- <span data-ttu-id="6381a-264">Nombre (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-264">First name (required)</span></span>
- <span data-ttu-id="6381a-265">Apellido (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-265">Last name (required)</span></span>
- <span data-ttu-id="6381a-266">Segundo nombre</span><span class="sxs-lookup"><span data-stu-id="6381a-266">Middle name</span></span>
- <span data-ttu-id="6381a-267">Antigüedad</span><span class="sxs-lookup"><span data-stu-id="6381a-267">Seniority date</span></span>
- <span data-ttu-id="6381a-268">Conocido como</span><span class="sxs-lookup"><span data-stu-id="6381a-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="6381a-269">Información personal</span><span class="sxs-lookup"><span data-stu-id="6381a-269">Personal information</span></span>

- <span data-ttu-id="6381a-270">Estado civil (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-270">Marital status (required)</span></span>
- <span data-ttu-id="6381a-271">Fecha de nacimiento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-271">Birth date (required)</span></span>
- <span data-ttu-id="6381a-272">Sexo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-272">Gender (required)</span></span>
- <span data-ttu-id="6381a-273">Persona con discapacidades</span><span class="sxs-lookup"><span data-stu-id="6381a-273">Person with disabilities</span></span>
- <span data-ttu-id="6381a-274">País o región, nacionalidad (solo para México)</span><span class="sxs-lookup"><span data-stu-id="6381a-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="6381a-275">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="6381a-275">Address information</span></span>

- <span data-ttu-id="6381a-276">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-276">Primary (required)</span></span>
- <span data-ttu-id="6381a-277">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-277">Country/region (required)</span></span>
- <span data-ttu-id="6381a-278">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-278">Postal code (required)</span></span>
- <span data-ttu-id="6381a-279">Número de calle (obligatorio) (solo para México)</span><span class="sxs-lookup"><span data-stu-id="6381a-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="6381a-280">Complemento de edificio (solo para México)</span><span class="sxs-lookup"><span data-stu-id="6381a-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="6381a-281">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-281">City (required)</span></span>
- <span data-ttu-id="6381a-282">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-282">State (required)</span></span>
- <span data-ttu-id="6381a-283">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="6381a-284">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="6381a-284">Contact information</span></span> 

- <span data-ttu-id="6381a-285">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-285">Primary (required)</span></span>
- <span data-ttu-id="6381a-286">Número de contacto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-286">Contact number (required)</span></span>
- <span data-ttu-id="6381a-287">Extensión</span><span class="sxs-lookup"><span data-stu-id="6381a-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="6381a-288">Información de nómina y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="6381a-288">Payroll information and earning codes</span></span>

<span data-ttu-id="6381a-289">A los empleados se les pueden asignar ganancias específicas de una frecuencia determinada de pago y tener un método de pago preferido.</span><span class="sxs-lookup"><span data-stu-id="6381a-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="6381a-290">Los siguientes campos se utilizan en Dayforce para ayudar a garantizar que se usen las preferencias y valores.</span><span class="sxs-lookup"><span data-stu-id="6381a-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="6381a-291">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="6381a-291">Earning codes</span></span>

- <span data-ttu-id="6381a-292">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-292">Position (required)</span></span>
- <span data-ttu-id="6381a-293">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-293">Earning Code (required)</span></span>
- <span data-ttu-id="6381a-294">Frecuencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-294">Frequency (required)</span></span>
- <span data-ttu-id="6381a-295">Importe (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="6381a-296">Información de nómina</span><span class="sxs-lookup"><span data-stu-id="6381a-296">Payroll information</span></span>

- <span data-ttu-id="6381a-297">Método de pago</span><span class="sxs-lookup"><span data-stu-id="6381a-297">Payment Method</span></span>
- <span data-ttu-id="6381a-298">Región económica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-298">Economic Region (required)</span></span>
- <span data-ttu-id="6381a-299">Id. de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="6381a-299">Employee Benefits ID</span></span>
- <span data-ttu-id="6381a-300">Número de id. nacional (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-300">National ID Number (required)</span></span>
- <span data-ttu-id="6381a-301">Número de servicio militar</span><span class="sxs-lookup"><span data-stu-id="6381a-301">Military Service Number</span></span>
- <span data-ttu-id="6381a-302">Id. de turno (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-302">Shift ID (required)</span></span>
- <span data-ttu-id="6381a-303">Número de identificación fiscal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-303">Tax Number (required)</span></span>
- <span data-ttu-id="6381a-304">Id. de sindicato (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-304">Union ID (required)</span></span>
- <span data-ttu-id="6381a-305">Id. de día laborable (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-305">Work Day ID (required)</span></span>
- <span data-ttu-id="6381a-306">Número de permiso de trabajo</span><span class="sxs-lookup"><span data-stu-id="6381a-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="6381a-307">Para el método de pago, México admite **Efectivo**, **Cheque** (cheque físico de la empresa) y **Pago electrónico**.</span><span class="sxs-lookup"><span data-stu-id="6381a-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="6381a-308">Si no se especifica ningún método de pago, **Cheque** se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6381a-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="6381a-309">Detalles del empleo</span><span class="sxs-lookup"><span data-stu-id="6381a-309">Employment details</span></span>

<span data-ttu-id="6381a-310">El historial de detalles de empleo se utiliza como información clave para derivar los estados de contratación, despido y recontratación de un empleado en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="6381a-311">Dayforce solo admite un registro de empleo activo a la vez.</span><span class="sxs-lookup"><span data-stu-id="6381a-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="6381a-312">Fecha de inicio de empleo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-312">Employment start date (required)</span></span>
- <span data-ttu-id="6381a-313">Fecha final del empleo</span><span class="sxs-lookup"><span data-stu-id="6381a-313">Employment end date</span></span>
- <span data-ttu-id="6381a-314">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="6381a-314">Start date</span></span>
- <span data-ttu-id="6381a-315">Fecha inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="6381a-315">Adjusted start date</span></span>
- <span data-ttu-id="6381a-316">Fecha de finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="6381a-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="6381a-317">Razón de la finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="6381a-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="6381a-318">Las fechas clave de un empleado se obtienen utilizando la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="6381a-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="6381a-319">Talent</span><span class="sxs-lookup"><span data-stu-id="6381a-319">Talent</span></span>                | <span data-ttu-id="6381a-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="6381a-321">Fecha de contratación más reciente</span><span class="sxs-lookup"><span data-stu-id="6381a-321">Most recent hire date</span></span> | <span data-ttu-id="6381a-322">Inicio de empleo del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="6381a-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="6381a-323">Fecha de finalización</span><span class="sxs-lookup"><span data-stu-id="6381a-323">Termination date</span></span>      | <span data-ttu-id="6381a-324">Fecha de finalización del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="6381a-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="6381a-325">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="6381a-325">Start date</span></span>            | <span data-ttu-id="6381a-326">Fecha de inicio ajustada, fecha de inicio o inicio de empleo del registro de historial de empleo inactivo actual</span><span class="sxs-lookup"><span data-stu-id="6381a-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="6381a-327">Fecha de contratación original</span><span class="sxs-lookup"><span data-stu-id="6381a-327">Original hire date</span></span>    | <span data-ttu-id="6381a-328">Inicio del empleo del registro del historial de empleo más temprano</span><span class="sxs-lookup"><span data-stu-id="6381a-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="6381a-329">Compensación</span><span class="sxs-lookup"><span data-stu-id="6381a-329">Compensation</span></span>

<span data-ttu-id="6381a-330">Un plan de compensación fija se debe asociar al puesto principal de cada empleado durante un período de empleo.</span><span class="sxs-lookup"><span data-stu-id="6381a-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="6381a-331">Este período comienza en la fecha de contratación del empleado (o la fecha de inicio del empleo) y continúa hasta la finalización.</span><span class="sxs-lookup"><span data-stu-id="6381a-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="6381a-332">Fecha de vigencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-332">Effective Date (required)</span></span>
- <span data-ttu-id="6381a-333">Fecha de expiración</span><span class="sxs-lookup"><span data-stu-id="6381a-333">Expiration date</span></span>
- <span data-ttu-id="6381a-334">Índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-334">Pay Rate (required)</span></span>
- <span data-ttu-id="6381a-335">Conversiones de índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="6381a-336">Equivalente anual (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="6381a-337">Equivalente por hora (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="6381a-338">Si un empleado por hora tiene varios puestos, se importa la compensación fija del puesto principal en Dayforce como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="6381a-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="6381a-339">En el caso de los puestos no principales, el índice por hora se guarda en el puesto correspondiente en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="6381a-340">Si un empleado a sueldo tiene varios puestos, se derivan el índice por hora acumulativa y el sueldo anual en todos los puestos activos y se utilizan como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="6381a-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="6381a-341">Números de identificación</span><span class="sxs-lookup"><span data-stu-id="6381a-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="6381a-342">Identificador de seguridad social</span><span class="sxs-lookup"><span data-stu-id="6381a-342">Social Security identifier</span></span> 

<span data-ttu-id="6381a-343">Cada empleado debe tener un identificador principal.</span><span class="sxs-lookup"><span data-stu-id="6381a-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="6381a-344">Este identificador debe ser de tipo de identificación **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="6381a-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="6381a-345">En Dayforce, se deriva automáticamente como el identificador de seguridad social del empleado que se requiere para ser contratado.</span><span class="sxs-lookup"><span data-stu-id="6381a-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="6381a-346">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-346">Primary (required)</span></span>
- <span data-ttu-id="6381a-347">Tipo de identificación = "Nº de SS"</span><span class="sxs-lookup"><span data-stu-id="6381a-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="6381a-348">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="6381a-348">Issued Date</span></span>
- <span data-ttu-id="6381a-349">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="6381a-349">Expiration Date</span></span>

<span data-ttu-id="6381a-350">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="6381a-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="6381a-351">Sin embargo, solo el registro que está marcado como **Principal** está integrado en Dayforce, independientemente de si el número está activo o caducado.</span><span class="sxs-lookup"><span data-stu-id="6381a-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="6381a-352">Cuentas bancarias y desembolsos</span><span class="sxs-lookup"><span data-stu-id="6381a-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="6381a-353">La información de cuenta bancaria válida se debe especificar para cualquier empleado que elija recibir el pago por transferencias de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="6381a-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="6381a-354">Talent</span><span class="sxs-lookup"><span data-stu-id="6381a-354">Talent</span></span>                         | <span data-ttu-id="6381a-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="6381a-356">Número de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="6381a-357">Código SWIFT (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-357">SWIFT code (required)</span></span>          | <span data-ttu-id="6381a-358">Campo **Identificador del banco** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="6381a-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="6381a-359">Número de sucursal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="6381a-360">Tipo de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-360">Bank account type (required)</span></span>   | <span data-ttu-id="6381a-361">Campo **Tipo de cuenta** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="6381a-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="6381a-362">Los valores admitidos incluyen **Comprobación** y **Nómina**.</span><span class="sxs-lookup"><span data-stu-id="6381a-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="6381a-363">Los empleados que elijan que se les pague a través de transferencia bancaria deben proporcionar un vínculo a una cuenta de remanente que esté en una entidad legal que tenga su dirección principal en México y esté asociada con una cuenta bancaria válida de un banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="6381a-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="6381a-364">Todas las demás cuentas no remanentes se ignoran.</span><span class="sxs-lookup"><span data-stu-id="6381a-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="6381a-365">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="6381a-365">Address information</span></span>

<span data-ttu-id="6381a-366">Cada empleado debe tener una ubicación principal.</span><span class="sxs-lookup"><span data-stu-id="6381a-366">Every employee must have one primary location.</span></span> <span data-ttu-id="6381a-367">En Dayforce, esta ubicación se usa para determinar la residencia principal del empleado para impuestos.</span><span class="sxs-lookup"><span data-stu-id="6381a-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="6381a-368">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-368">Primary (required)</span></span>
- <span data-ttu-id="6381a-369">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-369">Country/region (required)</span></span>
- <span data-ttu-id="6381a-370">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="6381a-371">Calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-371">Street (required)</span></span>
- <span data-ttu-id="6381a-372">Número de calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-372">Street Number (required)</span></span>
- <span data-ttu-id="6381a-373">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="6381a-373">Building Complement</span></span>
- <span data-ttu-id="6381a-374">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-374">City (required)</span></span>
- <span data-ttu-id="6381a-375">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-375">State (required)</span></span>
- <span data-ttu-id="6381a-376">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="6381a-377">Configure los datos para generar nóminas en Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="6381a-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="6381a-378">Si va a generar el sueldo de los empleados en Estados Unidos y Canadá, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="6381a-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="6381a-379">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="6381a-379">Departments are required on positions.</span></span>
- <span data-ttu-id="6381a-380">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6381a-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="6381a-381">Puede configurar Talent para requerir que los puestos especifiquen un departamento.</span><span class="sxs-lookup"><span data-stu-id="6381a-381">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="6381a-382">Para ello, vaya a **Puestos compartidos de recursos humanos > Puestos > Requerir departamentos en puestos**.</span><span class="sxs-lookup"><span data-stu-id="6381a-382">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="6381a-383">Recomendamos que este valor se aplique para la integración.</span><span class="sxs-lookup"><span data-stu-id="6381a-383">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="6381a-384">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="6381a-384">Job types</span></span>

<span data-ttu-id="6381a-385">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="6381a-385">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="6381a-386">Los tipos de trabajo son obligatorios para procesar la nómina en Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="6381a-386">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="6381a-387">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="6381a-387">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="6381a-388">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="6381a-388">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="6381a-389">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="6381a-389">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="6381a-390">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6381a-390">Job type</span></span>   | <span data-ttu-id="6381a-391">Descripción</span><span class="sxs-lookup"><span data-stu-id="6381a-391">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="6381a-392">Por hora</span><span class="sxs-lookup"><span data-stu-id="6381a-392">Hourly</span></span>     | <span data-ttu-id="6381a-393">Por hora</span><span class="sxs-lookup"><span data-stu-id="6381a-393">Hourly</span></span>      |
| <span data-ttu-id="6381a-394">Asalariado</span><span class="sxs-lookup"><span data-stu-id="6381a-394">Salaried</span></span>   | <span data-ttu-id="6381a-395">Asalariado</span><span class="sxs-lookup"><span data-stu-id="6381a-395">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="6381a-396">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="6381a-396">Position types</span></span> 

<span data-ttu-id="6381a-397">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="6381a-397">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="6381a-398">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="6381a-398">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="6381a-399">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="6381a-399">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="6381a-400">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="6381a-400">Position type</span></span>   | <span data-ttu-id="6381a-401">Descripción</span><span class="sxs-lookup"><span data-stu-id="6381a-401">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="6381a-402">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="6381a-402">Full-time</span></span>       | <span data-ttu-id="6381a-403">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="6381a-403">Full time employee</span></span> |
| <span data-ttu-id="6381a-404">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="6381a-404">Part-time</span></span>       | <span data-ttu-id="6381a-405">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="6381a-405">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="6381a-406">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="6381a-406">Reason codes</span></span>

<span data-ttu-id="6381a-407">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="6381a-407">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="6381a-408">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="6381a-408">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="6381a-409">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="6381a-409">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="6381a-410">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="6381a-410">Reason code</span></span>    | <span data-ttu-id="6381a-411">Descripción</span><span class="sxs-lookup"><span data-stu-id="6381a-411">Description</span></span>      | <span data-ttu-id="6381a-412">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="6381a-412">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="6381a-413">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="6381a-413">RESIGNATION</span></span>    | <span data-ttu-id="6381a-414">Dimisión</span><span class="sxs-lookup"><span data-stu-id="6381a-414">Resignation</span></span>      | <span data-ttu-id="6381a-415">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-415">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-416">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="6381a-416">TERMINATION</span></span>    | <span data-ttu-id="6381a-417">Finalización</span><span class="sxs-lookup"><span data-stu-id="6381a-417">Termination</span></span>      | <span data-ttu-id="6381a-418">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-418">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-419">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="6381a-419">RETIREMENT</span></span>     | <span data-ttu-id="6381a-420">Jubilación</span><span class="sxs-lookup"><span data-stu-id="6381a-420">Retirement</span></span>       | <span data-ttu-id="6381a-421">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-421">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-422">OTHER</span><span class="sxs-lookup"><span data-stu-id="6381a-422">OTHER</span></span>          | <span data-ttu-id="6381a-423">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="6381a-423">Other Reasons</span></span>    | <span data-ttu-id="6381a-424">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-424">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-425">MUERTE</span><span class="sxs-lookup"><span data-stu-id="6381a-425">DEATH</span></span>          | <span data-ttu-id="6381a-426">Muerte</span><span class="sxs-lookup"><span data-stu-id="6381a-426">Death</span></span>            | <span data-ttu-id="6381a-427">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-427">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-428">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="6381a-428">LEAVEOFABSENCE</span></span> | <span data-ttu-id="6381a-429">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="6381a-429">Leave of Absence</span></span> | <span data-ttu-id="6381a-430">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-430">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-431">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="6381a-431">CONTRACTEND</span></span>    | <span data-ttu-id="6381a-432">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="6381a-432">End of Contract</span></span>  | <span data-ttu-id="6381a-433">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-433">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-434">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="6381a-434">SALARYCHANGE</span></span>   | <span data-ttu-id="6381a-435">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="6381a-435">Change of Salary</span></span> | <span data-ttu-id="6381a-436">Compensación</span><span class="sxs-lookup"><span data-stu-id="6381a-436">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="6381a-437">Estado civil</span><span class="sxs-lookup"><span data-stu-id="6381a-437">Marital status</span></span>

<span data-ttu-id="6381a-438">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="6381a-438">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6381a-439">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-439">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="6381a-440">Talent</span><span class="sxs-lookup"><span data-stu-id="6381a-440">Talent</span></span>                 | <span data-ttu-id="6381a-441">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-441">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="6381a-442">Casado/a</span><span class="sxs-lookup"><span data-stu-id="6381a-442">Married</span></span>                | <span data-ttu-id="6381a-443">Casado/a</span><span class="sxs-lookup"><span data-stu-id="6381a-443">Married</span></span>              |
| <span data-ttu-id="6381a-444">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="6381a-444">Single</span></span>                 | <span data-ttu-id="6381a-445">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="6381a-445">Single</span></span>               |
| <span data-ttu-id="6381a-446">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="6381a-446">Widowed</span></span>                | <span data-ttu-id="6381a-447">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="6381a-447">Widowed</span></span>              |
| <span data-ttu-id="6381a-448">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="6381a-448">Divorced</span></span>               | <span data-ttu-id="6381a-449">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="6381a-449">Divorced</span></span>             |
| <span data-ttu-id="6381a-450">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="6381a-450">Registered Partnership</span></span> | <span data-ttu-id="6381a-451">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="6381a-451">Domestic Partnership</span></span> |
| <span data-ttu-id="6381a-452">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="6381a-452">None</span></span>                   | <span data-ttu-id="6381a-453">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="6381a-453">None</span></span>                 |
| <span data-ttu-id="6381a-454">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="6381a-454">Cohabiting</span></span>             | <span data-ttu-id="6381a-455">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="6381a-455">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="6381a-456">Género</span><span class="sxs-lookup"><span data-stu-id="6381a-456">Gender</span></span>

<span data-ttu-id="6381a-457">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="6381a-457">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6381a-458">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-458">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="6381a-459">Talent</span><span class="sxs-lookup"><span data-stu-id="6381a-459">Talent</span></span>       | <span data-ttu-id="6381a-460">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-460">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="6381a-461">Hombre</span><span class="sxs-lookup"><span data-stu-id="6381a-461">Male</span></span>         | <span data-ttu-id="6381a-462">Hombre</span><span class="sxs-lookup"><span data-stu-id="6381a-462">Male</span></span>            |
| <span data-ttu-id="6381a-463">Mujer</span><span class="sxs-lookup"><span data-stu-id="6381a-463">Female</span></span>       | <span data-ttu-id="6381a-464">Mujer</span><span class="sxs-lookup"><span data-stu-id="6381a-464">Female</span></span>          |
| <span data-ttu-id="6381a-465">No específico</span><span class="sxs-lookup"><span data-stu-id="6381a-465">Non-specific</span></span> | <span data-ttu-id="6381a-466">*No admitido*</span><span class="sxs-lookup"><span data-stu-id="6381a-466">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="6381a-467">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="6381a-467">Earning codes</span></span>

<span data-ttu-id="6381a-468">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="6381a-468">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="6381a-469">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="6381a-469">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="6381a-470">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="6381a-470">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="6381a-471">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="6381a-471">Supported frequencies</span></span>

- <span data-ttu-id="6381a-472">Todas</span><span class="sxs-lookup"><span data-stu-id="6381a-472">All</span></span>
- <span data-ttu-id="6381a-473">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="6381a-473">EVERYPAY</span></span>
- <span data-ttu-id="6381a-474">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="6381a-474">EACHPAYPERIOD</span></span>
- <span data-ttu-id="6381a-475">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="6381a-475">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="6381a-476">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="6381a-476">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="6381a-477">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-477">1OFMTH</span></span>
- <span data-ttu-id="6381a-478">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-478">LASTOFMTH</span></span>
- <span data-ttu-id="6381a-479">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-479">2OFMTH</span></span>
- <span data-ttu-id="6381a-480">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-480">3OFMTH</span></span>
- <span data-ttu-id="6381a-481">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-481">4OFMTH</span></span>
- <span data-ttu-id="6381a-482">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-482">5OFMTH</span></span>
- <span data-ttu-id="6381a-483">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-483">1N2OFMTH</span></span>
- <span data-ttu-id="6381a-484">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-484">3N4OFMTH</span></span>
- <span data-ttu-id="6381a-485">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-485">1N3OFMTH</span></span>
- <span data-ttu-id="6381a-486">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-486">1N4OFMTH</span></span>
- <span data-ttu-id="6381a-487">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-487">2N3OFMTH</span></span>
- <span data-ttu-id="6381a-488">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-488">2N4OFMTH</span></span>
- <span data-ttu-id="6381a-489">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-489">1N2N3OFMTH</span></span>
- <span data-ttu-id="6381a-490">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-490">1N2N4OFMTH</span></span>
- <span data-ttu-id="6381a-491">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-491">1N3N4OFMTH</span></span>
- <span data-ttu-id="6381a-492">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-492">2N3N4OFMTH</span></span>
- <span data-ttu-id="6381a-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="6381a-494">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="6381a-494">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="6381a-495">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="6381a-495">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="6381a-496">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="6381a-496">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="6381a-497">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="6381a-497">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="6381a-498">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="6381a-498">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="6381a-499">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6381a-499">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="6381a-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6381a-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="6381a-501">Direcciones</span><span class="sxs-lookup"><span data-stu-id="6381a-501">Addresses</span></span>

<span data-ttu-id="6381a-502">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="6381a-502">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="6381a-503">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="6381a-503">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="6381a-504">Talent</span><span class="sxs-lookup"><span data-stu-id="6381a-504">Talent</span></span>          | <span data-ttu-id="6381a-505">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-505">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="6381a-506">País/región</span><span class="sxs-lookup"><span data-stu-id="6381a-506">Country/Region</span></span>  | <span data-ttu-id="6381a-507">Código de país</span><span class="sxs-lookup"><span data-stu-id="6381a-507">Country Code</span></span>          |
| <span data-ttu-id="6381a-508">Código postal</span><span class="sxs-lookup"><span data-stu-id="6381a-508">Zip/Postal Code</span></span> | <span data-ttu-id="6381a-509">Código postal</span><span class="sxs-lookup"><span data-stu-id="6381a-509">Postal Code</span></span>           |
| <span data-ttu-id="6381a-510">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="6381a-510">State</span></span>           | <span data-ttu-id="6381a-511">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="6381a-511">State Code</span></span>            |
| <span data-ttu-id="6381a-512">Población</span><span class="sxs-lookup"><span data-stu-id="6381a-512">City</span></span>            | <span data-ttu-id="6381a-513">Población</span><span class="sxs-lookup"><span data-stu-id="6381a-513">City</span></span>                  |
| <span data-ttu-id="6381a-514">Comarca</span><span class="sxs-lookup"><span data-stu-id="6381a-514">County</span></span>          | <span data-ttu-id="6381a-515">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="6381a-515">County (Municipality)</span></span> |
| <span data-ttu-id="6381a-516">Calle</span><span class="sxs-lookup"><span data-stu-id="6381a-516">Street</span></span>          | <span data-ttu-id="6381a-517">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="6381a-517">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="6381a-518">Regiones de impuestos</span><span class="sxs-lookup"><span data-stu-id="6381a-518">Tax regions</span></span>

<span data-ttu-id="6381a-519">Las regiones de impuestos se usan para determinar los impuestos correspondientes que se deben aplicar durante la generación de nómina.</span><span class="sxs-lookup"><span data-stu-id="6381a-519">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="6381a-520">Las regiones de impuestos se asignan a Dayforce como direcciones de ubicación.</span><span class="sxs-lookup"><span data-stu-id="6381a-520">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="6381a-521">La región de impuestos predeterminada se debe asociar al puesto activo del trabajador.</span><span class="sxs-lookup"><span data-stu-id="6381a-521">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="6381a-522">Región de impuestos (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-522">Tax region (required)</span></span>
- <span data-ttu-id="6381a-523">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-523">Country/Region (required)</span></span>
- <span data-ttu-id="6381a-524">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-524">State (required)</span></span>
- <span data-ttu-id="6381a-525">Comarca</span><span class="sxs-lookup"><span data-stu-id="6381a-525">County</span></span> 
- <span data-ttu-id="6381a-526">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="6381a-526">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="6381a-527">Configurar los datos para generar nóminas en México</span><span class="sxs-lookup"><span data-stu-id="6381a-527">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="6381a-528">Si va a generar el sueldo de los empleados en México, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="6381a-528">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="6381a-529">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="6381a-529">Departments are required on positions.</span></span>
- <span data-ttu-id="6381a-530">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6381a-530">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="6381a-531">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="6381a-531">Job types</span></span>

<span data-ttu-id="6381a-532">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="6381a-532">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="6381a-533">Los tipos de trabajo son obligatorios para procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="6381a-533">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="6381a-534">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="6381a-534">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="6381a-535">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="6381a-535">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="6381a-536">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="6381a-536">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="6381a-537">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6381a-537">Job type</span></span>   | <span data-ttu-id="6381a-538">Descripción</span><span class="sxs-lookup"><span data-stu-id="6381a-538">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="6381a-539">Por hora</span><span class="sxs-lookup"><span data-stu-id="6381a-539">Hourly</span></span>     | <span data-ttu-id="6381a-540">MX Por hora</span><span class="sxs-lookup"><span data-stu-id="6381a-540">MX Hourly</span></span>   |
| <span data-ttu-id="6381a-541">Asalariado</span><span class="sxs-lookup"><span data-stu-id="6381a-541">Salaried</span></span>   | <span data-ttu-id="6381a-542">MX Asalariado</span><span class="sxs-lookup"><span data-stu-id="6381a-542">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="6381a-543">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="6381a-543">Position types</span></span> 

<span data-ttu-id="6381a-544">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="6381a-544">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="6381a-545">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="6381a-545">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="6381a-546">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="6381a-546">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="6381a-547">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="6381a-547">Position type</span></span>   | <span data-ttu-id="6381a-548">Descripción</span><span class="sxs-lookup"><span data-stu-id="6381a-548">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="6381a-549">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="6381a-549">Full-time</span></span>       | <span data-ttu-id="6381a-550">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="6381a-550">Full time employee</span></span> |
| <span data-ttu-id="6381a-551">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="6381a-551">Part-time</span></span>       | <span data-ttu-id="6381a-552">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="6381a-552">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="6381a-553">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="6381a-553">Reason codes</span></span>

<span data-ttu-id="6381a-554">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="6381a-554">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="6381a-555">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="6381a-555">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="6381a-556">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="6381a-556">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="6381a-557">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="6381a-557">Reason code</span></span>            | <span data-ttu-id="6381a-558">Descripción</span><span class="sxs-lookup"><span data-stu-id="6381a-558">Description</span></span>                    | <span data-ttu-id="6381a-559">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="6381a-559">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="6381a-560">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="6381a-560">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="6381a-561">Salida antes de la primera nómina</span><span class="sxs-lookup"><span data-stu-id="6381a-561">Departure before first payroll</span></span> | <span data-ttu-id="6381a-562">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-562">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-563">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="6381a-563">RESIGNATION</span></span>            | <span data-ttu-id="6381a-564">Dimisión</span><span class="sxs-lookup"><span data-stu-id="6381a-564">Resignation</span></span>                    | <span data-ttu-id="6381a-565">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-565">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-566">PENSION</span><span class="sxs-lookup"><span data-stu-id="6381a-566">PENSION</span></span>                | <span data-ttu-id="6381a-567">Pensión</span><span class="sxs-lookup"><span data-stu-id="6381a-567">Pension</span></span>                        | <span data-ttu-id="6381a-568">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-568">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-569">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="6381a-569">TERMINATION</span></span>            | <span data-ttu-id="6381a-570">Finalización</span><span class="sxs-lookup"><span data-stu-id="6381a-570">Termination</span></span>                    | <span data-ttu-id="6381a-571">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-571">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-572">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="6381a-572">RETIREMENT</span></span>             | <span data-ttu-id="6381a-573">Jubilación</span><span class="sxs-lookup"><span data-stu-id="6381a-573">Retirement</span></span>                     | <span data-ttu-id="6381a-574">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-574">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-575">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="6381a-575">ABSENTEE</span></span>               | <span data-ttu-id="6381a-576">Ausente</span><span class="sxs-lookup"><span data-stu-id="6381a-576">Absentee</span></span>                       | <span data-ttu-id="6381a-577">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-577">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-578">OTHER</span><span class="sxs-lookup"><span data-stu-id="6381a-578">OTHER</span></span>                  | <span data-ttu-id="6381a-579">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="6381a-579">Other Reasons</span></span>                  | <span data-ttu-id="6381a-580">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-580">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-581">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="6381a-581">CLOSURE</span></span>                | <span data-ttu-id="6381a-582">Cierre de operaciones</span><span class="sxs-lookup"><span data-stu-id="6381a-582">Business Closure</span></span>               | <span data-ttu-id="6381a-583">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-583">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-584">MUERTE</span><span class="sxs-lookup"><span data-stu-id="6381a-584">DEATH</span></span>                  | <span data-ttu-id="6381a-585">Muerte</span><span class="sxs-lookup"><span data-stu-id="6381a-585">Death</span></span>                          | <span data-ttu-id="6381a-586">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-586">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-587">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="6381a-587">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="6381a-588">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="6381a-588">Leave of Absence</span></span>               | <span data-ttu-id="6381a-589">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-589">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-590">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="6381a-590">CONTRACTEND</span></span>            | <span data-ttu-id="6381a-591">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="6381a-591">End of Contract</span></span>                | <span data-ttu-id="6381a-592">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="6381a-592">Terminate worker</span></span>     |
| <span data-ttu-id="6381a-593">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="6381a-593">SALARYCHANGE</span></span>           | <span data-ttu-id="6381a-594">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="6381a-594">Change of Salary</span></span>               | <span data-ttu-id="6381a-595">Compensación</span><span class="sxs-lookup"><span data-stu-id="6381a-595">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="6381a-596">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="6381a-596">Terms of employment</span></span>

<span data-ttu-id="6381a-597">Las condiciones laborales se usan para crear categorías de condiciones laborales.</span><span class="sxs-lookup"><span data-stu-id="6381a-597">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="6381a-598">Las condiciones se asignan a Dayforce como valores de indicador de empleo.</span><span class="sxs-lookup"><span data-stu-id="6381a-598">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="6381a-599">Las siguientes condiciones laborales y descripciones son obligatorias.</span><span class="sxs-lookup"><span data-stu-id="6381a-599">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="6381a-600">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="6381a-600">Terms of employment</span></span>   | <span data-ttu-id="6381a-601">Descripción</span><span class="sxs-lookup"><span data-stu-id="6381a-601">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="6381a-602">Normal</span><span class="sxs-lookup"><span data-stu-id="6381a-602">Regular</span></span>               | <span data-ttu-id="6381a-603">Normal</span><span class="sxs-lookup"><span data-stu-id="6381a-603">Regular</span></span>     |
| <span data-ttu-id="6381a-604">Directo</span><span class="sxs-lookup"><span data-stu-id="6381a-604">Direct</span></span>                | <span data-ttu-id="6381a-605">Directo</span><span class="sxs-lookup"><span data-stu-id="6381a-605">Direct</span></span>      |
| <span data-ttu-id="6381a-606">Prácticas</span><span class="sxs-lookup"><span data-stu-id="6381a-606">Internship</span></span>            | <span data-ttu-id="6381a-607">Prácticas</span><span class="sxs-lookup"><span data-stu-id="6381a-607">Internship</span></span>  |
| <span data-ttu-id="6381a-608">Permanente</span><span class="sxs-lookup"><span data-stu-id="6381a-608">Permanent</span></span>             | <span data-ttu-id="6381a-609">Permanente</span><span class="sxs-lookup"><span data-stu-id="6381a-609">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="6381a-610">Estado civil</span><span class="sxs-lookup"><span data-stu-id="6381a-610">Marital status</span></span>

<span data-ttu-id="6381a-611">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="6381a-611">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6381a-612">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-612">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="6381a-613">Talent</span><span class="sxs-lookup"><span data-stu-id="6381a-613">Talent</span></span>                 | <span data-ttu-id="6381a-614">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-614">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="6381a-615">Casado/a</span><span class="sxs-lookup"><span data-stu-id="6381a-615">Married</span></span>                | <span data-ttu-id="6381a-616">Casado/a</span><span class="sxs-lookup"><span data-stu-id="6381a-616">Married</span></span>                   |
| <span data-ttu-id="6381a-617">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="6381a-617">Single</span></span>                 | <span data-ttu-id="6381a-618">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="6381a-618">Single</span></span>                    |
| <span data-ttu-id="6381a-619">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="6381a-619">Widowed</span></span>                | <span data-ttu-id="6381a-620">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="6381a-620">Widowed</span></span>                   |
| <span data-ttu-id="6381a-621">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="6381a-621">Divorced</span></span>               | <span data-ttu-id="6381a-622">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="6381a-622">Divorced</span></span>                  |
| <span data-ttu-id="6381a-623">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="6381a-623">Registered Partnership</span></span> | <span data-ttu-id="6381a-624">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="6381a-624">Domestic Partnership</span></span>      |
| <span data-ttu-id="6381a-625">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="6381a-625">None</span></span>                   | <span data-ttu-id="6381a-626">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="6381a-626">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6381a-627">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="6381a-627">Cohabiting</span></span>             | <span data-ttu-id="6381a-628">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="6381a-628">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="6381a-629">Género</span><span class="sxs-lookup"><span data-stu-id="6381a-629">Gender</span></span>

<span data-ttu-id="6381a-630">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="6381a-630">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6381a-631">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-631">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="6381a-632">Talent</span><span class="sxs-lookup"><span data-stu-id="6381a-632">Talent</span></span>       | <span data-ttu-id="6381a-633">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-633">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="6381a-634">Hombre</span><span class="sxs-lookup"><span data-stu-id="6381a-634">Male</span></span>         | <span data-ttu-id="6381a-635">Hombre</span><span class="sxs-lookup"><span data-stu-id="6381a-635">Male</span></span>                      |
| <span data-ttu-id="6381a-636">Mujer</span><span class="sxs-lookup"><span data-stu-id="6381a-636">Female</span></span>       | <span data-ttu-id="6381a-637">Mujer</span><span class="sxs-lookup"><span data-stu-id="6381a-637">Female</span></span>                    |
| <span data-ttu-id="6381a-638">No específico</span><span class="sxs-lookup"><span data-stu-id="6381a-638">Non-specific</span></span> | <span data-ttu-id="6381a-639">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="6381a-639">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="6381a-640">Método de pago</span><span class="sxs-lookup"><span data-stu-id="6381a-640">Payment method</span></span>

<span data-ttu-id="6381a-641">Los métodos de pago ofrecen al empleado y la empresa una forma de describir cómo se pagará a los empleados.</span><span class="sxs-lookup"><span data-stu-id="6381a-641">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="6381a-642">Los métodos de pago se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="6381a-642">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6381a-643">En la siguiente tabla se muestra cómo los métodos de pago se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-643">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="6381a-644">Talent</span><span class="sxs-lookup"><span data-stu-id="6381a-644">Talent</span></span>             | <span data-ttu-id="6381a-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-645">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="6381a-646">Efectivo</span><span class="sxs-lookup"><span data-stu-id="6381a-646">Cash</span></span>               | <span data-ttu-id="6381a-647">Efectivo</span><span class="sxs-lookup"><span data-stu-id="6381a-647">Cash</span></span>                      |
| <span data-ttu-id="6381a-648">Pago electrónico</span><span class="sxs-lookup"><span data-stu-id="6381a-648">Electronic Payment</span></span> | <span data-ttu-id="6381a-649">Transferir</span><span class="sxs-lookup"><span data-stu-id="6381a-649">Transfer</span></span>                  |
| <span data-ttu-id="6381a-650">Comprobación</span><span class="sxs-lookup"><span data-stu-id="6381a-650">Check</span></span>              | <span data-ttu-id="6381a-651">Cheque</span><span class="sxs-lookup"><span data-stu-id="6381a-651">Cheque</span></span>                    |
| <span data-ttu-id="6381a-652">Efecto bancario</span><span class="sxs-lookup"><span data-stu-id="6381a-652">Bank Draft</span></span>         | <span data-ttu-id="6381a-653">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="6381a-653">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6381a-654">Otras</span><span class="sxs-lookup"><span data-stu-id="6381a-654">Other</span></span>              | <span data-ttu-id="6381a-655">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="6381a-655">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="6381a-656">Tipo de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="6381a-656">Bank account type</span></span>

<span data-ttu-id="6381a-657">Los tipos de cuenta bancaria se usan para los pagos electrónicos a los empleados.</span><span class="sxs-lookup"><span data-stu-id="6381a-657">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="6381a-658">Los tipos de cuenta bancaria se asignan a Dayforce como información de cuenta de transferencia.</span><span class="sxs-lookup"><span data-stu-id="6381a-658">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="6381a-659">Los tipos de cuenta bancaria se convierten, según proceda, en los valores aceptados en la integración.</span><span class="sxs-lookup"><span data-stu-id="6381a-659">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="6381a-660">Talent</span><span class="sxs-lookup"><span data-stu-id="6381a-660">Talent</span></span>            | <span data-ttu-id="6381a-661">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-661">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="6381a-662">Cuenta corriente</span><span class="sxs-lookup"><span data-stu-id="6381a-662">Checking Account</span></span>  | <span data-ttu-id="6381a-663">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="6381a-663">CheckingAccount</span></span>           |
| <span data-ttu-id="6381a-664">Cuenta de nómina</span><span class="sxs-lookup"><span data-stu-id="6381a-664">Payroll Account</span></span>   | <span data-ttu-id="6381a-665">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="6381a-665">PayrollAccount</span></span>            |
| <span data-ttu-id="6381a-666">Cuenta de ahorros</span><span class="sxs-lookup"><span data-stu-id="6381a-666">Savings Account</span></span>   | <span data-ttu-id="6381a-667">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="6381a-667">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6381a-668">Cuenta de BankGirot</span><span class="sxs-lookup"><span data-stu-id="6381a-668">BankGirot account</span></span> | <span data-ttu-id="6381a-669">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="6381a-669">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6381a-670">Cuenta de PlusGirot</span><span class="sxs-lookup"><span data-stu-id="6381a-670">PlusGirot account</span></span> | <span data-ttu-id="6381a-671">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="6381a-671">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="6381a-672">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="6381a-672">Earning codes</span></span>

<span data-ttu-id="6381a-673">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="6381a-673">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="6381a-674">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="6381a-674">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="6381a-675">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="6381a-675">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="6381a-676">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="6381a-676">Supported frequencies</span></span>

- <span data-ttu-id="6381a-677">Todas</span><span class="sxs-lookup"><span data-stu-id="6381a-677">All</span></span>
- <span data-ttu-id="6381a-678">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="6381a-678">EVERYPAY</span></span>
- <span data-ttu-id="6381a-679">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="6381a-679">EACHPAYPERIOD</span></span>
- <span data-ttu-id="6381a-680">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="6381a-680">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="6381a-681">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="6381a-681">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="6381a-682">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-682">1OFMTH</span></span>
- <span data-ttu-id="6381a-683">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-683">LASTOFMTH</span></span>
- <span data-ttu-id="6381a-684">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-684">2OFMTH</span></span>
- <span data-ttu-id="6381a-685">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-685">3OFMTH</span></span>
- <span data-ttu-id="6381a-686">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-686">4OFMTH</span></span>
- <span data-ttu-id="6381a-687">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-687">5OFMTH</span></span>
- <span data-ttu-id="6381a-688">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-688">1N2OFMTH</span></span>
- <span data-ttu-id="6381a-689">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-689">3N4OFMTH</span></span>
- <span data-ttu-id="6381a-690">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-690">1N3OFMTH</span></span>
- <span data-ttu-id="6381a-691">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-691">1N4OFMTH</span></span>
- <span data-ttu-id="6381a-692">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-692">2N3OFMTH</span></span>
- <span data-ttu-id="6381a-693">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-693">2N4OFMTH</span></span>
- <span data-ttu-id="6381a-694">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-694">1N2N3OFMTH</span></span>
- <span data-ttu-id="6381a-695">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-695">1N2N4OFMTH</span></span>
- <span data-ttu-id="6381a-696">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-696">1N3N4OFMTH</span></span>
- <span data-ttu-id="6381a-697">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-697">2N3N4OFMTH</span></span>
- <span data-ttu-id="6381a-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6381a-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="6381a-699">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="6381a-699">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="6381a-700">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="6381a-700">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="6381a-701">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="6381a-701">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="6381a-702">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="6381a-702">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="6381a-703">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="6381a-703">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="6381a-704">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6381a-704">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="6381a-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6381a-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="6381a-706">Direcciones</span><span class="sxs-lookup"><span data-stu-id="6381a-706">Addresses</span></span>

<span data-ttu-id="6381a-707">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="6381a-707">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="6381a-708">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="6381a-708">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="6381a-709">Talent</span><span class="sxs-lookup"><span data-stu-id="6381a-709">Talent</span></span>              | <span data-ttu-id="6381a-710">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6381a-710">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="6381a-711">País/región</span><span class="sxs-lookup"><span data-stu-id="6381a-711">Country/Region</span></span>      | <span data-ttu-id="6381a-712">Código de país</span><span class="sxs-lookup"><span data-stu-id="6381a-712">Country Code</span></span>          |
| <span data-ttu-id="6381a-713">Código postal</span><span class="sxs-lookup"><span data-stu-id="6381a-713">Zip/Postal Code</span></span>     | <span data-ttu-id="6381a-714">Código postal</span><span class="sxs-lookup"><span data-stu-id="6381a-714">Postal Code</span></span>           |
| <span data-ttu-id="6381a-715">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="6381a-715">State</span></span>               | <span data-ttu-id="6381a-716">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="6381a-716">State Code</span></span>            |
| <span data-ttu-id="6381a-717">Población</span><span class="sxs-lookup"><span data-stu-id="6381a-717">City</span></span>                | <span data-ttu-id="6381a-718">Población</span><span class="sxs-lookup"><span data-stu-id="6381a-718">City</span></span>                  |
| <span data-ttu-id="6381a-719">Comarca</span><span class="sxs-lookup"><span data-stu-id="6381a-719">County</span></span>              | <span data-ttu-id="6381a-720">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="6381a-720">County (Municipality)</span></span> |
| <span data-ttu-id="6381a-721">Calle</span><span class="sxs-lookup"><span data-stu-id="6381a-721">Street</span></span>              | <span data-ttu-id="6381a-722">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="6381a-722">Address Line 1</span></span>        |
| <span data-ttu-id="6381a-723">Número de calle</span><span class="sxs-lookup"><span data-stu-id="6381a-723">Street Number</span></span>       | <span data-ttu-id="6381a-724">Línea de dirección 2</span><span class="sxs-lookup"><span data-stu-id="6381a-724">Address Line 2</span></span>        |
| <span data-ttu-id="6381a-725">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="6381a-725">Building Complement</span></span> | <span data-ttu-id="6381a-726">Línea de dirección 5</span><span class="sxs-lookup"><span data-stu-id="6381a-726">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="6381a-727">Número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="6381a-727">Passport number</span></span>

<span data-ttu-id="6381a-728">Los empleados pueden declarar la información del pasaporte.</span><span class="sxs-lookup"><span data-stu-id="6381a-728">Employees can declare passport information.</span></span> <span data-ttu-id="6381a-729">Esta información es del tipo de identificación **Pasaporte** y se integra en Dayforce como parte de la información específica de México de un empleado.</span><span class="sxs-lookup"><span data-stu-id="6381a-729">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="6381a-730">Tipo de identificación = "Pasaporte"</span><span class="sxs-lookup"><span data-stu-id="6381a-730">Identification Type = "Passport"</span></span>
- <span data-ttu-id="6381a-731">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="6381a-731">Issued Date</span></span>
- <span data-ttu-id="6381a-732">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="6381a-732">Expiration Date</span></span>

<span data-ttu-id="6381a-733">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Pasaporte**.</span><span class="sxs-lookup"><span data-stu-id="6381a-733">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="6381a-734">Sin embargo, solo la entrada de pasaporte activa actual se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-734">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="6381a-735">Si todas las entradas de pasaporte han caducado, el pasaporte que se emitió más recientemente se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6381a-735">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
