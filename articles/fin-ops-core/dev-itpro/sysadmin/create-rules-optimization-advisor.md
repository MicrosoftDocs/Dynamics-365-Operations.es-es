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
ms.search.scope: Operations, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: e14949b871534868c42d2b26a116e10ff9f05179
ms.sourcegitcommit: 8ff2413b6cb504d2b36fce2bb50441b2e690330e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "3082005"
---
# <a name="create-rules-for-optimization-advisor"></a>Cree reglas para el asesor de optimización

[!include [banner](../includes/banner.md)]

Este tema explica cómo crear nuevas reglas para el **asesor de optimización**. Por ejemplo, puede crear una nueva regla que identifique los casos de solicitud de presupuesto que tengan un título vacío. El uso de títulos en los casos hace que se puedan identificar y buscar con facilidad. Aunque es bastante simple, este ejemplo muestra qué se puede lograr con reglas de optimización. 

Una *regla* es una comprobación de los datos de la aplicación. Si se cumple la condición que evalúa la regla, se crean oportunidades para optimizar procesos o mejorar datos creados. Se puede actuar sobre las oportunidades y, opcionalmente, se puede medir el impacto de las acciones. 

Para crear una nueva regla para el **Asesor de optimización**, agregue una nueva clase que amplíe la clase abstracta **SelfHealingRule** , implemente la interfaz **IDiagnosticsRule** y estén adornada por el atributo **DiagnosticRule**. La clase también debe tener un método adornado con el atributo **DiagnosticsRuleSubscription**. Por convención, eso se hace con el método **opportunityTitle**, que se tratará más adelante. Esta nueva clase se puede agregar a un modelo personalizado con una dependencia en el modelo **SelfHealingRules** . En el siguiente ejemplo, la regla que se implementada se denomina **RFQTitleSelfHealingRule**.

```xpp
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

La clase abstracta **SelfHealingRule** tiene métodos abstractos que deben implementarse en clase de herencia. La base es el método **evaluar** , que devuelve una lista de las oportunidades identificadas por la regla. Las oportunidades pueden ser por entidad jurídica o pueden aplicarse a todo el sistema.

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

El método indicado arriba realiza un bucle sobre las empresas y selecciona casos de solicitud de presupuesto con títulos vacíos en el método **findRFQCasesWithEmptyTitle**. Si se encuentra al menos uno de estos casos, se crea una oportunidad específica de la empresa con el método **getOpportunityForCompany** . Tenga en cuenta que el campo **Datos** en la tabla **SelfHealingOpportunity** es del tipo **Contenedor**, y por lo tanto puede contener cualquier dato relevante para la lógica específica de esta regla. El valor **OpportunityDate** con la marca de hora actual registra la hora de la última evaluación de la oportunidad.  

Las oportunidades también pueden ser entre empresas. En este caso, no es necesario el bucle sobre las empresas y la oportunidad debe crearse con el método **getOpportunityAcrossCompanies**. 

El siguiente código muestra el método **findRFQCasesWithEmptyTitle**, lo que devuelve los id. de casos de solicitud de presupuesto que tienen títulos vacíos.

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

Dos métodos más que deben implementarse son **opportunityTitle** y **opportunityDetails**. El primero devuelve un título corto para la oportunidad, mientras que el último devuelve una descripción detallada de la oportunidad, que también puede incluir datos.

El título devuelto por **opportunityTitle** aparece en la columna **Oportunidad de optimización** en el espacio de trabajo **Asesor de optimización**. También aparece como el encabezado del panel lateral que muestra más información acerca de la oportunidad. Por convención, este método se adorna con el atributo **DiagnosticRuleSubscription**, que toma los siguientes argumentos: 

* **Área de diagnóstico**: una enumeración del tipo **DiagnosticArea** que describe a qué área de la aplicación pertenece la regla, como **DiagnosticArea::SCM**. 

* **Nombre de regla:** una cadena con el nombre de la regla. Esto aparecerá en la columna **Nombre de regla** en el formulario **Regla de validación de diagnóstico** (**DiagnosticsValidationRuleMaintain**). 

* **Frecuencia de ejecución**: una enumeración del tipo **DiagnosticRunFrequency** que describe con qué frecuencia debe ejecutarse la regla, como **DiagnosticRunFrequency::Daily**. 

* **Descripción de la regla:** unna cadena con una descripción más detallada de la regla. Esto aparecerá en la columna **Descripción de la regla** en el formulario **Regla de validación de diagnóstico** (**DiagnosticsValidationRuleMaintain**). 

> [!NOTE]
> El atributo **DiagnosticRuleSubscription** es necesario para que funcione la regla. Normalmente, se usa en **opportunityTitle**, pero puede adornar cualquier método de la clase.

La siguiente es una implementación de ejemplo. Las cadenas sin formato se utilizan por simplicidad, pero una implementación correcta requiere etiquetas. 

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

La descripción devuelta por **opportunityDetails** aparece en el panel lateral que muestra más información acerca de la oportunidad. Esto toma el argumento **SelfHealingOpportunity**, que es el campo **Datos** que se puede usar para proporcionar más detalles acerca de la oportunidad. En el ejemplo, el método devuelve los Id. de los casos de solicitud de presupuesto con un título vacío. 

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

Los dos métodos abstractos restantes a implementar son **provideHealingAction** y **securityMenuItem**. 

**provideHealingAction** devuelve verdadero si se proporciona una acción curativa, de lo contrario, devuelve falso. Si devuelve verdadero, debe implementarse el método **performAction** o se liberará un error. El método **performAction** toma un argumento **SelfHealingOpportunity** , en el que los datos se pueden usar para la acción. En el ejemplo, la acción abre la **PurchRFQCaseTableListPage**para una corrección manual. 

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

En función de los detalles de la regla, es posible realizar una acción automática mediante los datos de la oportunidad. En este ejemplo, el sistema podría generar automáticamente títulos para casos de solicitud de presupuesto. 

**securityMenuItem** devuelve el nombre de un elemento de menú de acción de modo que la regla solo está visible para los usuarios que pueden acceder al elemento de menú de acción. La seguridad puede requerir que las reglas y oportunidades específicas estén accesibles solo para usuarios autorizados. En el ejemplo, solo los usuarios con acceso a **PurchRFQCaseTitleAction** pueden ver la oportunidad. Tenga en cuenta que este elemento de menú de acción se creó para este ejemplo, y se agregó como punto de entrada para el privilegio de seguridad **PurchRFQCaseTableMaintain**. 

> [!NOTE]
> El elemento de menú debe ser un elemento de menú de acción para que la seguridad funcione correctamente. Otros tipos de elementos de menú, como **Elementos del menú de visualización**, no funcionarán correctamente.

```xpp
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

Una vez que se ha compilado la regla, ejecute el siguiente trabajo para que se muestre en la interfaz de usuario (UI).

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

La regla se mostrará en el formulario **Regla de validación de diagnósticos**, disponible en **Administración del sistema** > **Tareas periódicas** > **Mantener regla de validación de diagnósticos**. Para que sea evaluada, vaya a **Administración del sistema** > **Tareas periódicas** > **Programación de la regla de validación de diagnósticos**, seleccione la frecuencia de la regla, como **Diaria**. Haga clic en **Aceptar**. Vaya a **Administración del sistema** > **Asesor de optimización** para ver la nueva oportunidad. 

El siguiente ejemplo es un fragmento de código con el esqueleto de una regla, incluidos todos los métodos y atributos necesarios. Le ayuda a iniciarse con la escritura de nuevas reglas.Las etiquetas y los elementos de menú de acción que se usan en el ejemplo se utilizan solo para efectos de demostración.

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

Para obtener más información, observe este breve vídeo en YouTube : [Asesor de optimización en Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)
