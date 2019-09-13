---
title: Guía de solución de problemas para integración de datos
description: Este tema proporciona información para solución de problemas de integración de datos entre Microsoft Dynamics 365 for Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 5e71729dafd2ad85a01b055363d1c7056b5558b2
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873114"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Guía de solución de problemas para integración de datos

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a>Habilitar los registros de seguimiento de complementos en Common Data Service e inspeccionar los detalles del error en el complemento de escritura dual

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Si tiene un problema o un error durante la sincronización de la escritura dual, siga estos pasos para inspeccionar los errores en el registro de seguimiento.

1. Antes de que pueda inspeccionar los errores, debe habilitar los registros de seguimiento de complementos. Para obtener instrucciones, consulte la sección "Ver registros de seguimiento" de [Tutorial: Escribir y registrar complementos](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).

    Ahora ya puede inspeccionar errores.

2. Inicie sesión en Microsoft Dynamics 365 for Sales.
3. Seleccione el botón **Configuración** (símbolo de engranaje) y, a continuación, seleccione **Configuración avanzada**.
4. En el menú **Configuración** , seleccione **Personalización \> Registro de seguimiento de complementos**.
5. Seleccione **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** como nombre del tipo para mostrar los detalles de error.

## <a name="inspect-dual-write-synchronization-errors-in-finance-and-operations"></a>Inspeccionar errores de sincronización de escritura dual en Finance and Operations

Siga estos pasos para inspeccionar errores durante las pruebas.

1. Inicie sesión en Microsoft Dynamics LifeCycle Services (LCS).
2. Abra el proyecto de LCS para el que quiere realizar la prueba de escritura dual.
3. Seleccione **Entornos hospedados en la nube**.
4. Cree una conexión al escritorio remoto para la máquina virtual (VM) de Dynamics 365 for Finance and Operations mediante el uso de la cuenta local que se muestra en el LCS.
5. Abra el visor de eventos. 
6. Vaya **Registros de aplicaciones y servicios \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacional**. Se muestran los errores y los detalles.

## <a name="unlink-one-common-data-service-environment-from-finance-and-operations-and-link-another-environment"></a>Desvincular un entorno Common Data Service de Finance and Operations y vincular otro entorno

Para actualizar los vínculos, siga estos pasos:

1. Vaya al entorno de Finance and Operations.
2. Abra Administración de datos.
3. Seleccione **Vínculo a CDS para aplicaciones**.
4. Seleccione todas las asignaciones que se están ejecutando y, a continuación, seleccione **Detener**.
5. Seleccione todas las asignaciones y, a continuación, seleccione **Eliminar**.

    > [!NOTE]
    > La opción **Eliminar** no está disponible si se selecciona la plantilla **CustomerV3-Account**. Anule la selección de esta plantilla según sea necesario. **CustomerV3-Account** es una antigua plantilla y funciona con la solución Prospect to Cash. Dado que el lanzamiento es global, aparecerá en todas las plantillas.

6. Seleccione **Desvincular entorno**.
7. Seleccione **Sí** para confirmar la operación.
8. Para vincular el nuevo entorno, siga los pasos de la [guía de instalación](https://aka.ms/dualwrite-docs).
