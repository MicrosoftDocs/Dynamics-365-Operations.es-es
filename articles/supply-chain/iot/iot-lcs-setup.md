---
title: Instalar el complemento Inteligencia IoT en LCS
description: Este tema explica cómo instalar el complemento Inteligencia IoT en Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 87d04c3df22e2d9ef56acb61e26304731a2a17a2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206061"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>Instalar el complemento Inteligencia IoT en LCS

[!include [banner](../../includes/banner.md)]

Este tema explica cómo instalar el complemento Inteligencia IoT en Microsoft Dynamics Lifecycle Services (LCS). Tenga en cuenta que los complementos no se pueden instalar en un entorno de demostración/prueba. Para poder instalar el complemento, debe [crear los recursos de Azure](iot-azure-setup.md).

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