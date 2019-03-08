---
title: Configurar la integración de nóminas entre Talent y Dayforce
description: Este tema explica cómo configurar la integración entre Microsoft Dynamics 365 for Talent y Ceridian Dayforce de modo que pueda procesar un período de pago.
author: jcart1106
manager: AnnBe
ms.date: 07/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: fcddf82cffb9f0ba94b83eb21809b810585ebc9e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "306079"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="11c94-103">Configurar la integración de nóminas entre Talent y Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="11c94-104">La integración entre Microsoft Dynamics 365 for Talent y Ceridian Dayforce se basa en varios pasos de configuración que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="11c94-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="11c94-105">Debe configurar la integración en Talent y Dayforce para poder procesar un período de pago.</span><span class="sxs-lookup"><span data-stu-id="11c94-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="11c94-106">Cuando se utiliza un servicio como Dayforce para completar períodos de pago, debe habilitar la integración en Talent.</span><span class="sxs-lookup"><span data-stu-id="11c94-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="11c94-107">La integración necesita los datos específicos de Talent.</span><span class="sxs-lookup"><span data-stu-id="11c94-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="11c94-108">Por lo tanto, debe comprobar que los datos que se asignen a Dayforce se hayan configurado en Talent de una forma que admita la integración.</span><span class="sxs-lookup"><span data-stu-id="11c94-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="11c94-109">La integración utiliza las amplias categorías de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="11c94-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="11c94-110">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="11c94-110">Human resources data</span></span>
- <span data-ttu-id="11c94-111">Catos de compensación</span><span class="sxs-lookup"><span data-stu-id="11c94-111">Compensation data</span></span>
- <span data-ttu-id="11c94-112">Datos de nómina, como ciclos de pago, períodos de sueldo, y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="11c94-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="11c94-113">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="11c94-113">Worker data</span></span>

<span data-ttu-id="11c94-114">Este tema describe los pasos que debe seguir para habilitar la integración.</span><span class="sxs-lookup"><span data-stu-id="11c94-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="11c94-115">También explica los tipos de datos y los detalles de configuración que requiere la integración.</span><span class="sxs-lookup"><span data-stu-id="11c94-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="11c94-116">Habilitar la integración</span><span class="sxs-lookup"><span data-stu-id="11c94-116">Enable the integration</span></span>

<span data-ttu-id="11c94-117">En Talent, debe activar la integración y especificar información de configuración para conectarse a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="11c94-118">Si desea que la transacción de contabilidad general que se genera se importe en Microsoft Dynamics 365 for Finance and Operations, también debe configurar una cuenta de almacenamiento de Microsoft Azure y especificar la cadena de conexión Azure Storage en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="11c94-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="11c94-119">Para activar la integración en Talent, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="11c94-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="11c94-120">En la página **Administración del sistema** , seleccione **Configuración de la integración**.</span><span class="sxs-lookup"><span data-stu-id="11c94-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="11c94-121">Permite especificar el extremo del Protocolo de transferencia de archivos (FTP) y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="11c94-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="11c94-122">Escriba el nombre de usuario y contraseña del usuario que accederá al extremo y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="11c94-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="11c94-123">Pruebe la conexión, como sea necesario, y establezca la opción **Habilitar la integración de nómina** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="11c94-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="11c94-124">Cuando está activada la integración, se crean el paquete y los archivos de exportación de datos, y se establece la frecuencia.</span><span class="sxs-lookup"><span data-stu-id="11c94-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="11c94-125">Puede cambiar esta frecuencia como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="11c94-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="11c94-126">Para obtener más información acerca de las cuentas de almacenamiento de Azure y las cadenas de conexión de Azure Storage, consulte los temas de Azure siguientes:</span><span class="sxs-lookup"><span data-stu-id="11c94-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="11c94-127">Acerca de las cuentas de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="11c94-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="11c94-128">Configurar las cadenas de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="11c94-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="11c94-129">Configurar los datos</span><span class="sxs-lookup"><span data-stu-id="11c94-129">Configure your data</span></span> 

<span data-ttu-id="11c94-130">Para procesar las nóminas, debe configurar los datos de recursos humanos en Talent.</span><span class="sxs-lookup"><span data-stu-id="11c94-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="11c94-131">Debe configurar datos de organización, como los trabajos y los puestos, así como las prestaciones y la información de compensación.</span><span class="sxs-lookup"><span data-stu-id="11c94-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="11c94-132">Esta información proporciona la información de empleo, pago y deducciones que se necesita para producir el sueldo del empleado.</span><span class="sxs-lookup"><span data-stu-id="11c94-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="11c94-133">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="11c94-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="11c94-134">Beneficios</span><span class="sxs-lookup"><span data-stu-id="11c94-134">Benefits</span></span> 

<span data-ttu-id="11c94-135">Recursos humanos ofrece herramientas para la configuración y el mantenimiento de prestaciones, deducciones y los planes de compensación de los trabajadores que una organización ofrece o procesa para sus trabajadores.</span><span class="sxs-lookup"><span data-stu-id="11c94-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="11c94-136">Al crear las prestaciones, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="11c94-137">Planes de prestaciones</span><span class="sxs-lookup"><span data-stu-id="11c94-137">Benefit plans</span></span>

- <span data-ttu-id="11c94-138">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-138">Plan (required)</span></span>
- <span data-ttu-id="11c94-139">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-139">Type (required)</span></span>
- <span data-ttu-id="11c94-140">Impacto de nómina (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-140">Payroll impact (required)</span></span>
- <span data-ttu-id="11c94-141">Recuperar atrasos</span><span class="sxs-lookup"><span data-stu-id="11c94-141">Recover arrears</span></span>
- <span data-ttu-id="11c94-142">Método de deducción</span><span class="sxs-lookup"><span data-stu-id="11c94-142">Deduction method</span></span>
- <span data-ttu-id="11c94-143">Prioridad de deducción</span><span class="sxs-lookup"><span data-stu-id="11c94-143">Deduction priority</span></span>
- <span data-ttu-id="11c94-144">Período de límite</span><span class="sxs-lookup"><span data-stu-id="11c94-144">Limit period</span></span>
- <span data-ttu-id="11c94-145">Importe límite</span><span class="sxs-lookup"><span data-stu-id="11c94-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="11c94-146">Beneficios</span><span class="sxs-lookup"><span data-stu-id="11c94-146">Benefits</span></span>

- <span data-ttu-id="11c94-147">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-147">Plan (required)</span></span>
- <span data-ttu-id="11c94-148">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-148">Type (required)</span></span>
- <span data-ttu-id="11c94-149">Opción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-149">Option (required)</span></span>
- <span data-ttu-id="11c94-150">Identificador de prestación (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-150">Benefit ID (required)</span></span>
- <span data-ttu-id="11c94-151">Frecuencia</span><span class="sxs-lookup"><span data-stu-id="11c94-151">Frequency</span></span>
- <span data-ttu-id="11c94-152">Base</span><span class="sxs-lookup"><span data-stu-id="11c94-152">Basis</span></span>
- <span data-ttu-id="11c94-153">Importe o índice</span><span class="sxs-lookup"><span data-stu-id="11c94-153">Amount or rate</span></span>
- <span data-ttu-id="11c94-154">Código de ganancias</span><span class="sxs-lookup"><span data-stu-id="11c94-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="11c94-155">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="11c94-155">Supported frequencies</span></span> 

- <span data-ttu-id="11c94-156">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="11c94-156">Weekly</span></span>
- <span data-ttu-id="11c94-157">Quincenal</span><span class="sxs-lookup"><span data-stu-id="11c94-157">Bi-weekly</span></span>
- <span data-ttu-id="11c94-158">Bimensual</span><span class="sxs-lookup"><span data-stu-id="11c94-158">Semi-monthly</span></span>
- <span data-ttu-id="11c94-159">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="11c94-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="11c94-160">Bases admitidas</span><span class="sxs-lookup"><span data-stu-id="11c94-160">Supported bases</span></span> 

- <span data-ttu-id="11c94-161">Importe fijo</span><span class="sxs-lookup"><span data-stu-id="11c94-161">Fixed amount</span></span>
- <span data-ttu-id="11c94-162">Porcentaje de ganancias</span><span class="sxs-lookup"><span data-stu-id="11c94-162">Percent of earnings</span></span>
- <span data-ttu-id="11c94-163">Horas productivas</span><span class="sxs-lookup"><span data-stu-id="11c94-163">Productive hours</span></span>

<span data-ttu-id="11c94-164">Dayforce crea las deducciones siguientes, según el impacto de nómina que hay definido en el plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="11c94-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="11c94-165">Selección en Talent</span><span class="sxs-lookup"><span data-stu-id="11c94-165">Selection in Talent</span></span>        | <span data-ttu-id="11c94-166">Resultado en Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="11c94-167">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="11c94-167">None</span></span>                       | <span data-ttu-id="11c94-168">No se crea ninguna deducción.</span><span class="sxs-lookup"><span data-stu-id="11c94-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="11c94-169">Solo deducción</span><span class="sxs-lookup"><span data-stu-id="11c94-169">Deduction only</span></span>             | <span data-ttu-id="11c94-170">Se crea una deducción del empleado.</span><span class="sxs-lookup"><span data-stu-id="11c94-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="11c94-171">Solo contribución</span><span class="sxs-lookup"><span data-stu-id="11c94-171">Contribution only</span></span>          | <span data-ttu-id="11c94-172">Se crea una deducción del empresario.</span><span class="sxs-lookup"><span data-stu-id="11c94-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="11c94-173">Deducción y contribución</span><span class="sxs-lookup"><span data-stu-id="11c94-173">Deduction and contribution</span></span> | <span data-ttu-id="11c94-174">Se crean las deducciones del empleado y del empresario.</span><span class="sxs-lookup"><span data-stu-id="11c94-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="11c94-175">Para obtener más información sobre cómo definir y administrar un programa de prestaciones, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="11c94-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="11c94-176">Proporcionar un programa de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="11c94-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="11c94-177">Crear una nueva prestación</span><span class="sxs-lookup"><span data-stu-id="11c94-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="11c94-178">Definir reglas y directivas de idoneidad para prestaciones</span><span class="sxs-lookup"><span data-stu-id="11c94-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="11c94-179">Inscribir y quitar prestaciones para trabajadores</span><span class="sxs-lookup"><span data-stu-id="11c94-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="11c94-180">Compensación</span><span class="sxs-lookup"><span data-stu-id="11c94-180">Compensation</span></span> 

<span data-ttu-id="11c94-181">La gestión de compensaciones se usa para controlar la entrega de salarios base y primas.</span><span class="sxs-lookup"><span data-stu-id="11c94-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="11c94-182">El sueldo base fijo de un empleado y los aumentos por méritos se controlan mediante planes de compensación fijos.</span><span class="sxs-lookup"><span data-stu-id="11c94-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="11c94-183">El pago de incentivos, como los pagos de bonificación, las primas por rendimiento, las acciones y las concesiones, así como también las primas ocasionales, se controlan a través de planes de compensación variable.</span><span class="sxs-lookup"><span data-stu-id="11c94-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="11c94-184">Dayforce utiliza la información de compensación para calcular la tarifa por hora o anual de un empleado.</span><span class="sxs-lookup"><span data-stu-id="11c94-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="11c94-185">Se requieren planes de compensación fija y conversiones de índice salarial.</span><span class="sxs-lookup"><span data-stu-id="11c94-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="11c94-186">Los empleados deben estar asociados a un plan de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="11c94-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="11c94-187">Para obtener más información acerca de los panes de compensación, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="11c94-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="11c94-188">Crear planes de compensación fija</span><span class="sxs-lookup"><span data-stu-id="11c94-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="11c94-189">Crear planes de compensación variable</span><span class="sxs-lookup"><span data-stu-id="11c94-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="11c94-190">Desarrollar planes y estructura de salarios o compensaciones</span><span class="sxs-lookup"><span data-stu-id="11c94-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="11c94-191">Procesar compensaciones</span><span class="sxs-lookup"><span data-stu-id="11c94-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="11c94-192">Definición del proceso de compensación y el cálculo de resultados</span><span class="sxs-lookup"><span data-stu-id="11c94-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="11c94-193">Inscribir a un empleado en un plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="11c94-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="11c94-194">Inscribir a un empleado en un plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="11c94-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="11c94-195">Trabajos</span><span class="sxs-lookup"><span data-stu-id="11c94-195">Jobs</span></span> 

<span data-ttu-id="11c94-196">Un trabajo es un conjunto de las tareas y responsabilidades que deberá cumplir la persona que realiza un trabajo.</span><span class="sxs-lookup"><span data-stu-id="11c94-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="11c94-197">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="11c94-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="11c94-198">Configurar los componentes de un trabajo</span><span class="sxs-lookup"><span data-stu-id="11c94-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="11c94-199">Definir nuevos trabajos</span><span class="sxs-lookup"><span data-stu-id="11c94-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="11c94-200">Puestos</span><span class="sxs-lookup"><span data-stu-id="11c94-200">Positions</span></span>

<span data-ttu-id="11c94-201">Un puesto es un caso individual de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="11c94-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="11c94-202">Por ejemplo, el puesto "Director de ventas (Este)" es uno de los puestos asociados al trabajo "Director de ventas".</span><span class="sxs-lookup"><span data-stu-id="11c94-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="11c94-203">Un puesto existe en un departamento.</span><span class="sxs-lookup"><span data-stu-id="11c94-203">A position exists in a department.</span></span> <span data-ttu-id="11c94-204">Solo un trabajador puede asociarse solo a cada puesto.</span><span class="sxs-lookup"><span data-stu-id="11c94-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="11c94-205">Tenga en cuenta los siguientes datos y configuración al configurar los puestos:</span><span class="sxs-lookup"><span data-stu-id="11c94-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="11c94-206">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-206">Position (required)</span></span>
- <span data-ttu-id="11c94-207">Descripción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-207">Description (required)</span></span>
- <span data-ttu-id="11c94-208">Trabajo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-208">Job (required)</span></span>
- <span data-ttu-id="11c94-209">Departamento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-209">Department (required)</span></span>
- <span data-ttu-id="11c94-210">Tipo de puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-210">Position type (required)</span></span>
- <span data-ttu-id="11c94-211">Equivalente de jornada completa</span><span class="sxs-lookup"><span data-stu-id="11c94-211">Full-time equivalent</span></span>
- <span data-ttu-id="11c94-212">Horas ordinarias anuales (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="11c94-213">Pagado por la entidad jurídica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="11c94-214">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-214">Pay cycle (required)</span></span>
- <span data-ttu-id="11c94-215">Dimensión financiera predeterminada – Centro de coste (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="11c94-216">Asignación de trabajador – Trabajador, inicio de la asignación, final de la asignación, código de motivo</span><span class="sxs-lookup"><span data-stu-id="11c94-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="11c94-217">Si varios puestos en el mismo departamento están asociados al mismo trabajo, se consolidan en un solo puesto en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="11c94-218">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="11c94-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="11c94-219">Organizar los recursos mediante departamentos, trabajos y puestos</span><span class="sxs-lookup"><span data-stu-id="11c94-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="11c94-220">Configurar puestos</span><span class="sxs-lookup"><span data-stu-id="11c94-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="11c94-221">Departamentos</span><span class="sxs-lookup"><span data-stu-id="11c94-221">Departments</span></span>

<span data-ttu-id="11c94-222">Un departamneto es una unidad operativa que representa una categoría o un área funcional de la organización.</span><span class="sxs-lookup"><span data-stu-id="11c94-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="11c94-223">Un departamento es responsable de un área específica de la organización, como ventas, contabilidad o recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="11c94-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="11c94-224">Puede usar departamentos para informar sobre las áreas funcionales.</span><span class="sxs-lookup"><span data-stu-id="11c94-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="11c94-225">Los departamentos pueden tener responsabilidad de pérdidas y ganancias.</span><span class="sxs-lookup"><span data-stu-id="11c94-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="11c94-226">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="11c94-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="11c94-227">Crear un departamento y asociarlo a la jerarquía de departamentos</span><span class="sxs-lookup"><span data-stu-id="11c94-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="11c94-228">Definir nuevos departamentos</span><span class="sxs-lookup"><span data-stu-id="11c94-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="11c94-229">Ciclos y períodos de pago</span><span class="sxs-lookup"><span data-stu-id="11c94-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="11c94-230">Un ciclo de pago determina la frecuencia con la que se ejecuta el cálculo de nómina y los días específicos en los que se paga a los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="11c94-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="11c94-231">Por ejemplo, un ciclo de pago puede ser mensual y a los empleados se les podría pagar el último día del mes.</span><span class="sxs-lookup"><span data-stu-id="11c94-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="11c94-232">De forma alternativa, un ciclo de pago puede ser semanal y a los empleados se les podría pagar el martes después del final del período de pago.</span><span class="sxs-lookup"><span data-stu-id="11c94-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="11c94-233">Los ciclos de pago se asignan a los puestos para controlar cuándo se paga a los trabajadores en esos puestos.</span><span class="sxs-lookup"><span data-stu-id="11c94-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="11c94-234">Después de crear ciclos de pago, puede generar los períodos de pago para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="11c94-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="11c94-235">Cada período de pago incluye una fecha de pago predeterminada basada en la información que proporcione.</span><span class="sxs-lookup"><span data-stu-id="11c94-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="11c94-236">Sin embargo, puede modificar la fecha de pago predeterminada en un período de pago para permitir excepciones, por ejemplo, cuando la fecha de pago se encuentra en un día festivo.</span><span class="sxs-lookup"><span data-stu-id="11c94-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="11c94-237">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="11c94-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="11c94-238">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-238">Pay cycle (required)</span></span>
- <span data-ttu-id="11c94-239">Frecuencia del ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="11c94-240">Fecha de inicio del período (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="11c94-241">Fecha de pago predeterminado (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="11c94-242">Esta información se integra con Dayforce como grupos salariales y se separa por país o región para cada ciclo de pago.</span><span class="sxs-lookup"><span data-stu-id="11c94-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="11c94-243">Al menos se debe generar un período de sueldo antes de la integración.</span><span class="sxs-lookup"><span data-stu-id="11c94-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="11c94-244">Dayforce genera los calendarios de grupo salarial y las fechas de pago, en función de la fecha inicial del primer período de pago y la fecha de pago predeterminada que se configuran en Talent.</span><span class="sxs-lookup"><span data-stu-id="11c94-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="11c94-245">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="11c94-245">Earning codes</span></span>

<span data-ttu-id="11c94-246">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="11c94-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="11c94-247">Los códigos tienen distintos parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="11c94-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="11c94-248">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="11c94-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="11c94-249">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-249">Earning Code (required)</span></span>
- <span data-ttu-id="11c94-250">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c94-250">Description</span></span>
- <span data-ttu-id="11c94-251">Unidad de medida</span><span class="sxs-lookup"><span data-stu-id="11c94-251">Unit of measure</span></span>
- <span data-ttu-id="11c94-252">Productivo</span><span class="sxs-lookup"><span data-stu-id="11c94-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="11c94-253">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="11c94-253">Worker data</span></span>

<span data-ttu-id="11c94-254">Los registros para los diferentes tipos de trabajadores que tiene son importantes para los sistemas de recursos humanos y nómina.</span><span class="sxs-lookup"><span data-stu-id="11c94-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="11c94-255">La información que se indique se puede utilizar para efectuar un seguimiento de los trabajadores y su información personal.</span><span class="sxs-lookup"><span data-stu-id="11c94-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="11c94-256">Puede mantener la información siguiente para los trabajadores:</span><span class="sxs-lookup"><span data-stu-id="11c94-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="11c94-257">**Básica**: permite mantener la información básica de un trabajador, como la información de contacto, información demográfica, información de identificación, información de familia, estado del servicio militar, información de expatriado y contactos personales y de emergencia.</span><span class="sxs-lookup"><span data-stu-id="11c94-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="11c94-258">**Empleo**: permite mantener la información sobre el empleo de un trabajador, como afiliación de la empresa u organización, asignación de puesto, fecha de inicio y finalización, idoneidad para el trabajo, condiciones de empleo, pensión, vacaciones y la información de reubicación.</span><span class="sxs-lookup"><span data-stu-id="11c94-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="11c94-259">**Bajas y ausencias**: permite mantener información sobre las ausencias de un trabajador, como calendarios de trabajo, transacciones de ausencia y configuración de ausencias.</span><span class="sxs-lookup"><span data-stu-id="11c94-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="11c94-260">**Compensación y nómina**: permite mantener la información sobre los planes de compensación y la información de nómina de un trabajador, como inscripción del plan, concesiones, desempeño, comisión, información fiscal, retiro y deducciones de sueldo.</span><span class="sxs-lookup"><span data-stu-id="11c94-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="11c94-261">Al introducir la información del trabajador, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="11c94-262">Información general</span><span class="sxs-lookup"><span data-stu-id="11c94-262">General information</span></span>

- <span data-ttu-id="11c94-263">Número de personal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-263">Personnel number (required)</span></span>
- <span data-ttu-id="11c94-264">Nombre (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-264">First name (required)</span></span>
- <span data-ttu-id="11c94-265">Apellido (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-265">Last name (required)</span></span>
- <span data-ttu-id="11c94-266">Segundo nombre</span><span class="sxs-lookup"><span data-stu-id="11c94-266">Middle name</span></span>
- <span data-ttu-id="11c94-267">Antigüedad</span><span class="sxs-lookup"><span data-stu-id="11c94-267">Seniority date</span></span>
- <span data-ttu-id="11c94-268">Conocido como</span><span class="sxs-lookup"><span data-stu-id="11c94-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="11c94-269">Información personal</span><span class="sxs-lookup"><span data-stu-id="11c94-269">Personal information</span></span>

- <span data-ttu-id="11c94-270">Estado civil (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-270">Marital status (required)</span></span>
- <span data-ttu-id="11c94-271">Fecha de nacimiento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-271">Birth date (required)</span></span>
- <span data-ttu-id="11c94-272">Sexo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-272">Gender (required)</span></span>
- <span data-ttu-id="11c94-273">Persona con discapacidades</span><span class="sxs-lookup"><span data-stu-id="11c94-273">Person with disabilities</span></span>
- <span data-ttu-id="11c94-274">País o región, nacionalidad (solo para México)</span><span class="sxs-lookup"><span data-stu-id="11c94-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="11c94-275">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="11c94-275">Address information</span></span>

- <span data-ttu-id="11c94-276">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-276">Primary (required)</span></span>
- <span data-ttu-id="11c94-277">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-277">Country/region (required)</span></span>
- <span data-ttu-id="11c94-278">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-278">Postal code (required)</span></span>
- <span data-ttu-id="11c94-279">Número de calle (obligatorio) (solo para México)</span><span class="sxs-lookup"><span data-stu-id="11c94-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="11c94-280">Complemento de edificio (solo para México)</span><span class="sxs-lookup"><span data-stu-id="11c94-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="11c94-281">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-281">City (required)</span></span>
- <span data-ttu-id="11c94-282">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-282">State (required)</span></span>
- <span data-ttu-id="11c94-283">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="11c94-284">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="11c94-284">Contact information</span></span> 

- <span data-ttu-id="11c94-285">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-285">Primary (required)</span></span>
- <span data-ttu-id="11c94-286">Número de contacto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-286">Contact number (required)</span></span>
- <span data-ttu-id="11c94-287">Extensión</span><span class="sxs-lookup"><span data-stu-id="11c94-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="11c94-288">Información de nómina y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="11c94-288">Payroll information and earning codes</span></span>

<span data-ttu-id="11c94-289">A los empleados se les pueden asignar ganancias específicas de una frecuencia determinada de pago y tener un método de pago preferido.</span><span class="sxs-lookup"><span data-stu-id="11c94-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="11c94-290">Los siguientes campos se utilizan en Dayforce para ayudar a garantizar que se usen las preferencias y valores.</span><span class="sxs-lookup"><span data-stu-id="11c94-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="11c94-291">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="11c94-291">Earning codes</span></span>

- <span data-ttu-id="11c94-292">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-292">Position (required)</span></span>
- <span data-ttu-id="11c94-293">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-293">Earning Code (required)</span></span>
- <span data-ttu-id="11c94-294">Frecuencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-294">Frequency (required)</span></span>
- <span data-ttu-id="11c94-295">Importe (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="11c94-296">Información de nómina</span><span class="sxs-lookup"><span data-stu-id="11c94-296">Payroll information</span></span>

- <span data-ttu-id="11c94-297">Método de pago</span><span class="sxs-lookup"><span data-stu-id="11c94-297">Payment Method</span></span>
- <span data-ttu-id="11c94-298">Región económica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-298">Economic Region (required)</span></span>
- <span data-ttu-id="11c94-299">Id. de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="11c94-299">Employee Benefits ID</span></span>
- <span data-ttu-id="11c94-300">Número de id. nacional (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-300">National ID Number (required)</span></span>
- <span data-ttu-id="11c94-301">Número de servicio militar</span><span class="sxs-lookup"><span data-stu-id="11c94-301">Military Service Number</span></span>
- <span data-ttu-id="11c94-302">Id. de turno (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-302">Shift ID (required)</span></span>
- <span data-ttu-id="11c94-303">Número de identificación fiscal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-303">Tax Number (required)</span></span>
- <span data-ttu-id="11c94-304">Id. de sindicato (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-304">Union ID (required)</span></span>
- <span data-ttu-id="11c94-305">Id. de día laborable (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-305">Work Day ID (required)</span></span>
- <span data-ttu-id="11c94-306">Número de permiso de trabajo</span><span class="sxs-lookup"><span data-stu-id="11c94-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="11c94-307">Para el método de pago, México admite **Efectivo**, **Cheque** (cheque físico de la empresa) y **Pago electrónico**.</span><span class="sxs-lookup"><span data-stu-id="11c94-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="11c94-308">Si no se especifica ningún método de pago, **Cheque** se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="11c94-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="11c94-309">Detalles del empleo</span><span class="sxs-lookup"><span data-stu-id="11c94-309">Employment details</span></span>

<span data-ttu-id="11c94-310">El historial de detalles de empleo se utiliza como información clave para derivar los estados de contratación, despido y recontratación de un empleado en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="11c94-311">Dayforce solo admite un registro de empleo activo a la vez.</span><span class="sxs-lookup"><span data-stu-id="11c94-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="11c94-312">Fecha de inicio de empleo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-312">Employment start date (required)</span></span>
- <span data-ttu-id="11c94-313">Fecha final del empleo</span><span class="sxs-lookup"><span data-stu-id="11c94-313">Employment end date</span></span>
- <span data-ttu-id="11c94-314">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="11c94-314">Start date</span></span>
- <span data-ttu-id="11c94-315">Fecha inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="11c94-315">Adjusted start date</span></span>
- <span data-ttu-id="11c94-316">Fecha de finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="11c94-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="11c94-317">Razón de la finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="11c94-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="11c94-318">Las fechas clave de un empleado se obtienen utilizando la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="11c94-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="11c94-319">Talent</span><span class="sxs-lookup"><span data-stu-id="11c94-319">Talent</span></span>                | <span data-ttu-id="11c94-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="11c94-321">Fecha de contratación más reciente</span><span class="sxs-lookup"><span data-stu-id="11c94-321">Most recent hire date</span></span> | <span data-ttu-id="11c94-322">Inicio de empleo del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="11c94-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="11c94-323">Fecha de finalización</span><span class="sxs-lookup"><span data-stu-id="11c94-323">Termination date</span></span>      | <span data-ttu-id="11c94-324">Fecha de finalización del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="11c94-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="11c94-325">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="11c94-325">Start date</span></span>            | <span data-ttu-id="11c94-326">Fecha de inicio ajustada, fecha de inicio o inicio de empleo del registro de historial de empleo inactivo actual</span><span class="sxs-lookup"><span data-stu-id="11c94-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="11c94-327">Fecha de contratación original</span><span class="sxs-lookup"><span data-stu-id="11c94-327">Original hire date</span></span>    | <span data-ttu-id="11c94-328">Inicio del empleo del registro del historial de empleo más temprano</span><span class="sxs-lookup"><span data-stu-id="11c94-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="11c94-329">Compensación</span><span class="sxs-lookup"><span data-stu-id="11c94-329">Compensation</span></span>

<span data-ttu-id="11c94-330">Un plan de compensación fija se debe asociar al puesto principal de cada empleado durante un período de empleo.</span><span class="sxs-lookup"><span data-stu-id="11c94-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="11c94-331">Este período comienza en la fecha de contratación del empleado (o la fecha de inicio del empleo) y continúa hasta la finalización.</span><span class="sxs-lookup"><span data-stu-id="11c94-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="11c94-332">Fecha de vigencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-332">Effective Date (required)</span></span>
- <span data-ttu-id="11c94-333">Fecha de expiración</span><span class="sxs-lookup"><span data-stu-id="11c94-333">Expiration date</span></span>
- <span data-ttu-id="11c94-334">Índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-334">Pay Rate (required)</span></span>
- <span data-ttu-id="11c94-335">Conversiones de índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="11c94-336">Equivalente anual (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="11c94-337">Equivalente por hora (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="11c94-338">Si un empleado por hora tiene varios puestos, se importa la compensación fija del puesto principal en Dayforce como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="11c94-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="11c94-339">En el caso de los puestos no principales, el índice por hora se guarda en el puesto correspondiente en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="11c94-340">Si un empleado a sueldo tiene varios puestos, se derivan el índice por hora acumulativa y el sueldo anual en todos los puestos activos y se utilizan como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="11c94-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="11c94-341">Números de identificación</span><span class="sxs-lookup"><span data-stu-id="11c94-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="11c94-342">Identificador de seguridad social</span><span class="sxs-lookup"><span data-stu-id="11c94-342">Social Security identifier</span></span> 

<span data-ttu-id="11c94-343">Cada empleado debe tener un identificador principal.</span><span class="sxs-lookup"><span data-stu-id="11c94-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="11c94-344">Este identificador debe ser de tipo de identificación **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="11c94-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="11c94-345">En Dayforce, se deriva automáticamente como el identificador de seguridad social del empleado que se requiere para ser contratado.</span><span class="sxs-lookup"><span data-stu-id="11c94-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="11c94-346">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-346">Primary (required)</span></span>
- <span data-ttu-id="11c94-347">Tipo de identificación = "Nº de SS"</span><span class="sxs-lookup"><span data-stu-id="11c94-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="11c94-348">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="11c94-348">Issued Date</span></span>
- <span data-ttu-id="11c94-349">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="11c94-349">Expiration Date</span></span>

<span data-ttu-id="11c94-350">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="11c94-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="11c94-351">Sin embargo, solo el registro que está marcado como **Principal** está integrado en Dayforce, independientemente de si el número está activo o caducado.</span><span class="sxs-lookup"><span data-stu-id="11c94-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="11c94-352">Cuentas bancarias y desembolsos</span><span class="sxs-lookup"><span data-stu-id="11c94-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="11c94-353">La información de cuenta bancaria válida se debe especificar para cualquier empleado que elija recibir el pago por transferencias de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="11c94-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="11c94-354">Talent</span><span class="sxs-lookup"><span data-stu-id="11c94-354">Talent</span></span>                         | <span data-ttu-id="11c94-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="11c94-356">Número de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="11c94-357">Código SWIFT (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-357">SWIFT code (required)</span></span>          | <span data-ttu-id="11c94-358">Campo **Identificador del banco** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="11c94-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="11c94-359">Número de sucursal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="11c94-360">Tipo de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-360">Bank account type (required)</span></span>   | <span data-ttu-id="11c94-361">Campo **Tipo de cuenta** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="11c94-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="11c94-362">Los valores admitidos incluyen **Comprobación** y **Nómina**.</span><span class="sxs-lookup"><span data-stu-id="11c94-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="11c94-363">Los empleados que elijan que se les pague a través de transferencia bancaria deben proporcionar un vínculo a una cuenta de remanente que esté en una entidad legal que tenga su dirección principal en México y esté asociada con una cuenta bancaria válida de un banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="11c94-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="11c94-364">Todas las demás cuentas no remanentes se ignoran.</span><span class="sxs-lookup"><span data-stu-id="11c94-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="11c94-365">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="11c94-365">Address information</span></span>

<span data-ttu-id="11c94-366">Cada empleado debe tener una ubicación principal.</span><span class="sxs-lookup"><span data-stu-id="11c94-366">Every employee must have one primary location.</span></span> <span data-ttu-id="11c94-367">En Dayforce, esta ubicación se usa para determinar la residencia principal del empleado para impuestos.</span><span class="sxs-lookup"><span data-stu-id="11c94-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="11c94-368">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-368">Primary (required)</span></span>
- <span data-ttu-id="11c94-369">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-369">Country/region (required)</span></span>
- <span data-ttu-id="11c94-370">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="11c94-371">Calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-371">Street (required)</span></span>
- <span data-ttu-id="11c94-372">Número de calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-372">Street Number (required)</span></span>
- <span data-ttu-id="11c94-373">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="11c94-373">Building Complement</span></span>
- <span data-ttu-id="11c94-374">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-374">City (required)</span></span>
- <span data-ttu-id="11c94-375">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-375">State (required)</span></span>
- <span data-ttu-id="11c94-376">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="11c94-377">Configure los datos para generar nóminas en Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="11c94-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="11c94-378">Si va a generar el sueldo de los empleados en Estados Unidos y Canadá, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="11c94-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="11c94-379">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="11c94-379">Departments are required on positions.</span></span>
- <span data-ttu-id="11c94-380">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="11c94-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="11c94-381">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="11c94-381">Job types</span></span>

<span data-ttu-id="11c94-382">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="11c94-382">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="11c94-383">Los tipos de trabajo son obligatorios para procesar la nómina en Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="11c94-383">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="11c94-384">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="11c94-384">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="11c94-385">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="11c94-385">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="11c94-386">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="11c94-386">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="11c94-387">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="11c94-387">Job type</span></span>   | <span data-ttu-id="11c94-388">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c94-388">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="11c94-389">Por hora</span><span class="sxs-lookup"><span data-stu-id="11c94-389">Hourly</span></span>     | <span data-ttu-id="11c94-390">Por hora</span><span class="sxs-lookup"><span data-stu-id="11c94-390">Hourly</span></span>      |
| <span data-ttu-id="11c94-391">Asalariado</span><span class="sxs-lookup"><span data-stu-id="11c94-391">Salaried</span></span>   | <span data-ttu-id="11c94-392">Asalariado</span><span class="sxs-lookup"><span data-stu-id="11c94-392">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="11c94-393">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="11c94-393">Position types</span></span> 

<span data-ttu-id="11c94-394">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="11c94-394">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="11c94-395">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="11c94-395">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="11c94-396">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="11c94-396">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="11c94-397">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="11c94-397">Position type</span></span>   | <span data-ttu-id="11c94-398">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c94-398">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="11c94-399">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="11c94-399">Full-time</span></span>       | <span data-ttu-id="11c94-400">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="11c94-400">Full time employee</span></span> |
| <span data-ttu-id="11c94-401">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="11c94-401">Part-time</span></span>       | <span data-ttu-id="11c94-402">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="11c94-402">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="11c94-403">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="11c94-403">Reason codes</span></span>

<span data-ttu-id="11c94-404">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="11c94-404">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="11c94-405">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="11c94-405">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="11c94-406">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="11c94-406">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="11c94-407">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="11c94-407">Reason code</span></span>    | <span data-ttu-id="11c94-408">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c94-408">Description</span></span>      | <span data-ttu-id="11c94-409">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="11c94-409">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="11c94-410">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="11c94-410">RESIGNATION</span></span>    | <span data-ttu-id="11c94-411">Dimisión</span><span class="sxs-lookup"><span data-stu-id="11c94-411">Resignation</span></span>      | <span data-ttu-id="11c94-412">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-412">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-413">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="11c94-413">TERMINATION</span></span>    | <span data-ttu-id="11c94-414">Finalización</span><span class="sxs-lookup"><span data-stu-id="11c94-414">Termination</span></span>      | <span data-ttu-id="11c94-415">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-415">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-416">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="11c94-416">RETIREMENT</span></span>     | <span data-ttu-id="11c94-417">Jubilación</span><span class="sxs-lookup"><span data-stu-id="11c94-417">Retirement</span></span>       | <span data-ttu-id="11c94-418">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-418">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-419">OTHER</span><span class="sxs-lookup"><span data-stu-id="11c94-419">OTHER</span></span>          | <span data-ttu-id="11c94-420">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="11c94-420">Other Reasons</span></span>    | <span data-ttu-id="11c94-421">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-421">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-422">MUERTE</span><span class="sxs-lookup"><span data-stu-id="11c94-422">DEATH</span></span>          | <span data-ttu-id="11c94-423">Muerte</span><span class="sxs-lookup"><span data-stu-id="11c94-423">Death</span></span>            | <span data-ttu-id="11c94-424">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-424">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-425">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="11c94-425">LEAVEOFABSENCE</span></span> | <span data-ttu-id="11c94-426">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="11c94-426">Leave of Absence</span></span> | <span data-ttu-id="11c94-427">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-427">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-428">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="11c94-428">CONTRACTEND</span></span>    | <span data-ttu-id="11c94-429">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="11c94-429">End of Contract</span></span>  | <span data-ttu-id="11c94-430">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-430">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-431">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="11c94-431">SALARYCHANGE</span></span>   | <span data-ttu-id="11c94-432">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="11c94-432">Change of Salary</span></span> | <span data-ttu-id="11c94-433">Compensación</span><span class="sxs-lookup"><span data-stu-id="11c94-433">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="11c94-434">Estado civil</span><span class="sxs-lookup"><span data-stu-id="11c94-434">Marital status</span></span>

<span data-ttu-id="11c94-435">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="11c94-435">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="11c94-436">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-436">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="11c94-437">Talent</span><span class="sxs-lookup"><span data-stu-id="11c94-437">Talent</span></span>                 | <span data-ttu-id="11c94-438">Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-438">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="11c94-439">Casado/a</span><span class="sxs-lookup"><span data-stu-id="11c94-439">Married</span></span>                | <span data-ttu-id="11c94-440">Casado/a</span><span class="sxs-lookup"><span data-stu-id="11c94-440">Married</span></span>              |
| <span data-ttu-id="11c94-441">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="11c94-441">Single</span></span>                 | <span data-ttu-id="11c94-442">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="11c94-442">Single</span></span>               |
| <span data-ttu-id="11c94-443">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="11c94-443">Widowed</span></span>                | <span data-ttu-id="11c94-444">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="11c94-444">Widowed</span></span>              |
| <span data-ttu-id="11c94-445">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="11c94-445">Divorced</span></span>               | <span data-ttu-id="11c94-446">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="11c94-446">Divorced</span></span>             |
| <span data-ttu-id="11c94-447">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="11c94-447">Registered Partnership</span></span> | <span data-ttu-id="11c94-448">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="11c94-448">Domestic Partnership</span></span> |
| <span data-ttu-id="11c94-449">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="11c94-449">None</span></span>                   | <span data-ttu-id="11c94-450">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="11c94-450">None</span></span>                 |
| <span data-ttu-id="11c94-451">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="11c94-451">Cohabiting</span></span>             | <span data-ttu-id="11c94-452">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="11c94-452">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="11c94-453">Género</span><span class="sxs-lookup"><span data-stu-id="11c94-453">Gender</span></span>

<span data-ttu-id="11c94-454">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="11c94-454">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="11c94-455">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-455">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="11c94-456">Talent</span><span class="sxs-lookup"><span data-stu-id="11c94-456">Talent</span></span>       | <span data-ttu-id="11c94-457">Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-457">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="11c94-458">Hombre</span><span class="sxs-lookup"><span data-stu-id="11c94-458">Male</span></span>         | <span data-ttu-id="11c94-459">Hombre</span><span class="sxs-lookup"><span data-stu-id="11c94-459">Male</span></span>            |
| <span data-ttu-id="11c94-460">Mujer</span><span class="sxs-lookup"><span data-stu-id="11c94-460">Female</span></span>       | <span data-ttu-id="11c94-461">Mujer</span><span class="sxs-lookup"><span data-stu-id="11c94-461">Female</span></span>          |
| <span data-ttu-id="11c94-462">No específico</span><span class="sxs-lookup"><span data-stu-id="11c94-462">Non-specific</span></span> | <span data-ttu-id="11c94-463">*No admitido*</span><span class="sxs-lookup"><span data-stu-id="11c94-463">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="11c94-464">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="11c94-464">Earning codes</span></span>

<span data-ttu-id="11c94-465">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="11c94-465">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="11c94-466">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="11c94-466">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="11c94-467">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="11c94-467">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="11c94-468">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="11c94-468">Supported frequencies</span></span>

- <span data-ttu-id="11c94-469">Todas</span><span class="sxs-lookup"><span data-stu-id="11c94-469">All</span></span>
- <span data-ttu-id="11c94-470">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="11c94-470">EVERYPAY</span></span>
- <span data-ttu-id="11c94-471">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="11c94-471">EACHPAYPERIOD</span></span>
- <span data-ttu-id="11c94-472">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="11c94-472">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="11c94-473">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="11c94-473">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="11c94-474">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-474">1OFMTH</span></span>
- <span data-ttu-id="11c94-475">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-475">LASTOFMTH</span></span>
- <span data-ttu-id="11c94-476">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-476">2OFMTH</span></span>
- <span data-ttu-id="11c94-477">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-477">3OFMTH</span></span>
- <span data-ttu-id="11c94-478">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-478">4OFMTH</span></span>
- <span data-ttu-id="11c94-479">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-479">5OFMTH</span></span>
- <span data-ttu-id="11c94-480">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-480">1N2OFMTH</span></span>
- <span data-ttu-id="11c94-481">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-481">3N4OFMTH</span></span>
- <span data-ttu-id="11c94-482">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-482">1N3OFMTH</span></span>
- <span data-ttu-id="11c94-483">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-483">1N4OFMTH</span></span>
- <span data-ttu-id="11c94-484">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-484">2N3OFMTH</span></span>
- <span data-ttu-id="11c94-485">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-485">2N4OFMTH</span></span>
- <span data-ttu-id="11c94-486">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-486">1N2N3OFMTH</span></span>
- <span data-ttu-id="11c94-487">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-487">1N2N4OFMTH</span></span>
- <span data-ttu-id="11c94-488">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-488">1N3N4OFMTH</span></span>
- <span data-ttu-id="11c94-489">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-489">2N3N4OFMTH</span></span>
- <span data-ttu-id="11c94-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="11c94-491">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="11c94-491">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="11c94-492">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="11c94-492">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="11c94-493">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="11c94-493">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="11c94-494">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="11c94-494">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="11c94-495">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="11c94-495">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="11c94-496">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="11c94-496">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="11c94-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="11c94-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="11c94-498">Direcciones</span><span class="sxs-lookup"><span data-stu-id="11c94-498">Addresses</span></span>

<span data-ttu-id="11c94-499">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="11c94-499">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="11c94-500">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="11c94-500">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="11c94-501">Talent</span><span class="sxs-lookup"><span data-stu-id="11c94-501">Talent</span></span>          | <span data-ttu-id="11c94-502">Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-502">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="11c94-503">País/región</span><span class="sxs-lookup"><span data-stu-id="11c94-503">Country/Region</span></span>  | <span data-ttu-id="11c94-504">Código de país</span><span class="sxs-lookup"><span data-stu-id="11c94-504">Country Code</span></span>          |
| <span data-ttu-id="11c94-505">Código postal</span><span class="sxs-lookup"><span data-stu-id="11c94-505">Zip/Postal Code</span></span> | <span data-ttu-id="11c94-506">Código postal</span><span class="sxs-lookup"><span data-stu-id="11c94-506">Postal Code</span></span>           |
| <span data-ttu-id="11c94-507">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="11c94-507">State</span></span>           | <span data-ttu-id="11c94-508">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="11c94-508">State Code</span></span>            |
| <span data-ttu-id="11c94-509">Población</span><span class="sxs-lookup"><span data-stu-id="11c94-509">City</span></span>            | <span data-ttu-id="11c94-510">Población</span><span class="sxs-lookup"><span data-stu-id="11c94-510">City</span></span>                  |
| <span data-ttu-id="11c94-511">Comarca</span><span class="sxs-lookup"><span data-stu-id="11c94-511">County</span></span>          | <span data-ttu-id="11c94-512">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="11c94-512">County (Municipality)</span></span> |
| <span data-ttu-id="11c94-513">Calle</span><span class="sxs-lookup"><span data-stu-id="11c94-513">Street</span></span>          | <span data-ttu-id="11c94-514">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="11c94-514">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="11c94-515">Regiones de impuestos</span><span class="sxs-lookup"><span data-stu-id="11c94-515">Tax regions</span></span>

<span data-ttu-id="11c94-516">Las regiones de impuestos se usan para determinar los impuestos correspondientes que se deben aplicar durante la generación de nómina.</span><span class="sxs-lookup"><span data-stu-id="11c94-516">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="11c94-517">Las regiones de impuestos se asignan a Dayforce como direcciones de ubicación.</span><span class="sxs-lookup"><span data-stu-id="11c94-517">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="11c94-518">La región de impuestos predeterminada se debe asociar al puesto activo del trabajador.</span><span class="sxs-lookup"><span data-stu-id="11c94-518">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="11c94-519">Región de impuestos (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-519">Tax region (required)</span></span>
- <span data-ttu-id="11c94-520">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-520">Country/Region (required)</span></span>
- <span data-ttu-id="11c94-521">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-521">State (required)</span></span>
- <span data-ttu-id="11c94-522">Comarca</span><span class="sxs-lookup"><span data-stu-id="11c94-522">County</span></span> 
- <span data-ttu-id="11c94-523">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="11c94-523">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="11c94-524">Configurar los datos para generar nóminas en México</span><span class="sxs-lookup"><span data-stu-id="11c94-524">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="11c94-525">Si va a generar el sueldo de los empleados en México, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="11c94-525">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="11c94-526">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="11c94-526">Departments are required on positions.</span></span>
- <span data-ttu-id="11c94-527">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="11c94-527">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="11c94-528">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="11c94-528">Job types</span></span>

<span data-ttu-id="11c94-529">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="11c94-529">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="11c94-530">Los tipos de trabajo son obligatorios para procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="11c94-530">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="11c94-531">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="11c94-531">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="11c94-532">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="11c94-532">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="11c94-533">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="11c94-533">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="11c94-534">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="11c94-534">Job type</span></span>   | <span data-ttu-id="11c94-535">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c94-535">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="11c94-536">Por hora</span><span class="sxs-lookup"><span data-stu-id="11c94-536">Hourly</span></span>     | <span data-ttu-id="11c94-537">MX Por hora</span><span class="sxs-lookup"><span data-stu-id="11c94-537">MX Hourly</span></span>   |
| <span data-ttu-id="11c94-538">Asalariado</span><span class="sxs-lookup"><span data-stu-id="11c94-538">Salaried</span></span>   | <span data-ttu-id="11c94-539">MX Asalariado</span><span class="sxs-lookup"><span data-stu-id="11c94-539">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="11c94-540">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="11c94-540">Position types</span></span> 

<span data-ttu-id="11c94-541">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="11c94-541">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="11c94-542">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="11c94-542">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="11c94-543">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="11c94-543">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="11c94-544">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="11c94-544">Position type</span></span>   | <span data-ttu-id="11c94-545">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c94-545">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="11c94-546">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="11c94-546">Full-time</span></span>       | <span data-ttu-id="11c94-547">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="11c94-547">Full time employee</span></span> |
| <span data-ttu-id="11c94-548">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="11c94-548">Part-time</span></span>       | <span data-ttu-id="11c94-549">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="11c94-549">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="11c94-550">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="11c94-550">Reason codes</span></span>

<span data-ttu-id="11c94-551">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="11c94-551">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="11c94-552">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="11c94-552">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="11c94-553">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="11c94-553">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="11c94-554">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="11c94-554">Reason code</span></span>            | <span data-ttu-id="11c94-555">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c94-555">Description</span></span>                    | <span data-ttu-id="11c94-556">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="11c94-556">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="11c94-557">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="11c94-557">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="11c94-558">Salida antes de la primera nómina</span><span class="sxs-lookup"><span data-stu-id="11c94-558">Departure before first payroll</span></span> | <span data-ttu-id="11c94-559">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-559">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-560">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="11c94-560">RESIGNATION</span></span>            | <span data-ttu-id="11c94-561">Dimisión</span><span class="sxs-lookup"><span data-stu-id="11c94-561">Resignation</span></span>                    | <span data-ttu-id="11c94-562">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-562">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-563">PENSION</span><span class="sxs-lookup"><span data-stu-id="11c94-563">PENSION</span></span>                | <span data-ttu-id="11c94-564">Pensión</span><span class="sxs-lookup"><span data-stu-id="11c94-564">Pension</span></span>                        | <span data-ttu-id="11c94-565">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-565">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-566">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="11c94-566">TERMINATION</span></span>            | <span data-ttu-id="11c94-567">Finalización</span><span class="sxs-lookup"><span data-stu-id="11c94-567">Termination</span></span>                    | <span data-ttu-id="11c94-568">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-568">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-569">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="11c94-569">RETIREMENT</span></span>             | <span data-ttu-id="11c94-570">Jubilación</span><span class="sxs-lookup"><span data-stu-id="11c94-570">Retirement</span></span>                     | <span data-ttu-id="11c94-571">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-571">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-572">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="11c94-572">ABSENTEE</span></span>               | <span data-ttu-id="11c94-573">Ausente</span><span class="sxs-lookup"><span data-stu-id="11c94-573">Absentee</span></span>                       | <span data-ttu-id="11c94-574">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-574">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-575">OTHER</span><span class="sxs-lookup"><span data-stu-id="11c94-575">OTHER</span></span>                  | <span data-ttu-id="11c94-576">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="11c94-576">Other Reasons</span></span>                  | <span data-ttu-id="11c94-577">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-577">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-578">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="11c94-578">CLOSURE</span></span>                | <span data-ttu-id="11c94-579">Cierre de operaciones</span><span class="sxs-lookup"><span data-stu-id="11c94-579">Business Closure</span></span>               | <span data-ttu-id="11c94-580">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-580">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-581">MUERTE</span><span class="sxs-lookup"><span data-stu-id="11c94-581">DEATH</span></span>                  | <span data-ttu-id="11c94-582">Muerte</span><span class="sxs-lookup"><span data-stu-id="11c94-582">Death</span></span>                          | <span data-ttu-id="11c94-583">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-583">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-584">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="11c94-584">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="11c94-585">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="11c94-585">Leave of Absence</span></span>               | <span data-ttu-id="11c94-586">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-586">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-587">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="11c94-587">CONTRACTEND</span></span>            | <span data-ttu-id="11c94-588">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="11c94-588">End of Contract</span></span>                | <span data-ttu-id="11c94-589">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="11c94-589">Terminate worker</span></span>     |
| <span data-ttu-id="11c94-590">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="11c94-590">SALARYCHANGE</span></span>           | <span data-ttu-id="11c94-591">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="11c94-591">Change of Salary</span></span>               | <span data-ttu-id="11c94-592">Compensación</span><span class="sxs-lookup"><span data-stu-id="11c94-592">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="11c94-593">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="11c94-593">Terms of employment</span></span>

<span data-ttu-id="11c94-594">Las condiciones laborales se usan para crear categorías de condiciones laborales.</span><span class="sxs-lookup"><span data-stu-id="11c94-594">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="11c94-595">Las condiciones se asignan a Dayforce como valores de indicador de empleo.</span><span class="sxs-lookup"><span data-stu-id="11c94-595">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="11c94-596">Las siguientes condiciones laborales y descripciones son obligatorias.</span><span class="sxs-lookup"><span data-stu-id="11c94-596">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="11c94-597">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="11c94-597">Terms of employment</span></span>   | <span data-ttu-id="11c94-598">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c94-598">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="11c94-599">Normal</span><span class="sxs-lookup"><span data-stu-id="11c94-599">Regular</span></span>               | <span data-ttu-id="11c94-600">Normal</span><span class="sxs-lookup"><span data-stu-id="11c94-600">Regular</span></span>     |
| <span data-ttu-id="11c94-601">Directo</span><span class="sxs-lookup"><span data-stu-id="11c94-601">Direct</span></span>                | <span data-ttu-id="11c94-602">Directo</span><span class="sxs-lookup"><span data-stu-id="11c94-602">Direct</span></span>      |
| <span data-ttu-id="11c94-603">Prácticas</span><span class="sxs-lookup"><span data-stu-id="11c94-603">Internship</span></span>            | <span data-ttu-id="11c94-604">Prácticas</span><span class="sxs-lookup"><span data-stu-id="11c94-604">Internship</span></span>  |
| <span data-ttu-id="11c94-605">Permanente</span><span class="sxs-lookup"><span data-stu-id="11c94-605">Permanent</span></span>             | <span data-ttu-id="11c94-606">Permanente</span><span class="sxs-lookup"><span data-stu-id="11c94-606">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="11c94-607">Estado civil</span><span class="sxs-lookup"><span data-stu-id="11c94-607">Marital status</span></span>

<span data-ttu-id="11c94-608">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="11c94-608">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="11c94-609">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-609">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="11c94-610">Talent</span><span class="sxs-lookup"><span data-stu-id="11c94-610">Talent</span></span>                 | <span data-ttu-id="11c94-611">Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-611">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="11c94-612">Casado/a</span><span class="sxs-lookup"><span data-stu-id="11c94-612">Married</span></span>                | <span data-ttu-id="11c94-613">Casado/a</span><span class="sxs-lookup"><span data-stu-id="11c94-613">Married</span></span>                   |
| <span data-ttu-id="11c94-614">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="11c94-614">Single</span></span>                 | <span data-ttu-id="11c94-615">Soltero/a</span><span class="sxs-lookup"><span data-stu-id="11c94-615">Single</span></span>                    |
| <span data-ttu-id="11c94-616">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="11c94-616">Widowed</span></span>                | <span data-ttu-id="11c94-617">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="11c94-617">Widowed</span></span>                   |
| <span data-ttu-id="11c94-618">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="11c94-618">Divorced</span></span>               | <span data-ttu-id="11c94-619">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="11c94-619">Divorced</span></span>                  |
| <span data-ttu-id="11c94-620">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="11c94-620">Registered Partnership</span></span> | <span data-ttu-id="11c94-621">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="11c94-621">Domestic Partnership</span></span>      |
| <span data-ttu-id="11c94-622">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="11c94-622">None</span></span>                   | <span data-ttu-id="11c94-623">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="11c94-623">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="11c94-624">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="11c94-624">Cohabiting</span></span>             | <span data-ttu-id="11c94-625">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="11c94-625">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="11c94-626">Género</span><span class="sxs-lookup"><span data-stu-id="11c94-626">Gender</span></span>

<span data-ttu-id="11c94-627">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="11c94-627">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="11c94-628">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-628">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="11c94-629">Talent</span><span class="sxs-lookup"><span data-stu-id="11c94-629">Talent</span></span>       | <span data-ttu-id="11c94-630">Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-630">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="11c94-631">Hombre</span><span class="sxs-lookup"><span data-stu-id="11c94-631">Male</span></span>         | <span data-ttu-id="11c94-632">Hombre</span><span class="sxs-lookup"><span data-stu-id="11c94-632">Male</span></span>                      |
| <span data-ttu-id="11c94-633">Mujer</span><span class="sxs-lookup"><span data-stu-id="11c94-633">Female</span></span>       | <span data-ttu-id="11c94-634">Mujer</span><span class="sxs-lookup"><span data-stu-id="11c94-634">Female</span></span>                    |
| <span data-ttu-id="11c94-635">No específico</span><span class="sxs-lookup"><span data-stu-id="11c94-635">Non-specific</span></span> | <span data-ttu-id="11c94-636">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="11c94-636">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="11c94-637">Método de pago</span><span class="sxs-lookup"><span data-stu-id="11c94-637">Payment method</span></span>

<span data-ttu-id="11c94-638">Los métodos de pago ofrecen al empleado y la empresa una forma de describir cómo se pagará a los empleados.</span><span class="sxs-lookup"><span data-stu-id="11c94-638">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="11c94-639">Los métodos de pago se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="11c94-639">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="11c94-640">En la siguiente tabla se muestra cómo los métodos de pago se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-640">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="11c94-641">Talent</span><span class="sxs-lookup"><span data-stu-id="11c94-641">Talent</span></span>             | <span data-ttu-id="11c94-642">Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-642">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="11c94-643">Efectivo</span><span class="sxs-lookup"><span data-stu-id="11c94-643">Cash</span></span>               | <span data-ttu-id="11c94-644">Efectivo</span><span class="sxs-lookup"><span data-stu-id="11c94-644">Cash</span></span>                      |
| <span data-ttu-id="11c94-645">Pago electrónico</span><span class="sxs-lookup"><span data-stu-id="11c94-645">Electronic Payment</span></span> | <span data-ttu-id="11c94-646">Transferir</span><span class="sxs-lookup"><span data-stu-id="11c94-646">Transfer</span></span>                  |
| <span data-ttu-id="11c94-647">Comprobación</span><span class="sxs-lookup"><span data-stu-id="11c94-647">Check</span></span>              | <span data-ttu-id="11c94-648">Cheque</span><span class="sxs-lookup"><span data-stu-id="11c94-648">Cheque</span></span>                    |
| <span data-ttu-id="11c94-649">Efecto bancario</span><span class="sxs-lookup"><span data-stu-id="11c94-649">Bank Draft</span></span>         | <span data-ttu-id="11c94-650">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="11c94-650">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="11c94-651">Otras</span><span class="sxs-lookup"><span data-stu-id="11c94-651">Other</span></span>              | <span data-ttu-id="11c94-652">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="11c94-652">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="11c94-653">Tipo de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="11c94-653">Bank account type</span></span>

<span data-ttu-id="11c94-654">Los tipos de cuenta bancaria se usan para los pagos electrónicos a los empleados.</span><span class="sxs-lookup"><span data-stu-id="11c94-654">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="11c94-655">Los tipos de cuenta bancaria se asignan a Dayforce como información de cuenta de transferencia.</span><span class="sxs-lookup"><span data-stu-id="11c94-655">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="11c94-656">Los tipos de cuenta bancaria se convierten, según proceda, en los valores aceptados en la integración.</span><span class="sxs-lookup"><span data-stu-id="11c94-656">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="11c94-657">Talent</span><span class="sxs-lookup"><span data-stu-id="11c94-657">Talent</span></span>            | <span data-ttu-id="11c94-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-658">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="11c94-659">Cuenta corriente</span><span class="sxs-lookup"><span data-stu-id="11c94-659">Checking Account</span></span>  | <span data-ttu-id="11c94-660">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="11c94-660">CheckingAccount</span></span>           |
| <span data-ttu-id="11c94-661">Cuenta de nómina</span><span class="sxs-lookup"><span data-stu-id="11c94-661">Payroll Account</span></span>   | <span data-ttu-id="11c94-662">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="11c94-662">PayrollAccount</span></span>            |
| <span data-ttu-id="11c94-663">Cuenta de ahorros</span><span class="sxs-lookup"><span data-stu-id="11c94-663">Savings Account</span></span>   | <span data-ttu-id="11c94-664">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="11c94-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="11c94-665">Cuenta de BankGirot</span><span class="sxs-lookup"><span data-stu-id="11c94-665">BankGirot account</span></span> | <span data-ttu-id="11c94-666">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="11c94-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="11c94-667">Cuenta de PlusGirot</span><span class="sxs-lookup"><span data-stu-id="11c94-667">PlusGirot account</span></span> | <span data-ttu-id="11c94-668">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="11c94-668">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="11c94-669">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="11c94-669">Earning codes</span></span>

<span data-ttu-id="11c94-670">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="11c94-670">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="11c94-671">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="11c94-671">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="11c94-672">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="11c94-672">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="11c94-673">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="11c94-673">Supported frequencies</span></span>

- <span data-ttu-id="11c94-674">Todas</span><span class="sxs-lookup"><span data-stu-id="11c94-674">All</span></span>
- <span data-ttu-id="11c94-675">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="11c94-675">EVERYPAY</span></span>
- <span data-ttu-id="11c94-676">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="11c94-676">EACHPAYPERIOD</span></span>
- <span data-ttu-id="11c94-677">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="11c94-677">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="11c94-678">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="11c94-678">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="11c94-679">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-679">1OFMTH</span></span>
- <span data-ttu-id="11c94-680">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-680">LASTOFMTH</span></span>
- <span data-ttu-id="11c94-681">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-681">2OFMTH</span></span>
- <span data-ttu-id="11c94-682">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-682">3OFMTH</span></span>
- <span data-ttu-id="11c94-683">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-683">4OFMTH</span></span>
- <span data-ttu-id="11c94-684">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-684">5OFMTH</span></span>
- <span data-ttu-id="11c94-685">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-685">1N2OFMTH</span></span>
- <span data-ttu-id="11c94-686">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-686">3N4OFMTH</span></span>
- <span data-ttu-id="11c94-687">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-687">1N3OFMTH</span></span>
- <span data-ttu-id="11c94-688">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-688">1N4OFMTH</span></span>
- <span data-ttu-id="11c94-689">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-689">2N3OFMTH</span></span>
- <span data-ttu-id="11c94-690">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-690">2N4OFMTH</span></span>
- <span data-ttu-id="11c94-691">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-691">1N2N3OFMTH</span></span>
- <span data-ttu-id="11c94-692">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-692">1N2N4OFMTH</span></span>
- <span data-ttu-id="11c94-693">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-693">1N3N4OFMTH</span></span>
- <span data-ttu-id="11c94-694">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-694">2N3N4OFMTH</span></span>
- <span data-ttu-id="11c94-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="11c94-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="11c94-696">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="11c94-696">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="11c94-697">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="11c94-697">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="11c94-698">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="11c94-698">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="11c94-699">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="11c94-699">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="11c94-700">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="11c94-700">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="11c94-701">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="11c94-701">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="11c94-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="11c94-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="11c94-703">Direcciones</span><span class="sxs-lookup"><span data-stu-id="11c94-703">Addresses</span></span>

<span data-ttu-id="11c94-704">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="11c94-704">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="11c94-705">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="11c94-705">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="11c94-706">Talent</span><span class="sxs-lookup"><span data-stu-id="11c94-706">Talent</span></span>              | <span data-ttu-id="11c94-707">Dayforce</span><span class="sxs-lookup"><span data-stu-id="11c94-707">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="11c94-708">País/región</span><span class="sxs-lookup"><span data-stu-id="11c94-708">Country/Region</span></span>      | <span data-ttu-id="11c94-709">Código de país</span><span class="sxs-lookup"><span data-stu-id="11c94-709">Country Code</span></span>          |
| <span data-ttu-id="11c94-710">Código postal</span><span class="sxs-lookup"><span data-stu-id="11c94-710">Zip/Postal Code</span></span>     | <span data-ttu-id="11c94-711">Código postal</span><span class="sxs-lookup"><span data-stu-id="11c94-711">Postal Code</span></span>           |
| <span data-ttu-id="11c94-712">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="11c94-712">State</span></span>               | <span data-ttu-id="11c94-713">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="11c94-713">State Code</span></span>            |
| <span data-ttu-id="11c94-714">Población</span><span class="sxs-lookup"><span data-stu-id="11c94-714">City</span></span>                | <span data-ttu-id="11c94-715">Población</span><span class="sxs-lookup"><span data-stu-id="11c94-715">City</span></span>                  |
| <span data-ttu-id="11c94-716">Comarca</span><span class="sxs-lookup"><span data-stu-id="11c94-716">County</span></span>              | <span data-ttu-id="11c94-717">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="11c94-717">County (Municipality)</span></span> |
| <span data-ttu-id="11c94-718">Calle</span><span class="sxs-lookup"><span data-stu-id="11c94-718">Street</span></span>              | <span data-ttu-id="11c94-719">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="11c94-719">Address Line 1</span></span>        |
| <span data-ttu-id="11c94-720">Número de calle</span><span class="sxs-lookup"><span data-stu-id="11c94-720">Street Number</span></span>       | <span data-ttu-id="11c94-721">Línea de dirección 2</span><span class="sxs-lookup"><span data-stu-id="11c94-721">Address Line 2</span></span>        |
| <span data-ttu-id="11c94-722">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="11c94-722">Building Complement</span></span> | <span data-ttu-id="11c94-723">Línea de dirección 5</span><span class="sxs-lookup"><span data-stu-id="11c94-723">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="11c94-724">Número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="11c94-724">Passport number</span></span>

<span data-ttu-id="11c94-725">Los empleados pueden declarar la información del pasaporte.</span><span class="sxs-lookup"><span data-stu-id="11c94-725">Employees can declare passport information.</span></span> <span data-ttu-id="11c94-726">Esta información es del tipo de identificación **Pasaporte** y se integra en Dayforce como parte de la información específica de México de un empleado.</span><span class="sxs-lookup"><span data-stu-id="11c94-726">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="11c94-727">Tipo de identificación = "Pasaporte"</span><span class="sxs-lookup"><span data-stu-id="11c94-727">Identification Type = "Passport"</span></span>
- <span data-ttu-id="11c94-728">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="11c94-728">Issued Date</span></span>
- <span data-ttu-id="11c94-729">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="11c94-729">Expiration Date</span></span>

<span data-ttu-id="11c94-730">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Pasaporte**.</span><span class="sxs-lookup"><span data-stu-id="11c94-730">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="11c94-731">Sin embargo, solo la entrada de pasaporte activa actual se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-731">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="11c94-732">Si todas las entradas de pasaporte han caducado, el pasaporte que se emitió más recientemente se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="11c94-732">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
