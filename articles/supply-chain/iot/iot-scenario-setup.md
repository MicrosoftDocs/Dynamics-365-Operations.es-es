---
title: Configuración de escenarios para Inteligencia IoT
description: Este tema describe cómo configurar un escenario en Supply Chain Management para Inteligencia IoT.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5633741fcd9c04b68e5b174447d7ead3c521ccd7
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597177"
---
# <a name="scenario-setup-for-iot-intelligence"></a><span data-ttu-id="6f965-103">Configuración de escenarios para Inteligencia IoT</span><span class="sxs-lookup"><span data-stu-id="6f965-103">Scenario setup for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6f965-104">Este tema describe cómo configurar un escenario en Supply Chain Management para Inteligencia IoT.</span><span class="sxs-lookup"><span data-stu-id="6f965-104">This topic describes how to configure a scenario in Supply Chain Management for IoT Intelligence.</span></span> <span data-ttu-id="6f965-105">Para poder configurar los escenarios, debe [configurar LCS](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="6f965-105">Before you can setup the scenarios, you must [setup LCS](iot-lcs-setup.md).</span></span>

<span data-ttu-id="6f965-106">En este tema, configurará el escenario **Tiempo de inactividad del equipo** para generar una notificación en Supply Chain Management cuando una máquina queda inactiva.</span><span class="sxs-lookup"><span data-stu-id="6f965-106">In this topic, you will configure the **Equipment downtime** scenario to generate a notification in Supply Chain Management when a machine goes down.</span></span>

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a><span data-ttu-id="6f965-107">Configure el escenario **Tiempo de inactividad del equipo** en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="6f965-107">Configure the **Equipment downtime** scenario in Supply Chain Management</span></span>

<span data-ttu-id="6f965-108">El escenario **Tiempo de inactividad del equipo** asigna una señal de inactividad parcial a un umbral de alerta de máquina.</span><span class="sxs-lookup"><span data-stu-id="6f965-108">The **Equipment downtime** scenario maps a part out signal to a machine alert threshold.</span></span> <span data-ttu-id="6f965-109">La máquina se supervisa solo cuando la máquina se selecciona para el escenario y se configura para ejecutarse en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6f965-109">The machine is monitored only when the machine is selected for the scenario and is set to running in Supply Chain Management.</span></span> <span data-ttu-id="6f965-110">Si el tiempo transcurrido desde la última señal de inactividad parcial de la máquina es mayor que el umbral de alerta, entonces se activa una notificación **Máquina inactiva**.</span><span class="sxs-lookup"><span data-stu-id="6f965-110">If the time since the machine’s last received Part Out signal is greater than the alert threshold, then a **Machine down** notification is triggered.</span></span> <span data-ttu-id="6f965-111">Si la máquina todavía está funcionando, cuando se recibe la próxima señal **PartOut**, se activa una notificación **Máquina reactivada**.</span><span class="sxs-lookup"><span data-stu-id="6f965-111">If the machine is still running, when the next **PartOut** signal is received a **Machine up** notification is triggered.</span></span> <span data-ttu-id="6f965-112">Si una máquina permanece inactiva durante 30 minutos, ae activa una nueva notificación **Máquina inactiva**.</span><span class="sxs-lookup"><span data-stu-id="6f965-112">If a machine stays down for 30 mins a new **Machine down** notification is triggered.</span></span>

<span data-ttu-id="6f965-113">El escenario **Tiempo de inactividad del equipo** tiene estas dependencias:</span><span class="sxs-lookup"><span data-stu-id="6f965-113">The **Equipment downtime** scenario has these dependencies:</span></span>

+ <span data-ttu-id="6f965-114">Una orden de producción debe estar ejecutándose en una máquina asignada para que se active una alerta.</span><span class="sxs-lookup"><span data-stu-id="6f965-114">A production order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="6f965-115">Una señal que representa la señal de inactividad parcial de una máquina asignada debe enviarse al IoT Hub con un nombre de propiedad único.</span><span class="sxs-lookup"><span data-stu-id="6f965-115">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="6f965-116">Una propiedad de marca de tiempo de milisegundos de Unix debe estar presente en el mensaje del centro de IoT.</span><span class="sxs-lookup"><span data-stu-id="6f965-116">A Unix milliseconds timestamp property must be present in the IoT hub message.</span></span>

<span data-ttu-id="6f965-117">Para configurar el escenario, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6f965-117">To configure the scenario, follow these steps:</span></span>

1. <span data-ttu-id="6f965-118">Inicie sesión en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6f965-118">Log into Supply Chain Management.</span></span>
2. <span data-ttu-id="6f965-119">Habilite el indicador de función de Inteligencia IoT.</span><span class="sxs-lookup"><span data-stu-id="6f965-119">Enable the IoT Intelligence feature flag.</span></span> <span data-ttu-id="6f965-120">Para más información, consulte [Resumen de administración de funciones](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6f965-120">For more information, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
3. <span data-ttu-id="6f965-121">Configurar las métricas.</span><span class="sxs-lookup"><span data-stu-id="6f965-121">Configure the metrics.</span></span> <span data-ttu-id="6f965-122">Para obtener más información consulte [Cómo configurar las métricas](iot-metrics-setup.md#configure-metrics).</span><span class="sxs-lookup"><span data-stu-id="6f965-122">For more information, see [How to configure metrics](iot-metrics-setup.md#configure-metrics).</span></span>
4. <span data-ttu-id="6f965-123">Navegue a **Control de producción**.</span><span class="sxs-lookup"><span data-stu-id="6f965-123">Navigate to **Production control**.</span></span>
5. <span data-ttu-id="6f965-124">Navegue a **Configurar \> Inteligencia IoT \> Gestión de escenarios**.</span><span class="sxs-lookup"><span data-stu-id="6f965-124">Navigate to **Setup \> IoT Intelligence \> Scenario management**.</span></span>
6. <span data-ttu-id="6f965-125">Haga clic en **Configurar**, en el icono **Tiempo de inactividad del equipo**.</span><span class="sxs-lookup"><span data-stu-id="6f965-125">Click **Configure** on the **Equipment downtime** tile.</span></span> <span data-ttu-id="6f965-126">El asistente de configuración comienza con la página **Definición del esquema del sensor del equipo**.</span><span class="sxs-lookup"><span data-stu-id="6f965-126">The configuration wizard starts with the **Equipment sensor schema definition** page.</span></span> <span data-ttu-id="6f965-127">El objetivo aquí es configurar el esquema en Supply Chain Management para que coincida con el formato JSON de los mensajes de IoT.</span><span class="sxs-lookup"><span data-stu-id="6f965-127">The goal here is to setup the schema in Supply Chain Management to match the JSON format of the IoT messages.</span></span> <span data-ttu-id="6f965-128">Se pueden definir múltiples esquemas de mensajes.</span><span class="sxs-lookup"><span data-stu-id="6f965-128">Multiple message schemas can be defined.</span></span> <span data-ttu-id="6f965-129">Para obtener más información, consulte [Formatos de esquema de mensaje para IoT Hub](iot-schema-format.md).</span><span class="sxs-lookup"><span data-stu-id="6f965-129">For more information, see [Message schema formats for IoT Hub](iot-schema-format.md).</span></span> <span data-ttu-id="6f965-130">En este ejemplo, la carga útil del mensaje contiene un lote de mensajes con este formato:</span><span class="sxs-lookup"><span data-stu-id="6f965-130">In this example, the message payload contains a batch of messages with this format:</span></span>

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. <span data-ttu-id="6f965-131">Agregue una fila a la tabla.</span><span class="sxs-lookup"><span data-stu-id="6f965-131">Add a row to the table.</span></span>

    1. <span data-ttu-id="6f965-132">Seleccione el **Nombre de esquema** en **Id.**.</span><span class="sxs-lookup"><span data-stu-id="6f965-132">Set the **Schema name** to **ID**.</span></span>
    2. <span data-ttu-id="6f965-133">Seleccione la **Ruta de esquema** en **/payload[\*]/id**.</span><span class="sxs-lookup"><span data-stu-id="6f965-133">Set the **Schema path** to **/payload[\*]/id**.</span></span>
    3. <span data-ttu-id="6f965-134">Seleccione la **Descripción** en **Id. del mensaje**.</span><span class="sxs-lookup"><span data-stu-id="6f965-134">Set the **Description** to **Message ID**.</span></span>

8. <span data-ttu-id="6f965-135">Agregue una fila a la tabla.</span><span class="sxs-lookup"><span data-stu-id="6f965-135">Add a row to the table.</span></span>

    1. <span data-ttu-id="6f965-136">Seleccione el **Nombre de esquema** en **Marca de tiempo**.</span><span class="sxs-lookup"><span data-stu-id="6f965-136">Set the **Schema name** to **Timestamp**.</span></span>
    2. <span data-ttu-id="6f965-137">Seleccione la **Ruta de esquema** en **/payload[\*]/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="6f965-137">Set the **Schema path** to **/payload[\*]/timestamp**.</span></span>
    3. <span data-ttu-id="6f965-138">Seleccione la **Descripción** en **Marca de tiempo del mensaje**.</span><span class="sxs-lookup"><span data-stu-id="6f965-138">Set the **Description** to **Message timestamp**.</span></span>

9. <span data-ttu-id="6f965-139">Agregue una fila a la tabla.</span><span class="sxs-lookup"><span data-stu-id="6f965-139">Add a row to the table.</span></span>

    1. <span data-ttu-id="6f965-140">Seleccione el **Nombre de esquema** en **Valor**.</span><span class="sxs-lookup"><span data-stu-id="6f965-140">Set the **Schema name** to **Value**.</span></span>
    2. <span data-ttu-id="6f965-141">Seleccione la **Ruta de esquema** en **/payload[\*]/value**.</span><span class="sxs-lookup"><span data-stu-id="6f965-141">Set the **Schema path** to **/payload[\*]/value**.</span></span>
    3. <span data-ttu-id="6f965-142">Seleccione la **Descripción** en **Valor del mensaje**.</span><span class="sxs-lookup"><span data-stu-id="6f965-142">Set the **Description** to **Message value**.</span></span>

    <span data-ttu-id="6f965-143">No necesita definir todas las propiedades del mensaje, solo las que necesita.</span><span class="sxs-lookup"><span data-stu-id="6f965-143">You don't need to define all the properties in the message, only the ones that you need.</span></span> <span data-ttu-id="6f965-144">En este ejemplo, no creó una fila para **Marca de tiempo de raíz**.</span><span class="sxs-lookup"><span data-stu-id="6f965-144">In this example, you did not create a row for **Root timestamp**.</span></span> <span data-ttu-id="6f965-145">La ruta para **Marca de tiempo de raíz** sería **/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="6f965-145">The path for **Root timestamp** would be **/timestamp**.</span></span>
  
10. <span data-ttu-id="6f965-146">Haga clic en **Siguiente** para ir a la página **Mapa del esquema del sensor del equipo**.</span><span class="sxs-lookup"><span data-stu-id="6f965-146">Click **Next** to go to the **Equipment sensor schema map** page.</span></span>
11. <span data-ttu-id="6f965-147">En la fila de **Id. de recurso de equipo**, seleccione **Nombre del esquema** en **Id.**.</span><span class="sxs-lookup"><span data-stu-id="6f965-147">In the row for **Equipment resource ID** set the **Schema name** to **ID**.</span></span> <span data-ttu-id="6f965-148">Los valores válidos se muestran en una tabla desplegable.</span><span class="sxs-lookup"><span data-stu-id="6f965-148">The valid values are displayed in a dropdown table.</span></span>
12. <span data-ttu-id="6f965-149">En la fila de **Hora UTC**, seleccione el **Nombre del esquema** en **Marca de tiempo**.</span><span class="sxs-lookup"><span data-stu-id="6f965-149">In the row for **UTC time** set the **Schema name** to **Timestamp**.</span></span> <span data-ttu-id="6f965-150">Los valores válidos se muestran en una tabla desplegable.</span><span class="sxs-lookup"><span data-stu-id="6f965-150">The valid values are displayed in a dropdown table.</span></span>
13. <span data-ttu-id="6f965-151">En la fila de **Señal producida parcialmente**, seleccione **Nombre del esquema** en **Valor**.</span><span class="sxs-lookup"><span data-stu-id="6f965-151">In the row for **Part produced signal** set the **Schema name** to **Value**.</span></span> <span data-ttu-id="6f965-152">Los valores válidos se muestran en una tabla desplegable.</span><span class="sxs-lookup"><span data-stu-id="6f965-152">The valid values are displayed in a dropdown table.</span></span>
14. <span data-ttu-id="6f965-153">Haga clic en **Siguiente** para la página **Configuración de id. de recurso de equipo**.</span><span class="sxs-lookup"><span data-stu-id="6f965-153">Click **Next** for the **Equipment resource ID configuration** page.</span></span>
15. <span data-ttu-id="6f965-154">En este paso, asigna los valores del mensaje de IoT Hub a los recursos de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6f965-154">In this step, you map the IoT Hub message values to the Supply Chain Management resources.</span></span>

    1. <span data-ttu-id="6f965-155">En la tabla **Valores de datos de señal**, agregue una nueva fila e introduzca **IoTInt.Machine1225.PartOut** en la columna **Valor**.</span><span class="sxs-lookup"><span data-stu-id="6f965-155">In the **Signal Data Values** table, add a new row, and enter **IoTInt.Machine1225.PartOut** in the **Value** column.</span></span> <span data-ttu-id="6f965-156">El valor de **IoTInt.Machine1225.PartOut** proviene de la propiedad **id** de JSON en el mensaje del centro de IoT.</span><span class="sxs-lookup"><span data-stu-id="6f965-156">The value **IoTInt.Machine1225.PartOut** comes from the JSON **id** property in the IoT hub message.</span></span>
    2. <span data-ttu-id="6f965-157">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6f965-157">Click **Save**.</span></span>
    3. <span data-ttu-id="6f965-158">En la tabla **Asignación de registros comerciales**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6f965-158">In the **Business Record Mapping** table, click **New**.</span></span> <span data-ttu-id="6f965-159">El valor predeterminado para **Tipo de registro comercial** está autorellenado y no es necesario cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="6f965-159">The default value for the **Business record type** is autopopulated, and you don't need to change it.</span></span>
    4. <span data-ttu-id="6f965-160">En la columna **Registro empresarial**, seleccione el recurso de máquina Administración de cadena suplementaria desde el que se envía este valor de señal.</span><span class="sxs-lookup"><span data-stu-id="6f965-160">In the **Business record** column, select the Supple Chain Management machine resource this signal value is being sent from.</span></span>
    5. <span data-ttu-id="6f965-161">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6f965-161">Click **Save**.</span></span>
    6. <span data-ttu-id="6f965-162">Repita estos pasos, agregando una nueva asignación de registros comerciales para **Máquina1226**.</span><span class="sxs-lookup"><span data-stu-id="6f965-162">Repeat these steps, adding a new business record mapping for **Machine1226**.</span></span> <span data-ttu-id="6f965-163">Puede asignar múltiples valores de datos de señal a un solo registro en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6f965-163">You can map multiple signal data values to a single record in Supply Chain Management.</span></span>

16. <span data-ttu-id="6f965-164">Utilice la columna **Seleccionado** para elegir qué máquinas desea procesar.</span><span class="sxs-lookup"><span data-stu-id="6f965-164">Use the **Selected** column to choose which machines you want to process.</span></span> <span data-ttu-id="6f965-165">No tiene que definir todos los valores de señal y no tiene que seleccionar todas las máquinas.</span><span class="sxs-lookup"><span data-stu-id="6f965-165">You do not have to define all signal values and you do not have to select all machines.</span></span>
17. <span data-ttu-id="6f965-166">Haga clic en **Siguiente** para ir a la página **Configuración de señal producida parcialmente**.</span><span class="sxs-lookup"><span data-stu-id="6f965-166">Click **Next** to go to the **Part produced signal configuration** page.</span></span>
18. <span data-ttu-id="6f965-167">En la tabla **Valores de datos de señal**, agregue una fila y establezca **Valor** en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="6f965-167">In the **Signal Data Values** table, add a row, and set **Value** to **True**.</span></span> <span data-ttu-id="6f965-168">El valor **Verdadero** proviene de la propiedad **valor** de JSON en el mensaje del centro de IoT.</span><span class="sxs-lookup"><span data-stu-id="6f965-168">The value **True** comes from the JSON **value** property in the IoT hub message.</span></span> <span data-ttu-id="6f965-169">Puede agregar tantos valores como necesite para su escenario.</span><span class="sxs-lookup"><span data-stu-id="6f965-169">You can add as many values as you need for your scenario.</span></span>
19. <span data-ttu-id="6f965-170">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6f965-170">Click **Save**.</span></span>
20. <span data-ttu-id="6f965-171">Haga clic en **Siguiente** para ir a la página **Umbral de inactividad del equipo**.</span><span class="sxs-lookup"><span data-stu-id="6f965-171">Click **Next** to go to the **Equipment downtime threshold** page.</span></span> <span data-ttu-id="6f965-172">Las máquinas enumeradas son las máquinas asignadas previamente a valores de señal.</span><span class="sxs-lookup"><span data-stu-id="6f965-172">The machines listed are the machines previously mapped to signal values.</span></span> <span data-ttu-id="6f965-173">En este paso, definirá un umbral para determinar si una máquina está inactiva.</span><span class="sxs-lookup"><span data-stu-id="6f965-173">In this step, you define a threshold to determine if a machine is down.</span></span> <span data-ttu-id="6f965-174">Por ejemplo, si establece el umbral en 10, Supply Chain Management genera una notificación si no hay un mensaje de inactividad parcial de una máquina durante 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="6f965-174">For example, if you set the threshold to 10, Supply Chain Management generates a notification if there is no part out message from a machine for 10 minutes.</span></span>
21. <span data-ttu-id="6f965-175">Haga clic en **Siguiente** para pasar a la página **Activar escenario**.</span><span class="sxs-lookup"><span data-stu-id="6f965-175">Click **Next** to go to the **Enable scenario** page.</span></span> <span data-ttu-id="6f965-176">Mueva el control deslizante para habilitar el escenario.</span><span class="sxs-lookup"><span data-stu-id="6f965-176">Toggle the slider to enable the scenario.</span></span>
22. <span data-ttu-id="6f965-177">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6f965-177">Click **Finish**.</span></span>

<span data-ttu-id="6f965-178">La configuración del escenario está completa.</span><span class="sxs-lookup"><span data-stu-id="6f965-178">The scenario setup is complete.</span></span> <span data-ttu-id="6f965-179">Inteligencia IoT comenzará a procesar automáticamente los mensajes de IoT Hub.</span><span class="sxs-lookup"><span data-stu-id="6f965-179">IoT Intelligence will automatically start processing the IoT Hub messages.</span></span>

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a><span data-ttu-id="6f965-180">Configurar el escenario **Calidad de producto** en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="6f965-180">Configure the **Product quality** scenario in Supply Chain Management</span></span>

<span data-ttu-id="6f965-181">El escenario **Calidad de producto** genera una notificación si un atributo de un artículo está fuera de un rango especificado.</span><span class="sxs-lookup"><span data-stu-id="6f965-181">The **Product quality** scenario generates a notification if an attribute of an item is outside a specified range.</span></span> <span data-ttu-id="6f965-182">Por ejemplo, un sensor podría enviar el peso de cada elemento a IoT Hub.</span><span class="sxs-lookup"><span data-stu-id="6f965-182">For example, a sensor could send the weight of each item to IoT Hub.</span></span> <span data-ttu-id="6f965-183">En Supply Chain Management, se generaría una notificación si el artículo era demasiado pesado o demasiado ligero.</span><span class="sxs-lookup"><span data-stu-id="6f965-183">In Supply Chain Management, a notification would be generated if the item was too heavy or too light.</span></span>

<span data-ttu-id="6f965-184">El escenario tiene estas dependencias:</span><span class="sxs-lookup"><span data-stu-id="6f965-184">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="6f965-185">Una orden de producción debe ejecutarse en una máquina asignada y producir un producto con un atributo de lote asignado para que se active una alerta.</span><span class="sxs-lookup"><span data-stu-id="6f965-185">A Production Order must be running on a mapped machine and producing a product with a mapped batch attribute for an alert to be triggered.</span></span>
+ <span data-ttu-id="6f965-186">Una señal que representa el atributo de lote debe enviarse al IoT Hub con un nombre de propiedad único.</span><span class="sxs-lookup"><span data-stu-id="6f965-186">A signal representing the batch attribute must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="6f965-187">Una propiedad de marca de tiempo de milisegundos de Unix debe estar presente en el mensaje de IoT Hub.</span><span class="sxs-lookup"><span data-stu-id="6f965-187">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a><span data-ttu-id="6f965-188">Configurar el escenario **Retrasos de producción** en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="6f965-188">Configure the **Production delays** scenario in Supply Chain Management</span></span>

<span data-ttu-id="6f965-189">El escenario **Retrasos de producción** genera una notificación si el rendimiento de producción cae por debajo de un valor umbral.</span><span class="sxs-lookup"><span data-stu-id="6f965-189">The **Production delays** scenario generates a notification if the production throughput falls below a threshold value.</span></span> <span data-ttu-id="6f965-190">En este escenario, se envía una señal **PartOut** a IoT Hub para cada artículo producido.</span><span class="sxs-lookup"><span data-stu-id="6f965-190">In this scenario, a **PartOut** signal is sent to IoT Hub for each item produced.</span></span> <span data-ttu-id="6f965-191">En Supply Chain Management, el retraso del pedido se calcula en función de cuánto tiempo está programada la ejecución de la orden de producción, cuántos artículos se deben producir, cuánto tiempo ha estado funcionando el trabajo y cuántas señales **PartOut** se reciben.</span><span class="sxs-lookup"><span data-stu-id="6f965-191">In Supply Chain Management, the order delay is calculated based on how long the production order is scheduled to run, how many items should be produced, how long the job has been running, and how many **PartOut** signals are received.</span></span> <span data-ttu-id="6f965-192">Se generaría una notificación de retraso si el número de señales **PartOut** para el trabajo caen por debajo del valor umbral del valor esperado.</span><span class="sxs-lookup"><span data-stu-id="6f965-192">A delay notification would be generated if the number of the **PartOut** signals for the job falls below the threshold value of the expected value.</span></span>

<span data-ttu-id="6f965-193">El escenario tiene estas dependencias:</span><span class="sxs-lookup"><span data-stu-id="6f965-193">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="6f965-194">Una orden de producción debe estar ejecutándose en una máquina asignada para que se active una alerta.</span><span class="sxs-lookup"><span data-stu-id="6f965-194">A Production Order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="6f965-195">Una señal que representa la señal de inactividad parcial de una máquina asignada debe enviarse al IoT Hub con un nombre de propiedad único.</span><span class="sxs-lookup"><span data-stu-id="6f965-195">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="6f965-196">Una propiedad de marca de tiempo de milisegundos de Unix debe estar presente en el mensaje de IoT Hub.</span><span class="sxs-lookup"><span data-stu-id="6f965-196">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="how-to-disable-a-scenario"></a><span data-ttu-id="6f965-197">Cómo deshabilitar un escenario</span><span class="sxs-lookup"><span data-stu-id="6f965-197">How to disable a scenario</span></span>

<span data-ttu-id="6f965-198">Para desactivar un escenario, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6f965-198">To disable a scenario, follow these steps:</span></span>

1. <span data-ttu-id="6f965-199">En Supply Chain Management, navegue hasta **Control de producción \> Configurar \> Inteligencia IoT \> Gestión de escenarios**.</span><span class="sxs-lookup"><span data-stu-id="6f965-199">In Supply Chain Management, navigate to **Production control \> Setup \> IoT Intelligence \> Scenario management**.</span></span>
2. <span data-ttu-id="6f965-200">Haga clic en **Configurar** en el escenario.</span><span class="sxs-lookup"><span data-stu-id="6f965-200">Click **Configure** on the scenario.</span></span>
3. <span data-ttu-id="6f965-201">Haga clic en **Siguiente** para llegar a la última pestaña del asistente.</span><span class="sxs-lookup"><span data-stu-id="6f965-201">Click **Next** to get to the last wizard tab.</span></span>
4. <span data-ttu-id="6f965-202">Mueva el control deslizante para desactivar el escenario.</span><span class="sxs-lookup"><span data-stu-id="6f965-202">Toggle the slider to disable the scenario.</span></span>
