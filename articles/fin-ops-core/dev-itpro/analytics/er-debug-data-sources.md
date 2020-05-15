---
title: Depurar las fuentes de datos de un formato ER ejecutado para analizar el flujo de datos y la transformación
description: Este tema explica cómo puede depurar las fuentes de datos de un formato ER ejecutado para comprender mejor el flujo y la transformación de datos configurados.
author: NickSelin
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 5b51c4beac0ddf1e2b53fe300e10c0f608e5d1e1
ms.sourcegitcommit: 153bb33722c02501bf7bcfd56ac887602d5dfbd3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "3318675"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a><span data-ttu-id="1d40e-103">Depurar las fuentes de datos de un formato ER ejecutado para analizar el flujo de datos y la transformación</span><span class="sxs-lookup"><span data-stu-id="1d40e-103">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

<span data-ttu-id="1d40e-104">Cuando [configure](tasks/er-format-configuration-2016-11.md) una solución de informes electrónicos (ER) para generar documentos electrónicos resultantes, se definen los métodos que se usan para sacar datos de la aplicción e introducirlos en la salida que se genera.</span><span class="sxs-lookup"><span data-stu-id="1d40e-104">When you [configure](tasks/er-format-configuration-2016-11.md) an Electronic reporting (ER) solution to generate outbound documents, you define the methods that are used to get data out of the application and enter it in the output that is generated.</span></span> <span data-ttu-id="1d40e-105">Para que el soporte del ciclo de vida de la solución ER sea más eficiente, su solución debe consistir en un [modelo de datos](general-electronic-reporting.md#DataModelComponent) ER y sus componentes [correspondientes](general-electronic-reporting.md#ModelMappingComponent), y también un [formato](general-electronic-reporting.md#FormatComponentOutbound) ER y sus componentes correspondientes, de modo que la asignación del modelo sea específica de la aplicación, mientras que otros componentes permanecen independientes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1d40e-105">To make the life cycle support of the ER solution more efficient, your solution should consist of an ER [data model](general-electronic-reporting.md#DataModelComponent) and its [mapping](general-electronic-reporting.md#ModelMappingComponent) components, and also an ER [format](general-electronic-reporting.md#FormatComponentOutbound) and its mapping components, so that the model mapping is application-specific, whereas other components remain application-agnostic.</span></span> <span data-ttu-id="1d40e-106">Por lo tanto, varios componentes de ER podrían [afectar](general-electronic-reporting.md#FormatComponentOutbound) al proceso de introducir datos en la salida generada.</span><span class="sxs-lookup"><span data-stu-id="1d40e-106">Therefore, several ER components might [affect](general-electronic-reporting.md#FormatComponentOutbound) the process of entering data in the generated output.</span></span>

<span data-ttu-id="1d40e-107">A veces, los datos de la salida generada parecen diferentes de los mismos datos en la base de datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1d40e-107">Sometimes, the data of the generated output looks different than the same data in the application database.</span></span> <span data-ttu-id="1d40e-108">En estos casos, querrá determinar qué componente de ER es responsable de la transformación de datos.</span><span class="sxs-lookup"><span data-stu-id="1d40e-108">In these cases, you will want to determine which ER component is responsible for the data transformation.</span></span> <span data-ttu-id="1d40e-109">La función del depurador de la fuente de datos ER reduce significativamente el tiempo y el coste involucrados en esta investigación.</span><span class="sxs-lookup"><span data-stu-id="1d40e-109">The ER data source debugger feature significantly reduces the time and cost that are involved in this investigation.</span></span> <span data-ttu-id="1d40e-110">Puede interrumpir la ejecución de un formato ER y abrir la interfaz del depurador de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1d40e-110">You can interrupt the execution of an ER format and open the data source debugger interface.</span></span> <span data-ttu-id="1d40e-111">Allí, puede examinar las fuentes de datos disponibles y seleccionar una fuente de datos individual para la ejecución.</span><span class="sxs-lookup"><span data-stu-id="1d40e-111">There, you can browse the available data sources and select an individual data source for execution.</span></span> <span data-ttu-id="1d40e-112">Esta ejecución manual simula la ejecución de la fuente de datos durante la ejecución real de un formato ER.</span><span class="sxs-lookup"><span data-stu-id="1d40e-112">This manual execution simulates the execution of the data source during the real run of an ER format.</span></span> <span data-ttu-id="1d40e-113">El resultado se presenta en una página donde puede analizar los datos que se reciben.</span><span class="sxs-lookup"><span data-stu-id="1d40e-113">The result is presented on a page where you can analyze the data that is received.</span></span>

<span data-ttu-id="1d40e-114">Para activar la función de depuración del origen de datos, configure **Habilitar la depuración de datos al ejecutar formato** en **Sí** en los parámetros de usuario ER.</span><span class="sxs-lookup"><span data-stu-id="1d40e-114">To turn on the data source debugging feature, set the **Enable data debugging at format run** option to **Yes** in the ER user parameters.</span></span> <span data-ttu-id="1d40e-115">Luego puede iniciar la depuración del origen de datos mientras ejecuta un formato ER para generar documentos salientes.</span><span class="sxs-lookup"><span data-stu-id="1d40e-115">You can then start data source debugging while you run an ER format to generate outbound documents.</span></span> <span data-ttu-id="1d40e-116">También puede usar la opción **Comenzar depuración** para iniciar la depuración del origen de datos para un formato ER que está configurado en el [Diseñador de operaciones ER](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span><span class="sxs-lookup"><span data-stu-id="1d40e-116">You can also use the **Start debugging** option to initiate data source debugging for an ER format that is configured in the [ER Operation designer](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span></span>

<span data-ttu-id="1d40e-117">Este tema proporciona pautas para iniciar la depuración del origen de datos para los formatos ER ejecutados.</span><span class="sxs-lookup"><span data-stu-id="1d40e-117">This topic provides guidelines for initiating data source debugging for executed ER formats.</span></span> <span data-ttu-id="1d40e-118">Explica cómo la información puede ayudarle a comprender el flujo de datos y las transformaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="1d40e-118">It explains how the information can help you understand the data flow and data transformations.</span></span> <span data-ttu-id="1d40e-119">Los ejemplos de este tema utilizan el proceso comercial para el procesamiento de los pagos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="1d40e-119">The examples in this topic use the business process for vendor payments processing.</span></span>

## <a name="limitations"></a><span data-ttu-id="1d40e-120">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="1d40e-120">Limitations</span></span>

<span data-ttu-id="1d40e-121">El depurador de fuente de datos se puede utilizar para acceder a los datos de las fuentes de datos que se utilizan en formatos ER que se ejecutan para generar documentos salientes.</span><span class="sxs-lookup"><span data-stu-id="1d40e-121">The data source debugger can be used to access the data of data sources that are used in ER formats that are run to generate outbound documents.</span></span> <span data-ttu-id="1d40e-122">No se puede utilizar para depurar fuentes de datos de formatos ER diseñados para analizar documentos entrantes.</span><span class="sxs-lookup"><span data-stu-id="1d40e-122">It can't be used to debug data sources of ER formats that are designed to parse inbound documents.</span></span>

<span data-ttu-id="1d40e-123">Actualmente no se puede acceder a las siguientes configuraciones de formatos ER para la depuración de fuentes de datos:</span><span class="sxs-lookup"><span data-stu-id="1d40e-123">The following settings of ER formats aren't currently accessible for data source debugging:</span></span>

- <span data-ttu-id="1d40e-124">Transformaciones de formato</span><span class="sxs-lookup"><span data-stu-id="1d40e-124">Format transformations</span></span>
- <span data-ttu-id="1d40e-125">Reglas de validación de formato y mapeo</span><span class="sxs-lookup"><span data-stu-id="1d40e-125">Format and mapping validation rules</span></span>
- <span data-ttu-id="1d40e-126">Habilitar expresiones</span><span class="sxs-lookup"><span data-stu-id="1d40e-126">Enabling expressions</span></span>
- <span data-ttu-id="1d40e-127">Detalles de la recopilación de datos en memoria</span><span class="sxs-lookup"><span data-stu-id="1d40e-127">Details of in-memory data collection</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1d40e-128">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1d40e-128">Prerequisites</span></span>

- <span data-ttu-id="1d40e-129">Para completar los ejemplos de este tema, debe tener acceso a uno de los siguientes [roles](../sysadmin/tasks/assign-users-security-roles.md):</span><span class="sxs-lookup"><span data-stu-id="1d40e-129">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="1d40e-130">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="1d40e-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="1d40e-131">Consultor funcional de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="1d40e-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="1d40e-132">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="1d40e-132">System administrator</span></span>

- <span data-ttu-id="1d40e-133">La empresa debe establecerse en **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-133">The company must be set to **DEMF**.</span></span>

- <span data-ttu-id="1d40e-134">Siga los pasos del [Apéndice 1](#appendix1) de este tema para descargar los componentes de la solución ER de Microsoft que se requieren para procesar los pagos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="1d40e-134">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the Microsoft ER solution that are required to process vendor payments.</span></span>
- <span data-ttu-id="1d40e-135">Siga los pasos del [Apéndice 2](#appendix2) de este tema para preparar los proveedores para el procesamiento de pagos de proveedores utilizando la solución ER que descargará.</span><span class="sxs-lookup"><span data-stu-id="1d40e-135">Follow the steps in [Appendix 2](#appendix2) of this topic to prepare Accounts payable for vendor payment processing by using the ER solution that you will download.</span></span>

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a><span data-ttu-id="1d40e-136">Procesar un pago de proveedor para obtener un archivo de pago</span><span class="sxs-lookup"><span data-stu-id="1d40e-136">Process a vendor payment to get a payment file</span></span>

1. <span data-ttu-id="1d40e-137">Siga los pasos del [Apéndice 3](#appendix3) de este tema para procesar pagos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="1d40e-137">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>

    ![Procesamiento de pagos de proveedores en curso](./media/er-data-debugger-process-payment.png)

2. <span data-ttu-id="1d40e-139">Descargue y guarde el archivo zip en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="1d40e-139">Download and save the zip file to your local computer.</span></span>
3. <span data-ttu-id="1d40e-140">Extraiga el archivo de pago **Transferencia de crédito ISO20022.xml** del archivo zip.</span><span class="sxs-lookup"><span data-stu-id="1d40e-140">Extract the **ISO20022 Credit transfer.xml** payment file from the zip file.</span></span>
4. <span data-ttu-id="1d40e-141">Abra el archivo de pago extraído utilizando el visor de archivos XML.</span><span class="sxs-lookup"><span data-stu-id="1d40e-141">Open the extracted payment file by using the XML file viewer.</span></span>

    <span data-ttu-id="1d40e-142">En el archivo de pagos, el número de cuenta bancaria internacional (IBAN) del proveedor no contiene espacios.</span><span class="sxs-lookup"><span data-stu-id="1d40e-142">In the payment file, the International Bank Account Number (IBAN) code of the vendor bank account contains no spaces.</span></span> <span data-ttu-id="1d40e-143">Por lo tanto, difiere del valor que se [introdujo](#enteredIBANcode) en la página **Cuentas bancarias**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-143">Therefore, it differs from the value that was [entered](#enteredIBANcode) on the **Bank accounts** page.</span></span>

    ![Código IBAN sin espacios](./media/er-data-debugger-payment-file.png)

    <span data-ttu-id="1d40e-145">Puede usar el depurador de origen de datos ER para saber qué componente de la solución ER se usa para truncar espacios en el código IBAN.</span><span class="sxs-lookup"><span data-stu-id="1d40e-145">You can use the ER data source debugger to learn which component of the ER solution is used to truncate spaces in the IBAN code.</span></span>

## <a name="turn-on-data-source-debugging"></a><span data-ttu-id="1d40e-146">Activar la depuración del origen de datos</span><span class="sxs-lookup"><span data-stu-id="1d40e-146">Turn on data source debugging</span></span>

1. <span data-ttu-id="1d40e-147">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-147">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="1d40e-148">En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-148">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="1d40e-149">Establece la opción **Habilitar depuración de datos al ejecutar formato** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-149">Set the **Enable data debugging at format run** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d40e-150">Este parámetro es específico del usuario y específico de la compañía.</span><span class="sxs-lookup"><span data-stu-id="1d40e-150">This parameter is user-specific and company-specific.</span></span>

    ![Cuadro de diálogo parámetros de usuario](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a><span data-ttu-id="1d40e-152">Procesar un pago a proveedor para la depuración</span><span class="sxs-lookup"><span data-stu-id="1d40e-152">Process a vendor payment for debugging</span></span>

1. <span data-ttu-id="1d40e-153">Siga los pasos del [Apéndice 3](#appendix3) de este tema para procesar pagos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="1d40e-153">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>
2. <span data-ttu-id="1d40e-154">En el cuadro de mensaje, seleccione **Sí** para confirmar que desea interrumpir el procesamiento de pagos del proveedor y, en su lugar, iniciar la depuración del origen de datos en la página **Orígenes de datos de depuración**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-154">In the message box, select **Yes** to confirm that you want to interrupt vendor payment processing and instead start data source debugging on the **Debug Datasources** page.</span></span>

    ![Cuadro de mensaje de confirmación](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a><span data-ttu-id="1d40e-156">Fuentes de datos de depuración que se utilizan en el procesamiento de pagos</span><span class="sxs-lookup"><span data-stu-id="1d40e-156">Debug data sources that are used in payment processing</span></span>

### <a name="debug-the-model-mapping"></a><span data-ttu-id="1d40e-157">Depurar la asignación del modelo</span><span class="sxs-lookup"><span data-stu-id="1d40e-157">Debug the model mapping</span></span>

1. <span data-ttu-id="1d40e-158">En la página **Fuentes de datos de depuración**, en el Panel Acciones, seleccione **Asignación de modelos** para comenzar a depurar desde este componente ER.</span><span class="sxs-lookup"><span data-stu-id="1d40e-158">On the **Debug Datasources** page, on the Action Pane, select **Model mapping** to start to debug from this ER component.</span></span>
2. <span data-ttu-id="1d40e-159">En el panel de origen de datos de la izquierda, seleccione la fuente de datos **\$notSentTransactions** y luego seleccione **Leer todos los registros**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-159">In the data source pane on the left, select the **\$notSentTransactions** data source, and then select **Read all records**.</span></span>

    <span data-ttu-id="1d40e-160">Puede elegir **Leer 1 registro**, **Leer 10 registros**, **Leer 100 registros** o **Leer todos los registros** para forzar que se lea el número apropiado de registros desde la fuente de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1d40e-160">You can select **Read 1 record**, **Read 10 records**, **Read 100 records**, or **Read all records** to force the appropriate number of records to be read from the selected data source.</span></span> <span data-ttu-id="1d40e-161">De esta manera, puede simular el acceso al origen de datos desde el formato ER en ejecución.</span><span class="sxs-lookup"><span data-stu-id="1d40e-161">In this way, you can simulate access to the data source from the running ER format.</span></span>

3. <span data-ttu-id="1d40e-162">En el panel de datos de la derecha, seleccione **Expandir todo**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-162">In the data pane on the right, select **Expand all**.</span></span>

    <span data-ttu-id="1d40e-163">Puede ver que la fuente de datos seleccionada del tipo **Lista de registros** contiene un único registro.</span><span class="sxs-lookup"><span data-stu-id="1d40e-163">You can see that the selected data source of the **Record list** type contains a single record.</span></span>

4. <span data-ttu-id="1d40e-164">Amplíe el origen de datos **\$TnotSentTransactions** y seleccione el método anidado **vendBankAccountInTransactionCompany ()**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-164">Expand the **\$notSentTransactions** data source, and select the nested **vendBankAccountInTransactionCompany()** method.</span></span>
5. <span data-ttu-id="1d40e-165">Amplíe el método **vendBankAccountInTransactionCompany()** y seleccione el campo anidado **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-165">Expand the **vendBankAccountInTransactionCompany()** method, and select the nested **IBAN** field.</span></span>
6. <span data-ttu-id="1d40e-166">Seleccione **Obtener valor**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-166">Select **Get value**.</span></span>

    <span data-ttu-id="1d40e-167">Puede elegir **Obtener valor** para forzar la lectura del valor de un campo seleccionado del origen de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1d40e-167">You can select **Get value** to force the value of a selected field of the selected data source to be read.</span></span> <span data-ttu-id="1d40e-168">De esta manera, puede simular el acceso a este campo desde el formato ER en ejecución.</span><span class="sxs-lookup"><span data-stu-id="1d40e-168">In this way, you can simulate access to this field from the running ER format.</span></span>

7. <span data-ttu-id="1d40e-169">Seleccione **Expandir todo**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-169">Select **Expand all**.</span></span>

    ![Valor del campo IBAN en la asignación del modelo](./media/er-data-debugger-debugging-model-mapping.png)

    <span data-ttu-id="1d40e-171">Como puede ver, la asignación del modelo no es responsable de los espacios truncados, porque el código IBAN que devuelve para la cuenta bancaria del proveedor incluye espacios.</span><span class="sxs-lookup"><span data-stu-id="1d40e-171">As you can see, the model mapping isn't responsible for the truncated spaces, because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="1d40e-172">Por lo tanto, debe continuar con la depuración del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1d40e-172">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format-mapping"></a><span data-ttu-id="1d40e-173">Depurar la asignación de formato</span><span class="sxs-lookup"><span data-stu-id="1d40e-173">Debug the format mapping</span></span>

1. <span data-ttu-id="1d40e-174">En la página **Fuentes de datos de depuración**, en el Panel Acciones, seleccione **Asignación de formato** para continuar depurando desde este componente ER.</span><span class="sxs-lookup"><span data-stu-id="1d40e-174">On the **Debug Datasources** page, on the Action Pane, select **Format mapping** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="1d40e-175">Seleccione el origen de datos **\$PaymentByDebtor** y luego seleccione **Leer todos los registros**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-175">Select the **\$PaymentByDebtor** data source, and then select **Read all records**.</span></span>
3. <span data-ttu-id="1d40e-176">Expandir **\$PaymentByDebtor**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-176">Expand **\$PaymentByDebtor**.</span></span>
4. <span data-ttu-id="1d40e-177">Expandir **\$PaymentByDebtor.Lines** y luego seleccione **Leer todos los registros**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-177">Expand **\$PaymentByDebtor.Lines**, and then select **Read all records**.</span></span>
5. <span data-ttu-id="1d40e-178">Expanda **\$PaymentByDebtor.Lines.CreditorAccount**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-178">Expand **\$PaymentByDebtor.Lines.CreditorAccount**.</span></span>
6. <span data-ttu-id="1d40e-179">Expanda **\$PaymentByDebtor.Lines.CreditorAccount.Identification** y luego seleccione **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-179">Expand **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, and then select **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span></span>
7. <span data-ttu-id="1d40e-180">Seleccione **Obtener valor**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-180">Select **Get value**.</span></span>
8. <span data-ttu-id="1d40e-181">Seleccione **Expandir todo**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-181">Select **Expand all**.</span></span>

    ![Valor del campo IBAN en la asignación de formato](./media/er-data-debugger-debugging-format-mapping.png)

    <span data-ttu-id="1d40e-183">Como puede ver, los orígenes de datos de la asignación de formato no son responsables de los espacios truncados, porque el código IBAN que devuelven para la cuenta bancaria del proveedor incluye espacios.</span><span class="sxs-lookup"><span data-stu-id="1d40e-183">As you can see, the data sources of the format mapping aren't responsible for the truncated spaces, because the IBAN code that they return for the vendor bank account includes spaces.</span></span> <span data-ttu-id="1d40e-184">Por lo tanto, debe continuar con la depuración del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1d40e-184">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format"></a><span data-ttu-id="1d40e-185">Depurar el formato</span><span class="sxs-lookup"><span data-stu-id="1d40e-185">Debug the format</span></span>

1. <span data-ttu-id="1d40e-186">En la página **Orígenes de datos de depuración**, en el Panel Acciones, seleccione **Formato** para continuar depurando desde este componente ER.</span><span class="sxs-lookup"><span data-stu-id="1d40e-186">On the **Debug Datasources** page, on the Action Pane, select **Format** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="1d40e-187">Expanda los elementos de formato para seleccionar **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** y luego seleccione **Leer todos los registros**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-187">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, and then select **Read all records**.</span></span>
3. <span data-ttu-id="1d40e-188">Expanda los elementos de formato para seleccionar **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** y luego seleccione **Leer todos los registros**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-188">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, and then select **Read all records**.</span></span>
4. <span data-ttu-id="1d40e-189">Expanda los elementos de formato para seleccionar **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** y luego seleccione **Obtener valor**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-189">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, and then select **Get value**.</span></span>
5. <span data-ttu-id="1d40e-190">Seleccione **Expandir todo**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-190">Select **Expand all**.</span></span>

    ![Valor del campo IBAN en el formato](./media/er-data-debugger-debugging-format.png)

   <span data-ttu-id="1d40e-192">Como puede ver, el enlace de formato no es responsable de los espacios truncados, porque el código IBAN que devuelve para la cuenta bancaria del proveedor incluye espacios.</span><span class="sxs-lookup"><span data-stu-id="1d40e-192">As you can see, the format binding isn't responsible for the truncated spaces because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="1d40e-193">Por lo tanto, el elemento **BankIBAN** está configurado para utilizar una transformación de formato que trunca espacios.</span><span class="sxs-lookup"><span data-stu-id="1d40e-193">Therefore, the **BankIBAN** element is configured to use a format transformation that truncates spaces.</span></span>

6. <span data-ttu-id="1d40e-194">Cierre el depurador de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1d40e-194">Close the data source debugger.</span></span>

### <a name="review-the-format-transformations"></a><span data-ttu-id="1d40e-195">Revisar las transformaciones de formato</span><span class="sxs-lookup"><span data-stu-id="1d40e-195">Review the format transformations</span></span>

1. <span data-ttu-id="1d40e-196">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="1d40e-197">En la página **Configuraciones**, seleccione **Modelo de pago** \> **Transferencia de crédito ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-197">On the **Configurations** page, select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="1d40e-198">Seleccione **Diseñador** y luego expanda los elementos de formato para seleccionar **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-198">Select **Designer**, and then expand the elements to select **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span></span>

    ![Elemento BankIBAN de registro en la página Diseñador de formato](./media/er-data-debugger-referred-transformation.png)

    <span data-ttu-id="1d40e-200">Como puede ver, el elemento **BankIBAN** está configurado para utilizar la transformación **eliminar no alfanumérico**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-200">As you can see, the **BankIBAN** element is configured to use the **remove not alphanumeric** transformation.</span></span>

4. <span data-ttu-id="1d40e-201">Seleccione la pestaña **Transformaciones**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-201">Select the **Transformations** tab.</span></span>

    ![Pestaña Transformaciones para el elemento BankIBAN](./media/er-data-debugger-transformation.png)

    <span data-ttu-id="1d40e-203">Como puede ver, la transformación **eliminar no alfanumérico** se configura para utilizar una expresión que trunca espacios de la cadena de texto que se proporciona.</span><span class="sxs-lookup"><span data-stu-id="1d40e-203">As you can see, the **remove not alphanumeric** transformation is configured to use an expression that truncates spaces from the text string that is provided.</span></span>

## <a name="start-to-debug-in-the-operation-designer"></a><span data-ttu-id="1d40e-204">Comenzar a depurar en el Diseñador de operaciones</span><span class="sxs-lookup"><span data-stu-id="1d40e-204">Start to debug in the Operation designer</span></span>

<span data-ttu-id="1d40e-205">Cuando configura una versión de borrador del formato ER que se puede ejecutar directamente desde el Diseñador de operaciones, puede acceder al depurador de origen de datos seleccionando **Comenzar depuración** en el panel Acciones.</span><span class="sxs-lookup"><span data-stu-id="1d40e-205">When you configure a draft version of the ER format that can be run directly from the Operation designer, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Botón Iniciar depuración en la página Diseñador de formato](./media/er-data-debugger-run-from-designer.png)

<span data-ttu-id="1d40e-207">La asignación de formato y los componentes de formato del formato ER que se está editando están disponibles para la depuración.</span><span class="sxs-lookup"><span data-stu-id="1d40e-207">The format mapping and format components of the ER format that is being edited are available for debugging.</span></span>

## <a name="start-to-debug-in-the-model-mapping-designer"></a><span data-ttu-id="1d40e-208">Comenzar a depurar en el Diseñador de asignación de modelo</span><span class="sxs-lookup"><span data-stu-id="1d40e-208">Start to debug in the Model mapping designer</span></span>

<span data-ttu-id="1d40e-209">Cuando configura una asignación del modelo ER que se puede ejecutar desde la página **Asignación de modelo**, puede acceder al depurador de origen de datos seleccionando **Comenzar depuración** en el panel Acciones.</span><span class="sxs-lookup"><span data-stu-id="1d40e-209">When you configure an ER model mapping that can be run from the **Model mapping** page, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Botón Iniciar depuración en la página Diseñador de asignación de modelo](./media/er-data-debugger-run-from-designer-mapping.png)

<span data-ttu-id="1d40e-211">El componente de asignación de modelo de la asignación ER que se está editando está disponible para la depuración.</span><span class="sxs-lookup"><span data-stu-id="1d40e-211">The model mapping component of the ER mapping that is being edited is available for debugging.</span></span>

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a><span data-ttu-id="1d40e-212">Apéndice 1: obtener una solución ER</span><span class="sxs-lookup"><span data-stu-id="1d40e-212">Appendix 1: Get an ER solution</span></span>

### <a name="download-an-er-solution"></a><span data-ttu-id="1d40e-213">Descargar una solución ER</span><span class="sxs-lookup"><span data-stu-id="1d40e-213">Download an ER solution</span></span>

<span data-ttu-id="1d40e-214">Si desea utilizar una solución de ER para generar un archivo de pago electrónico para un pago de proveedor que se procesa, puede [descargar](download-electronic-reporting-configuration-lcs.md) el formato de pago de ER **Transferencia de crédito ISO20022** disponible en la biblioteca Activos compartidos de Lifecycle Services (LCS) en Microsoft Dynamics o del repositorio global.</span><span class="sxs-lookup"><span data-stu-id="1d40e-214">If you want to use an ER solution to generate an electronic payment file for a vendor payment that is processed, you can [download](download-electronic-reporting-configuration-lcs.md) the **ISO20022 Credit transfer** ER payment format that is available from the Shared asset library in Microsoft Dynamics Lifecycle Services (LCS) or from the Global repository.</span></span>

![Importación del formato de pago de ER en la página Repositorio de configuración](./media/er-data-debugger-import-from-repo.png)

<span data-ttu-id="1d40e-216">Además del formato ER seleccionado, las siguientes [configuraciones](general-electronic-reporting.md#Configuration) deben importarse automáticamente a suinstancia de Microsoft Dynamics 365 Finance como parte de la solución ER **Transferencia de crédito ISO20022**:</span><span class="sxs-lookup"><span data-stu-id="1d40e-216">In addition to the selected ER format, the following [configurations](general-electronic-reporting.md#Configuration) must be automatically imported into your Microsoft Dynamics 365 Finance instance as part of the **ISO20022 Credit transfer** ER solution:</span></span>

- <span data-ttu-id="1d40e-217">**Modelo de pago** [Configuración del modelo de datos de ER](general-electronic-reporting.md#DataModelComponent)</span><span class="sxs-lookup"><span data-stu-id="1d40e-217">**Payment model** [ER data model configuration](general-electronic-reporting.md#DataModelComponent)</span></span>
- <span data-ttu-id="1d40e-218">[Configuración de formato ER](general-electronic-reporting.md#FormatComponentOutbound) de **Transferencia de crédito ISO20022**</span><span class="sxs-lookup"><span data-stu-id="1d40e-218">**ISO20022 Credit transfer** [ER format configuration](general-electronic-reporting.md#FormatComponentOutbound)</span></span>
- <span data-ttu-id="1d40e-219">[Configuración de la asignación del modelo de ER](general-electronic-reporting.md#ModelMappingComponent) de la **Asignación de modelo de pago 1611**</span><span class="sxs-lookup"><span data-stu-id="1d40e-219">**Payment model mapping 1611** [ER model mapping configuration](general-electronic-reporting.md#ModelMappingComponent)</span></span>
- <span data-ttu-id="1d40e-220">Configuración de la asignación del modelo de ER de la **Asignación de modelo de pago a destino ISO20022**</span><span class="sxs-lookup"><span data-stu-id="1d40e-220">**Payment model mapping to destination ISO20022** ER model mapping configuration</span></span>

<span data-ttu-id="1d40e-221">Puede encontrar estas configuraciones en la página **Configuraciones** del marco ER (**Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**).</span><span class="sxs-lookup"><span data-stu-id="1d40e-221">You can find these configurations on the **Configurations** page of the ER framework (**Organization administration** \> **Electronic reporting** \> **Configurations**).</span></span>

![Configuraciones importadas en la página Configuraciones](./media/er-data-debugger-configurations.png)

<span data-ttu-id="1d40e-223">Si falta alguna de las configuraciones enumeradas anteriormente en el árbol de configuración, debe descargarlas manualmente de la biblioteca Activos compartidos de LCS de la misma manera que descargó el formato de pago de ER **Transferencia de crédito ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-223">If any of the previously listed configurations are missing in the configuration tree, you must manually download them from the LCS Shared asset library in the same way that you downloaded the **ISO20022 Credit transfer** ER payment format.</span></span>

### <a name="analyze-the-downloaded-er-solution"></a><span data-ttu-id="1d40e-224">Analizar la solución ER descargada</span><span class="sxs-lookup"><span data-stu-id="1d40e-224">Analyze the downloaded ER solution</span></span>

#### <a name="review-the-model-mapping"></a><span data-ttu-id="1d40e-225">Revisar la asignación de modelo</span><span class="sxs-lookup"><span data-stu-id="1d40e-225">Review the model mapping</span></span>

1. <span data-ttu-id="1d40e-226">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-226">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="1d40e-227">Seleccione **Modelo de pago** \> **Asignación del modelo de pago 1611**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-227">Select **Payment model** \> **Payment model mapping 1611**.</span></span>
3. <span data-ttu-id="1d40e-228">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-228">Select **Designer**.</span></span>
4. <span data-ttu-id="1d40e-229">Selecciona el registro de asignación **Asignación del modelo de pago ISO20022 CT**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-229">Select the **Payment model mapping ISO20022 CT** mapping record.</span></span>
5. <span data-ttu-id="1d40e-230">Seleccione **Diseñador** y luego revise la asignación de modelo que se abre.</span><span class="sxs-lookup"><span data-stu-id="1d40e-230">Select **Designer**, and then review the model mapping that is opened.</span></span>

    <span data-ttu-id="1d40e-231">Tenga en cuenta que el campo **Pagos** del modelo de datos está vinculado al origen de datos **\$notSentTransactions** que devuelve la lista de líneas de pago de proveedores que se están procesando.</span><span class="sxs-lookup"><span data-stu-id="1d40e-231">Notice that the **Payments** field of the data model is bound to the **\$notSentTransactions** data source that returns the list of vendor payment lines that are being processed.</span></span>

    ![Campo de pagos en la página Diseñador de asignación de modelo](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a><span data-ttu-id="1d40e-233">Revisar la asignación de formato</span><span class="sxs-lookup"><span data-stu-id="1d40e-233">Review the format mapping</span></span>

1. <span data-ttu-id="1d40e-234">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-234">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="1d40e-235">Seleccione **Modelo de pago** \> **Transferencia de crédito ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-235">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="1d40e-236">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-236">Select **Designer**.</span></span>
4. <span data-ttu-id="1d40e-237">En la pestaña **Asignación**, revise la asignación de formato que se abre.</span><span class="sxs-lookup"><span data-stu-id="1d40e-237">On the **Mapping** tab, review the format mapping that is opened.</span></span>

    <span data-ttu-id="1d40e-238">Tenga en cuenta que el elemento **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** del archivo **ISO20022CTReports** \> **XMLHeader** está vinculado al origen de datos **\$PaymentByDebtor** que está configurado para agrupar registros de campo **Pagos** del modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="1d40e-238">Notice that the **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** element of the **ISO20022CTReports** \> **XMLHeader** file is bound to the **\$PaymentByDebtor** data source that is configured to group records of the data model's **Payments** field.</span></span>

    ![Elemento PmtInf de la página Diseñador de formato](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a><span data-ttu-id="1d40e-240">Revisar el formato</span><span class="sxs-lookup"><span data-stu-id="1d40e-240">Review the format</span></span>

1. <span data-ttu-id="1d40e-241">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-241">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="1d40e-242">Seleccione **Modelo de pago** \> **Transferencia de crédito ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-242">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="1d40e-243">Seleccione **Diseñador** y luego revise el formato que se abre.</span><span class="sxs-lookup"><span data-stu-id="1d40e-243">Select **Designer**, and then review the format that is opened.</span></span>

    <span data-ttu-id="1d40e-244">Observe que el elemento de formato en **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** está configurado para introducir el código IBAN de la cuenta del proveedor en el archivo de pago.</span><span class="sxs-lookup"><span data-stu-id="1d40e-244">Notice that the format element under **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** is configured to enter the IBAN code of the vendor account in the payment file.</span></span>

    ![Elemento BankIBAN de registro en la página Diseñador de formato](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a><span data-ttu-id="1d40e-246">Apéndice 2: configuración de proveedores</span><span class="sxs-lookup"><span data-stu-id="1d40e-246">Appendix 2: Configure Accounts payable</span></span>

### <a name="modify-a-vendor-property"></a><span data-ttu-id="1d40e-247">Modificar una propiedad de proveedor</span><span class="sxs-lookup"><span data-stu-id="1d40e-247">Modify a vendor property</span></span>

1. <span data-ttu-id="1d40e-248">Vaya a **Proveedores** \> **Proveedores** \> **Todos los proveedores**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-248">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="1d40e-249">Seleccione el proveedor **DE-01002** y, a continuación, en el panel Acciones, en la ficha **Proveedor**, en el grupo **Configurar**, seleccione **Cuentas bancarias**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-249">Select vendor **DE-01002**, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="1d40e-250">En la ficha desplegable **Identificación**, en el campo **IBAN**, <a name="enteredIBANcode"></a>introduzca **GB33 BUKB 2020 1555 5555 55**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-250">On the **Identification** FastTab, in the **IBAN** field, <a name="enteredIBANcode"></a>enter **GB33 BUKB 2020 1555 5555 55**.</span></span>
4. <span data-ttu-id="1d40e-251">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-251">Select **Save**.</span></span>

![Campo IBAN establecido en la página Cuentas bancarias de proveedor](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a><span data-ttu-id="1d40e-253">Configurar un método de pago</span><span class="sxs-lookup"><span data-stu-id="1d40e-253">Set up a method of payment</span></span>

1. <span data-ttu-id="1d40e-254">Vaya a **Proveedores** \> **Configuración de pagos** \> **Formas de pago**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-254">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="1d40e-255">Seleccione el método de pago **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-255">Select the **SEPA CT** payment method.</span></span>
3. <span data-ttu-id="1d40e-256">En la ficha desplegable **Formatos de archivo**, en al sección **Formatos de archivo**, establezca la opción **Formato de exportación electrónica genérica** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-256">On the **File formats** FastTab, in the **File formats** section, set the **Generic electronic Export format** option to **Yes**.</span></span>
4. <span data-ttu-id="1d40e-257">En el campo **Configuración de formato de exportación**, seleccione el formato ER **Transferencia de crédito ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-257">In the **Export format configuration** field, select the **ISO20022 Credit transfer** ER format.</span></span>
5. <span data-ttu-id="1d40e-258">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-258">Select **Save**.</span></span>

![Configuración de formatos de archivo en la página Métodos de pago](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a><span data-ttu-id="1d40e-260">Agregar un pago de proveedor</span><span class="sxs-lookup"><span data-stu-id="1d40e-260">Add a vendor payment</span></span>

1. <span data-ttu-id="1d40e-261">Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-261">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="1d40e-262">Agregar un diario de pagos nuevo.</span><span class="sxs-lookup"><span data-stu-id="1d40e-262">Add a new payment journal.</span></span>
3. <span data-ttu-id="1d40e-263">Seleccione **Líneas** y agregue una nueva línea de pago.</span><span class="sxs-lookup"><span data-stu-id="1d40e-263">Select **Lines**, and add a new payment line.</span></span>
4. <span data-ttu-id="1d40e-264">En el campo **Cuenta**, seleccione el proveedor **DE-01002**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-264">In the **Account** field, select vendor **DE-01002**.</span></span>
5. <span data-ttu-id="1d40e-265">En el campo **Débito**, introduzca un valor.</span><span class="sxs-lookup"><span data-stu-id="1d40e-265">In the **Debit** field, enter a value.</span></span>
6. <span data-ttu-id="1d40e-266">En el campo **Método de pago**, seleccione **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-266">In the **Method of payment** field, select **SEPA CT**.</span></span>
7. <span data-ttu-id="1d40e-267">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-267">Select **Save**.</span></span>

![Pago de proveedor agregado en la página Pagos a proveedores](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a><span data-ttu-id="1d40e-269">Apéndice 3: procesar un pago a proveedor</span><span class="sxs-lookup"><span data-stu-id="1d40e-269">Appendix 3: Process a vendor payment</span></span>

1. <span data-ttu-id="1d40e-270">Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-270">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="1d40e-271">En la página **Diario de pagos a proveedores**, seleccione el diario de pagos que creó anteriormente y luego seleccione **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-271">On the **Vendor payment journal** page, select the payment journal that you previously created, and then select **Lines**.</span></span>
3. <span data-ttu-id="1d40e-272">Seleccione la línea de pago y, a continuación, seleccione **Estado de pago** \> **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-272">Select the payment line, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="1d40e-273">Seleccione **Generar pagos**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-273">Select **Generate payments**.</span></span>
5. <span data-ttu-id="1d40e-274">En el campo **Método de pago**, seleccione **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-274">In the **Method of payment** field, select **SEPA CT**.</span></span>
6. <span data-ttu-id="1d40e-275">En el campo **Cuenta bancaria**, seleccione **DEMF OPER**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-275">In the **Bank account** field, select **DEMF OPER**.</span></span>
7. <span data-ttu-id="1d40e-276">En el cuadro de diálogo **Generar pagos**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-276">In the **Generate payments** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="1d40e-277">En el cuadro de diálogo **Parámetros de informes electrónicos**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d40e-277">In the **Electronic report parameters** dialog box, select **OK**.</span></span>
