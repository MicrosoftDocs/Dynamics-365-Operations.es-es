---
title: Utilizar una ruta relativa en vínculos de datos de modelos y formatos de ER
description: .
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable , ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: a026eec379f98fd32080df50b5e114b423db34ad
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182816"
---
# <a name="use-a-relative-path-in-data-bindings-of-er-models-and-formats"></a><span data-ttu-id="69792-103">Utilizar una ruta relativa en vínculos de datos de modelos y formatos de ER</span><span class="sxs-lookup"><span data-stu-id="69792-103">Use a relative path in data bindings of ER models and formats</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="69792-104">La herramienta Informes electrónicos (ER) permite a los usuarios definir estructuras en formato electrónico y, a continuación, describir cómo deben rellenarse esas estructuras con los datos y algoritmos que existen en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="69792-104">The Electronic reporting (ER) tool lets users define electronic format structures and then describe how those structures should be filled by using data and algorithms that exist in the application.</span></span> <span data-ttu-id="69792-105">Para obtener más información, consulte [Crear configuraciones de informes electrónicos (ER)](electronic-reporting-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="69792-105">For more information, see [Create Electronic reporting (ER) configurations](electronic-reporting-configuration.md).</span></span> <span data-ttu-id="69792-106">Para especificar el flujo de datos para recuperar los datos de Finance and Operations y utilizarlos para generar un documento electrónico, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69792-106">To specify the data flow for retrieving Finance and Operations data and using it to generate  an electronic document, you need to do the following:</span></span>

- <span data-ttu-id="69792-107">Enlace los orígenes de datos configurados con los elementos del modelo de datos específico del dominio diseñado.</span><span class="sxs-lookup"><span data-stu-id="69792-107">Bind configured data sources to elements of the designed domain-specific data model.</span></span> <span data-ttu-id="69792-108">La estructura del modelo y los orígenes de datos seleccionados podrían formar parte de una estructura jerárquica compleja.</span><span class="sxs-lookup"><span data-stu-id="69792-108">The model structure and selected data sources might be part of a complex hierarchical structure.</span></span> <span data-ttu-id="69792-109">Debido a esto, los enlaces finales pueden ser bastante grandes y contener muchos elementos de diferentes tipos (por ejemplo, relaciones, tablas y métodos,).</span><span class="sxs-lookup"><span data-stu-id="69792-109">Because of this, final bindings can be quite large and contain many elements of different types (for example, relations, tables, and methods,).</span></span> <span data-ttu-id="69792-110">Los enlaces pueden ser menos legibles y bastante complejos de revisar y entender, especialmente para los que no son propietarios.</span><span class="sxs-lookup"><span data-stu-id="69792-110">The bindings can become less readable and quite complex to review and understand, especially for non-owners.</span></span> 
- <span data-ttu-id="69792-111">Enlace elementos del modelo de datos con componentes del formato para definir qué datos se rellenarán del modelo de datos a la salida del formato generado.</span><span class="sxs-lookup"><span data-stu-id="69792-111">Bind data model elements with format components to define what data will be populated from the data model to the generated format’s output.</span></span>

<span data-ttu-id="69792-112">Para mejorar la facilidad de uso de los diseñadores de asignación de ER, se ha liberado la característica de la ruta relativa.</span><span class="sxs-lookup"><span data-stu-id="69792-112">To improve usability of ER mapping designers, the relative path feature has been released.</span></span> <span data-ttu-id="69792-113">De forma predeterminada, la opción de representación de la ruta relativa está activada para cualquier nueva instancia de la aplicación donde se habilita la experiencia de diseño de ER ( Microsoft Dynamics 365 Finance, Microsoft Regulatory Configuration Service).</span><span class="sxs-lookup"><span data-stu-id="69792-113">By default, the relative path representation option is turned on for any new instance of the application where ER design experience is enabled (Microsoft Dynamics 365 Finance, Microsoft Regulatory Configuration Service).</span></span> <span data-ttu-id="69792-114">Implementamos el parámetro de la ruta relativa de modo que los usuarios puedan seguir utilizando la ruta completa cuando trabajen con esta presentación de enlaces de ER.</span><span class="sxs-lookup"><span data-stu-id="69792-114">We implemented the relative path parameter so that users can keep using the full path when work with this presentation of ER bindings.</span></span>

<span data-ttu-id="69792-115">[![Parámetros de usuario](./media/relative-path-01.png)](./media/relative-path-01.png)</span><span class="sxs-lookup"><span data-stu-id="69792-115">[![User parameters](./media/relative-path-01.png)](./media/relative-path-01.png)</span></span>

 
<span data-ttu-id="69792-116">Cuando se activa el parámetro de uso de la ruta relativa, un único carácter @ reemplaza la ruta del elemento principal en el enlace del elemento del modelo actual.</span><span class="sxs-lookup"><span data-stu-id="69792-116">When the relative path usage parameter is turned on, a single @ character replaces the path to the parent item in the binding of the current model element.</span></span> <span data-ttu-id="69792-117">La ruta de enlace completa se acorta, lo que hace que toda la asignación sea más obvia y más fácil de entender.</span><span class="sxs-lookup"><span data-stu-id="69792-117">The entire binding path becomes shorter, which makes the entire mapping more obvious and easier to understand.</span></span> <span data-ttu-id="69792-118">En la mayoría de los casos, no se requiere desplazamiento adicional en el diseñador de ER para ver todos los enlaces del modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="69792-118">In most cases, no additional scrolling is required in the ER designer to view all the bindings of the data model.</span></span>

<span data-ttu-id="69792-119">[![Diseñador de asignación de modelo](./media/relative-path-02.png)](./media/relative-path-02.png)</span><span class="sxs-lookup"><span data-stu-id="69792-119">[![Model mapping designer](./media/relative-path-02.png)](./media/relative-path-02.png)</span></span>
 
<span data-ttu-id="69792-120">Cuando empiece a diseñar una nueva expresión de ER, debe introducir solo un carácter para definir un enlace a un campo del elemento principal.</span><span class="sxs-lookup"><span data-stu-id="69792-120">When you start designing a new ER expression, you need to enter only one character to define a binding to a field of the parent item.</span></span>

<span data-ttu-id="69792-121">[![Diseñador de fórmula](./media/relative-path-03.png)](./media/relative-path-03.png)</span><span class="sxs-lookup"><span data-stu-id="69792-121">[![Formula designer](./media/relative-path-03.png)](./media/relative-path-03.png)</span></span>
 
<span data-ttu-id="69792-122">Si decide cambiar el origen de datos del elemento del modelo principal, con un uso de ruta absoluta, tiene que volver a enlazar manualmente este elemento del modelo, así como todos los elementos anidados, a un nuevo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="69792-122">When you decide to change the data source of the parent model item, with absolute path usage, you have to manually rebind this model item, as well as all nested items, to a new data source.</span></span> <span data-ttu-id="69792-123">Cuando se activa el uso de una ruta relativa y selecciona un nuevo origen de datos que se enlazará a un elemento principal, se le ofrece una opción para volver a enlazar automáticamente todos los elementos anidados de este elemento principal con un clic.</span><span class="sxs-lookup"><span data-stu-id="69792-123">When relative path usage is turned on, and you select a new data source to be bound to a parent item, you are offered an option to automatically rebind all nested elements of this parent item with one click.</span></span>

<span data-ttu-id="69792-124">[![Reemplazar mensaje de ruta existente](./media/relative-path-04.png)](./media/relative-path-04.png)</span><span class="sxs-lookup"><span data-stu-id="69792-124">[![Replace existing path message](./media/relative-path-04.png)](./media/relative-path-04.png)</span></span>
 
<span data-ttu-id="69792-125">Si confirma que vuelve a enlazar elementos anidados, el nuevo elemento principal se colocará en la ruta de cada elemento anidado que contenga el elemento principal existente.</span><span class="sxs-lookup"><span data-stu-id="69792-125">If you confirm rebinding of nested items, the new parent item will be placed to the path of each nested item containing the existing parent item.</span></span>
<span data-ttu-id="69792-126">Esta característica no interrumpe la compatibilidad con versiones anteriores del marco de ER.</span><span class="sxs-lookup"><span data-stu-id="69792-126">This feature does not break the backward compatibility of the ER framework.</span></span> <span data-ttu-id="69792-127">Todas las configuraciones de ER previamente diseñadas funcionarán con esta nueva característica, y no se requiere ninguna actualización o conversión.</span><span class="sxs-lookup"><span data-stu-id="69792-127">All previously designed ER configurations will work with this new feature, and no upgrades or conversions are required.</span></span>

> [!NOTE]
> <span data-ttu-id="69792-128">Todos los cambios introducidos por la modificación masiva de enlaces de elementos anidados en asignaciones de modelo se guardan correctamente en un delta de configuración (seguimiento de cambios).</span><span class="sxs-lookup"><span data-stu-id="69792-128">All changes that are introduced by mass modification of bindings of nested elements in model mappings are correctly saved in a configuration delta (trace of changes).</span></span> <span data-ttu-id="69792-129">Esto permite a los clientes reorganizar su versión derivada de asignaciones de modelo a cualquier nueva versión base de esta que se ha modificado mediante esta nueva característica.</span><span class="sxs-lookup"><span data-stu-id="69792-129">This allows customers to rebase their derived version of model mappings to any new base version of it that has been modified by using this new feature.</span></span>