---
title: Cuentas de usuario de dispositivo móvil
description: Este tema describe cómo configurar y administrar cuentas de usuario que permitan a los trabajadores iniciar sesión y usar la aplicación de almacén.
author: Mirzaab
ms.date: 09/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-09-15
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f3a930814a1fb98e3b1611adf309c10e66b49b9d
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902106"
---
# <a name="mobile-device-user-accounts"></a>Cuentas de usuario de dispositivo móvil

[!include [banner](../includes/banner.md)]

Cada vez que un trabajador comienza a utilizar la aplicación del almacén, debe iniciar sesión con un nombre de usuario y una contraseña. Se puede asociar cualquier número de usuarios de la aplicación de almacén con cada trabajador del sistema, y los almacenes suelen estar asociados con cada uno de esos usuarios de la aplicación de almacén. También se configuran varias opciones para cada trabajador, para establecer la configuración predeterminada y otras configuraciones que son relevantes para el uso de la aplicación del almacén.

## <a name="set-up-the-required-worker-and-employee-records"></a>Configure los registros de trabajadores y empleados requeridos

Antes de poder configurar los usuarios de la aplicación de almacén, cada trabajador ya debe existir como empleado o trabajador de Supply Chain Management en el módulo **Recursos humanos**.

## <a name="set-up-mobile-device-user-accounts"></a><a name="set-wma-users"></a>Configurar cuentas de usuario de dispositivo móvil

Una vez configurados los trabajadores y empleados necesarios en Recursos humanos, puede asignar usuarios de la aplicación de almacén a cada uno de ellos y configurar otras opciones que afecten la forma en que pueden usar la aplicación.

1. Vaya a **Gestión de almacenes \> Configuración \> Empleado**.
1. Para editar un trabajador existente, selecciónelo en el panel de lista. En el Panel de acciones, seleccione **Nuevo** para agregar un nuevo registro.
1. Si está configurando un nuevo trabajador, siga estos pasos:

    1. En el campo **Empleado**, seleccione el usuario de destino en la lista de empleados.
    1. Seleccione **Seleccionar**.
    1. En el panel Acciones, seleccione **Guardar**.

1. Se puede utilizar un perfil predeterminado para guiar al trabajador del almacén en la estación de empaque a través del proceso que se requiere allí. Alternativamente, el perfil predeterminado se puede utilizar para guardar la configuración de perfil preferida del trabajador. En la ficha desplegable **Perfil**, establezca los siguientes campos:

    - **Política de embalaje de contenedores** - Seleccione una política de empaque de contenedores que defina cómo se deben procesar los contenedores en la estación de empaque. La política de empaque de contenedores que se selecciona aquí será preseleccionada para el trabajador cuando abra la estación de empaque. Para obtener más información, consulte la siguiente publicación de blog: [Funcionalidad de empaque mejorada](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611),
    - **ID de perfil de embalaje** - Seleccione un ID de perfil de embalaje que defina la política de embalaje y la configuración del contenedor que se utilizan. Si el ID de perfil de embalaje seleccionado está asociado con una política de embalaje de contenedores, no podrá cambiar el ajuste **Política de embalaje de contenedores** en esta página.

1. En la ficha desplegable **Estación de embalaje predeterminada**, configure los siguientes campos para definir la estación de embalaje predeterminada que se aplica cuando el trabajador inicia sesión. El trabajador todavía puede seleccionar otra estación de embalaje según sea oportuno.

    - **Sitio** - Seleccione el sitio donde se encuentra la estación de empaque predeterminada.
    - **Almacén** - Seleccione el almacén donde se encuentra la estación de empaque predeterminada.
    - **Localización** - Seleccione la ubicación de la estación de embalaje predeterminada.

1. La ficha desplegable **Usuarios** le permite crear cualquier número de cuentas de usuario de la aplicación de almacén para el trabajador seleccionado. Cada cuenta está asociada a un almacén o almacenes específicos. Utilice la barra de herramientas para agregar o eliminar cuentas de usuario, restablecer la contraseña de una cuenta seleccionada o asignar almacenes a una cuenta seleccionada. Para cada cuenta de usuario, puede configurar los siguientes campos:

    - **Id. de usuario:** introduzca un id. exclusivo.
    - **Nombre de usuario:** introduzca un nombre para el Id.
    - **Almacén predeterminado** - Establecer el almacén predeterminado donde trabaja habitualmente el trabajador. Puede usar la barra de herramientas para asignar almacenes adicionales, y el trabajador puede cambiar entre almacenes usando la actividad indirecta **Cambiar de almacén** del elemento de menú del dispositivo móvil.
    - **Nombre del menú** - Seleccione el menú raíz que será la página de inicio del trabajador. La capacidad de configurar un menú raíz para cada trabajador es útil porque le permite controlar la estructura del menú que cada trabajador puede usar. Por ejemplo, el menú para los trabajadores que están activos solo en el área de salida se puede personalizar para las tareas relacionadas con las operaciones de salida de esa área.
    - **Inactivo** - Una casilla de verificación seleccionada indica que la cuenta de usuario está inactiva. La cuenta de usuario se desactiva automáticamente si un trabajador ingresa la contraseña incorrecta cinco veces seguidas en la aplicación del almacén. Sin embargo, también puede seleccionar esta casilla de forma manual. Desmarque la casilla de verificación para que el usuario vuelva a estar activo.

1. En la ficha desplegable **Trabajo**, establezca los siguientes campos:

    - **Permitir la anulación de la ubicación de la selección** - Establezca esta opción en *Sí* para permitir que el trabajador anule la ubicación para recoger los pasos. Esta capacidad puede resultar útil si el inventario físico no coincide con la ubicación sugerida por el sistema.
    - **Permitir la anulación de la ubicación de colocación** - Establezca esta opción en *Sí* para permitir que el trabajador anule la ubicación para los pasos de colocación. Esta capacidad puede ser útil si la ubicación de almacenamiento sugerida está actualmente llena o no está disponible, o si las ubicaciones de almacenamiento cambiaron.
    - **Permitir ventas por sobre picking** - Establezca esta opción en *Sí* para permitir que el trabajador haga una selección excesiva cuando se recogen las órdenes de venta. Para obtener más información, vea [Selección en exceso de pedidos de ventas y pedidos de transferencia](over-picking-for-sales-and-transfer-orders.md).
    - **Permitir pedidos de transferencia sobre picking** - Establezca esta opción en *Sí* para permitir que el trabajador haga una selección excesiva cuando se recogen las órdenes de transferencia. Para obtener más información, vea [Selección en exceso de pedidos de ventas y pedidos de transferencia](over-picking-for-sales-and-transfer-orders.md).
    - **Permitir el movimiento de inventario con trabajo asociado** - Establezca esta opción en *Sí* para permitir que el trabajador mueva el inventario que ya está reservado o asociado con otro trabajo. Para obtener más información, vea [Movimiento de inventario con trabajo asociado en gestión de almacenes](move-inventory-associated-work.md).
    - **Permitir la reasignación manual de artículos** - Establezca esta opción en *Sí* para permitir la reasignación manual del trabajador durante el picking corto. La reasignación de artículos guía a los trabajadores a seleccionar el inventario de otra ubicación. Aunque la reasignación automática está disponible para todos los trabajadores, la reasignación manual requiere una configuración explícita para un trabajador. La capacidad de controlar la reasignación manual para cada trabajador puede ser útil porque le permite controlar la visibilidad que tiene cada trabajador cuando, por ejemplo, la recolección de artículos en el área de cuarentena o en lote se limita a los trabajadores de confianza. Para obtener más información, consulte la siguiente publicación de blog: [Reasignación automática y manual de artículos durante el picking corto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/11/07/automatic-and-manual-item-reallocation-during-the-short-picking-dynamics-365-for-operations-1611/).
    - **Es supervisor de conteo cíclico** - Establezca esta opción en *Sí* para convertir al trabajador en supervisor de recuento cíclico. En este caso, todos los recuentos de ciclos que realiza el trabajador en la aplicación del almacén serán aprobados de inmediato. Los campos **Límite máximo porcentual**, **Límite de cantidad máxima** y **Límite de valor máximo** no se tienen en cuenta para los trabajadores que esta opción está configurada en *Sí*.
    - **Límite de porcentaje máximo** – Especifique el límite de porcentaje más alto que una cuenta cíclica puede diferir del recuento previsto sin requerir la aprobación de un supervisor de la cuenta cíclica.
    - **Límite de cantidad máxima** - Ingrese la cantidad total que la cantidad ingresada puede diferir de la cantidad esperada (en unidades) sin requerir la aprobación de un supervisor de conteo de ciclos.
    - **Límite del valor máximo** – Especifique el importe máximo que el coste de inventario puede diferir del coste previsto sin requerir la aprobación de un supervisor de la cuenta cíclica.

1. En el panel Acciones, seleccione **Guardar**.
1. Si agregó una cuenta de usuario nueva, aparece el cuadro de diálogo **Establecer contraseña** donde puede crear una contraseña sencilla que el usuario puede usar para iniciar sesión en la aplicación móvil. Ingrese la contraseña simple dos veces y luego seleccione **Guardar contraseña** para continuar.

## <a name="set-the-language-number-formats-and-time-zone-for-each-warehouse-app-user"></a>Establezca el idioma, los formatos numéricos y la zona horaria para cada usuario de la aplicación de almacén.

Cuando un trabajador inicia sesión en la aplicación móvil Warehouse Management, el idioma, los formatos numéricos y la zona horaria cambian para coincidir con las preferencias de ese trabajador. La configuración de la cuenta para el trabajador que se selecciona en el paso 3 en la sección [Configurar cuentas de usuario de dispositivos móviles](#set-wma-users) determina la configuración que se utiliza. Si necesita configuraciones separadas para cada usuario, use diferentes cuentas de trabajador. El siguiente procedimiento muestra cómo cambiar el idioma, los formatos numéricos y la zona horaria para cada usuario de la aplicación de almacén.

1. Vaya a **Gestión de almacenes \> Configuración \> Empleado**.
1. Busque el nombre del trabajador que desea configurar. Asegúrese de que el trabajador tenga todas las cuentas de usuario de la aplicación de almacén requeridas que se enumeran en la ficha desplegable **Usuarios**. Cree un nuevo trabajador y/o agregue cuentas de usuario de la aplicación de almacén según sea necesario, siguiendo los pasos de la sección [Configurar cuentas de usuario de dispositivos móviles](#set-wma-users).
1. Vaya a **Administración del sistema \> Usuarios \> Usuarios**.
1. Seleccione la cuenta de usuario donde la columna **Persona** muestra el nombre del trabajador que encontró en el paso 2.

    > [!IMPORTANT]
    > Los valores de **ID de usuario** que se enumeran en la página **Usuarios** *no* están relacionados con el valor que se muestra en la ficha desplegable **Usuarios** de la página **Trabajador** que abrió en el paso 1.

1. En el panel de acciones, seleccione **Opciones de usuario**.
1. En la pestaña **Preferencias**, establezca los campos siguientes:

    - **Idioma** - Seleccione el idioma que prefiera el trabajador. Este campo también controla el formato de fecha que se muestra en la aplicación del almacén.
    - **Formato de fecha, hora y número** - Seleccione el idioma que determinará los formatos de números que se muestran en la aplicación del almacén. Tenga en cuenta que los formatos de fecha y hora que se muestran en la aplicación del almacén están determinados por el campo **Idioma**, no por este campo.
    - **Zona horaria** - Seleccione la zona horaria donde trabaja el trabajador. Este campo afecta la marca de tiempo de todos los registros que el trabajador realiza mediante la aplicación.

> [!NOTE]
> En algunos casos, la aplicación del almacén no podrá encontrar configuraciones de trabajador específicas que establezcan el idioma, los formatos numéricos y la zona horaria. Se aplican las siguientes reglas:
>
> - Si la aplicación no está conectada a un entorno de Supply Chain Management (por ejemplo, la primera vez que se inicia la aplicación después de su instalación), se utiliza el idioma del dispositivo local. Cuando cambia el idioma del dispositivo, también cambia el idioma de la aplicación. Para obtener más información sobre cómo configurar el idioma para el dispositivo local, consulte la documentación de su dispositivo y / o sistema operativo.
> - Si la aplicación está conectada a un entorno de Supply Chain Management, pero no se establecen preferencias para el trabajador que inició sesión, el idioma, los formatos de números y la zona horaria se seleccionan en función de la cuenta asociada con la ID de cliente que usa el dispositivo. para conectarse a Supply Chain Management. Para obtener más información, vea [Crear y configurar una cuenta de usuario en Supply Chain Management](install-configure-warehouse-management-app.md#user-azure-ad).

> [!TIP]
> Si observa que se muestran marcas de tiempo incorrectas para los registros que se realizan con la aplicación del almacén, es posible que deba ajustar la zona horaria establecida para la cuenta de usuario que los trabajadores usan para iniciar sesión y / o autenticarse con Supply Chain Management. Como se mencionó anteriormente, la configuración de la zona horaria puede provenir de la cuenta de usuario que se utiliza para iniciar sesión en la aplicación del almacén, como se configuró en la página **Trabajador**. Alternativamente, si la cuenta de usuario no está configurada en la página **Trabajador**, la zona horaria proviene de la cuenta de usuario que está asociada con el ID de cliente que se utiliza para la autenticación, como se configura en la página **[Aplicaciones de Azure Active Directory](install-configure-warehouse-management-app.md)**.
