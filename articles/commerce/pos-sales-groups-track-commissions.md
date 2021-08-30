---
title: Seguimiento de las comisiones en el punto de venta (POS) mediante los grupos de ventas
description: Es habitual en la práctica del comercio al por menor realizar un seguimiento de las ventas en función del asociado que trabajó con el cliente (dando asistencia, vendiendo productos adicionales, facilitando ventas cruzadas y procesando la transacción).
author: jblucher
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ca77ad5564cc93e9fcf335b5a49548f91c7c13face41fd73477ae4083f78be57
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770918"
---
# <a name="track-commissions-in-the-point-of-sale-pos-by-using-sales-groups"></a>Seguimiento de las comisiones en el punto de venta (POS) mediante los grupos de ventas

[!include [banner](includes/banner.md)]

Es habitual en la práctica del comercio al por menor realizar un seguimiento de las ventas en función del asociado que trabajó con el cliente (dando asistencia, vendiendo productos adicionales, facilitando ventas cruzadas y procesando la transacción).

Seguir las ventas en función del representante de ventas es una medida de las capacidades de venta de los socios, mientras que las ventas del cajero son una medida de velocidad y de eficacia. Las ventas seguidas por Representante de ventas también se usan a menudo para calcular las comisiones u otros incentivos.

## <a name="configuring-a-worker-to-be-a-sales-representative-in-pos"></a>Configuración de un trabajador para ser un representante de ventas de PDV

Al agregar un trabajador a un grupo de ventas, este se vuelve apto para la comisión y se puede identificar como representante de ventas en el sistema. Un trabajador que no está en un grupo de ventas no es apto para recibir una comisión y no estará en la lista de representantes de ventas en la aplicación de punto de venta (PDV). En PDV, la lista de representantes de ventas se deriva de todos los grupos de ventas que contienen al menos a un trabajador asignado a la tienda. La lista se muestra en el sistema PDV como una combinación de identificación del grupo de ventas y de nombre (identificador: Nombre). Un grupo de ventas predeterminado se puede asignar a los trabajadores como apoyo en los casos en que el minorista elige establecer el representante de ventas en las líneas de PDV automáticamente. Los usuarios pueden seleccionar cualquier grupo de ventas al que pertenezca el trabajador.

## <a name="functionality-profile-settings"></a>Configuración de perfil de funcionalidad

Existen varias configuraciones del perfil de funcionalidad para un almacén que determinan el flujo y el proceso en PDV en que participan los representantes de ventas.

<table>
<thead>
<tr>
<th>Perfil</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td>Usar cajero de manera predeterminada cuando esté disponible</td>
<td>Si se habilita esta opción, el sistema PDV rellenará automáticamente las líneas de transacción con el grupo de ventas predeterminado del cajero actual. Si un cajero no tiene un grupo de ventas predeterminado especificado, el valor no se establecerá. Un usuario podría sin embargo establecer manualmente el grupo de ventas mediante un botón de la cuadrícula de botones de PDV.</td>
</tr>
<tr>
<td>Solicitar representante de ventas</td>
<td>Esta opción tiene tres valores posibles:
<ul>
<li><strong>No</strong>: si se selecciona esta opción, no se pedirá al usuario que seleccione un grupo de ventas. El valor se podría seguir estableciendo mediante el grupo de ventas predeterminado de un cajero o manualmente mediante un botón de la cuadrícula de botones de PDV.</li>
<li><strong>Inicio de la transacción</strong>: si se selecciona esta opción, y la opción de <strong>usar cajero de manera predeterminada</strong> no se habilita o el cajero actual no tiene un grupo de ventas predeterminado, se le solicitará al usuario que seleccione un grupo de ventas al principio de cada transacción. Si selecciona un grupo de ventas desde este indicador todas las líneas posteriores tendrán como valor predeterminado el grupo de ventas seleccionado. Un usuario podría sin embargo establecer manualmente el grupo de ventas mediante un botón de la cuadrícula de botones de PDV.</li>
<li><strong>Para cada línea</strong>: si se selecciona esta opción, y la opción de <strong>usar cajero de manera predeterminada</strong> no se habilita o el cajero actual no tiene un grupo de ventas predeterminado, se le solicitará al usuario que seleccione un grupo de ventas después de añadir cada línea. Un usuario podría sin embargo establecer manualmente el grupo de ventas mediante un botón de la cuadrícula de botones de PDV.</li>
</ul>
</td>
</tr>
<tr>
<td>Requerir</td>
<td>Esta opción solo se aplica cuando PDV se configura para solicitar un representante de ventas. Si está habilitado, el usuario tendrá que elegir un grupo de ventas antes de continuar. Si no lo hace, se le solicitará que elija, pero puede cancelar y continuar sin crear una selección. Después de que se agregue la línea, aun así un usuario con permisos suficientes podría quitar el grupo de ventas de la línea. “Requerir representante de ventas” no se aplica en esta situación.</td>
</tr>
</tbody>
</table>

## <a name="displaying-the-sales-representative-information-on-the-pos-transactions-screen"></a>Presentar la información del representante de ventas en la pantalla de las transacciones de PDV

El diseño y los contenidos de la pantalla de transacción de PDV son configurables mediante el diseñador de pantalla y los diseños de pantalla asignados a las tiendas, los registros o trabajadores. El campo **Representante de ventas** se puede agregar a la ficha Líneas del panel de recepción.  Esto mostrará el identificador del grupo de ventas especificado para cada línea en la visualización de la transacción.

## <a name="adding-sales-representative-operations-to-pos-button-grids"></a>Agregar el representante de ventas a las cuadrículas de botones de PDV

PDV permite a los usuarios configurar cuadrículas de botones, que se incluyen en diseños de visualización para proporcionar acceso a las operaciones de PDV. Las siguientes operaciones de PDV se pueden asignar a los botones de la cuadrícula de botones que pertenecen a los representantes de ventas.

| Operación                                 | Descripción |
|-------------------------------------------|-------------|
| Establecer representante de ventas en línea          | Esta operación de PDV muestra una lista de grupos de ventas aptos (identificador: Nombre) para la tienda. La selección de un grupo de ventas de esta lista establecerá el valor de la línea de transacción actual. |
| Borrar representante de ventas en línea        | Esta operación de PDV quita el valor del grupo de ventas actual de la línea de transacción actual. |
| Establecer representantes de ventas en la transacción   | Esta operación de PDV muestra una lista de grupos de ventas aptos (identificador: Nombre) para la tienda. La selección de un grupo de ventas de esta lista establecerá el valor predeterminado de la transacción actual. Cualquier línea existente sin un grupo de ventas asignado se definirá, así como las líneas agregadas posteriormente. |
| Borrar el representante de ventas en la transacción | Esta operación de PDV quita el valor del grupo de ventas predeterminado actual de la transacción actual. No influye en las líneas que ya existen en la transacción. |

## <a name="calculating-commissions"></a>Cálculos de comisiones

La comisión se calcula para los trabajadores de grupos de ventas especificados en el momento del registro de la declaración o del registro de pedido de ventas. El importe de la comisión se determina en función de la parte de la comisión del trabajador, como se define en la configuración del cálculo de la comisión asociada y en el grupo de ventas para el cliente o los productos de la transacción.


[!INCLUDE[footer-include](../includes/footer-banner.md)]