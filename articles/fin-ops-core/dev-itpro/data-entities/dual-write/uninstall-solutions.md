---
title: Desinstalar soluciones de orquestación de aplicaciones de escritura dual
description: Este artículo explica como desinstalar soluciones de orquestación de aplicaciones de escritura dual.
author: RamaKrishnamoorthy
ms.date: 03/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2022-01-21
ms.openlocfilehash: 676802ddabac69db4947cf806e9103f67cece3de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870385"
---
# <a name="uninstall-dual-write-application-orchestration-solutions"></a>Desinstalar soluciones de orquestación de aplicaciones de escritura dual

[!include [banner](../../includes/banner.md)]

Este artículo explica como desinstalar soluciones de orquestación de aplicaciones de escritura dual.

Algunos clientes instalan sin querer el paquete de orquestación de aplicaciones de escritura dual que instala varias soluciones en su entorno de Microsoft Dataverse. La instalación de soluciones extrañas en el paquete puede causar problemas inesperados e indeseables.

Para solucionar problemas relacionados con la instalación del paquete de orquestación de aplicaciones de escritura dual, desinstale las soluciones de escritura dual no deseadas en el siguiente orden:

1. Dynamics365FinanceAndOperationsAnchor_managed
1. msdyn_OneFSSCM_managed (si está presente)
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps_managed
1. Dynamics365Notes_managed (Para desinstalar esta solución, debe abrir un ticket de soporte con Microsoft).
1. DualWriteCore_managed
1. Dynamics365AssetManagementApp_managed
1. Dynamics365AssetManagement_managed
1. Dynamics365SupplyChainExtended_managed
1. Dynamics365FinanceExtended_managed
1. HCMCommon_managed
1. Dynamics365FinanceAndOperationsCommon_managed
1. Dynamics365Company_managed
1. CurrencyExchangeRates_managed
1. msdyn_AssetCommon_managed
1. FieldServiceCommon_managed

Si se instalaron soluciones de libreta de direcciones global y de grupo, desinstálelas en el siguiente orden:

1. Dynamics365FinanceAndOperationsAnchor
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps
1. msdyn_DualWriteCore
1. Dynamics365AssetManagementApp
1. Dynamics365AssetManagement
1. Dynamics365SupplyChainExtended
1. Dynamics365FinanceExtended
1. HCMCommon
1. Dynamics365FinanceAndOperationsCommon
1. Parte
1. Dynamics365Company_managed
1. CurrencyExchangeRates
1. msdyn_AssetCommon
1. FieldServiceCommon
