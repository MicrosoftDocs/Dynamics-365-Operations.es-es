---
title: Volver a utilizar configuraciones de producto
description: Puede especificar que desee volver a usar automáticamente una configuración existente para un producto. A continuación, cuando un usuario completa una sesión de configuración, el sistema comprueba si ya existe una configuración que coincide con las selecciones del usuario. Si se encuentra una configuración que coincide, se vuelven a usar el id. de configuración, la lista de materiales (L. MAT) correspondiente y la ruta.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 21dc25b878ff65b57b060fe3d74b5d120fa4b5cd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260608"
---
# <a name="reuse-product-configurations"></a><span data-ttu-id="61c0a-105">Volver a utilizar configuraciones de producto</span><span class="sxs-lookup"><span data-stu-id="61c0a-105">Reuse product configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61c0a-106">Puede especificar que desee volver a usar automáticamente una configuración existente para un producto.</span><span class="sxs-lookup"><span data-stu-id="61c0a-106">You can specify that you want to automatically reuse an existing configuration for a product.</span></span> <span data-ttu-id="61c0a-107">A continuación, cuando un usuario completa una sesión de configuración, el sistema comprueba si ya existe una configuración que coincide con las selecciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="61c0a-107">Then, when a user has completed a configuration session, the system verifies whether a configuration that matches the user’s selections already exists.</span></span> <span data-ttu-id="61c0a-108">Si se encuentra una configuración que coincide, se vuelven a usar el id. de configuración, la lista de materiales (L. MAT) correspondiente y la ruta.</span><span class="sxs-lookup"><span data-stu-id="61c0a-108">If a matching configuration is found, the configuration ID, corresponding bill of materials (BOM), and route are reused.</span></span>

<a name="requirements-for-reusing-configurations"></a><span data-ttu-id="61c0a-109">Requisitos para volver a usar las configuraciones</span><span class="sxs-lookup"><span data-stu-id="61c0a-109">Requirements for reusing configurations</span></span>
---------------------------------------

<span data-ttu-id="61c0a-110">Para habilitar las configuraciones que se reutilizarán, debe especificar la siguiente información para componentes y atributos en la página de **Detalles del modelo de configuración de productos**:</span><span class="sxs-lookup"><span data-stu-id="61c0a-110">To enable configurations to be reused, you must specify the following information for the components and attributes on the **Product configuration model details** page:</span></span>

-   <span data-ttu-id="61c0a-111">**Componentes y subcomponentes**: en la ficha desplegable **General** del campo **Reutilizar configuraciones** seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="61c0a-111">**Components and subcomponents** – On the **General** FastTab, in the **Reuse configurations** field, select **Yes**.</span></span>
-   <span data-ttu-id="61c0a-112">**Atributos**: en la ficha desplegable **Atributos**, seleccione la opción **Incluir en la reutilización**.</span><span class="sxs-lookup"><span data-stu-id="61c0a-112">**Attributes** – On the **Attributes** FastTab, select the **Include in reuse** option.</span></span> <span data-ttu-id="61c0a-113">La opción se muestra solo cuando el componente relacionado se habilita para un nuevo uso.</span><span class="sxs-lookup"><span data-stu-id="61c0a-113">This option appears only when the related component is enabled for reuse.</span></span> <span data-ttu-id="61c0a-114">Si no selecciona ningún atributo para un nuevo uso, la configuración siempre se vuelve a usar, independientemente de las selecciones del usuario durante una sesión de configuración.</span><span class="sxs-lookup"><span data-stu-id="61c0a-114">If you don't select any attributes for reuse, the configuration is always reused, regardless of the user’s selections during a configuration session.</span></span> <span data-ttu-id="61c0a-115">Los atributos de valor de la configuración existente deben coincidir con las selecciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="61c0a-115">The attribute values in the existing configuration must match the user’s selections.</span></span> <span data-ttu-id="61c0a-116">Por ejemplo, si el usuario selecciona como color el **Azul** durante una sesión de configuración, el sistema comprueba si una configuración existente del componente tiene el color azul.</span><span class="sxs-lookup"><span data-stu-id="61c0a-116">For example, if the user selects **Blue** as the color during a configuration session, the system verifies whether an existing configuration of the component has the color blue.</span></span>

## <a name="resetting-configuration-reuse"></a><span data-ttu-id="61c0a-117">Restablecer la reutilización de la configuración</span><span class="sxs-lookup"><span data-stu-id="61c0a-117">Resetting configuration reuse</span></span>
<span data-ttu-id="61c0a-118">Cuando restablece la reutilización de la configuración, las configuraciones anteriormente creadas ya no se tienen en cuenta.</span><span class="sxs-lookup"><span data-stu-id="61c0a-118">When you reset configuration reuse, previously created configurations are no longer considered.</span></span> <span data-ttu-id="61c0a-119">Es posible que desee restablecer la reutilización de la configuración si se ha cambiado el BOM o la ruta pero no se modificaron ningún atributo relacionado.</span><span class="sxs-lookup"><span data-stu-id="61c0a-119">You might want to reset configuration reuse if the BOM or route was changed, but no related attributes were changed.</span></span> <span data-ttu-id="61c0a-120">Se restablece la reutilización de la configuración en la ficha desplegable **General** del componente.</span><span class="sxs-lookup"><span data-stu-id="61c0a-120">You reset configuration reuse on the **General** FastTab for the component.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]