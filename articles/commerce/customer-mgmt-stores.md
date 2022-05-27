---
title: Gestión de clientes en tiendas
description: Este tema explica cómo los minoristas pueden habilitar las capacidades de gestión de clientes en el punto de venta (PDV) en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5a352ba479ca5e635ef521b99f31bd26d5d837ac
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687342"
---
# <a name="customer-management-in-stores"></a>Gestión de clientes en tiendas

[!include [banner](includes/banner.md)]

Este tema explica cómo los minoristas pueden habilitar las capacidades de gestión de clientes en el punto de venta (PDV) en Microsoft Dynamics 365 Commerce.

Es importante que los empleados de la tienda puedan crear y editar registros de clientes en el PDV. De esa manera, pueden capturar cualquier actualización de la información del cliente, como la dirección de correo electrónico, el número de teléfono y la dirección. Esta información es útil en sistemas posteriores, como el marketing, porque la efectividad de esos sistemas depende de la precisión de los datos de sus clientes.

Los asociados de ventas pueden activar el flujo de trabajo de creación de clientes desde dos puntos de entrada de PDV. Pueden seleccionar un botón que esté asignado a la operación **Agregar cliente**, o pueden seleccionar **Crear cliente** en la barra de la aplicación, en la página de resultados de búsqueda. En ambos casos, aparece el cuadro de diálogo **Nuevo cliente**, donde los asociados de ventas pueden introducir los detalles requeridos del cliente, como el nombre del cliente, la dirección de correo electrónico, el número de teléfono, la dirección y cualquier información adicional que sea relevante para la empresa. Esa información adicional se puede capturar utilizando los atributos del cliente que están asociados con el cliente. Para obtener más información sobre los atributos del cliente, consulte [Atributos del cliente](dev-itpro/customer-attributes.md).

Los asociados de ventas también pueden capturar direcciones de correo electrónico y números de teléfono secundarios. Además, pueden capturar la preferencia del cliente sobre la recepción de información de marketing a través de cualquiera de esas direcciones de correo electrónico o números de teléfono secundarios. Para habilitar esta capacidad, los minoristas deben activar la característica **Capturar varios correos electrónicos y números de teléfono y dar consentimiento para la comercialización de estos contactos** en el característica en el espacio de trabajo **Gestión de funciones** en la sede de Commerce (**Administración de sistemas \> Espacios de trabajo \> Gestión de funciones**).

## <a name="default-customer-properties"></a>Propiedades de cliente predeterminadas

Los minoristas pueden utilizar la página **Todas las tiendas** en la sede de Commerce (**Comercio minorista \> Canales \> Tiendas**) para asociar un cliente predeterminado a cada tienda. A continuación, Commerce copia las propiedades definidas para el cliente predeterminado en todos los registros de clientes nuevos que se crean. Por ejemplo, el cuadro de diálogo **Crear cliente** muestra las propiedades que se heredan del cliente predeterminado asociado con la tienda. Esas propiedades incluyen el **tipo de cliente**, el **grupo de clientes**, la **preferencia de recibo**, el **correo de recibo** la **divisa** y el **idioma**. Las **afiliaciones** (agrupaciones de clientes) también se heredan del cliente predeterminado. Sin embargo, las **dimensiones financieras** se heredan del grupo de clientes asociado con el cliente predeterminado, no del propio cliente predeterminado.

> [!NOTE]
> El valor **correo electrónico de recibo** se copia del cliente predeterminado solo si no se proporciona el ID de correo electrónico del recibo para los clientes recién creados. Esto significa que si el ID del correo electrónico del recibo está presente en el cliente predeterminado, todos los clientes creados desde el sitio de comercio electrónico obtendrán el mismo ID del correo electrónico del recibo, ya que no hay una interfaz de usuario para capturar el ID del correo electrónico del recibo del cliente. Le recomendamos que deje el campo **correo electrónico de recibo** en blanco para el cliente predeterminado de la tienda y solo utilícelo si tiene un proceso comercial que depende de la presencia de una dirección de correo electrónico de recibo. 

Los asociados de ventas pueden capturar varias direcciones para un cliente. El nombre y el número de teléfono del cliente se heredan de la información de contacto asociada a cada dirección. La ficha desplegable **Direcciones** de un registro de cliente incluye un campo **Objetivo** que los asociados de ventas pueden editar. Si el tipo de cliente es **Persona**, el valor predeterminado es **Inicio**. Si el tipo de cliente es **Organización**, el valor predeterminado es **Empresa**. Entre otros valores que admite este campo se encuentran **Hogar**, **Oficina** y **Buzón**. El valor del campo **País** de una dirección se hereda de la dirección principal que se especifica en la página **Unidad Operativa** en la sede de Commerce en **Administración de la organización \> Organizaciones \> Unidades operativas**.



## <a name="additional-resources"></a>Recursos adicionales

[Modo de creación de clientes asincrónico](async-customer-mode.md)

[Convertir clientes de modo asincrónico y en clientes de modo sincrónico](convert-async-to-sync.md)

[Atributos de cliente](dev-itpro/customer-attributes.md)

[Exclusión de datos sin conexión](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
