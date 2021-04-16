---
title: Integración de notas
description: Este tema describe la integración de datos de notas en escritura doble.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
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
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: beab7f2fc4fd96ce7a28734d2449445b3b5d4451
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750845"
---
# <a name="note-integration"></a>Integración de notas

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Durante los procesos comerciales, los usuarios de Microsoft Dynamics 365 a menudo recopilan información sobre sus clientes. Esta información se registra como actividades y notas. Este tema describe la integración de datos de notas en escritura doble.

La información del cliente se puede clasificar de las siguientes formas:

+ **Información procesable que un usuario de Dynamics 365 maneja en nombre de un cliente**: por ejemplo, Contoso (un usuario de Dynamics 365) está realizando un espectáculo de juegos. Uno de los clientes de Contoso (un cliente) quiere asistir al espectáculo de juegos. El cliente le pide a un empleado de Contoso que le reserve un espacio en el espectáculo de juegos. La reserva se produce en el calendario de asistentes a eventos de Contoso.
+ **Información procesable para un usuario de Dynamics 365**: por ejemplo, un cliente que compra una unidad Surface introduce instrucciones especiales que indican que el dispositivo debe envolverse para regalo antes de la entrega. Estas instrucciones son información procesable que debe manejar el empleado de Contoso responsable del empaquetado.
+ **Información no procesable**: por ejemplo, un cliente visita la tienda de Contoso y, durante su conversación con un asociado de la tienda, expresa interés en juegos y accesorios para juegos de *Halo*. El asociado de la tienda toma nota de esta información. El motor de recomendaciones de productos lo utiliza para hacer recomendaciones al cliente.

En general, la información procesable se captura como *actividades* en las aplicaciones de Finance and Operations y las aplicaciones de participación del cliente. La información no procesable se captura como *notas* en las aplicaciones de Finance and Operations y como *anotaciones* en las aplicaciones de participación del cliente.

> [!TIP]
> Aunque las notas están destinadas para información no procesable, las aplicaciones no le impedirán usarlas para almacenar y manejar información procesable si desea usarlas de esa manera.

Microsoft está lanzando actualmente funcionalidad para la integración de notas. (La funcionalidad para la integración de actividades se lanzará más adelante). Tenga en cuenta que la integración está disponible para clientes, proveedores, pedidos de venta y pedidos de compra.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Crear una nota en una aplicación de interacción con el cliente

Para crear una nota en una aplicación de interacción con el cliente y luego sincronizarla con una aplicación de Finance and Operations, siga estos pasos.

1. En la aplicación de interacción con el cliente, abra el registro de la cuenta de un cliente.
2. En el panel **Escala de tiempo**, seleccione el signo más (**+**) y luego seleccione **Nota** para crear una nota.

    ![Creación de una nota en una aplicación de interacción con el cliente](media/notes-ce-1.png)

3. Introduzca un título y una descripción, y luego seleccione **Agregar nota**.

    ![Introducción de un título y una descripción](media/notes-ce-2.png)

    La nueva nota se agrega a la escala de tiempo del cliente.

    ![Nueva nota en la escala de tiempo del cliente](media/notes-ce-3.png)

4. Inicie sesión en la aplicación Finance and Operations y abra el mismo registro de cliente. Tenga en cuenta que el botón **Archivos adjuntos** (símbolo de un clip) de la esquina superior derecha indica que el registro tiene un archivo adjunto.

    ![Notificación sobre un archivo adjunto](media/notes-ce-4.png)

5. Seleccione el botón **Archivos adjuntos** para abrir la página **Archivos adjuntos**. Debería encontrar la nota que creó en la aplicación de interacción con el cliente.

    ![Nota de la aplicación de interacción con el cliente](media/notes-ce-5.png)

Las actualizaciones de la nota se sincronizan entre sí, entre la aplicación Finance and Operations y la aplicación de interacción con el cliente.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Crear una nota en una aplicación de Finance and Operations

También puede crear una nota en una aplicación de Finance and Operations, y se sincronizará con una aplicación de interacción con el cliente.

Para crear una nota en una aplicación de Finance and Operations y luego sincronizarla con una aplicación de interacción con el cliente, siga estos pasos.

1. En la aplicación Finance and Operations, en la página **Archivos adjuntos**, seleccione **Nueva** \> **Nota**.

    ![Creación de una nota en la aplicación Finance and Operations](media/notes-fo-1.png)

2. Introduzca un título y un breve conjunto de instrucciones, y luego seleccione **Guardar**.

    ![Introducción de un título e instrucciones](media/notes-fo-2.png)

3. En la aplicación de interacción con el cliente, actualice el registro. Debería encontrar la nueva nota en la escala de tiempo.

    ![Nueva nota en la escala de tiempo en la aplicación de interacción con el cliente](media/notes-fo-3.png)

Puede clasificar una nota como interna o externa.

- En la aplicación Finance and Operations, en la página **Archivos adjuntos**, abra la nota y, a continuación, en el campo **Restricción** campo, seleccione **Interna** o **Externa**.

    ![Campo de restricción](media/notes-fo-4.png)

También puede crear una URL.

1. En la aplicación Finance and Operations, en la página **Archivos adjuntos**, seleccione **Nueva** \> **URL**.
2. Escriba un título y la URL.
3. En el campo **Restricción**, seleccione **Interna** o **Externa**.

    ![Creación de una URL en la aplicación Finance and Operations](media/notes-fo-5.png)

4. Seleccione **Guardar**.

    Debido a que las aplicaciones de participación del cliente no tienen un tipo de URL, la URL se integra con escritura doble en forma de nota.

    ![URL que aparece como uan nota en la aplicación de interacción con el cliente](media/notes-ce-6.png)

> [!NOTE]
> No se admiten archivos adjuntos.

## <a name="templates"></a>Plantillas

La integración de notas incluye una colección de mapas de tabla que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.

| Aplicación de Finance and Operations | Aplicación Customer Engagement | Descripción |
|----------------------------|-------------------------|-------------|
| [Archivos adjuntos de clientes](mapping-reference.md#230) | Anotaciones | Empresas que utilizan texto sin formato y las URL para capturar información específica del cliente (tanto para organizaciones como para personas). |
| [Documentos adjuntos de proveedor](mapping-reference.md#231) | Anotaciones | Empresas que utilizan texto sin formato y las URL para capturar información específica del proveedor (tanto para organizaciones como para personas). |
| [Datos adjuntos de documento de encabezado de pedido de ventas](mapping-reference.md#229) | Anotaciones | Empresas que utilizan texto sin formato y las URL para capturar información específica de pedidos de ventas. |
| [Datos adjuntos de documento de encabezado de pedido de compra](mapping-reference.md#232) | Anotaciones | Empresas que utilizan texto sin formato y las URL para capturar información específica de pedidos de compras. |

Para más información, consulte [Referencia de asignación de escritura doble](mapping-reference.md).
