---
title: Crear un cliente predeterminado
description: Este artículo describe cómo crear un cliente predeterminado para usarlo al crear un canal en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b4658356e268d045fcb7065b397411ffc5161864
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894538"
---
# <a name="create-a-default-customer"></a>Crear un cliente predeterminado

[!include [banner](includes/banner.md)]

Este artículo describe cómo crear un cliente predeterminado para usarlo al crear un canal en Microsoft Dynamics 365 Commerce.

Al crear un canal, deberá proporcionar un cliente predeterminado. Se puede crear fácilmente un cliente predeterminado después de crear primero el grupo de clientes y la libreta de direcciones de clientes.

## <a name="create-a-customer-group"></a>Creación de un grupo de clientes

Si todavía no existen grupos de clientes, puede crear uno. Ejemplos pueden ser grupos para representar diferentes grupos de clientes, como mayoristas, minoristas, Internet, empleados, etc.

Para crear un grupo de clientes, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Comercio minorista y comercio \> Clientes \> Grupos de clientes**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el cuadro **Grupo de clientes**, especifique un id. de grupo de clientes.
1. Especifique una descripción adecuada en el cuadro **Descripción**.
1. Especifique un valor adecuado en el cuadro **Condiciones de pago**.
1. En el cuadro **Tiempo entre la fecha de vencimiento de la factura y la fecha de pago**, ingrese un valor apropiado.
1. En el cuadro **Grupo de impuestos predeterminado**, ingrese un grupo de impuestos si corresponde.
1. Seleccione la casilla **Los precios incluyen impuestos** si es aplicable.
1. En el cuadro **Motivo de cancelación predeterminado**, especifique un valor apropiado, según corresponda.

La siguiente imagen muestra varios grupos de clientes configurados.

![Grupos de clientes.](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a>Crear una nueva libreta de direcciones de clientes.

Un cliente debe estar asociado con una libreta de direcciones. Si aún no ha creado una, deberá hacerlo.

Para crear una libreta de direcciones de clientes, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canales \> Libretas de direcciones**.
1. En el panel de acciones, seleccione **Nueva**.
1. Escriba un nombre en el cuadro **Nombre**.
1. En el cuadro **Descripción**, escriba una descripción.
1. En el panel de acciones, seleccione **Guardar**.

En la imagen siguiente se muestra un ejemplo de libreta de direcciones.

![Libreta de direcciones.](media/address-book.png)

## <a name="create-a-default-customer"></a>Crear un cliente predeterminado

Para crear un cliente predeterminado, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Venta minorista y comercio \> Clientes \> Todos los clientes**.
1. En el panel de acciones, seleccione **Nueva**.
1. En la lista desplegable **Tipo**, seleccione "Persona".
1. En la lista desplegable **Cuenta de cliente**, seleccione o ingrese un número de cuenta (por ejemplo, "100001").
1. En la lista desplegable **Nombre de pila**, seleccione o escriba un nombre (por ejemplo, "Predeterminado").
1. En la lista desplegable **Segundo nombre**, seleccione o escriba un nombre (por ejemplo, "Venta minorista").
1. En la lista desplegable **Apellido**, seleccione o escriba un nombre (por ejemplo, "Cliente").
1. En la lista desplegable **Divisa**, seleccione o escriba una divisa (por ejemplo, "USD").
1. En la lista desplegable **Divisa**, seleccione el grupo de clientes creado anteriormente.
1. En la lista desplegable **Libretas de direcciones**, seleccione una libreta de direcciones de clientes existente.
1. Seleccione **Guardar** para guardar y volver a la pantalla de detalles del cliente para el nuevo cliente.

> [!NOTE]
> No es necesario agregar una dirección para un cliente predeterminado.

En la imagen siguiente se muestra un ejemplo de creación de cliente.

![Creación de un cliente predeterminado.](media/default-customer-creation.png)

La siguiente imagen muestra una configuración predeterminada del cliente.

![Ejemplo de configuración de cliente.](media/default-customer-configuration1.png)

La mayoría de los valores predeterminados en la pantalla de desviaciones del cliente pueden permanecer, pero se deben cambiar dos valores.

1. En la pantalla de detalles del cliente, expanda **Valores predeterminados de pedido de ventas**.
1. En la lista desplegable **Sitio**, seleccione o ingrese un sitio preconfigurado.
1. En la lista desplegable **Almacén**, seleccione o ingrese un almacén preconfigurado.

En la imagen siguiente se muestra un ejemplo de configuración de cliente.

![Ejemplo de configuración de cliente.](media/default-customer-configuration2.png)

## <a name="additional-resources"></a>Recursos adicionales

[Información general de canales](channels-overview.md)

[Requisitos previos de configuración del canal](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
