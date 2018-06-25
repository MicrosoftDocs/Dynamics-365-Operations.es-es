---
title: "Visión general de aviso de optimización"
description: "Este tema describe cómo puede usar el asesor de optimización para ayudar a garantizar la configuración óptima de Microsoft Dynamics 365 Finance and Operations."
author: roxanadiaconu
manager: AnnBe
ms.date: 03/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 83648a93f367510d7b04bbd04a9f37689ecfaa59
ms.openlocfilehash: 6eab759e68ac67303f088e9df017fd60ef1f2db6
ms.contentlocale: es-es
ms.lasthandoff: 05/23/2018

---

# <a name="optimization-advisor-overview"></a><span data-ttu-id="52d6b-103">Visión general de aviso de optimización</span><span class="sxs-lookup"><span data-stu-id="52d6b-103">Optimization advisor overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52d6b-104">Este tema describe cómo puede usar el asesor de optimización para ayudar a garantizar la configuración óptima de Microsoft Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="52d6b-104">This topic describes how you can use Optimization advisor to help guarantee optimal configuration of Microsoft Dynamics 365 Finance and Operations.</span></span>

## <a name="overview"></a><span data-ttu-id="52d6b-105">Información general</span><span class="sxs-lookup"><span data-stu-id="52d6b-105">Overview</span></span>

<span data-ttu-id="52d6b-106">La configuración incorrecta y la configuración de un módulo pueden afectar negativamente a la disponibilidad de funciones de Finance and Operations, el rendimiento del sistema, y la ejecución fluida de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="52d6b-106">Incorrect configuration and setup of a module can adversely affect the availability of features in Finance and Operations, system performance, and the smooth operation of business processes.</span></span> <span data-ttu-id="52d6b-107">La calidad de datos empresariales (por ejemplo, la corrección, la integridad y la limpieza de los datos) también afecta al rendimiento del sistema, así como a las capacidades de toma de decisiones de una organización, su productividad, etc.</span><span class="sxs-lookup"><span data-stu-id="52d6b-107">The quality of business data (for example, the correctness, completeness, and cleanliness of the data) also affects system performance, and an organization's decision-making capabilities, productivity, and so on.</span></span>

<span data-ttu-id="52d6b-108">El espacio de trabajo **Asesor de optimización** es una herramienta que permite a los usuarios avanzados, analistas de negocios, consultores funcionales, y las funciones del soporte para la TI identificar problemas en la configuración y datos empresariales de módulo.</span><span class="sxs-lookup"><span data-stu-id="52d6b-108">The **Optimization advisor** workspace is a tool that lets power users, business analysts, functional consultants, and IT support functions identify issues in module configuration and business data.</span></span> <span data-ttu-id="52d6b-109">El asesor de optimización sugiere las prácticas recomendadas para la configuración de módulo e identifica los datos empresariales que son obsoletos o incorrectos.</span><span class="sxs-lookup"><span data-stu-id="52d6b-109">Optimization advisor suggests best practices for module configuration and identifies business data that is obsolete or incorrect.</span></span>

<span data-ttu-id="52d6b-110">El asesor de optimización ejecuta periódicamente un conjunto de reglas de prácticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="52d6b-110">Optimization advisor periodically runs a set of best practice rules.</span></span> <span data-ttu-id="52d6b-111">Se lanza un conjunto predeterminado de reglas junto con Microsoft Dynamics 365 for Finance and Operations versión 8.0 (abril de 2018).</span><span class="sxs-lookup"><span data-stu-id="52d6b-111">A default set of rules is released together with Microsoft Dynamics 365 for Finance and Operations version 8.0 (April 2018).</span></span> <span data-ttu-id="52d6b-112">Sin embargo, los usuarios también pueden crear reglas que sean específicas a sus personalizaciones, soluciones de fabricantes de software independientes (ISV) y datos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="52d6b-112">However, users can also create rules that are specific to their customizations, solutions from independent software vendors (ISVs), and business data.</span></span> <span data-ttu-id="52d6b-113">Para obtener más información acerca de cómo crear reglas, consulte [Crear nuevas reglas](./create-rules-optimization-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="52d6b-113">For more information about how to create rules, see [Create new rules](./create-rules-optimization-advisor.md).</span></span>

<span data-ttu-id="52d6b-114">Cuando una infracción de una regla se detecta, se genera una oportunidad de optimización y aparece en el espacio de trabajo **Asesor de optimización**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-114">When a violation of a rule is detected, an optimization opportunity is generated and appears in the **Optimization advisor** workspace.</span></span> <span data-ttu-id="52d6b-115">Un usuario puede realizar la acción correctora adecuada directamente desde el espacio de trabajo **Asistente de optimización**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-115">A user can take appropriate corrective action directly from the **Optimization advisor** workspace.</span></span>

<span data-ttu-id="52d6b-116">Las ocasiones pueden ser específicas de la empresa o entre empresas, en función del tipo de configuración y de datos que se estén validando.</span><span class="sxs-lookup"><span data-stu-id="52d6b-116">Opportunities can be company-specific or cross-company, depending on the type of setup and data that is being validated.</span></span> <span data-ttu-id="52d6b-117">Las oportunidades entre empresas se pueden ver desde todas las empresas.</span><span class="sxs-lookup"><span data-stu-id="52d6b-117">Cross-company opportunities can be viewed from all companies.</span></span> <span data-ttu-id="52d6b-118">Para ver las oportunidades de una empresa específica, primero debe seleccionar la empresa.</span><span class="sxs-lookup"><span data-stu-id="52d6b-118">To view the opportunities for a specific company, you must first select the company.</span></span>

<span data-ttu-id="52d6b-119">Las directivas de seguridad estándar se aplican a las oportunidades de optimización.</span><span class="sxs-lookup"><span data-stu-id="52d6b-119">Standard security policies apply to optimization opportunities.</span></span> <span data-ttu-id="52d6b-120">Por ejemplo, las oportunidades de optimización relacionadas con la configuración del módulo **Administración de almacenes** están visibles solo para los usuarios que tengan acceso a la gestión de almacenes y puedan cambiar su configuración.</span><span class="sxs-lookup"><span data-stu-id="52d6b-120">For example, the optimization opportunities that are related to configuration of the **Warehouse management** module are visible only to users who have access to Warehouse management and can change its setup.</span></span>

<span data-ttu-id="52d6b-121">Cuando realiza acciones en algunas oportunidades de optimización, el sistema calcula el impacto de la oportunidad en términos de reducción del tiempo de ejecución de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="52d6b-121">When you take action on some optimization opportunities, the system calculates the impact of the opportunity in terms of the reduction in the runtime of business processes.</span></span> <span data-ttu-id="52d6b-122">Desafortunadamente, esta característica no está disponible para todas las oportunidades de optimización.</span><span class="sxs-lookup"><span data-stu-id="52d6b-122">Unfortunately, this feature isn't available for all optimization opportunities.</span></span>

<span data-ttu-id="52d6b-123">Para obtener más información acerca del asesor de optimización, mire el vídeo corto [Asistente de optimización en Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ).</span><span class="sxs-lookup"><span data-stu-id="52d6b-123">To learn more about Optimization advisor, watch the short [Optimization advisor in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ) video.</span></span>

## <a name="optimization-rules"></a><span data-ttu-id="52d6b-124">Reglas de optimización</span><span class="sxs-lookup"><span data-stu-id="52d6b-124">Optimization rules</span></span>

<span data-ttu-id="52d6b-125">Para ver la lista completa de reglas del asesor de optimización y para ver con qué frecuencia se evalúan las reglas, vaya **Administración del sistema** &gt; **Tareas periódicas** &gt; **Mantener la regla de validación de los diagnósticos**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-125">To view the complete list of Optimization advisor rules and to see how often the rules are evaluated, go to **System administration** &gt; **Periodic tasks** &gt; **Maintain diagnostics validation rule**.</span></span> <span data-ttu-id="52d6b-126">Solo se evalúan las reglas que tengan un estado **Activo**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-126">Only rules that have a status of **Active** are evaluated.</span></span> <span data-ttu-id="52d6b-127">La frecuencia de evaluación se puede establecer **Diario**, **Semanal**, **Mensual**, o **No programado**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-127">The evaluation frequency can be set to **Daily**, **Weekly**, **Monthly**, or **Unscheduled**.</span></span>

<span data-ttu-id="52d6b-128">Para activar una evaluación de reglas no programadas, o reevaluar reglas periódicas de fuera de la programación predefinida, vaya **Administración del sistema** &gt; **Tareas periódicas** &gt; **Regla de validación de los diagnósticos de programación**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-128">To trigger the evaluation of unscheduled rules, or to reevaluate periodic rules outside their predefined schedule, go to **System administration** &gt; **Periodic tasks** &gt; **Schedule diagnostics validation rule**.</span></span> <span data-ttu-id="52d6b-129">A continuación, en el cuadro de diálogo **Validación de diagnóstico de la regla**, seleccione una frecuencia de evaluación.</span><span class="sxs-lookup"><span data-stu-id="52d6b-129">Then, in the **Diagnostic rule validation** dialog box, select an evaluation frequency.</span></span> <span data-ttu-id="52d6b-130">Todas las reglas que tengan la frecuencia especificada serán evaluadas.</span><span class="sxs-lookup"><span data-stu-id="52d6b-130">All rules that have the specified frequency will be reevaluated.</span></span>

<span data-ttu-id="52d6b-131">El conjunto de reglas actual de optimización se puede dividir en las categorías siguientes.</span><span class="sxs-lookup"><span data-stu-id="52d6b-131">The current set of optimization rules can be divided into the following categories.</span></span>

### <a name="module-configuration-and-setup"></a><span data-ttu-id="52d6b-132">Instalación y configuración de módulo</span><span class="sxs-lookup"><span data-stu-id="52d6b-132">Module configuration and setup</span></span>

<span data-ttu-id="52d6b-133">La configuración de la gestión de almacenes es un proceso complicado.</span><span class="sxs-lookup"><span data-stu-id="52d6b-133">The setup of Warehouse management is a complicated process.</span></span> <span data-ttu-id="52d6b-134">Para que el proceso sea más sencillos, algunas reglas se han introducido para ayudar a validar la corrección de la configuración.</span><span class="sxs-lookup"><span data-stu-id="52d6b-134">To make the process easier, some rules have been introduced to help validate the correctness of the setup.</span></span> <span data-ttu-id="52d6b-135">Por ejemplo, una regla valida la configuración de las directivas de la ubicación del almacén para las ubicaciones fijas de la variante del producto para los pedidos de ventas y pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="52d6b-135">For example, one rule validates the setup of warehouse location directives for fixed product variant locations for sales orders and transfer orders.</span></span>

<span data-ttu-id="52d6b-136">Además, algunas reglas comprueban si las características que se han habilitado se están utilizando realmente.</span><span class="sxs-lookup"><span data-stu-id="52d6b-136">Additionally, some rules check whether features that have been enabled are actually used.</span></span> <span data-ttu-id="52d6b-137">Por ejemplo, una regla determina si está usando el módulo **Planificación maestra**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-137">For example, one rule determines whether you're using the **Master planning** module.</span></span> <span data-ttu-id="52d6b-138">Si la regla determina que no está usando el módulo, se genera una oportunidad de optimización para sugerir que desactive los procesos de planificación.</span><span class="sxs-lookup"><span data-stu-id="52d6b-138">If the rule determines that you aren't using the module, an optimization opportunity is generated to suggest that you turn off the planning processes.</span></span>

### <a name="system-configuration"></a><span data-ttu-id="52d6b-139">Configuración del sistema</span><span class="sxs-lookup"><span data-stu-id="52d6b-139">System configuration</span></span>

<span data-ttu-id="52d6b-140">Si la funcionalidad específica que se controla mediante una clave de configuración no se utiliza, se genera una oportunidad de optimización que sugiere que deshabilite la clave de configuración.</span><span class="sxs-lookup"><span data-stu-id="52d6b-140">If specific functionality that is controlled by a configuration key isn't used, an optimization opportunity is generated to suggest that you disable the configuration key.</span></span> <span data-ttu-id="52d6b-141">Los ejemplos de claves de configuración incluyen **Peso capturado**, **Planificación presupuestaria**, **Proyecto** y **Lista de proveedores aprobada**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-141">Examples of configuration keys include **Catch weight**, **Budget planning**, **Project**, and **Approved vendor list**.</span></span>

### <a name="business-data-consistency-and-cleanup"></a><span data-ttu-id="52d6b-142">Coherencia y limpieza de datos empresariales</span><span class="sxs-lookup"><span data-stu-id="52d6b-142">Business data consistency and cleanup</span></span>

<span data-ttu-id="52d6b-143">Si los datos maestros no son correctos (por ejemplo, si tiene conversiones de unidad de medida para las unidades que no se han definido o si tiene conversiones de unidad de medida que tengan una división por 0 \[cero\]), se genera una oportunidad de optimización para sugerir que corrija los datos.</span><span class="sxs-lookup"><span data-stu-id="52d6b-143">If master data isn't correct (for example, if you have unit of measure conversions for units that haven't been defined, or if you have unit of measure conversions that have a division by 0 \[zero\]), an optimization opportunity is generated to suggest that you correct the data.</span></span> 

<span data-ttu-id="52d6b-144">Si tiene demasiadas entradas del historial de trabajos por lotes, artículos obsoletos, entradas disponibles cerradas para los artículos habilitados de almacenes, etc., o si estas entradas y artículos son demasiado antiguos, se generan oportunidades de optimización para sugerir que limpie los datos.</span><span class="sxs-lookup"><span data-stu-id="52d6b-144">If you have too many batch job history entries, obsolete items, closed on-hand entries for warehouse enabled items, and so on, or if those entries and items are too old, optimization opportunities are generated to suggest that you clean up the data.</span></span> <span data-ttu-id="52d6b-145">Conservando los datos limpios, puede ayudar a mejorar el rendimiento general del sistema.</span><span class="sxs-lookup"><span data-stu-id="52d6b-145">By keeping your data clean, you can help improve overall system performance.</span></span>

### <a name="best-practices"></a><span data-ttu-id="52d6b-146">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="52d6b-146">Best practices</span></span>

<span data-ttu-id="52d6b-147">Si no está ejecutando algunos procesos de negocio según las prácticas recomendadas (por ejemplo, si se ejecuta el cierre previo de inventario antes de cerrar el inventario, o si usa el lote programado para la transferencia por lotes del subdiario contable), las oportunidades de optimización le informarán acerca de la práctica recomendada y le pedirán que la siga.</span><span class="sxs-lookup"><span data-stu-id="52d6b-147">If you aren't running some business processes according to best practices (for example, if you run inventory pre-closing before the inventory is closed, or if you use the scheduled batch for subledger journal batch transfer), optimization opportunities inform you about the best practice and ask that you follow it.</span></span>

## <a name="optimization-opportunities"></a><span data-ttu-id="52d6b-148">Oportunidades de optimización</span><span class="sxs-lookup"><span data-stu-id="52d6b-148">Optimization opportunities</span></span>

<span data-ttu-id="52d6b-149">Para ver las oportunidades de optimización que se generan durante la evaluación de las reglas de optimización, abra el espacio de trabajo **Asesor de optimización**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-149">To view the optimization opportunities that are generated during the evaluation of optimization rules, open the **Optimization advisor** workspace.</span></span>

<span data-ttu-id="52d6b-150">En este espacio de trabajo, puede ver más información acerca de una oportunidad seleccionando **Más información**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-150">In this workspace, you can view more information about an opportunity by selecting **More information**.</span></span> <span data-ttu-id="52d6b-151">Si desea que el sistema tome medidas y corrija la configuración, limpie los datos, etc., de modo que usted no tenga que abrir las páginas correspondientes, seleccione **Tomar medidas**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-151">If you want the system to take action and correct the setup, clean the data, and so on, so that you don't have to open the corresponding pages yourself, select **Take action**.</span></span>

<span data-ttu-id="52d6b-152">No hay flujo de trabajo para las oportunidades de optimización.</span><span class="sxs-lookup"><span data-stu-id="52d6b-152">There is no workflow for optimization opportunities.</span></span> <span data-ttu-id="52d6b-153">Tras seleccionar **Tomar medidas** o utilizar una ruta de navegación que se proporcione en el cuadro de diálogo **Más información**, la oportunidad de optimización desaparece de la lista.</span><span class="sxs-lookup"><span data-stu-id="52d6b-153">After you select **Take action** or use a navigation path that is provided in the **More information** dialog box, the optimization opportunity disappears from the list.</span></span> <span data-ttu-id="52d6b-154">Si la acción correctiva no resuelve un problema completamente, la oportunidad se generará de nuevo la próxima vez que se evalúe la regla.</span><span class="sxs-lookup"><span data-stu-id="52d6b-154">If the corrective action doesn't completely resolve an issue, the opportunity will be generated again the next time that the rule is evaluated.</span></span>

<span data-ttu-id="52d6b-155">Si una oportunidad no aplica a su rol, puede seleccionar **Ocultar de mi lista**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-155">If an opportunity doesn't apply to your role, you can select **Hide from my list**.</span></span> <span data-ttu-id="52d6b-156">Incluso si la regla detrás de esta oportunidad se activa de nuevo más adelante, no verá la oportunidad en la lista.</span><span class="sxs-lookup"><span data-stu-id="52d6b-156">Even if the rule behind this opportunity is triggered again later, you won't see the opportunity in your list.</span></span>

<span data-ttu-id="52d6b-157">Para desactivar la evaluación de reglas específicas, seleccione la oportunidad que generó la regla y, a continuación seleccione **Desactivar análisis**.</span><span class="sxs-lookup"><span data-stu-id="52d6b-157">To deactivate the evaluation of specific rules, select the opportunity that was generated by the rule, and then select **Deactivate analysis**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52d6b-158">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="52d6b-158">Additional resources</span></span>

[<span data-ttu-id="52d6b-159">Crear nuevas reglas</span><span class="sxs-lookup"><span data-stu-id="52d6b-159">Create new rules</span></span>](./create-rules-optimization-advisor.md)

[<span data-ttu-id="52d6b-160">Asistente de optimización en Dynamics 365 for Finance and Operations (Vídeo)</span><span class="sxs-lookup"><span data-stu-id="52d6b-160">Optimization advisor in Dynamics 365 for Finance and Operations (Video)</span></span>](https://www.youtube.com/watch?v=MRsAzgFCUSQ)
