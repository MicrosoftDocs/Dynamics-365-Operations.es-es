---
title: Cambiar entre diseños de proveedor
description: Este tema describe como cambiar la integración de datos de proveedor entre aplicaciones de Finance and Operations y Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
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
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 731efd3ae841960f3a2c0b9be210c5c68ac835f5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685518"
---
# <a name="switch-between-vendor-designs"></a>Cambiar entre diseños de proveedor

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a>Flujo de datos del proveedor 

Si elige usar la entidad **Cuenta** para almacenar proveedores del tipo **Organización** y la entidad **Contacto** para almacenar proveedores del tipo **Persona**, configure los siguientes flujos de trabajo. De lo contrario, esta configuración no es necesaria.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Utilice el diseño de proveedor extendido para proveedores del tipo Organización

El paquete de solución **Dynamics365FinanceExtended** contiene las siguientes plantillas de proceso de flujo de trabajo. Creará un flujo de trabajo para cada plantilla.

+ Crear proveedores en la tabla Cuentas
+ Crear proveedores en la tabla Proveedores
+ Actualizar proveedores en la tabla Cuentas
+ Actualizar proveedores en la tabla Proveedores

Para crear nuevos procesos de flujo de trabajo mediante las plantillas de proceso de flujo de trabajo, siga estos pasos.

1. Cree un proceso de flujo de trabajo para la entidad **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Crear proveedores en la tabla Cuentas**. A continuación seleccione **Aceptar**. Este flujo de trabajo gestiona el escenario de creación de proveedor para la entidad **Cuenta**.

    ![Crear proveedores en el proceso de flujo de trabajo de la tabla Cuentas](media/create_process.png)

2. Cree un proceso de flujo de trabajo para la entidad **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Actualizar proveedores en la tabla Cuentas**. A continuación seleccione **Aceptar**. Este flujo de trabajo gestiona el escenario de actualización de proveedor para la entidad **Cuenta**.
3. Cree un proceso de flujo de trabajo para la entidad **Cuenta** y seleccione la plantilla de proceso de flujo de trabajo **Crear proveedores en la tabla Proveedores**.
4. Cree un proceso de flujo de trabajo para la entidad **Cuenta** y seleccione la plantilla de proceso de flujo de trabajo **Actualizar proveedores en la tabla Proveedores**.
5. Puede configurar los flujos de trabajo como flujos de trabajo en tiempo real o en segundo plano, dependiendo de sus requisitos. Para configurar un flujo de trabajo como flujo de trabajo en segundo plano, seleccione **Convertir a un flujo de trabajo en segundo plano**.

    ![Botón convertir a un flujo de trabajo en segundo plano](media/background_workflow.png)

6. Active los flujos de trabajo que ha creado para las tablas **Cuenta** y **Proveedor** para comenzar a utilizar la entidad **Cuenta** para almacenar información de proveedores del tipo **Organización**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Utilice el diseño de proveedor extendido para proveedores del tipo Persona

El paquete de solución **Dynamics365FinanceExtended** contiene las siguientes plantillas de proceso de flujo de trabajo. Creará un flujo de trabajo para cada plantilla.

+ Crear proveedores de tipo Persona en la tabla Proveedores
+ Crear proveedores de tipo Persona en la tabla Contactos
+ Actualizar proveedores de tipo Persona en la tabla Contactos
+ Actualizar proveedores de tipo Persona en la tabla Proveedores

Para crear nuevos procesos de flujo de trabajo mediante las plantillas de proceso de flujo de trabajo, siga estos pasos.

1. Cree un proceso de flujo de trabajo para la entidad **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Crear proveedores de tipo Persona en la tabla Contactos**. A continuación seleccione **Aceptar**. Este flujo de trabajo gestiona el escenario de creación de proveedor para la entidad **Contacto**.
2. Cree un proceso de flujo de trabajo para la entidad **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Actualizar proveedores de tipo Persona en la tabla Contactos**. A continuación seleccione **Aceptar**. Este flujo de trabajo gestiona el escenario de actualización de proveedor para la entidad **Contacto**.
3. Cree un proceso de flujo de trabajo para la entidad **Contacto** y seleccione la plantilal **Crear proveedores del tipo Persona en la tabla Proveedores**.
4. Cree un proceso de flujo de trabajo para la entidad **Contacto** y seleccione la plantilla **Actualizar proveedores del tipo Persona en la tabla Proveedores**.
5. Puede configurar los flujos de trabajo como flujos de trabajo en tiempo real o en segundo plano, dependiendo de sus requisitos. Para configurar un flujo de trabajo como flujo de trabajo en segundo plano, seleccione **Convertir a un flujo de trabajo en segundo plano**.
6. Active los flujos de trabajo que ha creado en las tablas **Contacto** y **Proveedor** para comenzar a utilizar la entidad **Contacto** para almacenar información de proveedores del tipo **Persona**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]