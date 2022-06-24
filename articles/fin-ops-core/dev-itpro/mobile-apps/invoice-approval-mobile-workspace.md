---
title: Espacio de trabajo móvil Aprobaciones de facturas
description: Este artículo proporciona información sobre del área de trabajo móvil Aprobaciones de facturas.
author: abruer
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: e9067e33038ee09b8f8cdcc8dd597ab5be9cfe7f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868680"
---
# <a name="invoice-approvals-mobile-workspace"></a>Espacio de trabajo móvil Aprobaciones de facturas

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../includes/mobile-app-deprecation-banner.md)]

Este artículo proporciona información sobre del área de trabajo móvil **Aprobaciones de facturas**. Este espacio de trabajo proporciona una lista de facturas que se le han asignado a través del proceso de flujo de trabajo del encabezado de factura de proveedor. 

Este espacio de trabajo móvil se debe usar con la aplicación móvil Finance and Operations.

## <a name="overview"></a>Información general

El área de trabajo móvil **Aprobaciones de facturas** permite a los empleados y directores de proveedores ver las facturas que se les han asignado como parte del proceso de flujo de trabajo del encabezado de factura de proveedor. Puede ver la información de la factura e incluso los detalles de la línea y la distribución, que le ayudarán a tomar decisiones informadas de aprobación. En el área de trabajo, puede tomar medidas para mover la factura por el proceso de flujo de trabajo. 

## <a name="prerequisites"></a>Requisitos previos

Para poder usar este espacio de trabajo móvil, antes debe satisfacer los siguientes requisitos previos:

<table>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Rol</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Microsoft Dynamics 365 Finance debe estar implementado en la organización.</td>
<td>Administrador del sistema</td>
<td>Consulte <a href="../deployment/deploy-demo-environment.md">Implementar un entorno de demostración</a>.
</td>
</tr>
<tr class="even">
<td>El área de trabajo móvil <strong>Aprobaciones de facturas</strong> debe publicarse.</td>
<td>Administrador del sistema</td>
<td>Consulte <a href="publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Descargar e instalar la aplicación móvil

Descargue e instale la aplicación móvil Finance and Operations:

-   [Para teléfonos Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Iniciar sesión en la aplicación móvil

1.  Inicie la aplicación en su dispositivo móvil.
2.  Especifique la dirección URL Microsoft Dynamics 365.
3.  La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.
4.  Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.

    [![Toque la pantalla para actualizar.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a>Aprobar facturas mediante el área de trabajo móvil Aprobaciones de facturas
1.  En el dispositivo móvil, seleccione el área de trabajo **Aprobaciones de facturas**.
2.  Seleccione la factura que le ha sido asignada por el proceso de flujo de trabajo del encabezado de factura de proveedor.
3.  En la página **Detalles de la factura**, revise la información de encabezado de factura, como la información del proveedor y la fecha.
4.  Seleccione una línea de la factura para ver su información más detallada en la vista **Detalles de línea de factura**.
5.  En la vista **Detalles de línea de factura**, seleccione la **Distribuciones** para mostrar las distribuciones de la línea. Aquí puede ver la contabilidad para la línea de factura. La información que se muestra incluye las dimensiones financieras y la cuenta principal.
6.  En la página **Detalles de línea de factura**, seleccione la **Distribuciones** para mostrar todas las distribuciones. Aquí puede ver la contabilidad para la toda la factura. La información que se muestra incluye las dimensiones financieras y las cuentas principales. 
7.  Seleccione **Datos adjuntos** para ver las notas o los archivo que están asociadas a la factura.
8.  En la página **Detalles de la factura**, seleccione la acción del flujo de trabajo adecuado para completar el proceso de revisión.
9.  Seleccione **Listo**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
