---
title: Editar información personal
description: Este artículo describe cómo editar información personal en el autoservicio para empleados y gerentes.
author: andreabichsel
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2170d3b8c476fb82786721512013eae45bb78ce5
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052154"
---
# <a name="edit-personal-information"></a>Editar información personal

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede editar su información personal en Dynamics 365 Human Resources en el **Espacio de trabajo de autoservicio para empleados**.

La información personal que puede editar incluye:

- Direcciones
- Detalles de contacto
- Contactos personales
- Números de identificación
- Método de pago
- Imagen utilizada en Human Resources

>[!NOTE]
>Es posible que no pueda editar ciertos tipos de información personal, como los datos de contacto de la empresa. Para más información, vea [Restringir la edición de información personal](hr-employee-self-service-restrict-editing.md).

Los parámetros establecidos en la libreta de direcciones global determinan los roles que pueden ver su información personal.

1. En Human Resources, seleccione **Autoservicio para los empleados**.

2. Seleccione **Editar detalles personales**.

3. Para cambiar su dirección, seleccione la pestaña **Direcciones**. Los cambios que haga aparecen en el espacio de trabajo **Gestión de personal** para alertar a RRHH.

    - Para agrear una dirección nueva, seleccione **Agregar**.
    - Para editar una dirección existente, seleccione la dirección y luego seleccione **Editar**.
    - Para ver un mapa, seleccione **Mapa**.
    - Para agregar o eliminar un contacto, seleccione **Mas opciones** y luego seleccione **Avanzado**. En **Información del contacto**, seleccione **Agregar** o **Eliminar** y edite los campos según sea necesario.
    - Para configurar su zona horaria y ubicación, seleccione **Mas opciones** y luego seleccione **Avanzado**. En **General**, edite los campos según sea necesario.

4. Para cambiar sus datos de contacto, seleccione la pestaña **Detalles de contacto**. Puede proporcionar diferentes tipos de información de contacto, incluidos teléfonos, correos electrónicos y enlaces de redes sociales. Puede establecer un detalle de contacto como primario, pero solo puede establecer uno de cada tipo como primario.

    - Para agrear información de contacto nueva , seleccione **Agregar**. Edite los campos según sea necesario.
    - Para editar una información de contacto existente, seleccione el elemento y luego seleccione **Editar**. Edite los campos según sea necesario.
    - Para establecer un detalle de contacto como privado, seleccione el elemento, seleccione **Avanzado** y luego establezca **Privado** a **Sí**. Seleccione **Aceptar**.
      >[!NOTE]
      >El botón **Avanzado** no está disponible si su administrador ha habilitado la característica **(Versión preliminar) Impedir que los empleados agreguen o editen la dirección y la información de contacto para fines seleccionados** en su entorno. Para más información, vea [Restringir la edición de información personal](hr-employee-self-service-restrict-editing.md).
  
5. Para cambiar sus contactos personales, seleccione la pestaña **Contactos personales**. Puede designar contactos de emergencia, beneficiarios y dependientes. Un contacto puede ser una persona u organización. La característica **Gestión de beneficios** utiliza información de contacto personal. Para más información, consulte [Configurar las opciones de elegibilidad de contacto personal](hr-benefits-setup-contact-eligibility-options.md).

6. Para cambiar sus números de identificación, como el Número de Seguro Social, seleccione la pestaña **Números de identificación**. Los cambios pueden pasar por un proceso de aprobación si su organización configura un flujo de trabajo de aprobación.

    - Para agregar un número de identificación, seleccione **Nuevo**. Complete los campos según sea necesario y seleccione **Guardar**.
    - Para editar un número, seleccione **Editar**. Edite los campos según sea necesario y seleccione **Guardar**.

7. Para cambiar los métodos por los cuales le pagan, seleccione la pestaña **Mi informacion de pago**. Esta pestaña solo está disponible si los métodos de pago están habilitados en el formulario **Parámetros de recursos humanos**. HR puede habilitar **Giro bancario**, **Efectivo**, **Cheque**, **Pago electrónico** u **Otro**. HR también puede deshabilitar la validación de pagos electrónicos (utilizada para la nómina de EE. UU.) y la validación de la cuenta bancaria y el número de ruta.

8. Para cambiar la imagen que se muestra en Human Resources para su perfil, seleccione la pestaña **Imagen**. Dependiendo de la configuración de su organización, las imágenes pueden enrutarse para su aprobación.

    - Para cargar una imagen, seleccione **Subir imagen nueva**.
    - Para eliminar una imagen, seleccione la imagen y luego seleccione **Eliminar**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]