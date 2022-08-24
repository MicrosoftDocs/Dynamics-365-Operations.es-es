---
title: Solucionar problemas de configuración e instalación de Store Commerce
description: Este artículo explica cómo solucionar problemas de configuración e instalación en la aplicación Store Commerce de Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: e3d115e84af1aaf5266eff6588ca6996a333e51a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286340"
---
# <a name="troubleshoot-store-commerce-setup-and-installation-issues"></a>Solucionar problemas de configuración e instalación de Store Commerce

[!include [banner](../includes/banner.md)]

Este artículo explica cómo solucionar problemas de configuración e instalación en la aplicación Store Commerce de Microsoft Dynamics 365 Commerce.

## <a name="i-cant-activate-the-app-and-i-receive-a-connectivity-error-message"></a>No puedo activar la aplicación y recibo un mensaje de error de conectividad

Después de ingresar la URL válida del punto de venta de la nube (CPOS), es posible que reciba un mensaje de error de conectividad similar al siguiente ejemplo:

> Se produjo un error de conectividad y su dispositivo no se puede conectar al CPOS. La URL de CPOS escrita puede tener algunos problemas.

En este caso, revise la URL en busca de errores tipográficos o determine si no se puede acceder a CPOS porque está desconectado.

Además, verifique que la versión de Cloud Scale Unit (CSU) sea 10.0.25 (9.35.\*.\*) o posterior. Se requiere CPOS versión 10.0.25 o posterior para usar la aplicación Store Commerce.

## <a name="i-cant-install-the-app-because-modern-pos-is-already-installed"></a>No puedo instalar la aplicación porque Modern POS ya está instalado

Durante la instalación es posible que reciba un mensaje de error como el siguiente:

> Una versión (9.\*.\*.\*) de este producto (Modern POS) se instaló previamente a través del instalador heredado.

Para corregir el error, debe desinstalar la aplicación Modern Point of Sale (MPOS) para todos los usuarios del equipo y luego volver a intentarla. Puede confirmar si MPOS se ha eliminado para todos los usuarios ejecutando el siguiente comando de PowerShell.

```PowerShell
Get-AppxPackage | Where-Object {$_.PackageFullName -like "Microsoft.Dynamics.*.Pos"} | Remove-AppxPackage -Allusers
```

## <a name="i-cant-activate-the-app-because-of-an-invalid-url-or-an-error-state"></a>No puedo activar la aplicación debido a una URL no válida o un estado de error

Si la URL de CPOS que ingresó no es válida y desea cambiarla, o si la aplicación Store Commerce se encuentra en un estado de error durante la activación, puede reiniciar el proceso restableciendo la aplicación. La aplicación Store Commerce guardará solo una URL de CPOS válida.

Para restablecer la aplicación Store Commerce, siga estos pasos.

1. En el menú **Inicio** de Windows, seleccione y mantenga presionada (o haga clic con el botón derecho) la aplicación y luego seleccione **Más \> Configuración de la aplicación**.
2. Desplácese hacia abajo en la página de configuración de la aplicación hasta que encuentre el botón **Reiniciar**.
3. Seleccione **Restablecer**. A continuación, cuando se le pida, confirme que desea restablecer la aplicación.
