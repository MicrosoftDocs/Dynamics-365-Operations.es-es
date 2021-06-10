---
title: Configurar la integración con Dayforce
description: La integración entre Microsoft Dynamics 365 Human Resources y Ceridian Dayforce se basa en varios pasos de configuración que se describen en este artículo. Debe configurar la integración en Human Resources y Dayforce para poder procesar un período de pago.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d150daa92fe79cf6620ce5ddf1a01f369c64053
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051506"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="b5788-104">Configurar la integración con Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b5788-105">La integración entre Microsoft Dynamics 365 Human Resources y Ceridian Dayforce se basa en varios pasos de configuración que se describen en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b5788-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="b5788-106">Debe configurar la integración en Human Resources y Dayforce para poder procesar un período de pago.</span><span class="sxs-lookup"><span data-stu-id="b5788-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="b5788-107">Cuando se utiliza un servicio como Dayforce para completar períodos de pago, debe habilitar la integración en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5788-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="b5788-108">La integración necesita los datos específicos de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5788-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="b5788-109">Por lo tanto, debe comprobar que los datos que se asignen a Dayforce se hayan configurado en Human Resources de una forma que admita la integración.</span><span class="sxs-lookup"><span data-stu-id="b5788-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="b5788-110">La integración utiliza las amplias categorías de datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5788-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="b5788-111">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-111">Human resources data</span></span>
- <span data-ttu-id="b5788-112">Catos de compensación</span><span class="sxs-lookup"><span data-stu-id="b5788-112">Compensation data</span></span>
- <span data-ttu-id="b5788-113">Datos de nómina, como ciclos de pago, períodos de sueldo, y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="b5788-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="b5788-114">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="b5788-114">Worker data</span></span>

<span data-ttu-id="b5788-115">Este artículo describe los pasos que debe seguir para habilitar la integración.</span><span class="sxs-lookup"><span data-stu-id="b5788-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="b5788-116">También explica los tipos de datos y los detalles de configuración que requiere la integración.</span><span class="sxs-lookup"><span data-stu-id="b5788-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="b5788-117">Habilitar la integración</span><span class="sxs-lookup"><span data-stu-id="b5788-117">Enable the integration</span></span>

<span data-ttu-id="b5788-118">En Human Resources, debe activar la integración y especificar información de configuración para conectarse a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="b5788-119">Si desea que la transacción de contabilidad general que se genera se importe en Microsoft Dynamics 365 Finance, también debe configurar una cuenta de almacenamiento de Microsoft Azure y especificar la cadena de conexión Azure Storage en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b5788-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="b5788-120">Para activar la integración en Human Resources, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b5788-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="b5788-121">En la página **Administración del sistema** , seleccione **Configuración de la integración**.</span><span class="sxs-lookup"><span data-stu-id="b5788-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="b5788-122">Permite especificar el extremo del Protocolo de transferencia de archivos (FTP) y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="b5788-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="b5788-123">Escriba el nombre de usuario y contraseña del usuario que accederá al extremo y la ruta de carpeta de FTP seguro.</span><span class="sxs-lookup"><span data-stu-id="b5788-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="b5788-124">Pruebe la conexión, como sea necesario, y establezca la opción **Habilitar la integración de nómina** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b5788-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="b5788-125">Cuando está activada la integración, se crean el paquete y los archivos de exportación de datos, y se establece la frecuencia.</span><span class="sxs-lookup"><span data-stu-id="b5788-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="b5788-126">Puede cambiar esta frecuencia como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b5788-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="b5788-127">Para obtener más información acerca de las cuentas de almacenamiento de Azure y las cadenas de conexión de Azure Storage, consulte los artículos de Azure siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5788-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="b5788-128">Acerca de las cuentas de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="b5788-128">About Azure storage accounts</span></span>](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="b5788-129">Configurar las cadenas de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="b5788-129">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="b5788-130">Detalles técnicos cuando está habilitada la integración de nóminas</span><span class="sxs-lookup"><span data-stu-id="b5788-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="b5788-131">La activación de la integración de nóminas tiene dos efectos primarios:</span><span class="sxs-lookup"><span data-stu-id="b5788-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="b5788-132">Se crea un proyecto de exportación de datos con el nombre "Exportación de la integración de nóminas".</span><span class="sxs-lookup"><span data-stu-id="b5788-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="b5788-133">Este proyecto contiene las entidades y los campos necesarios para la integración de nóminas.</span><span class="sxs-lookup"><span data-stu-id="b5788-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="b5788-134">Para examinar el proyecto, vaya **Administración del sistema**, seleccione el icono **Administración de datos** y abra el proyecto de datos de la lista de proyectos.</span><span class="sxs-lookup"><span data-stu-id="b5788-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="b5788-135">Este trabajo por lotes ejecuta el proyecto de exportación de datos, cifra el paquete de datos resultante y transfiere el archivo del paquete de datos al extremo de SFTP configurado en la pantalla **Configuración de la integración**.</span><span class="sxs-lookup"><span data-stu-id="b5788-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="b5788-136">El paquete de datos transferido al extremo de SFTP se cifra mediante una clave que es única para el paquete.</span><span class="sxs-lookup"><span data-stu-id="b5788-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="b5788-137">La clave está en Azure Key Vault, a la que solo puede acceder Ceridian.</span><span class="sxs-lookup"><span data-stu-id="b5788-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="b5788-138">No es posible descifrar y examinar el contenido del paquete de datos.</span><span class="sxs-lookup"><span data-stu-id="b5788-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="b5788-139">Si tiene que examinar el contenido del paquete de datos, debe exportar manualmente el proyecto de datos "Exportación de la integración de nóminas", descargarlo y abrirlo.</span><span class="sxs-lookup"><span data-stu-id="b5788-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="b5788-140">La exportación manual aplicará cifrado o transferirá el paquete.</span><span class="sxs-lookup"><span data-stu-id="b5788-140">Manual export will not apply encryption or transfer the package.</span></span>
> <span data-ttu-id="b5788-141">Para los casos en los que los archivos de integración se envían desde un UAT de Dynamics 365 Human Resources o entorno de espacio aislado a un entorno Ceridian Dayforce Test, puede utilizar la siguiente URL del almacén de claves: https://payrollintegrationprod.vault.azure.net.</span><span class="sxs-lookup"><span data-stu-id="b5788-141">For instances where the integration files are sent from a Dynamics 365 Human Resources UAT or Sandbox environment to a Ceridian Dayforce Test environment, you can use the following key vault URL: https://payrollintegrationprod.vault.azure.net.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="b5788-142">Configurar los datos</span><span class="sxs-lookup"><span data-stu-id="b5788-142">Configure your data</span></span> 

<span data-ttu-id="b5788-143">Para procesar las nóminas, debe configurar los datos de recursos humanos en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5788-143">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="b5788-144">Debe configurar datos de organización, como los trabajos y los puestos, así como las prestaciones y la información de compensación.</span><span class="sxs-lookup"><span data-stu-id="b5788-144">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="b5788-145">Esta información proporciona la información de empleo, pago y deducciones que se necesita para producir el sueldo del empleado.</span><span class="sxs-lookup"><span data-stu-id="b5788-145">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="b5788-146">Datos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-146">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="b5788-147">Beneficios</span><span class="sxs-lookup"><span data-stu-id="b5788-147">Benefits</span></span> 

<span data-ttu-id="b5788-148">Recursos humanos ofrece herramientas para la configuración y el mantenimiento de prestaciones, deducciones y los planes de compensación de los trabajadores que una organización ofrece o procesa para sus trabajadores.</span><span class="sxs-lookup"><span data-stu-id="b5788-148">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="b5788-149">Al crear las prestaciones, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-149">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="b5788-150">Planes de prestaciones</span><span class="sxs-lookup"><span data-stu-id="b5788-150">Benefit plans</span></span>

- <span data-ttu-id="b5788-151">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-151">Plan (required)</span></span>
- <span data-ttu-id="b5788-152">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-152">Type (required)</span></span>
- <span data-ttu-id="b5788-153">Impacto de nómina (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-153">Payroll impact (required)</span></span>
- <span data-ttu-id="b5788-154">Recuperar atrasos</span><span class="sxs-lookup"><span data-stu-id="b5788-154">Recover arrears</span></span>
- <span data-ttu-id="b5788-155">Método de deducción</span><span class="sxs-lookup"><span data-stu-id="b5788-155">Deduction method</span></span>
- <span data-ttu-id="b5788-156">Prioridad de deducción</span><span class="sxs-lookup"><span data-stu-id="b5788-156">Deduction priority</span></span>
- <span data-ttu-id="b5788-157">Período de límite</span><span class="sxs-lookup"><span data-stu-id="b5788-157">Limit period</span></span>
- <span data-ttu-id="b5788-158">Importe límite</span><span class="sxs-lookup"><span data-stu-id="b5788-158">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="b5788-159">Beneficios</span><span class="sxs-lookup"><span data-stu-id="b5788-159">Benefits</span></span>

- <span data-ttu-id="b5788-160">Plan (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-160">Plan (required)</span></span>
- <span data-ttu-id="b5788-161">Tipo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-161">Type (required)</span></span>
- <span data-ttu-id="b5788-162">Opción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-162">Option (required)</span></span>
- <span data-ttu-id="b5788-163">Identificador de prestación (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-163">Benefit ID (required)</span></span>
- <span data-ttu-id="b5788-164">Frecuencia</span><span class="sxs-lookup"><span data-stu-id="b5788-164">Frequency</span></span>
- <span data-ttu-id="b5788-165">Base</span><span class="sxs-lookup"><span data-stu-id="b5788-165">Basis</span></span>
- <span data-ttu-id="b5788-166">Importe o índice</span><span class="sxs-lookup"><span data-stu-id="b5788-166">Amount or rate</span></span>
- <span data-ttu-id="b5788-167">Código de ganancias</span><span class="sxs-lookup"><span data-stu-id="b5788-167">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="b5788-168">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="b5788-168">Supported frequencies</span></span> 

- <span data-ttu-id="b5788-169">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="b5788-169">Weekly</span></span>
- <span data-ttu-id="b5788-170">Quincenal</span><span class="sxs-lookup"><span data-stu-id="b5788-170">Bi-weekly</span></span>
- <span data-ttu-id="b5788-171">Bimensual</span><span class="sxs-lookup"><span data-stu-id="b5788-171">Semi-monthly</span></span>
- <span data-ttu-id="b5788-172">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="b5788-172">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="b5788-173">Bases admitidas</span><span class="sxs-lookup"><span data-stu-id="b5788-173">Supported bases</span></span> 

- <span data-ttu-id="b5788-174">Importe fijo</span><span class="sxs-lookup"><span data-stu-id="b5788-174">Fixed amount</span></span>
- <span data-ttu-id="b5788-175">Porcentaje de ganancias</span><span class="sxs-lookup"><span data-stu-id="b5788-175">Percent of earnings</span></span>
- <span data-ttu-id="b5788-176">Horas productivas</span><span class="sxs-lookup"><span data-stu-id="b5788-176">Productive hours</span></span>

<span data-ttu-id="b5788-177">Dayforce crea las deducciones siguientes, según el impacto de nómina que hay definido en el plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="b5788-177">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="b5788-178">Selección en Human Resources</span><span class="sxs-lookup"><span data-stu-id="b5788-178">Selection in Human Resources</span></span>        | <span data-ttu-id="b5788-179">Resultado en Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-179">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="b5788-180">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b5788-180">None</span></span>                       | <span data-ttu-id="b5788-181">No se crea ninguna deducción.</span><span class="sxs-lookup"><span data-stu-id="b5788-181">No deduction is created.</span></span>                      |
| <span data-ttu-id="b5788-182">Solo deducción</span><span class="sxs-lookup"><span data-stu-id="b5788-182">Deduction only</span></span>             | <span data-ttu-id="b5788-183">Se crea una deducción del empleado.</span><span class="sxs-lookup"><span data-stu-id="b5788-183">An employee deduction is created.</span></span>             |
| <span data-ttu-id="b5788-184">Solo contribución</span><span class="sxs-lookup"><span data-stu-id="b5788-184">Contribution only</span></span>          | <span data-ttu-id="b5788-185">Se crea una deducción del empresario.</span><span class="sxs-lookup"><span data-stu-id="b5788-185">An employer deduction is created.</span></span>             |
| <span data-ttu-id="b5788-186">Deducción y contribución</span><span class="sxs-lookup"><span data-stu-id="b5788-186">Deduction and contribution</span></span> | <span data-ttu-id="b5788-187">Se crean las deducciones del empleado y del empresario.</span><span class="sxs-lookup"><span data-stu-id="b5788-187">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="b5788-188">Para obtener más información sobre cómo definir y administrar un programa de prestaciones, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="b5788-188">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="b5788-189">Proporcionar un programa de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="b5788-189">Deliver an employee benefits program</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="b5788-190">Crear un nuevo beneficio</span><span class="sxs-lookup"><span data-stu-id="b5788-190">Create a new benefit</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="b5788-191">Definir reglas y directivas de idoneidad para prestaciones</span><span class="sxs-lookup"><span data-stu-id="b5788-191">Define benefit eligibility rules and policies</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="b5788-192">Inscribir y quitar prestaciones para trabajadores</span><span class="sxs-lookup"><span data-stu-id="b5788-192">Enroll and remove benefits from workers</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="b5788-193">Compensación</span><span class="sxs-lookup"><span data-stu-id="b5788-193">Compensation</span></span> 

<span data-ttu-id="b5788-194">La gestión de compensaciones se usa para controlar la entrega de salarios base y primas.</span><span class="sxs-lookup"><span data-stu-id="b5788-194">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="b5788-195">El sueldo base fijo de un empleado y los aumentos por méritos se controlan mediante planes de compensación fijos.</span><span class="sxs-lookup"><span data-stu-id="b5788-195">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="b5788-196">El pago de incentivos, como los pagos de bonificación, las primas por rendimiento, las acciones y las concesiones, así como también las primas ocasionales, se controlan a través de planes de compensación variable.</span><span class="sxs-lookup"><span data-stu-id="b5788-196">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="b5788-197">Dayforce utiliza la información de compensación para calcular la tarifa por hora o anual de un empleado.</span><span class="sxs-lookup"><span data-stu-id="b5788-197">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="b5788-198">Se requieren planes de compensación fija y conversiones de índice salarial.</span><span class="sxs-lookup"><span data-stu-id="b5788-198">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="b5788-199">Los empleados deben estar asociados a un plan de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="b5788-199">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="b5788-200">Para obtener más información acerca de los panes de compensación, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="b5788-200">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="b5788-201">Crear planes de compensación fija</span><span class="sxs-lookup"><span data-stu-id="b5788-201">Create fixed compensation plans</span></span>](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="b5788-202">Crear planes de compensación variable</span><span class="sxs-lookup"><span data-stu-id="b5788-202">Create variable compensation plans</span></span>](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="b5788-203">Desarrollar planes y estructura de salarios o compensaciones</span><span class="sxs-lookup"><span data-stu-id="b5788-203">Develop salary/compensation structure and plans</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="b5788-204">Procesar compensaciones</span><span class="sxs-lookup"><span data-stu-id="b5788-204">Process compensation</span></span>](/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="b5788-205">Definición del proceso de compensación y el cálculo de resultados</span><span class="sxs-lookup"><span data-stu-id="b5788-205">Define compensation process and calculate results</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="b5788-206">Inscribir a un empleado en un plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="b5788-206">Enroll an employee in a fixed compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="b5788-207">Inscribir a un empleado en un plan de compensación variable</span><span class="sxs-lookup"><span data-stu-id="b5788-207">Enroll an employee in a variable compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="b5788-208">Trabajos</span><span class="sxs-lookup"><span data-stu-id="b5788-208">Jobs</span></span> 

<span data-ttu-id="b5788-209">Un trabajo es un conjunto de las tareas y responsabilidades que deberá cumplir la persona que realiza un trabajo.</span><span class="sxs-lookup"><span data-stu-id="b5788-209">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="b5788-210">Para obtener más información, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="b5788-210">For more information, see the following articles:</span></span>

- [<span data-ttu-id="b5788-211">Configurar los componentes de un trabajo</span><span class="sxs-lookup"><span data-stu-id="b5788-211">Setting up the components of a job</span></span>](/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="b5788-212">Definir nuevos trabajos</span><span class="sxs-lookup"><span data-stu-id="b5788-212">Define new jobs</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="b5788-213">Puestos</span><span class="sxs-lookup"><span data-stu-id="b5788-213">Positions</span></span>

<span data-ttu-id="b5788-214">Un puesto es un caso individual de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="b5788-214">A position is an individual instance of a job.</span></span> <span data-ttu-id="b5788-215">Por ejemplo, el puesto "Director de ventas (Este)" es uno de los puestos asociados al trabajo "Director de ventas".</span><span class="sxs-lookup"><span data-stu-id="b5788-215">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="b5788-216">Un puesto existe en un departamento.</span><span class="sxs-lookup"><span data-stu-id="b5788-216">A position exists in a department.</span></span> <span data-ttu-id="b5788-217">Solo un trabajador puede asociarse solo a cada puesto.</span><span class="sxs-lookup"><span data-stu-id="b5788-217">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="b5788-218">Tenga en cuenta los siguientes datos y configuración al configurar los puestos:</span><span class="sxs-lookup"><span data-stu-id="b5788-218">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="b5788-219">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-219">Position (required)</span></span>
- <span data-ttu-id="b5788-220">Descripción (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-220">Description (required)</span></span>
- <span data-ttu-id="b5788-221">Trabajo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-221">Job (required)</span></span>
- <span data-ttu-id="b5788-222">Departamento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-222">Department (required)</span></span>
- <span data-ttu-id="b5788-223">Tipo de puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-223">Position type (required)</span></span>
- <span data-ttu-id="b5788-224">Equivalente de jornada completa</span><span class="sxs-lookup"><span data-stu-id="b5788-224">Full-time equivalent</span></span>
- <span data-ttu-id="b5788-225">Horas ordinarias anuales (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-225">Annual regular hours (required)</span></span>
- <span data-ttu-id="b5788-226">Pagado por la entidad jurídica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-226">Paid by legal entity (required)</span></span>
- <span data-ttu-id="b5788-227">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-227">Pay cycle (required)</span></span>
- <span data-ttu-id="b5788-228">Dimensión financiera predeterminada – Centro de coste (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-228">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="b5788-229">Asignación de trabajador – Trabajador, inicio de la asignación, final de la asignación, código de motivo</span><span class="sxs-lookup"><span data-stu-id="b5788-229">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="b5788-230">Si varios puestos en el mismo departamento están asociados al mismo trabajo, se consolidan en un solo puesto en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-230">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="b5788-231">Para obtener más información, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="b5788-231">For more information, see the following articles:</span></span>

- [<span data-ttu-id="b5788-232">Organizar los recursos mediante departamentos, trabajos y puestos</span><span class="sxs-lookup"><span data-stu-id="b5788-232">Organize your workforce using departments, jobs, and positions</span></span>](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="b5788-233">Configurar puestos</span><span class="sxs-lookup"><span data-stu-id="b5788-233">Set up positions</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="b5788-234">Departamentos</span><span class="sxs-lookup"><span data-stu-id="b5788-234">Departments</span></span>

<span data-ttu-id="b5788-235">Un departamneto es una unidad operativa que representa una categoría o un área funcional de la organización.</span><span class="sxs-lookup"><span data-stu-id="b5788-235">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="b5788-236">Un departamento es responsable de un área específica de la organización, como ventas, contabilidad o recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="b5788-236">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="b5788-237">Puede usar departamentos para informar sobre las áreas funcionales.</span><span class="sxs-lookup"><span data-stu-id="b5788-237">You can use departments to report on functional areas.</span></span> <span data-ttu-id="b5788-238">Los departamentos pueden tener responsabilidad de pérdidas y ganancias.</span><span class="sxs-lookup"><span data-stu-id="b5788-238">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="b5788-239">Para obtener más información, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="b5788-239">For more information, see the following articles:</span></span>

- [<span data-ttu-id="b5788-240">Crear un departamento y asociarlo a la jerarquía del departamento</span><span class="sxs-lookup"><span data-stu-id="b5788-240">Create a department and associate it with the department hierarchy</span></span>](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="b5788-241">Definir nuevos departamentos</span><span class="sxs-lookup"><span data-stu-id="b5788-241">Define new departments</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="b5788-242">Ciclos y períodos de pago</span><span class="sxs-lookup"><span data-stu-id="b5788-242">Pay cycles and pay periods</span></span>

<span data-ttu-id="b5788-243">Un ciclo de pago determina la frecuencia con la que se ejecuta el cálculo de nómina y los días específicos en los que se paga a los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="b5788-243">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="b5788-244">Por ejemplo, un ciclo de pago puede ser mensual y a los empleados se les podría pagar el último día del mes.</span><span class="sxs-lookup"><span data-stu-id="b5788-244">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="b5788-245">De forma alternativa, un ciclo de pago puede ser semanal y a los empleados se les podría pagar el martes después del final del período de pago.</span><span class="sxs-lookup"><span data-stu-id="b5788-245">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="b5788-246">Los ciclos de pago se asignan a los puestos para controlar cuándo se paga a los trabajadores en esos puestos.</span><span class="sxs-lookup"><span data-stu-id="b5788-246">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="b5788-247">Después de crear ciclos de pago, puede generar los períodos de pago para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="b5788-247">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="b5788-248">Cada período de pago incluye una fecha de pago predeterminada basada en la información que proporcione.</span><span class="sxs-lookup"><span data-stu-id="b5788-248">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="b5788-249">Sin embargo, puede modificar la fecha de pago predeterminada en un período de pago para permitir excepciones, por ejemplo, cuando la fecha de pago se encuentra en un día festivo.</span><span class="sxs-lookup"><span data-stu-id="b5788-249">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="b5788-250">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="b5788-250">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="b5788-251">Ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-251">Pay cycle (required)</span></span>
- <span data-ttu-id="b5788-252">Frecuencia del ciclo de pago (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-252">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="b5788-253">Fecha de inicio del período (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-253">Period start date (first pay period required)</span></span>
- <span data-ttu-id="b5788-254">Fecha de pago predeterminado (primer período de pago obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-254">Default payment date (first pay period required)</span></span>

<span data-ttu-id="b5788-255">Esta información se integra con Dayforce como grupos salariales y se separa por país o región para cada ciclo de pago.</span><span class="sxs-lookup"><span data-stu-id="b5788-255">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="b5788-256">Al menos se debe generar un período de sueldo antes de la integración.</span><span class="sxs-lookup"><span data-stu-id="b5788-256">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="b5788-257">Dayforce genera los calendarios de grupo salarial y las fechas de pago, en función de la fecha inicial del primer período de pago y la fecha de pago predeterminada que se configuran en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5788-257">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="b5788-258">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="b5788-258">Earning codes</span></span>

<span data-ttu-id="b5788-259">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="b5788-259">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="b5788-260">Los códigos tienen distintos parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="b5788-260">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="b5788-261">La siguiente información se usa en Dayforce:</span><span class="sxs-lookup"><span data-stu-id="b5788-261">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="b5788-262">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-262">Earning Code (required)</span></span>
- <span data-ttu-id="b5788-263">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5788-263">Description</span></span>
- <span data-ttu-id="b5788-264">Unidad de medida</span><span class="sxs-lookup"><span data-stu-id="b5788-264">Unit of measure</span></span>
- <span data-ttu-id="b5788-265">Productivo</span><span class="sxs-lookup"><span data-stu-id="b5788-265">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="b5788-266">Datos de trabajadores</span><span class="sxs-lookup"><span data-stu-id="b5788-266">Worker data</span></span>

<span data-ttu-id="b5788-267">Los registros para los diferentes tipos de trabajadores que tiene son importantes para los sistemas de recursos humanos y nómina.</span><span class="sxs-lookup"><span data-stu-id="b5788-267">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="b5788-268">La información que se indique se puede utilizar para efectuar un seguimiento de los trabajadores y su información personal.</span><span class="sxs-lookup"><span data-stu-id="b5788-268">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="b5788-269">Puede mantener la información siguiente para los trabajadores:</span><span class="sxs-lookup"><span data-stu-id="b5788-269">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="b5788-270">**Básica**: permite mantener la información básica de un trabajador, como la información de contacto, información demográfica, información de identificación, información de familia, estado del servicio militar, información de expatriado y contactos personales y de emergencia.</span><span class="sxs-lookup"><span data-stu-id="b5788-270">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="b5788-271">**Empleo**: permite mantener la información sobre el empleo de un trabajador, como afiliación de la empresa u organización, asignación de puesto, fecha de inicio y finalización, idoneidad para el trabajo, condiciones de empleo, pensión, vacaciones y la información de reubicación.</span><span class="sxs-lookup"><span data-stu-id="b5788-271">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="b5788-272">**Bajas y ausencias**: permite mantener información sobre las ausencias de un trabajador, como calendarios de trabajo, transacciones de ausencia y configuración de ausencias.</span><span class="sxs-lookup"><span data-stu-id="b5788-272">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="b5788-273">**Compensación y nómina**: permite mantener la información sobre los planes de compensación y la información de nómina de un trabajador, como inscripción del plan, concesiones, desempeño, comisión, información fiscal, retiro y deducciones de sueldo.</span><span class="sxs-lookup"><span data-stu-id="b5788-273">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="b5788-274">Al introducir la información del trabajador, tenga presente los datos y las configuraciones siguientes que se usan en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-274">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="b5788-275">Información general</span><span class="sxs-lookup"><span data-stu-id="b5788-275">General information</span></span>

- <span data-ttu-id="b5788-276">Número de personal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-276">Personnel number (required)</span></span>
- <span data-ttu-id="b5788-277">Nombre (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-277">First name (required)</span></span>
- <span data-ttu-id="b5788-278">Apellido (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-278">Last name (required)</span></span>
- <span data-ttu-id="b5788-279">Segundo nombre</span><span class="sxs-lookup"><span data-stu-id="b5788-279">Middle name</span></span>
- <span data-ttu-id="b5788-280">Antigüedad</span><span class="sxs-lookup"><span data-stu-id="b5788-280">Seniority date</span></span>
- <span data-ttu-id="b5788-281">Conocido como</span><span class="sxs-lookup"><span data-stu-id="b5788-281">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="b5788-282">Información personal</span><span class="sxs-lookup"><span data-stu-id="b5788-282">Personal information</span></span>

- <span data-ttu-id="b5788-283">Estado civil (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-283">Marital status (required)</span></span>
- <span data-ttu-id="b5788-284">Fecha de nacimiento (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-284">Birth date (required)</span></span>
- <span data-ttu-id="b5788-285">Sexo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-285">Gender (required)</span></span>
- <span data-ttu-id="b5788-286">Persona con discapacidades</span><span class="sxs-lookup"><span data-stu-id="b5788-286">Person with disabilities</span></span>
- <span data-ttu-id="b5788-287">País o región, nacionalidad (solo para México)</span><span class="sxs-lookup"><span data-stu-id="b5788-287">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="b5788-288">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="b5788-288">Address information</span></span>

- <span data-ttu-id="b5788-289">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-289">Primary (required)</span></span>
- <span data-ttu-id="b5788-290">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-290">Country/region (required)</span></span>
- <span data-ttu-id="b5788-291">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-291">Postal code (required)</span></span>
- <span data-ttu-id="b5788-292">Número de calle (obligatorio) (solo para México)</span><span class="sxs-lookup"><span data-stu-id="b5788-292">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="b5788-293">Complemento de edificio (solo para México)</span><span class="sxs-lookup"><span data-stu-id="b5788-293">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="b5788-294">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-294">City (required)</span></span>
- <span data-ttu-id="b5788-295">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-295">State (required)</span></span>
- <span data-ttu-id="b5788-296">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-296">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="b5788-297">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="b5788-297">Contact information</span></span> 

- <span data-ttu-id="b5788-298">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-298">Primary (required)</span></span>
- <span data-ttu-id="b5788-299">Número de contacto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-299">Contact number (required)</span></span>
- <span data-ttu-id="b5788-300">Extensión</span><span class="sxs-lookup"><span data-stu-id="b5788-300">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="b5788-301">Información de nómina y códigos de ganancias</span><span class="sxs-lookup"><span data-stu-id="b5788-301">Payroll information and earning codes</span></span>

<span data-ttu-id="b5788-302">A los empleados se les pueden asignar ganancias específicas de una frecuencia determinada de pago y tener un método de pago preferido.</span><span class="sxs-lookup"><span data-stu-id="b5788-302">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="b5788-303">Los siguientes campos se utilizan en Dayforce para ayudar a garantizar que se usen las preferencias y valores.</span><span class="sxs-lookup"><span data-stu-id="b5788-303">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="b5788-304">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="b5788-304">Earning codes</span></span>

- <span data-ttu-id="b5788-305">Puesto (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-305">Position (required)</span></span>
- <span data-ttu-id="b5788-306">Código de ganancias (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-306">Earning Code (required)</span></span>
- <span data-ttu-id="b5788-307">Frecuencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-307">Frequency (required)</span></span>
- <span data-ttu-id="b5788-308">Importe (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-308">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="b5788-309">Información de nómina</span><span class="sxs-lookup"><span data-stu-id="b5788-309">Payroll information</span></span>

- <span data-ttu-id="b5788-310">Método de pago</span><span class="sxs-lookup"><span data-stu-id="b5788-310">Payment Method</span></span>
- <span data-ttu-id="b5788-311">Región económica (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-311">Economic Region (required)</span></span>
- <span data-ttu-id="b5788-312">Id. de prestaciones de empleado</span><span class="sxs-lookup"><span data-stu-id="b5788-312">Employee Benefits ID</span></span>
- <span data-ttu-id="b5788-313">Número de id. nacional (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-313">National ID Number (required)</span></span>
- <span data-ttu-id="b5788-314">Número de servicio militar</span><span class="sxs-lookup"><span data-stu-id="b5788-314">Military Service Number</span></span>
- <span data-ttu-id="b5788-315">Id. de turno (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-315">Shift ID (required)</span></span>
- <span data-ttu-id="b5788-316">Número de identificación fiscal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-316">Tax Number (required)</span></span>
- <span data-ttu-id="b5788-317">Id. de sindicato (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-317">Union ID (required)</span></span>
- <span data-ttu-id="b5788-318">Id. de día laborable (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-318">Work Day ID (required)</span></span>
- <span data-ttu-id="b5788-319">Número de permiso de trabajo</span><span class="sxs-lookup"><span data-stu-id="b5788-319">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="b5788-320">Para el método de pago, México admite **Efectivo**, **Cheque** (cheque físico de la empresa) y **Pago electrónico**.</span><span class="sxs-lookup"><span data-stu-id="b5788-320">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="b5788-321">Si no se especifica ningún método de pago, **Cheque** se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b5788-321">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="b5788-322">Detalles del empleo</span><span class="sxs-lookup"><span data-stu-id="b5788-322">Employment details</span></span>

<span data-ttu-id="b5788-323">El historial de detalles de empleo se utiliza como información clave para derivar los estados de contratación, despido y recontratación de un empleado en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-323">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="b5788-324">Dayforce solo admite un registro de empleo activo a la vez.</span><span class="sxs-lookup"><span data-stu-id="b5788-324">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="b5788-325">Fecha de inicio de empleo (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-325">Employment start date (required)</span></span>
- <span data-ttu-id="b5788-326">Fecha final del empleo</span><span class="sxs-lookup"><span data-stu-id="b5788-326">Employment end date</span></span>
- <span data-ttu-id="b5788-327">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="b5788-327">Start date</span></span>
- <span data-ttu-id="b5788-328">Fecha inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="b5788-328">Adjusted start date</span></span>
- <span data-ttu-id="b5788-329">Fecha de finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="b5788-329">Termination date (required upon termination)</span></span>
- <span data-ttu-id="b5788-330">Razón de la finalización (obligatorio en el momento de la finalización)</span><span class="sxs-lookup"><span data-stu-id="b5788-330">Termination reason (required upon termination)</span></span>

<span data-ttu-id="b5788-331">Las fechas clave de un empleado se obtienen utilizando la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="b5788-331">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="b5788-332">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-332">Human Resources</span></span>                | <span data-ttu-id="b5788-333">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-333">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b5788-334">Fecha de contratación más reciente</span><span class="sxs-lookup"><span data-stu-id="b5788-334">Most recent hire date</span></span> | <span data-ttu-id="b5788-335">Inicio de empleo del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="b5788-335">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="b5788-336">Fecha de finalización</span><span class="sxs-lookup"><span data-stu-id="b5788-336">Termination date</span></span>      | <span data-ttu-id="b5788-337">Fecha de finalización del registro actual de historial de empleo no finalizado</span><span class="sxs-lookup"><span data-stu-id="b5788-337">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="b5788-338">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="b5788-338">Start date</span></span>            | <span data-ttu-id="b5788-339">Fecha de inicio ajustada, fecha de inicio o inicio de empleo del registro de historial de empleo inactivo actual</span><span class="sxs-lookup"><span data-stu-id="b5788-339">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="b5788-340">Fecha de contratación original</span><span class="sxs-lookup"><span data-stu-id="b5788-340">Original hire date</span></span>    | <span data-ttu-id="b5788-341">Inicio del empleo del registro del historial de empleo más temprano</span><span class="sxs-lookup"><span data-stu-id="b5788-341">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="b5788-342">Compensación</span><span class="sxs-lookup"><span data-stu-id="b5788-342">Compensation</span></span>

<span data-ttu-id="b5788-343">Un plan de compensación fija se debe asociar al puesto principal de cada empleado durante un período de empleo.</span><span class="sxs-lookup"><span data-stu-id="b5788-343">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="b5788-344">Este período comienza en la fecha de contratación del empleado (o la fecha de inicio del empleo) y continúa hasta la finalización.</span><span class="sxs-lookup"><span data-stu-id="b5788-344">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="b5788-345">Fecha de vigencia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-345">Effective Date (required)</span></span>
- <span data-ttu-id="b5788-346">Fecha de expiración</span><span class="sxs-lookup"><span data-stu-id="b5788-346">Expiration date</span></span>
- <span data-ttu-id="b5788-347">Índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-347">Pay Rate (required)</span></span>
- <span data-ttu-id="b5788-348">Conversiones de índice salarial (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-348">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="b5788-349">Equivalente anual (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-349">Annual equivalent (required)</span></span>
- <span data-ttu-id="b5788-350">Equivalente por hora (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-350">Hourly equivalent (required)</span></span>

<span data-ttu-id="b5788-351">Si un empleado por hora tiene varios puestos, se importa la compensación fija del puesto principal en Dayforce como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="b5788-351">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="b5788-352">En el caso de los puestos no principales, el índice por hora se guarda en el puesto correspondiente en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-352">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="b5788-353">Si un empleado a sueldo tiene varios puestos, se derivan el índice por hora acumulativa y el sueldo anual en todos los puestos activos y se utilizan como índice/salario base de nivel de empleado.</span><span class="sxs-lookup"><span data-stu-id="b5788-353">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="b5788-354">Números de identificación</span><span class="sxs-lookup"><span data-stu-id="b5788-354">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="b5788-355">Identificador de seguridad social</span><span class="sxs-lookup"><span data-stu-id="b5788-355">Social Security identifier</span></span> 

<span data-ttu-id="b5788-356">Cada empleado debe tener un identificador principal.</span><span class="sxs-lookup"><span data-stu-id="b5788-356">Every employee must have one primary identifier.</span></span> <span data-ttu-id="b5788-357">Este identificador debe ser de tipo de identificación **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="b5788-357">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="b5788-358">En Dayforce, se deriva automáticamente como el identificador de seguridad social del empleado que se requiere para ser contratado.</span><span class="sxs-lookup"><span data-stu-id="b5788-358">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="b5788-359">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-359">Primary (required)</span></span>
- <span data-ttu-id="b5788-360">Tipo de identificación = "Nº de SS"</span><span class="sxs-lookup"><span data-stu-id="b5788-360">Identification Type = "SSN"</span></span>
- <span data-ttu-id="b5788-361">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="b5788-361">Issued Date</span></span>
- <span data-ttu-id="b5788-362">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="b5788-362">Expiration Date</span></span>

<span data-ttu-id="b5788-363">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Nº de SS**.</span><span class="sxs-lookup"><span data-stu-id="b5788-363">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="b5788-364">Sin embargo, solo el registro que está marcado como **Principal** está integrado en Dayforce, independientemente de si el número está activo o caducado.</span><span class="sxs-lookup"><span data-stu-id="b5788-364">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="b5788-365">Cuentas bancarias y desembolsos</span><span class="sxs-lookup"><span data-stu-id="b5788-365">Bank accounts and disbursements</span></span>

<span data-ttu-id="b5788-366">La información de cuenta bancaria válida se debe especificar para cualquier empleado que elija recibir el pago por transferencias de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="b5788-366">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="b5788-367">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-367">Human Resources</span></span>                         | <span data-ttu-id="b5788-368">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-368">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b5788-369">Número de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-369">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="b5788-370">Código SWIFT (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-370">SWIFT code (required)</span></span>          | <span data-ttu-id="b5788-371">Campo **Identificador del banco** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="b5788-371">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="b5788-372">Número de sucursal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-372">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="b5788-373">Tipo de cuenta bancaria (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-373">Bank account type (required)</span></span>   | <span data-ttu-id="b5788-374">Campo **Tipo de cuenta** utilizado al procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="b5788-374">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="b5788-375">Los valores admitidos incluyen **Comprobación** y **Nómina**.</span><span class="sxs-lookup"><span data-stu-id="b5788-375">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="b5788-376">Los empleados que elijan que se les pague a través de transferencia bancaria deben proporcionar un vínculo a una cuenta de remanente que esté en una entidad legal que tenga su dirección principal en México y esté asociada con una cuenta bancaria válida de un banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="b5788-376">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="b5788-377">Todas las demás cuentas no remanentes se ignoran.</span><span class="sxs-lookup"><span data-stu-id="b5788-377">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="b5788-378">Información de dirección</span><span class="sxs-lookup"><span data-stu-id="b5788-378">Address information</span></span>

<span data-ttu-id="b5788-379">Cada empleado debe tener una ubicación principal.</span><span class="sxs-lookup"><span data-stu-id="b5788-379">Every employee must have one primary location.</span></span> <span data-ttu-id="b5788-380">En Dayforce, esta ubicación se usa para determinar la residencia principal del empleado para impuestos.</span><span class="sxs-lookup"><span data-stu-id="b5788-380">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="b5788-381">Principal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-381">Primary (required)</span></span>
- <span data-ttu-id="b5788-382">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-382">Country/region (required)</span></span>
- <span data-ttu-id="b5788-383">Código postal (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-383">Zip/postal code (required)</span></span>
- <span data-ttu-id="b5788-384">Calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-384">Street (required)</span></span>
- <span data-ttu-id="b5788-385">Número de calle (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-385">Street Number (required)</span></span>
- <span data-ttu-id="b5788-386">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="b5788-386">Building Complement</span></span>
- <span data-ttu-id="b5788-387">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-387">City (required)</span></span>
- <span data-ttu-id="b5788-388">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-388">State (required)</span></span>
- <span data-ttu-id="b5788-389">Provincia (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-389">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="b5788-390">Configure los datos para generar nóminas en Estados Unidos y Canadá</span><span class="sxs-lookup"><span data-stu-id="b5788-390">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="b5788-391">Si va a generar el sueldo de los empleados en Estados Unidos y Canadá, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="b5788-391">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="b5788-392">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="b5788-392">Departments are required on positions.</span></span>
- <span data-ttu-id="b5788-393">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b5788-393">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="b5788-394">Puede configurar Human Resources para requerir que los puestos especifiquen un departamento.</span><span class="sxs-lookup"><span data-stu-id="b5788-394">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="b5788-395">Para ello, vaya a **Puestos compartidos de recursos humanos > Puestos > Requerir departamentos en puestos**.</span><span class="sxs-lookup"><span data-stu-id="b5788-395">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="b5788-396">Recomendamos que este valor se aplique para la integración.</span><span class="sxs-lookup"><span data-stu-id="b5788-396">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="b5788-397">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b5788-397">Job types</span></span>

<span data-ttu-id="b5788-398">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="b5788-398">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="b5788-399">Los tipos de trabajo son obligatorios para procesar la nómina en Estados Unidos y Canadá.</span><span class="sxs-lookup"><span data-stu-id="b5788-399">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="b5788-400">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="b5788-400">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="b5788-401">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="b5788-401">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="b5788-402">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="b5788-402">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="b5788-403">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b5788-403">Job type</span></span>   | <span data-ttu-id="b5788-404">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5788-404">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="b5788-405">Por hora</span><span class="sxs-lookup"><span data-stu-id="b5788-405">Hourly</span></span>     | <span data-ttu-id="b5788-406">Por hora</span><span class="sxs-lookup"><span data-stu-id="b5788-406">Hourly</span></span>      |
| <span data-ttu-id="b5788-407">Asalariado</span><span class="sxs-lookup"><span data-stu-id="b5788-407">Salaried</span></span>   | <span data-ttu-id="b5788-408">Asalariado</span><span class="sxs-lookup"><span data-stu-id="b5788-408">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="b5788-409">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="b5788-409">Position types</span></span> 

<span data-ttu-id="b5788-410">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="b5788-410">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="b5788-411">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="b5788-411">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="b5788-412">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="b5788-412">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="b5788-413">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="b5788-413">Position type</span></span>   | <span data-ttu-id="b5788-414">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5788-414">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="b5788-415">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="b5788-415">Full-time</span></span>       | <span data-ttu-id="b5788-416">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="b5788-416">Full time employee</span></span> |
| <span data-ttu-id="b5788-417">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="b5788-417">Part-time</span></span>       | <span data-ttu-id="b5788-418">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="b5788-418">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="b5788-419">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="b5788-419">Reason codes</span></span>

<span data-ttu-id="b5788-420">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="b5788-420">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="b5788-421">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="b5788-421">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="b5788-422">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="b5788-422">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="b5788-423">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="b5788-423">Reason code</span></span>    | <span data-ttu-id="b5788-424">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5788-424">Description</span></span>      | <span data-ttu-id="b5788-425">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="b5788-425">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="b5788-426">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="b5788-426">RESIGNATION</span></span>    | <span data-ttu-id="b5788-427">Dimisión</span><span class="sxs-lookup"><span data-stu-id="b5788-427">Resignation</span></span>      | <span data-ttu-id="b5788-428">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-428">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-429">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="b5788-429">TERMINATION</span></span>    | <span data-ttu-id="b5788-430">Finalización</span><span class="sxs-lookup"><span data-stu-id="b5788-430">Termination</span></span>      | <span data-ttu-id="b5788-431">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-431">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-432">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="b5788-432">RETIREMENT</span></span>     | <span data-ttu-id="b5788-433">Jubilación</span><span class="sxs-lookup"><span data-stu-id="b5788-433">Retirement</span></span>       | <span data-ttu-id="b5788-434">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-434">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-435">OTHER</span><span class="sxs-lookup"><span data-stu-id="b5788-435">OTHER</span></span>          | <span data-ttu-id="b5788-436">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="b5788-436">Other Reasons</span></span>    | <span data-ttu-id="b5788-437">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-437">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-438">MUERTE</span><span class="sxs-lookup"><span data-stu-id="b5788-438">DEATH</span></span>          | <span data-ttu-id="b5788-439">Muerte</span><span class="sxs-lookup"><span data-stu-id="b5788-439">Death</span></span>            | <span data-ttu-id="b5788-440">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-440">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-441">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="b5788-441">LEAVEOFABSENCE</span></span> | <span data-ttu-id="b5788-442">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="b5788-442">Leave of Absence</span></span> | <span data-ttu-id="b5788-443">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-443">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-444">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="b5788-444">CONTRACTEND</span></span>    | <span data-ttu-id="b5788-445">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="b5788-445">End of Contract</span></span>  | <span data-ttu-id="b5788-446">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-446">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-447">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="b5788-447">SALARYCHANGE</span></span>   | <span data-ttu-id="b5788-448">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="b5788-448">Change of Salary</span></span> | <span data-ttu-id="b5788-449">Compensación</span><span class="sxs-lookup"><span data-stu-id="b5788-449">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="b5788-450">Estado civil</span><span class="sxs-lookup"><span data-stu-id="b5788-450">Marital status</span></span>

<span data-ttu-id="b5788-451">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="b5788-451">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b5788-452">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-452">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="b5788-453">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-453">Human Resources</span></span>                 | <span data-ttu-id="b5788-454">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-454">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="b5788-455">Casado/a</span><span class="sxs-lookup"><span data-stu-id="b5788-455">Married</span></span>                | <span data-ttu-id="b5788-456">Casado/a</span><span class="sxs-lookup"><span data-stu-id="b5788-456">Married</span></span>              |
| <span data-ttu-id="b5788-457">Único</span><span class="sxs-lookup"><span data-stu-id="b5788-457">Single</span></span>                 | <span data-ttu-id="b5788-458">Único</span><span class="sxs-lookup"><span data-stu-id="b5788-458">Single</span></span>               |
| <span data-ttu-id="b5788-459">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="b5788-459">Widowed</span></span>                | <span data-ttu-id="b5788-460">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="b5788-460">Widowed</span></span>              |
| <span data-ttu-id="b5788-461">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="b5788-461">Divorced</span></span>               | <span data-ttu-id="b5788-462">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="b5788-462">Divorced</span></span>             |
| <span data-ttu-id="b5788-463">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="b5788-463">Registered Partnership</span></span> | <span data-ttu-id="b5788-464">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="b5788-464">Domestic Partnership</span></span> |
| <span data-ttu-id="b5788-465">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="b5788-465">None</span></span>                   | <span data-ttu-id="b5788-466">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="b5788-466">None</span></span>                 |
| <span data-ttu-id="b5788-467">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="b5788-467">Cohabiting</span></span>             | <span data-ttu-id="b5788-468">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="b5788-468">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="b5788-469">Género</span><span class="sxs-lookup"><span data-stu-id="b5788-469">Gender</span></span>

<span data-ttu-id="b5788-470">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="b5788-470">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b5788-471">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-471">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="b5788-472">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-472">Human Resources</span></span>       | <span data-ttu-id="b5788-473">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-473">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="b5788-474">Masculino</span><span class="sxs-lookup"><span data-stu-id="b5788-474">Male</span></span>         | <span data-ttu-id="b5788-475">Masculino</span><span class="sxs-lookup"><span data-stu-id="b5788-475">Male</span></span>            |
| <span data-ttu-id="b5788-476">Femenino</span><span class="sxs-lookup"><span data-stu-id="b5788-476">Female</span></span>       | <span data-ttu-id="b5788-477">Femenino</span><span class="sxs-lookup"><span data-stu-id="b5788-477">Female</span></span>          |
| <span data-ttu-id="b5788-478">No específico</span><span class="sxs-lookup"><span data-stu-id="b5788-478">Non-specific</span></span> | <span data-ttu-id="b5788-479">*No admitido*</span><span class="sxs-lookup"><span data-stu-id="b5788-479">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="b5788-480">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="b5788-480">Earning codes</span></span>

<span data-ttu-id="b5788-481">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="b5788-481">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="b5788-482">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="b5788-482">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="b5788-483">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="b5788-483">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="b5788-484">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="b5788-484">Supported frequencies</span></span>

- <span data-ttu-id="b5788-485">Todas</span><span class="sxs-lookup"><span data-stu-id="b5788-485">All</span></span>
- <span data-ttu-id="b5788-486">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="b5788-486">EVERYPAY</span></span>
- <span data-ttu-id="b5788-487">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="b5788-487">EACHPAYPERIOD</span></span>
- <span data-ttu-id="b5788-488">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="b5788-488">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="b5788-489">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="b5788-489">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="b5788-490">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-490">1OFMTH</span></span>
- <span data-ttu-id="b5788-491">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-491">LASTOFMTH</span></span>
- <span data-ttu-id="b5788-492">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-492">2OFMTH</span></span>
- <span data-ttu-id="b5788-493">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-493">3OFMTH</span></span>
- <span data-ttu-id="b5788-494">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-494">4OFMTH</span></span>
- <span data-ttu-id="b5788-495">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-495">5OFMTH</span></span>
- <span data-ttu-id="b5788-496">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-496">1N2OFMTH</span></span>
- <span data-ttu-id="b5788-497">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-497">3N4OFMTH</span></span>
- <span data-ttu-id="b5788-498">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-498">1N3OFMTH</span></span>
- <span data-ttu-id="b5788-499">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-499">1N4OFMTH</span></span>
- <span data-ttu-id="b5788-500">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-500">2N3OFMTH</span></span>
- <span data-ttu-id="b5788-501">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-501">2N4OFMTH</span></span>
- <span data-ttu-id="b5788-502">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-502">1N2N3OFMTH</span></span>
- <span data-ttu-id="b5788-503">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-503">1N2N4OFMTH</span></span>
- <span data-ttu-id="b5788-504">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-504">1N3N4OFMTH</span></span>
- <span data-ttu-id="b5788-505">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-505">2N3N4OFMTH</span></span>
- <span data-ttu-id="b5788-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="b5788-507">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="b5788-507">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="b5788-508">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="b5788-508">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="b5788-509">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="b5788-509">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="b5788-510">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="b5788-510">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="b5788-511">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="b5788-511">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="b5788-512">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b5788-512">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="b5788-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b5788-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="b5788-514">Direcciones</span><span class="sxs-lookup"><span data-stu-id="b5788-514">Addresses</span></span>

<span data-ttu-id="b5788-515">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="b5788-515">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="b5788-516">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="b5788-516">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="b5788-517">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-517">Human Resources</span></span>          | <span data-ttu-id="b5788-518">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-518">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="b5788-519">País/región</span><span class="sxs-lookup"><span data-stu-id="b5788-519">Country/Region</span></span>  | <span data-ttu-id="b5788-520">Código de país</span><span class="sxs-lookup"><span data-stu-id="b5788-520">Country Code</span></span>          |
| <span data-ttu-id="b5788-521">Código postal</span><span class="sxs-lookup"><span data-stu-id="b5788-521">Zip/Postal Code</span></span> | <span data-ttu-id="b5788-522">Código postal</span><span class="sxs-lookup"><span data-stu-id="b5788-522">Postal Code</span></span>           |
| <span data-ttu-id="b5788-523">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="b5788-523">State</span></span>           | <span data-ttu-id="b5788-524">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="b5788-524">State Code</span></span>            |
| <span data-ttu-id="b5788-525">Población</span><span class="sxs-lookup"><span data-stu-id="b5788-525">City</span></span>            | <span data-ttu-id="b5788-526">Población</span><span class="sxs-lookup"><span data-stu-id="b5788-526">City</span></span>                  |
| <span data-ttu-id="b5788-527">Comarca</span><span class="sxs-lookup"><span data-stu-id="b5788-527">County</span></span>          | <span data-ttu-id="b5788-528">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="b5788-528">County (Municipality)</span></span> |
| <span data-ttu-id="b5788-529">Calle</span><span class="sxs-lookup"><span data-stu-id="b5788-529">Street</span></span>          | <span data-ttu-id="b5788-530">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="b5788-530">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="b5788-531">Regiones de impuestos</span><span class="sxs-lookup"><span data-stu-id="b5788-531">Tax regions</span></span>

<span data-ttu-id="b5788-532">Las regiones de impuestos se usan para determinar los impuestos correspondientes que se deben aplicar durante la generación de nómina.</span><span class="sxs-lookup"><span data-stu-id="b5788-532">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="b5788-533">Las regiones de impuestos se asignan a Dayforce como direcciones de ubicación.</span><span class="sxs-lookup"><span data-stu-id="b5788-533">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="b5788-534">La región de impuestos predeterminada se debe asociar al puesto activo del trabajador.</span><span class="sxs-lookup"><span data-stu-id="b5788-534">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="b5788-535">Región de impuestos (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-535">Tax region (required)</span></span>
- <span data-ttu-id="b5788-536">País o región (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-536">Country/Region (required)</span></span>
- <span data-ttu-id="b5788-537">Estado (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-537">State (required)</span></span>
- <span data-ttu-id="b5788-538">Comarca</span><span class="sxs-lookup"><span data-stu-id="b5788-538">County</span></span> 
- <span data-ttu-id="b5788-539">Ciudad (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="b5788-539">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="b5788-540">Configurar los datos para generar nóminas en México</span><span class="sxs-lookup"><span data-stu-id="b5788-540">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="b5788-541">Si va a generar el sueldo de los empleados en México, los siguientes elementos deben estar configurados:</span><span class="sxs-lookup"><span data-stu-id="b5788-541">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="b5788-542">Se requieren departamentos en los puestos.</span><span class="sxs-lookup"><span data-stu-id="b5788-542">Departments are required on positions.</span></span>
- <span data-ttu-id="b5788-543">Los centros de coste deben configurarse como dimensiones financieras y deben ser el primer elemento de la cadena de dimensión financiera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b5788-543">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="b5788-544">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b5788-544">Job types</span></span>

<span data-ttu-id="b5788-545">Los tipos de trabajo se utilizan para agrupar trabajos similares en categorías.</span><span class="sxs-lookup"><span data-stu-id="b5788-545">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="b5788-546">Los tipos de trabajo son obligatorios para procesar la nómina en México.</span><span class="sxs-lookup"><span data-stu-id="b5788-546">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="b5788-547">Entre los ejemplos de tipos de trabajo se incluyen jornada completa y tiempo parcial, o con sueldo y paga por horas.</span><span class="sxs-lookup"><span data-stu-id="b5788-547">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="b5788-548">Los tipos de trabajo se asignan a Dayforce como tipos de sueldo que indican si un empleado trabaja por horas o es asalariado.</span><span class="sxs-lookup"><span data-stu-id="b5788-548">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="b5788-549">Los siguientes tipos de trabajo y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="b5788-549">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="b5788-550">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b5788-550">Job type</span></span>   | <span data-ttu-id="b5788-551">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5788-551">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="b5788-552">Por hora</span><span class="sxs-lookup"><span data-stu-id="b5788-552">Hourly</span></span>     | <span data-ttu-id="b5788-553">MX Por hora</span><span class="sxs-lookup"><span data-stu-id="b5788-553">MX Hourly</span></span>   |
| <span data-ttu-id="b5788-554">Asalariado</span><span class="sxs-lookup"><span data-stu-id="b5788-554">Salaried</span></span>   | <span data-ttu-id="b5788-555">MX Asalariado</span><span class="sxs-lookup"><span data-stu-id="b5788-555">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="b5788-556">Tipos de puestos</span><span class="sxs-lookup"><span data-stu-id="b5788-556">Position types</span></span> 

<span data-ttu-id="b5788-557">Use los tipos de puesto para describir si el puesto es a jornada completa, a tiempo parcial u otro tipo.</span><span class="sxs-lookup"><span data-stu-id="b5788-557">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="b5788-558">Los tipos de puesto se asignan a Dayforce como clases de sueldo que indican si un empleado a jornada completa o a tiempo parcial.</span><span class="sxs-lookup"><span data-stu-id="b5788-558">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="b5788-559">Los siguientes tipos de puesto y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="b5788-559">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="b5788-560">Tipo de puesto</span><span class="sxs-lookup"><span data-stu-id="b5788-560">Position type</span></span>   | <span data-ttu-id="b5788-561">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5788-561">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="b5788-562">Jornada completa</span><span class="sxs-lookup"><span data-stu-id="b5788-562">Full-time</span></span>       | <span data-ttu-id="b5788-563">Empleado a jornada completa</span><span class="sxs-lookup"><span data-stu-id="b5788-563">Full time employee</span></span> |
| <span data-ttu-id="b5788-564">A tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="b5788-564">Part-time</span></span>       | <span data-ttu-id="b5788-565">Empleado a tiempo parcial</span><span class="sxs-lookup"><span data-stu-id="b5788-565">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="b5788-566">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="b5788-566">Reason codes</span></span>

<span data-ttu-id="b5788-567">Los códigos de motivos proporcionan información sobre el estado de un empleado.</span><span class="sxs-lookup"><span data-stu-id="b5788-567">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="b5788-568">Los códigos de motivos se asignan a Dayforce como motivos de estado que indican el motivo de los cambios en el puesto de un empleado o su situación laboral.</span><span class="sxs-lookup"><span data-stu-id="b5788-568">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="b5788-569">Los siguientes códigos de motivos y descripciones son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="b5788-569">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="b5788-570">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="b5788-570">Reason code</span></span>            | <span data-ttu-id="b5788-571">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5788-571">Description</span></span>                    | <span data-ttu-id="b5788-572">Situaciones aplicables</span><span class="sxs-lookup"><span data-stu-id="b5788-572">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="b5788-573">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="b5788-573">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="b5788-574">Salida antes de la primera nómina</span><span class="sxs-lookup"><span data-stu-id="b5788-574">Departure before first payroll</span></span> | <span data-ttu-id="b5788-575">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-575">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-576">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="b5788-576">RESIGNATION</span></span>            | <span data-ttu-id="b5788-577">Dimisión</span><span class="sxs-lookup"><span data-stu-id="b5788-577">Resignation</span></span>                    | <span data-ttu-id="b5788-578">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-578">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-579">PENSION</span><span class="sxs-lookup"><span data-stu-id="b5788-579">PENSION</span></span>                | <span data-ttu-id="b5788-580">Pensión</span><span class="sxs-lookup"><span data-stu-id="b5788-580">Pension</span></span>                        | <span data-ttu-id="b5788-581">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-581">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-582">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="b5788-582">TERMINATION</span></span>            | <span data-ttu-id="b5788-583">Finalización</span><span class="sxs-lookup"><span data-stu-id="b5788-583">Termination</span></span>                    | <span data-ttu-id="b5788-584">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-584">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-585">JUBILACIÓN</span><span class="sxs-lookup"><span data-stu-id="b5788-585">RETIREMENT</span></span>             | <span data-ttu-id="b5788-586">Jubilación</span><span class="sxs-lookup"><span data-stu-id="b5788-586">Retirement</span></span>                     | <span data-ttu-id="b5788-587">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-587">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-588">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="b5788-588">ABSENTEE</span></span>               | <span data-ttu-id="b5788-589">Ausente</span><span class="sxs-lookup"><span data-stu-id="b5788-589">Absentee</span></span>                       | <span data-ttu-id="b5788-590">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-590">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-591">OTHER</span><span class="sxs-lookup"><span data-stu-id="b5788-591">OTHER</span></span>                  | <span data-ttu-id="b5788-592">Otros motivos</span><span class="sxs-lookup"><span data-stu-id="b5788-592">Other Reasons</span></span>                  | <span data-ttu-id="b5788-593">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-593">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-594">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="b5788-594">CLOSURE</span></span>                | <span data-ttu-id="b5788-595">Cierre de operaciones</span><span class="sxs-lookup"><span data-stu-id="b5788-595">Business Closure</span></span>               | <span data-ttu-id="b5788-596">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-596">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-597">MUERTE</span><span class="sxs-lookup"><span data-stu-id="b5788-597">DEATH</span></span>                  | <span data-ttu-id="b5788-598">Muerte</span><span class="sxs-lookup"><span data-stu-id="b5788-598">Death</span></span>                          | <span data-ttu-id="b5788-599">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-599">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-600">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="b5788-600">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="b5788-601">Permiso para ausentarse</span><span class="sxs-lookup"><span data-stu-id="b5788-601">Leave of Absence</span></span>               | <span data-ttu-id="b5788-602">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-602">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-603">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="b5788-603">CONTRACTEND</span></span>            | <span data-ttu-id="b5788-604">Fin de contrato</span><span class="sxs-lookup"><span data-stu-id="b5788-604">End of Contract</span></span>                | <span data-ttu-id="b5788-605">Dar de baja a trabajador</span><span class="sxs-lookup"><span data-stu-id="b5788-605">Terminate worker</span></span>     |
| <span data-ttu-id="b5788-606">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="b5788-606">SALARYCHANGE</span></span>           | <span data-ttu-id="b5788-607">Cambio de salario</span><span class="sxs-lookup"><span data-stu-id="b5788-607">Change of Salary</span></span>               | <span data-ttu-id="b5788-608">Compensación</span><span class="sxs-lookup"><span data-stu-id="b5788-608">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="b5788-609">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="b5788-609">Terms of employment</span></span>

<span data-ttu-id="b5788-610">Las condiciones laborales se usan para crear categorías de condiciones laborales.</span><span class="sxs-lookup"><span data-stu-id="b5788-610">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="b5788-611">Las condiciones se asignan a Dayforce como valores de indicador de empleo.</span><span class="sxs-lookup"><span data-stu-id="b5788-611">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="b5788-612">Las siguientes condiciones laborales y descripciones son obligatorias.</span><span class="sxs-lookup"><span data-stu-id="b5788-612">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="b5788-613">Condiciones laborales</span><span class="sxs-lookup"><span data-stu-id="b5788-613">Terms of employment</span></span>   | <span data-ttu-id="b5788-614">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5788-614">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="b5788-615">Normal</span><span class="sxs-lookup"><span data-stu-id="b5788-615">Regular</span></span>               | <span data-ttu-id="b5788-616">Normal</span><span class="sxs-lookup"><span data-stu-id="b5788-616">Regular</span></span>     |
| <span data-ttu-id="b5788-617">Directo</span><span class="sxs-lookup"><span data-stu-id="b5788-617">Direct</span></span>                | <span data-ttu-id="b5788-618">Directo</span><span class="sxs-lookup"><span data-stu-id="b5788-618">Direct</span></span>      |
| <span data-ttu-id="b5788-619">Prácticas</span><span class="sxs-lookup"><span data-stu-id="b5788-619">Internship</span></span>            | <span data-ttu-id="b5788-620">Prácticas</span><span class="sxs-lookup"><span data-stu-id="b5788-620">Internship</span></span>  |
| <span data-ttu-id="b5788-621">Permanente</span><span class="sxs-lookup"><span data-stu-id="b5788-621">Permanent</span></span>             | <span data-ttu-id="b5788-622">Permanente</span><span class="sxs-lookup"><span data-stu-id="b5788-622">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="b5788-623">Estado civil</span><span class="sxs-lookup"><span data-stu-id="b5788-623">Marital status</span></span>

<span data-ttu-id="b5788-624">Los valores de estado civil se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="b5788-624">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b5788-625">En la siguiente tabla se muestra cómo los valores de estado civil se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-625">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="b5788-626">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-626">Human Resources</span></span>                 | <span data-ttu-id="b5788-627">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-627">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="b5788-628">Casado/a</span><span class="sxs-lookup"><span data-stu-id="b5788-628">Married</span></span>                | <span data-ttu-id="b5788-629">Casado/a</span><span class="sxs-lookup"><span data-stu-id="b5788-629">Married</span></span>                   |
| <span data-ttu-id="b5788-630">Único</span><span class="sxs-lookup"><span data-stu-id="b5788-630">Single</span></span>                 | <span data-ttu-id="b5788-631">Único</span><span class="sxs-lookup"><span data-stu-id="b5788-631">Single</span></span>                    |
| <span data-ttu-id="b5788-632">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="b5788-632">Widowed</span></span>                | <span data-ttu-id="b5788-633">Viudo/a</span><span class="sxs-lookup"><span data-stu-id="b5788-633">Widowed</span></span>                   |
| <span data-ttu-id="b5788-634">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="b5788-634">Divorced</span></span>               | <span data-ttu-id="b5788-635">Divorciado/a</span><span class="sxs-lookup"><span data-stu-id="b5788-635">Divorced</span></span>                  |
| <span data-ttu-id="b5788-636">Unión registrada</span><span class="sxs-lookup"><span data-stu-id="b5788-636">Registered Partnership</span></span> | <span data-ttu-id="b5788-637">Sociedad doméstica</span><span class="sxs-lookup"><span data-stu-id="b5788-637">Domestic Partnership</span></span>      |
| <span data-ttu-id="b5788-638">Sin ordenar</span><span class="sxs-lookup"><span data-stu-id="b5788-638">None</span></span>                   | <span data-ttu-id="b5788-639">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="b5788-639">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b5788-640">Cohabitando</span><span class="sxs-lookup"><span data-stu-id="b5788-640">Cohabiting</span></span>             | <span data-ttu-id="b5788-641">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="b5788-641">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="b5788-642">Género</span><span class="sxs-lookup"><span data-stu-id="b5788-642">Gender</span></span>

<span data-ttu-id="b5788-643">Las designaciones de género se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="b5788-643">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b5788-644">En la siguiente tabla se muestra cómo las designaciones de género se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-644">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="b5788-645">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-645">Human Resources</span></span>       | <span data-ttu-id="b5788-646">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-646">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="b5788-647">Masculino</span><span class="sxs-lookup"><span data-stu-id="b5788-647">Male</span></span>         | <span data-ttu-id="b5788-648">Masculino</span><span class="sxs-lookup"><span data-stu-id="b5788-648">Male</span></span>                      |
| <span data-ttu-id="b5788-649">Femenino</span><span class="sxs-lookup"><span data-stu-id="b5788-649">Female</span></span>       | <span data-ttu-id="b5788-650">Femenino</span><span class="sxs-lookup"><span data-stu-id="b5788-650">Female</span></span>                    |
| <span data-ttu-id="b5788-651">No específico</span><span class="sxs-lookup"><span data-stu-id="b5788-651">Non-specific</span></span> | <span data-ttu-id="b5788-652">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="b5788-652">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="b5788-653">Método de pago</span><span class="sxs-lookup"><span data-stu-id="b5788-653">Payment method</span></span>

<span data-ttu-id="b5788-654">Los métodos de pago ofrecen al empleado y la empresa una forma de describir cómo se pagará a los empleados.</span><span class="sxs-lookup"><span data-stu-id="b5788-654">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="b5788-655">Los métodos de pago se asignan a Dayforce y se traducen, según corresponda, a los valores aceptados tras la integración.</span><span class="sxs-lookup"><span data-stu-id="b5788-655">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b5788-656">En la siguiente tabla se muestra cómo los métodos de pago se asignan a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-656">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="b5788-657">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-657">Human Resources</span></span>             | <span data-ttu-id="b5788-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-658">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="b5788-659">Efectivo</span><span class="sxs-lookup"><span data-stu-id="b5788-659">Cash</span></span>               | <span data-ttu-id="b5788-660">Efectivo</span><span class="sxs-lookup"><span data-stu-id="b5788-660">Cash</span></span>                      |
| <span data-ttu-id="b5788-661">Pago electrónico</span><span class="sxs-lookup"><span data-stu-id="b5788-661">Electronic Payment</span></span> | <span data-ttu-id="b5788-662">Transferir</span><span class="sxs-lookup"><span data-stu-id="b5788-662">Transfer</span></span>                  |
| <span data-ttu-id="b5788-663">Comprobación</span><span class="sxs-lookup"><span data-stu-id="b5788-663">Check</span></span>              | <span data-ttu-id="b5788-664">Cheque</span><span class="sxs-lookup"><span data-stu-id="b5788-664">Cheque</span></span>                    |
| <span data-ttu-id="b5788-665">Efecto bancario</span><span class="sxs-lookup"><span data-stu-id="b5788-665">Bank Draft</span></span>         | <span data-ttu-id="b5788-666">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="b5788-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b5788-667">Otras</span><span class="sxs-lookup"><span data-stu-id="b5788-667">Other</span></span>              | <span data-ttu-id="b5788-668">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="b5788-668">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="b5788-669">Tipo de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="b5788-669">Bank account type</span></span>

<span data-ttu-id="b5788-670">Los tipos de cuenta bancaria se usan para los pagos electrónicos a los empleados.</span><span class="sxs-lookup"><span data-stu-id="b5788-670">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="b5788-671">Los tipos de cuenta bancaria se asignan a Dayforce como información de cuenta de transferencia.</span><span class="sxs-lookup"><span data-stu-id="b5788-671">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="b5788-672">Los tipos de cuenta bancaria se convierten, según proceda, en los valores aceptados en la integración.</span><span class="sxs-lookup"><span data-stu-id="b5788-672">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="b5788-673">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-673">Human Resources</span></span>            | <span data-ttu-id="b5788-674">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-674">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="b5788-675">Cuenta corriente</span><span class="sxs-lookup"><span data-stu-id="b5788-675">Checking Account</span></span>  | <span data-ttu-id="b5788-676">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="b5788-676">CheckingAccount</span></span>           |
| <span data-ttu-id="b5788-677">Cuenta de nómina</span><span class="sxs-lookup"><span data-stu-id="b5788-677">Payroll Account</span></span>   | <span data-ttu-id="b5788-678">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="b5788-678">PayrollAccount</span></span>            |
| <span data-ttu-id="b5788-679">Cuenta de ahorros</span><span class="sxs-lookup"><span data-stu-id="b5788-679">Savings Account</span></span>   | <span data-ttu-id="b5788-680">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="b5788-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b5788-681">Cuenta de BankGirot</span><span class="sxs-lookup"><span data-stu-id="b5788-681">BankGirot account</span></span> | <span data-ttu-id="b5788-682">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="b5788-682">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b5788-683">Cuenta de PlusGirot</span><span class="sxs-lookup"><span data-stu-id="b5788-683">PlusGirot account</span></span> | <span data-ttu-id="b5788-684">*No se admite en México*</span><span class="sxs-lookup"><span data-stu-id="b5788-684">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="b5788-685">Códigos de ganancia</span><span class="sxs-lookup"><span data-stu-id="b5788-685">Earning codes</span></span>

<span data-ttu-id="b5788-686">Los códigos de ganancias identifican de forma exclusiva cada tipo de ganancias que reciben trabajadores.</span><span class="sxs-lookup"><span data-stu-id="b5788-686">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="b5788-687">Los códigos abarcan varios parámetros relacionados con las ganancias, como las reglas de contabilidad, las leyes tributarias, los requisitos de informes y la capacidad de valor bruto.</span><span class="sxs-lookup"><span data-stu-id="b5788-687">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="b5788-688">Si se usa una frecuencia no admitida, la frecuencia **Cada sueldo** se utiliza de forma predeterminada para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="b5788-688">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="b5788-689">Frecuencias admitidas</span><span class="sxs-lookup"><span data-stu-id="b5788-689">Supported frequencies</span></span>

- <span data-ttu-id="b5788-690">Todas</span><span class="sxs-lookup"><span data-stu-id="b5788-690">All</span></span>
- <span data-ttu-id="b5788-691">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="b5788-691">EVERYPAY</span></span>
- <span data-ttu-id="b5788-692">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="b5788-692">EACHPAYPERIOD</span></span>
- <span data-ttu-id="b5788-693">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="b5788-693">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="b5788-694">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="b5788-694">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="b5788-695">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-695">1OFMTH</span></span>
- <span data-ttu-id="b5788-696">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-696">LASTOFMTH</span></span>
- <span data-ttu-id="b5788-697">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-697">2OFMTH</span></span>
- <span data-ttu-id="b5788-698">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-698">3OFMTH</span></span>
- <span data-ttu-id="b5788-699">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-699">4OFMTH</span></span>
- <span data-ttu-id="b5788-700">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-700">5OFMTH</span></span>
- <span data-ttu-id="b5788-701">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-701">1N2OFMTH</span></span>
- <span data-ttu-id="b5788-702">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-702">3N4OFMTH</span></span>
- <span data-ttu-id="b5788-703">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-703">1N3OFMTH</span></span>
- <span data-ttu-id="b5788-704">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-704">1N4OFMTH</span></span>
- <span data-ttu-id="b5788-705">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-705">2N3OFMTH</span></span>
- <span data-ttu-id="b5788-706">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-706">2N4OFMTH</span></span>
- <span data-ttu-id="b5788-707">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-707">1N2N3OFMTH</span></span>
- <span data-ttu-id="b5788-708">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-708">1N2N4OFMTH</span></span>
- <span data-ttu-id="b5788-709">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-709">1N3N4OFMTH</span></span>
- <span data-ttu-id="b5788-710">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-710">2N3N4OFMTH</span></span>
- <span data-ttu-id="b5788-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b5788-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="b5788-712">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="b5788-712">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="b5788-713">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="b5788-713">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="b5788-714">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="b5788-714">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="b5788-715">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="b5788-715">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="b5788-716">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="b5788-716">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="b5788-717">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b5788-717">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="b5788-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b5788-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="b5788-719">Direcciones</span><span class="sxs-lookup"><span data-stu-id="b5788-719">Addresses</span></span>

<span data-ttu-id="b5788-720">La identificación de códigos específicos de país o región, estado y condado (municipio) requiere formatos específicos que los proveedores de Dayforce y en el país o región puedan reconocer.</span><span class="sxs-lookup"><span data-stu-id="b5788-720">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="b5788-721">Aunque el formato de las ciudades sea flexible, cada una debe asociarse a un estado.</span><span class="sxs-lookup"><span data-stu-id="b5788-721">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="b5788-722">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b5788-722">Human Resources</span></span>              | <span data-ttu-id="b5788-723">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b5788-723">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="b5788-724">País/región</span><span class="sxs-lookup"><span data-stu-id="b5788-724">Country/Region</span></span>      | <span data-ttu-id="b5788-725">Código de país</span><span class="sxs-lookup"><span data-stu-id="b5788-725">Country Code</span></span>          |
| <span data-ttu-id="b5788-726">Código postal</span><span class="sxs-lookup"><span data-stu-id="b5788-726">Zip/Postal Code</span></span>     | <span data-ttu-id="b5788-727">Código postal</span><span class="sxs-lookup"><span data-stu-id="b5788-727">Postal Code</span></span>           |
| <span data-ttu-id="b5788-728">Comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="b5788-728">State</span></span>               | <span data-ttu-id="b5788-729">Código de la comunidad autónoma</span><span class="sxs-lookup"><span data-stu-id="b5788-729">State Code</span></span>            |
| <span data-ttu-id="b5788-730">Población</span><span class="sxs-lookup"><span data-stu-id="b5788-730">City</span></span>                | <span data-ttu-id="b5788-731">Población</span><span class="sxs-lookup"><span data-stu-id="b5788-731">City</span></span>                  |
| <span data-ttu-id="b5788-732">Comarca</span><span class="sxs-lookup"><span data-stu-id="b5788-732">County</span></span>              | <span data-ttu-id="b5788-733">Condado (municipio)</span><span class="sxs-lookup"><span data-stu-id="b5788-733">County (Municipality)</span></span> |
| <span data-ttu-id="b5788-734">Calle</span><span class="sxs-lookup"><span data-stu-id="b5788-734">Street</span></span>              | <span data-ttu-id="b5788-735">Línea de dirección 1</span><span class="sxs-lookup"><span data-stu-id="b5788-735">Address Line 1</span></span>        |
| <span data-ttu-id="b5788-736">Número de calle</span><span class="sxs-lookup"><span data-stu-id="b5788-736">Street Number</span></span>       | <span data-ttu-id="b5788-737">Línea de dirección 2</span><span class="sxs-lookup"><span data-stu-id="b5788-737">Address Line 2</span></span>        |
| <span data-ttu-id="b5788-738">Complemento de edificio</span><span class="sxs-lookup"><span data-stu-id="b5788-738">Building Complement</span></span> | <span data-ttu-id="b5788-739">Línea de dirección 5</span><span class="sxs-lookup"><span data-stu-id="b5788-739">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="b5788-740">Número de pasaporte</span><span class="sxs-lookup"><span data-stu-id="b5788-740">Passport number</span></span>

<span data-ttu-id="b5788-741">Los empleados pueden declarar la información del pasaporte.</span><span class="sxs-lookup"><span data-stu-id="b5788-741">Employees can declare passport information.</span></span> <span data-ttu-id="b5788-742">Esta información es del tipo de identificación **Pasaporte** y se integra en Dayforce como parte de la información específica de México de un empleado.</span><span class="sxs-lookup"><span data-stu-id="b5788-742">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="b5788-743">Tipo de identificación = "Pasaporte"</span><span class="sxs-lookup"><span data-stu-id="b5788-743">Identification Type = "Passport"</span></span>
- <span data-ttu-id="b5788-744">Fecha de emisión</span><span class="sxs-lookup"><span data-stu-id="b5788-744">Issued Date</span></span>
- <span data-ttu-id="b5788-745">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="b5788-745">Expiration Date</span></span>

<span data-ttu-id="b5788-746">Los empleados pueden declarar números de identificación múltiples del tipo de identificación del **Pasaporte**.</span><span class="sxs-lookup"><span data-stu-id="b5788-746">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="b5788-747">Sin embargo, solo la entrada de pasaporte activa actual se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-747">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="b5788-748">Si todas las entradas de pasaporte han caducado, el pasaporte que se emitió más recientemente se integra en Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b5788-748">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]