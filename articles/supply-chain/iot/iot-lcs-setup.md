---
title: Instalar el complemento Inteligencia IoT en LCS
description: Este artículo explica cómo instalar el complemento Inteligencia IoT en Microsoft Dynamics Lifecycle Services (LCS).
author: johanhoffmann
ms.date: 08/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e18b05be1f2ba78c71515e4e76f180355d044b98
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227860"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>Instalar el complemento Inteligencia IoT en LCS

[!include [banner](../../includes/banner.md)]
[!INCLUDE [iot-sdi-announcement](../../includes/iot-sdi-announcement.md)]

Este artículo explica cómo instalar el complemento Inteligencia IoT en Microsoft Dynamics Lifecycle Services (LCS). Tenga en cuenta que los complementos no se pueden instalar en un entorno de demostración/prueba. Para poder instalar el complemento, debe [crear los recursos de Azure](iot-azure-setup.md).

Puede instalar y configurar Inteligencia de IoT sin escribir ningún código. Estos son los pasos básicos.

1. [Configurar recursos de Azure](iot-azure-setup.md) - Cree un centro de IoT, una caché de Redis y una bóveda de claves a las que se pueda acceder desde Supply Chain Management.
2. [Formatos de esquema de mensajes para IoT Hub](iot-schema-format.md) - Configure sus dispositivos para enviar mensajes a IoT Hub y defina el formato de mensaje de notación de objetos JavaScript (JSON).
3. En Gestión de funciones, habilite la marca de función de Inteligencia de IoT.
4. Instale el complemento Inteligencia de IoT en Microsoft Dynamics Lifecycle Services (LCS) - Instale el complemento en LCS y configure los secretos de Azure. (como se describe en este artículo).
5. [Configurar métricas](iot-metrics-setup.md) - Configurar métricas en Supply Chain Management.
6. [Configuración de escenario](iot-scenario-setup.md) - Configurar los escenarios en Supply Chain Management.

## <a name="set-up-the-lcs-environment"></a>Configurar el entorno LCS

1. Abra LCS y vaya a su entorno Microsoft Dynamics 365 Supply Chain Management.
2. Desplácese a la sección **Complementos del entorno**.
3. Seleccione **Instalar un nuevo complemento** para mostrar la lista de complementos que se han habilitado para el entorno.
4. En el cuadro de diálogo **Seleccionar un complemento para instalar**, seleccione **Inteligencia IoT**.
5. En el cuadro de diálogo **Configurar complemento**, proporcione los detalles de su centro de IoT y caché Redis. Puede encontrar los valores necesarios en el almacén de claves que creó en [Crear recursos de Azure](iot-azure-setup.md).

    + **Id. de inquilino**: en Azure Portal, vaya al almacén de claves y luego, en el panel de navegación izquierdo, seleccione **Resumen** y copie el valor **Id. de directorio**. Pegue ese valor en el cuadro de diálogo **Configurar complemento**.
    + **URI de almacén de claves de punto final compatible con IoT Event Hub**: vaya al almacén de claves y luego, en el panel de navegación izquierdo, seleccione **Resumen** y copie el valor **Nombre DNS**. Pegue ese valor en el cuadro de diálogo **Configurar complemento**.
    + **Nombre secreto de punto final compatible con IoT Event Hub**: vaya al almacén de claves y luego, en el panel de navegación izquierdo, seleccione **Secretos** y copie el nombre del secreto donde se almacena la cadena de conexión del centro de eventos para el centro de IoT. Pegue ese valor en el cuadro de diálogo **Configurar complemento**.
    + **URI de almacén de claves de caché Redis**: vaya al almacén de claves y luego, en el panel de navegación izquierdo, seleccione **Resumen** y copie el valor **Nombre DNS**. Pegue ese valor en el cuadro de diálogo **Configurar complemento**.
    + **Nombre secreto de punto final de caché Redis**: vaya al almacén de claves y luego, en el panel de navegación izquierdo, seleccione **Secretos** y copie el nombre del secreto donde se almacena la cadena de la caché Redis. Pegue ese valor en el cuadro de diálogo **Configurar complemento**.

6. Seleccione la casilla de verificación para aceptar los términos y condiciones.
7. Seleccione **Instalar**.
8. Aparece un cuadro de mensaje que dice: "El complemento se ha activado correctamente para la instalación". Seleccione **Aceptar**.

La configuración de LCS ya está completa. El siguiente paso es [configurar los escenarios](iot-scenario-setup.md).

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a>Desinstalar el complemento

1. En Supply Chain Management, [desactive los escenarios](iot-scenario-setup.md#disable-a-scenario).
2. En LCS, vaya a sus detalles de Supply Chain Management.
3. Desplácese a la sección **Complementos del entorno**.
4. Seleccione **Desinstalar** para el complemento Inteligencia IoT.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]