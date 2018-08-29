---
title: "Configuración de idioma del usuario y aplicación de punto de venta (PDV)"
description: "Este tema describe cómo cambiar la configuración del idioma en el PDV moderno de venta minorista (MPOS) y el PDV de la nube."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 1ea4309d57a7b6b4ca4ae3fdd995c95d93c5c080
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="point-of-sale-pos-application-and-user-language-settings"></a><span data-ttu-id="84f3f-103">Configuración de idioma del usuario y aplicación de punto de venta (PDV)</span><span class="sxs-lookup"><span data-stu-id="84f3f-103">Point of sale (POS) application and user language settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="84f3f-104">Este tema describe cómo cambiar la configuración del idioma en el PDV moderno de venta minorista (MPOS) y el PDV de la nube.</span><span class="sxs-lookup"><span data-stu-id="84f3f-104">This topic describes how to change language settings in Retail Modern POS (MPOS) and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="84f3f-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="84f3f-105">Overview</span></span>
<span data-ttu-id="84f3f-106">Tanto el PDV moderno de venta minorista (MPOS) como el PDV de la nube admiten entornos en los que la configuración del idioma y las traducciones pueden variar entre los ajustes del usuario y los de la tienda.</span><span class="sxs-lookup"><span data-stu-id="84f3f-106">Retail Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="84f3f-107">Por ejemplo, la tienda podría estar situada en una región donde el inglés es más común para sus clientes, pero algunos trabajadores prefieren usar la aplicación con traducciones al francés.</span><span class="sxs-lookup"><span data-stu-id="84f3f-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="84f3f-108">Idioma de los datos</span><span class="sxs-lookup"><span data-stu-id="84f3f-108">Data language</span></span>
<span data-ttu-id="84f3f-109">Independientemente de la configuración del usuario, el PDV moderno de venta minorista y el PDV de la nube usarán siempre la configuración del idioma de las tiendas para determinar las traducciones usadas para los datos.</span><span class="sxs-lookup"><span data-stu-id="84f3f-109">Regardless of the user’s settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="84f3f-110">Esto garantiza que todos los usuarios y clientes tengan una experiencia coherente.</span><span class="sxs-lookup"><span data-stu-id="84f3f-110">This will ensure that all users and customers will have a consistent experience.</span></span>  <span data-ttu-id="84f3f-111">Algunos ejemplos de datos incluyen:</span><span class="sxs-lookup"><span data-stu-id="84f3f-111">Examples of data include:</span></span>

-   <span data-ttu-id="84f3f-112">Productos</span><span class="sxs-lookup"><span data-stu-id="84f3f-112">Products</span></span>
-   <span data-ttu-id="84f3f-113">Atributos y valores</span><span class="sxs-lookup"><span data-stu-id="84f3f-113">Attributes and values</span></span>
-   <span data-ttu-id="84f3f-114">Nombres de categoría</span><span class="sxs-lookup"><span data-stu-id="84f3f-114">Category names</span></span>
-   <span data-ttu-id="84f3f-115">Recibos de transacciones impresas o enviadas por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="84f3f-115">Printed or emailed transaction receipts</span></span>
-   <span data-ttu-id="84f3f-116">Nombres de métodos de pago</span><span class="sxs-lookup"><span data-stu-id="84f3f-116">Payment method names</span></span>
-   <span data-ttu-id="84f3f-117">Mensajes de visualización de líneas</span><span class="sxs-lookup"><span data-stu-id="84f3f-117">Line display messages</span></span>

<span data-ttu-id="84f3f-118">El idioma de la tienda también se usará para la pantalla principal de inicio de sesión del PDV, ya que no se conoce al usuario antes de iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="84f3f-118">The store’s language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="84f3f-119">Si una traducción no está disponible para el idioma de la tienda, el PDV volverá al idioma de la empresa.</span><span class="sxs-lookup"><span data-stu-id="84f3f-119">If a translation is not available for the store’s language, the POS will revert to the company’s language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="84f3f-120">Configuración de ajustes del idioma de la tienda</span><span class="sxs-lookup"><span data-stu-id="84f3f-120">Configuring the store’s language setting</span></span>

<span data-ttu-id="84f3f-121">La configuración del idioma de la tienda se define como **Todas las tiendas de venta minorista** en la página **Tiendas minoristas** en **General &gt; Configuración regional &gt; Idioma.</span><span class="sxs-lookup"><span data-stu-id="84f3f-121">The store’s language setting is set from **All retail stores** on the **Retail Store** page under **General &gt; Regional Settings &gt; Language.</span></span> <span data-ttu-id="84f3f-122">**Use el menú desplegable para elegir el idioma para cada tienda.</span><span class="sxs-lookup"><span data-stu-id="84f3f-122">**Use the drop down to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="84f3f-123">Idioma de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="84f3f-123">User interface language</span></span>
<span data-ttu-id="84f3f-124">La configuración del idioma del usuario del PDV determina las traducciones usadas en la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="84f3f-124">The POS user’s language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="84f3f-125">Esto incluye todas las etiquetas, los menús y las listas que no se consideren datos.</span><span class="sxs-lookup"><span data-stu-id="84f3f-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="84f3f-126">Una excepción a esto es el texto que aparece en las cuadrículas de botones del PDV.</span><span class="sxs-lookup"><span data-stu-id="84f3f-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="84f3f-127">No admiten traducciones, por lo que mostrarán siempre el texto como se define en el botón.</span><span class="sxs-lookup"><span data-stu-id="84f3f-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="84f3f-128">Para admitir botones traducidos, tendrá que copiar y mantener cuadrículas de botones independientes y asignarlas a los usuarios si procede.</span><span class="sxs-lookup"><span data-stu-id="84f3f-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="84f3f-129">Configuración de ajustes del idioma del usuario</span><span class="sxs-lookup"><span data-stu-id="84f3f-129">Configuring the user’s language setting</span></span>

<span data-ttu-id="84f3f-130">La configuración del idioma del usuario del PDV se define en **Todos los trabajadores** en la página **Trabajador** en **Venta minorista &gt; Idioma**.</span><span class="sxs-lookup"><span data-stu-id="84f3f-130">The POS user’s language setting is set from **All workers** on the **Worker** page under **Retail &gt; Language**.</span></span>  <span data-ttu-id="84f3f-131">N se establece en la pestaña del perfil principal. Esta configuración no es usada por PDV.</span><span class="sxs-lookup"><span data-stu-id="84f3f-131">It is not set on the main Profile tab.  This setting is not used by POS.</span></span> <span data-ttu-id="84f3f-132">Si el idioma del usuario no se define o se define como un idioma donde no están disponibles las traducciones, el PDV volverá al idioma de la tienda.</span><span class="sxs-lookup"><span data-stu-id="84f3f-132">If the user’s language is not set or it is set to a language where translations are not available, the POS will revert to the store’s language.</span></span>  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| <span data-ttu-id="84f3f-133">** **</span><span class="sxs-lookup"><span data-stu-id="84f3f-133">** **</span></span>       | <span data-ttu-id="84f3f-134">**Idioma de la IU** ** **</span><span class="sxs-lookup"><span data-stu-id="84f3f-134">**UI language** ** **</span></span>      | <span data-ttu-id="84f3f-135">**Idioma de los datos (productos, formatos de recibos, visualización de líneas, etc.)**</span><span class="sxs-lookup"><span data-stu-id="84f3f-135">**Data language (products, receipt formats, line display, etc.)**</span></span> |
| <span data-ttu-id="84f3f-136">**Empresa**</span><span class="sxs-lookup"><span data-stu-id="84f3f-136">**Company**</span></span> | <span data-ttu-id="84f3f-137">Predeterminada</span><span class="sxs-lookup"><span data-stu-id="84f3f-137">Default</span></span>                    | <span data-ttu-id="84f3f-138">Predeterminada</span><span class="sxs-lookup"><span data-stu-id="84f3f-138">Default</span></span>                                                           |
| <span data-ttu-id="84f3f-139">**Tienda**</span><span class="sxs-lookup"><span data-stu-id="84f3f-139">**Store**</span></span>   | <span data-ttu-id="84f3f-140">Reemplaza a la empresa</span><span class="sxs-lookup"><span data-stu-id="84f3f-140">Overrides company</span></span>          | <span data-ttu-id="84f3f-141">Reemplaza a la empresa</span><span class="sxs-lookup"><span data-stu-id="84f3f-141">Overrides company</span></span>                                                 |
| <span data-ttu-id="84f3f-142">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="84f3f-142">**User**</span></span>    | <span data-ttu-id="84f3f-143">Reemplaza a la tienda o a la empresa</span><span class="sxs-lookup"><span data-stu-id="84f3f-143">Overrides store or company</span></span> | <span data-ttu-id="84f3f-144">Nunca</span><span class="sxs-lookup"><span data-stu-id="84f3f-144">Never</span></span>                                                             |






