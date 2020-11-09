---
title: Verifique que la doble escritura esté configurada en aplicaciones Finance and Operations y Common Data Service
description: Este tema explica cómo puede determinar si la escritura doble está configurada en aplicaciones Finance and Operations y en Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2ddac76871a3ac574a1edcb5446be6c64e5e4682
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997239"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="ac642-103">Verifique que la doble escritura esté configurada en aplicaciones Finance and Operations y Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ac642-103">Verify that dual-write is configured in Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="ac642-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ac642-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="ac642-105">Específicamente explica cómo puede determinar si la escritura doble está configurada en aplicaciones Finance and Operations y en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ac642-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Common Data Service.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="ac642-106">Verifique que la doble escritura esté configurada en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ac642-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="ac642-107">Para determinar si los errores que ve cuando intenta guardar registros para la actualización provienen de doble escritura, primero verifique que la doble escritura esté configurada.</span><span class="sxs-lookup"><span data-stu-id="ac642-107">To determine whether the errors that you see when you try to save records for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="ac642-108">Si tiene privilegios de administrador en la aplicación Finance and Operations, vaya a **Espacios de trabajo \> Gestión de datos** y seleccione el mosaico **Doble escritura**.</span><span class="sxs-lookup"><span data-stu-id="ac642-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management** , and select the **Dual-write** tile.</span></span> <span data-ttu-id="ac642-109">Si se muestran los detalles de los entornos vinculados y la lista de mapas de entidades que se están ejecutando, se configura la escritura doble.</span><span class="sxs-lookup"><span data-stu-id="ac642-109">If the details of the linked environments and the list of entity maps that are running are shown, dual-write is configured.</span></span>

    ![Comprobar la conexión de la aplicación Finance and Operations con privilegios de administrador](media/verify_fin_ops_1.png)

+ <span data-ttu-id="ac642-111">Si no tiene privilegios de administrador, aparecerá un mensaje de error: *No se pueden escribir datos en la entidad nombre de la entidad \<entity name\>*.</span><span class="sxs-lookup"><span data-stu-id="ac642-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="ac642-112">En el ejemplo de la siguiente ilustración, no puede crear un registro de cliente en la aplicación Finance and Operations, porque la escritura doble está configurada, pero el grupo de clientes y los datos de referencia de términos de pago no existen en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ac642-112">In the example in the following illustration, you can't create a customer record in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Common Data Service.</span></span>

    ![Verificando la conexión de la aplicación Finance and Operations cuando no tiene privilegios de administrador](media/verify_fin_ops_2.png)

<span data-ttu-id="ac642-114">Para obtener información sobre cómo solucionar problemas al crear datos en aplicaciones Finance and Operations, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="ac642-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a><span data-ttu-id="ac642-115">Verifique que la doble escritura esté configurada en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ac642-115">Verify that dual-write is configured in Common Data Service</span></span>

<span data-ttu-id="ac642-116">Cuando crea datos, si ve el campo **Empresa** en páginas en Common Data Service, la doble escritura está configurada.</span><span class="sxs-lookup"><span data-stu-id="ac642-116">When you create data, if you see the **Company** field on pages in Common Data Service, dual-write is configured.</span></span>

![Verificando la conexión Common Data Service](media/verify_cds.png)

<span data-ttu-id="ac642-118">Para obtener información sobre cómo solucionar problemas al crear datos en Common Data Service, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="ac642-118">For information about how to fix issues when you create data in Common Data Service, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="ac642-119">Para obtener información sobre cómo ver los detalles del error si encuentra algún error mientras crea datos en Common Data Service, consulte [Habilitar y ver el inicio de sesión de seguimiento del complemento Common Data Service para ver detalles del error](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span><span class="sxs-lookup"><span data-stu-id="ac642-119">For information about how to view error details if you encounter any errors while you create data in Common Data Service, see [Enable and view the plug-in trace log in Common Data Service to view error details](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span></span>
