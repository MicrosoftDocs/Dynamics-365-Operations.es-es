---
title: Cree reglas para el asesor de optimización
description: Este tema describe cómo agregar nuevas reglas al asesor de optimización.
author: roxanadiaconu
manager: AnnBe
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: sericks
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 7052aeb4154cefe30a1935dfdca53085a035deb6
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687620"
---
# <a name="create-rules-for-optimization-advisor"></a><span data-ttu-id="faf6b-103">Cree reglas para el asesor de optimización</span><span class="sxs-lookup"><span data-stu-id="faf6b-103">Create rules for Optimization advisor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="faf6b-104">Este tema explica cómo crear nuevas reglas para el **asesor de optimización**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-104">This topic explains how to create new rules for **Optimization advisor**.</span></span> <span data-ttu-id="faf6b-105">Por ejemplo, puede crear una nueva regla que identifique los casos de solicitud de presupuesto que tengan un título vacío.</span><span class="sxs-lookup"><span data-stu-id="faf6b-105">For example, you can create a new rule that identifies which Request for Quotations (RFQ) cases have an empty title.</span></span> <span data-ttu-id="faf6b-106">El uso de títulos en los casos hace que se puedan identificar y buscar con facilidad.</span><span class="sxs-lookup"><span data-stu-id="faf6b-106">Using titles on cases makes them easily identifiable and searchable.</span></span> <span data-ttu-id="faf6b-107">Aunque es bastante simple, este ejemplo muestra qué se puede lograr con reglas de optimización.</span><span class="sxs-lookup"><span data-stu-id="faf6b-107">While quite simple, this example shows what can be achieved with optimization rules.</span></span> 

<span data-ttu-id="faf6b-108">Una *regla* es una comprobación de los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="faf6b-108">A *rule* is a check on application data.</span></span> <span data-ttu-id="faf6b-109">Si se cumple la condición que evalúa la regla, se crean oportunidades para optimizar procesos o mejorar datos creados.</span><span class="sxs-lookup"><span data-stu-id="faf6b-109">If the condition that the rule evaluates is met, opportunities to optimize processes or improve data are created.</span></span> <span data-ttu-id="faf6b-110">Se puede actuar sobre las oportunidades y, opcionalmente, se puede medir el impacto de las acciones.</span><span class="sxs-lookup"><span data-stu-id="faf6b-110">The opportunities can be acted upon and, optionally, the impact of the actions can be measured.</span></span> 

<span data-ttu-id="faf6b-111">Para crear una nueva regla para el **Asesor de optimización**, agregue una nueva clase que amplíe la clase abstracta **SelfHealingRule** , implemente la interfaz **IDiagnosticsRule** y estén adornada por el atributo **DiagnosticRule**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-111">To create a new rule for the **Optimization advisor**, add a new class that extends the **SelfHealingRule** abstract class, implements the **IDiagnosticsRule** interface, and is decorated by the **DiagnosticRule** attribute.</span></span> <span data-ttu-id="faf6b-112">La clase también debe tener un método adornado con el atributo **DiagnosticsRuleSubscription**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-112">The class must also have a method decorated with the **DiagnosticsRuleSubscription** attribute.</span></span> <span data-ttu-id="faf6b-113">Por convención, eso se hace con el método **opportunityTitle**, que se tratará más adelante.</span><span class="sxs-lookup"><span data-stu-id="faf6b-113">By convention, that is done on the **opportunityTitle** method, which will be discussed later.</span></span> <span data-ttu-id="faf6b-114">Esta nueva clase se puede agregar a un modelo personalizado con una dependencia en el modelo **SelfHealingRules** .</span><span class="sxs-lookup"><span data-stu-id="faf6b-114">This new class can be added to a custom model with a dependency on the **SelfHealingRules** model.</span></span> <span data-ttu-id="faf6b-115">En el siguiente ejemplo, la regla que se implementada se denomina **RFQTitleSelfHealingRule**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-115">In the following example, the rule being implemented is called **RFQTitleSelfHealingRule**.</span></span>

```xpp
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

<span data-ttu-id="faf6b-116">La clase abstracta **SelfHealingRule** tiene métodos abstractos que deben implementarse en clase de herencia.</span><span class="sxs-lookup"><span data-stu-id="faf6b-116">The **SelfHealingRule** abstract class has abstract methods that must be implemented in inheriting classes.</span></span> <span data-ttu-id="faf6b-117">La base es el método **evaluar** , que devuelve una lista de las oportunidades identificadas por la regla.</span><span class="sxs-lookup"><span data-stu-id="faf6b-117">The core is the **evaluate** method, which returns a list of the opportunities identified by the rule.</span></span> <span data-ttu-id="faf6b-118">Las oportunidades pueden ser por entidad jurídica o pueden aplicarse a todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="faf6b-118">Opportunities can be per legal entity or can apply to the whole system.</span></span>

```xpp
protected List evaluate() 
{ 
    List results = new List(Types::Record); 
    
    DataArea dataArea; 

    while select id from dataArea 
        where !dataArea.isVirtual 
    { 
        changecompany(dataArea.id) 
        { 
            container result = this.findRFQCasesWithEmptyTitle(); 

            if (conLen(result) > 0) 
            { 
                SelfHealingOpportunity opportunity = this.getOpportunityForCompany(dataArea.Id); 
                opportunity.EvaluationState = SelfHealingEvaluationState::Evaluated; 
                opportunity.Data = result; 
                opportunity.OpportunityDate = DateTimeUtil::utcNow(); 
                
                results.addEnd(opportunity); 
            } 
        } 
    } 
    
    return results; 
} 
```

<span data-ttu-id="faf6b-119">El método indicado arriba realiza un bucle sobre las empresas y selecciona casos de solicitud de presupuesto con títulos vacíos en el método **findRFQCasesWithEmptyTitle**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-119">The method shown above loops over companies and selects RFQ cases with empty titles in the **findRFQCasesWithEmptyTitle** method.</span></span> <span data-ttu-id="faf6b-120">Si se encuentra al menos uno de estos casos, se crea una oportunidad específica de la empresa con el método **getOpportunityForCompany** .</span><span class="sxs-lookup"><span data-stu-id="faf6b-120">If at least one such case is found, then a company-specific opportunity is created with the **getOpportunityForCompany** method.</span></span> <span data-ttu-id="faf6b-121">Tenga en cuenta que el campo **Datos** en la tabla **SelfHealingOpportunity** es del tipo **Contenedor**, y por lo tanto puede contener cualquier dato relevante para la lógica específica de esta regla.</span><span class="sxs-lookup"><span data-stu-id="faf6b-121">Notice that the field **Data** in the **SelfHealingOpportunity** table is of type **Container**, and can therefore contain any data relevant to the logic specific to this rule.</span></span> <span data-ttu-id="faf6b-122">El valor **OpportunityDate** con la marca de hora actual registra la hora de la última evaluación de la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="faf6b-122">Setting **OpportunityDate** with the current timestamp registers the time of the latest evaluation of the opportunity.</span></span>  

<span data-ttu-id="faf6b-123">Las oportunidades también pueden ser entre empresas.</span><span class="sxs-lookup"><span data-stu-id="faf6b-123">Opportunities can also be cross-company.</span></span> <span data-ttu-id="faf6b-124">En este caso, no es necesario el bucle sobre las empresas y la oportunidad debe crearse con el método **getOpportunityAcrossCompanies**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-124">In this case, the loop over companies is not necessary and the opportunity must be created with the **getOpportunityAcrossCompanies** method.</span></span> 

<span data-ttu-id="faf6b-125">El siguiente código muestra el método **findRFQCasesWithEmptyTitle**, lo que devuelve los id. de casos de solicitud de presupuesto que tienen títulos vacíos.</span><span class="sxs-lookup"><span data-stu-id="faf6b-125">The following code shows the **findRFQCasesWithEmptyTitle** method, which returns the IDs of the RFQ cases that have empty titles.</span></span>

```xpp
private container findRFQCasesWithEmptyTitle() 
{ 
    container result; 

    PurchRFQCaseTable rfqCase; 
    while select RFQCaseId from rfqCase 
        where rfqCase.Name == '' 
    { 
        result += rfqCase.RFQCaseId; 
    } 
    
    return result; 
} 
```

<span data-ttu-id="faf6b-126">Dos métodos más que deben implementarse son **opportunityTitle** y **opportunityDetails**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-126">Two more methods that must be implemented are **opportunityTitle** and **opportunityDetails**.</span></span> <span data-ttu-id="faf6b-127">El primero devuelve un título corto para la oportunidad, mientras que el último devuelve una descripción detallada de la oportunidad, que también puede incluir datos.</span><span class="sxs-lookup"><span data-stu-id="faf6b-127">The former returns a short title for the opportunity, the latter returns a detailed description of the opportunity, which can also include data.</span></span>

<span data-ttu-id="faf6b-128">El título devuelto por **opportunityTitle** aparece en la columna **Oportunidad de optimización** en el espacio de trabajo **Asesor de optimización**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-128">The title returned by **opportunityTitle** appears under the **Optimization opportunity** column in the **Optimization advisor** workspace.</span></span> <span data-ttu-id="faf6b-129">También aparece como el encabezado del panel lateral que muestra más información acerca de la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="faf6b-129">It also appears as the header of the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="faf6b-130">Por convención, este método se adorna con el atributo **DiagnosticRuleSubscription**, que toma los siguientes argumentos:</span><span class="sxs-lookup"><span data-stu-id="faf6b-130">By convention, this method is decorated with the **DiagnosticRuleSubscription** attribute, which takes the following arguments:</span></span> 

* <span data-ttu-id="faf6b-131">**Área de diagnóstico**: una enumeración del tipo **DiagnosticArea** que describe a qué área de la aplicación pertenece la regla, como **DiagnosticArea::SCM**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-131">**Diagnostic area** – An enum of type **DiagnosticArea** that describes what area of the application the rule belongs to, such as **DiagnosticArea::SCM**.</span></span> 

* <span data-ttu-id="faf6b-132">**Nombre de regla:** una cadena con el nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="faf6b-132">**Rule name** – A string with the rule name.</span></span> <span data-ttu-id="faf6b-133">Esto aparecerá en la columna **Nombre de regla** en el formulario **Regla de validación de diagnóstico** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="faf6b-133">This will appear under the **Rule name** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

* <span data-ttu-id="faf6b-134">**Frecuencia de ejecución**: una enumeración del tipo **DiagnosticRunFrequency** que describe con qué frecuencia debe ejecutarse la regla, como **DiagnosticRunFrequency::Daily**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-134">**Run frequency** – An enum of type **DiagnosticRunFrequency** that describes how often the rule should be run, such as **DiagnosticRunFrequency::Daily**.</span></span> 

* <span data-ttu-id="faf6b-135">**Descripción de la regla:** unna cadena con una descripción más detallada de la regla.</span><span class="sxs-lookup"><span data-stu-id="faf6b-135">**Rule description** – A string with a more detailed description of the rule.</span></span> <span data-ttu-id="faf6b-136">Esto aparecerá en la columna **Descripción de la regla** en el formulario **Regla de validación de diagnóstico** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="faf6b-136">This will appear under the **Rule description** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

> [!NOTE]
> <span data-ttu-id="faf6b-137">El atributo **DiagnosticRuleSubscription** es necesario para que funcione la regla.</span><span class="sxs-lookup"><span data-stu-id="faf6b-137">The **DiagnosticRuleSubscription** attribute is required for the rule to work.</span></span> <span data-ttu-id="faf6b-138">Normalmente, se usa en **opportunityTitle**, pero puede adornar cualquier método de la clase.</span><span class="sxs-lookup"><span data-stu-id="faf6b-138">Typically, it is used on **opportunityTitle**, but it can decorate any method of the class.</span></span>

<span data-ttu-id="faf6b-139">La siguiente es una implementación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="faf6b-139">The following is an example implementation.</span></span> <span data-ttu-id="faf6b-140">Las cadenas sin formato se utilizan por simplicidad, pero una implementación correcta requiere etiquetas.</span><span class="sxs-lookup"><span data-stu-id="faf6b-140">Raw strings are used for simplicity, but a correct implementation requires labels.</span></span> 

```xpp
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

<span data-ttu-id="faf6b-141">La descripción devuelta por **opportunityDetails** aparece en el panel lateral que muestra más información acerca de la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="faf6b-141">The description returned by **opportunityDetails** appears on the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="faf6b-142">Esto toma el argumento **SelfHealingOpportunity**, que es el campo **Datos** que se puede usar para proporcionar más detalles acerca de la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="faf6b-142">This takes the **SelfHealingOpportunity** argument, which is **Data** field that can be used to provide more details about the opportunity.</span></span> <span data-ttu-id="faf6b-143">En el ejemplo, el método devuelve los Id. de los casos de solicitud de presupuesto con un título vacío.</span><span class="sxs-lookup"><span data-stu-id="faf6b-143">In the example, the method returns the IDs of the RFQ cases with an empty title.</span></span> 

```xpp
public str opportunityDetails(SelfHealingOpportunity _opportunity) 
{ 
    str details = ''; 
    container opportunityData = _opportunity.Data; 
    int affectedRFQCasesCount = conLen(opportunityData); 

    if (affectedRFQCasesCount != 0) 
    { 
        details = 'The following Request for Quotation cases have an empty title:\n'; 
        for (int i = 1; i <= affectedRFQCasesCount ; i++) 
        { 
            PurchRFQCaseId rfqCaseId = conPeek(opportunityData, i); 
            details += rfqCaseId + '\n'; 
        } 
    } 

    return details; 
}
```

<span data-ttu-id="faf6b-144">Los dos métodos abstractos restantes a implementar son **provideHealingAction** y **securityMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-144">The two remaining abstract methods to implement are **provideHealingAction** and **securityMenuItem**.</span></span> 

<span data-ttu-id="faf6b-145">**provideHealingAction** devuelve verdadero si se proporciona una acción curativa, de lo contrario, devuelve falso.</span><span class="sxs-lookup"><span data-stu-id="faf6b-145">**provideHealingAction** returns true if a healing action is provided, otherwise, it returns false.</span></span> <span data-ttu-id="faf6b-146">Si devuelve verdadero, debe implementarse el método **performAction** o se liberará un error.</span><span class="sxs-lookup"><span data-stu-id="faf6b-146">If true is returned, the method **performAction** must be implemented, or an error will be thrown.</span></span> <span data-ttu-id="faf6b-147">El método **performAction** toma un argumento **SelfHealingOpportunity** , en el que los datos se pueden usar para la acción.</span><span class="sxs-lookup"><span data-stu-id="faf6b-147">The **performAction** method takes a **SelfHealingOpportunity** argument, in which the data can be used for the action.</span></span> <span data-ttu-id="faf6b-148">En el ejemplo, la acción abre la **PurchRFQCaseTableListPage** para una corrección manual.</span><span class="sxs-lookup"><span data-stu-id="faf6b-148">In the example, the action opens the **PurchRFQCaseTableListPage**, for manual correction.</span></span> 

```xpp
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

<span data-ttu-id="faf6b-149">En función de los detalles de la regla, es posible realizar una acción automática mediante los datos de la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="faf6b-149">Depending on the specifics of the rule, it might be possible to take an automatic action using the opportunity data.</span></span> <span data-ttu-id="faf6b-150">En este ejemplo, el sistema podría generar automáticamente títulos para casos de solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="faf6b-150">In this example, the system could generate titles for RFQ cases automatically.</span></span> 

<span data-ttu-id="faf6b-151">**securityMenuItem** devuelve el nombre de un elemento de menú de acción de modo que la regla solo está visible para los usuarios que pueden acceder al elemento de menú de acción.</span><span class="sxs-lookup"><span data-stu-id="faf6b-151">**securityMenuItem** returns the name of an action menu item such that the rule is only visible to users who can access the action menu item.</span></span> <span data-ttu-id="faf6b-152">La seguridad puede requerir que las reglas y oportunidades específicas estén accesibles solo para usuarios autorizados.</span><span class="sxs-lookup"><span data-stu-id="faf6b-152">Security might require that specific rules and opportunities are accessible only to authorized users.</span></span> <span data-ttu-id="faf6b-153">En el ejemplo, solo los usuarios con acceso a **PurchRFQCaseTitleAction** pueden ver la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="faf6b-153">In the example, only users with access to **PurchRFQCaseTitleAction** can view the opportunity.</span></span> <span data-ttu-id="faf6b-154">Tenga en cuenta que este elemento de menú de acción se creó para este ejemplo, y se agregó como punto de entrada para el privilegio de seguridad **PurchRFQCaseTableMaintain**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-154">Notice that this action menu item was created for this example, and was added as an entry point for the **PurchRFQCaseTableMaintain** security privilege.</span></span> 

> [!NOTE]
> <span data-ttu-id="faf6b-155">El elemento de menú debe ser un elemento de menú de acción para que la seguridad funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="faf6b-155">The menu item must be an action menu item for security to work correctly.</span></span> <span data-ttu-id="faf6b-156">Otros tipos de elementos de menú, como **Elementos del menú de visualización**, no funcionarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="faf6b-156">Other menu item types, such as **Display menu items** will not work correctly.</span></span>

```xpp
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

<span data-ttu-id="faf6b-157">Una vez que se ha compilado la regla, ejecute el siguiente trabajo para que se muestre en la interfaz de usuario (UI).</span><span class="sxs-lookup"><span data-stu-id="faf6b-157">After the rule has compiled, execute the following job to have it display in the user interface (UI).</span></span>

```xpp
class ScanNewRulesJob 
{         
    public static void main(Args _args) 
    {         
        SysExtensionCache::clearAllScopes(); 
        var controller = new DiagnosticsRuleController(); 
        controller.runOperation(); 
    } 
} 
```

<span data-ttu-id="faf6b-158">La regla se mostrará en el formulario **Regla de validación de diagnósticos**, disponible en **Administración del sistema** > **Tareas periódicas** > **Mantener regla de validación de diagnósticos**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-158">The rule will display in the **Diagnostics validation rule** form, available from **System administration** > **Periodic tasks** > **Maintain diagnostics validation rule**.</span></span> <span data-ttu-id="faf6b-159">Para que sea evaluada, vaya a **Administración del sistema** > **Tareas periódicas** > **Programación de la regla de validación de diagnósticos**, seleccione la frecuencia de la regla, como **Diaria**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-159">To have it evaluated, go to **System administration** > **Periodic tasks** > **Schedule diagnostics validation rule**, select the frequency of the rule, such as **Daily**.</span></span> <span data-ttu-id="faf6b-160">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="faf6b-160">Click **OK**.</span></span> <span data-ttu-id="faf6b-161">Vaya a **Administración del sistema** > **Asesor de optimización** para ver la nueva oportunidad.</span><span class="sxs-lookup"><span data-stu-id="faf6b-161">Go to **System administration** > **Optimization advisor** to view the new opportunity.</span></span> 

<span data-ttu-id="faf6b-162">El siguiente ejemplo es un fragmento de código con el esqueleto de una regla, incluidos todos los métodos y atributos necesarios.</span><span class="sxs-lookup"><span data-stu-id="faf6b-162">The following example is a code snippet with the skeleton of a rule including all the required methods and attributes.</span></span> <span data-ttu-id="faf6b-163">Le ayuda a iniciarse con la escritura de nuevas reglas.</span><span class="sxs-lookup"><span data-stu-id="faf6b-163">It helps you get started with writing new rules.</span></span> <span data-ttu-id="faf6b-164">Las etiquetas y los elementos de menú de acción que se usan en el ejemplo se utilizan solo para efectos de demostración.</span><span class="sxs-lookup"><span data-stu-id="faf6b-164">The labels and action menu items that are used in the example are only used for demonstration purpose.</span></span>

```xpp
[DiagnosticsRuleAttribute]
public final class SkeletonSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule
{
    [DiagnosticsRuleSubscription(DiagnosticsArea::SCM,
                                 "@SkeletonRuleLabels:SkeletonRuleTitle", // Label with the title of the rule
                                 DiagnosticsRunFrequency::Monthly,
                                 "@SkeletonRuleLabels:SkeletonRuleDescription")] // Label with a description of the rule
    public str opportunityTitle()
    {
        // Return a label with the title of the opportunity
        return "@SkeletonRuleLabels:SkeletonOpportunityTitle";
    }

    public str opportunityDetails(SelfHealingOpportunity _opportunity)
    {
        str details = "";

        // Use _opportunity.data to provide details on the opportunity

        return details;
    }

    protected List evaluate()
    {
        List results = new List(Types::Record);

        // Write here the core logic of the rule

        // When creating an opportunity, use:
        //     * this.getOpportunityForCompany() for company specific opportunities
        //     * this.getOpportunityAcrossCompanies() for cross-company opportunities

        return results;
    }

    public boolean providesHealingAction()
    {
        return true;
    }

    protected void performAction(SelfHealingOpportunity _opportunity)
    {
        // Place here the code that performs the healing action

        // To open a form, use the following:
        // new MenuFunction(menuItemDisplayStr(SkeletonRuleDisplayMenuItem), MenuItemType::Display).run();
    }

    public MenuName securityMenuItem()
    {
        return menuItemActionStr(SkeletonRuleActionMenuItem);
    }

}
```

<span data-ttu-id="faf6b-165">Para obtener más información, observe este breve vídeo en YouTube : [Asesor de optimización en Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)</span><span class="sxs-lookup"><span data-stu-id="faf6b-165">For more information, watch the short YouTube video: [Optimization advisor in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)</span></span>
