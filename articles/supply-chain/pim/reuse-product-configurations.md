---
title: Volver a utilizar configuraciones de producto
description: "Puede especificar que desee volver a usar automáticamente una configuración existente para un producto. A continuación, cuando un usuario completa una sesión de configuración, el sistema comprueba si ya existe una configuración que coincide con las selecciones del usuario. Si se encuentra una configuración que coincide, se vuelven a usar el id. de configuración, la lista de materiales (L. MAT) correspondiente y la ruta."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: c447440c33c1f80c6056974086b90d3b43e8499e
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---

# <a name="reuse-product-configurations"></a><span data-ttu-id="d604d-105">Volver a utilizar configuraciones de producto</span><span class="sxs-lookup"><span data-stu-id="d604d-105">Reuse product configurations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d604d-106">Puede especificar que desee volver a usar automáticamente una configuración existente para un producto.</span><span class="sxs-lookup"><span data-stu-id="d604d-106">You can specify that you want to automatically reuse an existing configuration for a product.</span></span> <span data-ttu-id="d604d-107">A continuación, cuando un usuario completa una sesión de configuración, el sistema comprueba si ya existe una configuración que coincide con las selecciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="d604d-107">Then, when a user has completed a configuration session, the system verifies whether a configuration that matches the user’s selections already exists.</span></span> <span data-ttu-id="d604d-108">Si se encuentra una configuración que coincide, se vuelven a usar el id. de configuración, la lista de materiales (L. MAT) correspondiente y la ruta.</span><span class="sxs-lookup"><span data-stu-id="d604d-108">If a matching configuration is found, the configuration ID, corresponding bill of materials (BOM), and route are reused.</span></span>

<a name="requirements-for-reusing-configurations"></a><span data-ttu-id="d604d-109">Requisitos para volver a usar las configuraciones</span><span class="sxs-lookup"><span data-stu-id="d604d-109">Requirements for reusing configurations</span></span>
---------------------------------------

<span data-ttu-id="d604d-110">Para habilitar las configuraciones que se reutilizarán, debe especificar la siguiente información para componentes y atributos en la página de **Detalles del modelo de configuración de productos**:</span><span class="sxs-lookup"><span data-stu-id="d604d-110">To enable configurations to be reused, you must specify the following information for the components and attributes on the **Product configuration model details** page:</span></span>

-   <span data-ttu-id="d604d-111">**Componentes y subcomponentes**: en la ficha desplegable **General** del campo **Reutilizar configuraciones** seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d604d-111">**Components and subcomponents** – On the **General** FastTab, in the **Reuse configurations** field, select **Yes**.</span></span>
-   <span data-ttu-id="d604d-112">**Atributos**: en la ficha desplegable **Atributos**, seleccione la opción **Incluir en la reutilización**.</span><span class="sxs-lookup"><span data-stu-id="d604d-112">**Attributes** – On the **Attributes** FastTab, select the **Include in reuse** option.</span></span> <span data-ttu-id="d604d-113">La opción se muestra solo cuando el componente relacionado se habilita para un nuevo uso.</span><span class="sxs-lookup"><span data-stu-id="d604d-113">This option appears only when the related component is enabled for reuse.</span></span> <span data-ttu-id="d604d-114">Si no selecciona ningún atributo para un nuevo uso, la configuración siempre se vuelve a usar, independientemente de las selecciones del usuario durante una sesión de configuración.</span><span class="sxs-lookup"><span data-stu-id="d604d-114">If you don't select any attributes for reuse, the configuration is always reused, regardless of the user’s selections during a configuration session.</span></span> <span data-ttu-id="d604d-115">Los atributos de valor de la configuración existente deben coincidir con las selecciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="d604d-115">The attribute values in the existing configuration must match the user’s selections.</span></span> <span data-ttu-id="d604d-116">Por ejemplo, si el usuario selecciona como color el **Azul** durante una sesión de configuración, el sistema comprueba si una configuración existente del componente tiene el color azul.</span><span class="sxs-lookup"><span data-stu-id="d604d-116">For example, if the user selects **Blue** as the color during a configuration session, the system verifies whether an existing configuration of the component has the color blue.</span></span>

## <a name="resetting-configuration-reuse"></a><span data-ttu-id="d604d-117">Restablecer la reutilización de la configuración</span><span class="sxs-lookup"><span data-stu-id="d604d-117">Resetting configuration reuse</span></span>
<span data-ttu-id="d604d-118">Cuando restablece la reutilización de la configuración, las configuraciones anteriormente creadas ya no se tienen en cuenta.</span><span class="sxs-lookup"><span data-stu-id="d604d-118">When you reset configuration reuse, previously created configurations are no longer considered.</span></span> <span data-ttu-id="d604d-119">Es posible que desee restablecer la reutilización de la configuración si se ha cambiado el BOM o la ruta pero no se modificaron ningún atributo relacionado.</span><span class="sxs-lookup"><span data-stu-id="d604d-119">You might want to reset configuration reuse if the BOM or route was changed, but no related attributes were changed.</span></span> <span data-ttu-id="d604d-120">Se restablece la reutilización de la configuración en la ficha desplegable **General** del componente.</span><span class="sxs-lookup"><span data-stu-id="d604d-120">You reset configuration reuse on the **General** FastTab for the component.</span></span>




