---
title: Extracto de prestaciones
description: El informe de declaración de prestaciones explica las prestaciones en las que un empleado está inscrito actualmente.
author: twheeloc
ms.date: 09/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 36e7082a890ebec3031021a0871cddad91597447
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337072"
---
# <a name="benefit-statement"></a>Extracto de prestaciones

El informe de **Declaración de prestaciones** proporciona un extracto de las prestaciones en las que un empleado está inscrito actualmente. Un empleado puede acceder directamente al informe o el administrador de prestaciones. La **Declaración de prestaciones** proporciona una lista de las prestaciones inscritas del empleado, las opciones de cobertura, los costes y los dependientes o beneficiarios inscritos. El extracto se puede imprimir para un solo trabajador o para varios trabajadores.

> [!NOTE]
La función **Extracto de prestaciones** debe estar habilitada en el espacio de trabajo **Gestión de características**. Para hacer esto, la característica **Gestión de prestaciones** estar activada en Gestión de características. 


## <a name="importing-the-benefit-statement"></a>Importación de la declaración de prestaciones 

Debe importar la **Declaración de prestaciones** utilizando la configuración del informe antes de que la **Declaración de prestaciones** esté disponible. Para ello, realice los pasos siguientes:

1.  Vaya al espacio de trabajo **Administración del sistema**.

2.  Seleccione el icono **Informes electrónicos**.

3.  Vaya a **Proveedores de configuración** y seleccione **Repositorios**.

  ![Selección de Repositorios.](https://user-images.githubusercontent.com/26801678/134203290-7faf7245-ed08-44e9-95a1-a7ba278c42c6.png)

4.  Seleccione **Recursos de RRHH** de la lista y luego seleccione **Abrir**.

    ![Repositorios de configuración.](https://user-images.githubusercontent.com/26801678/134203619-b3fd087d-1fe9-45ef-a588-1afedfe38dfd.png)

5.  Seleccione el **Modelo de declaración de prestaciones** en el panel izquierdo y expándala para que aparezca **Formato de declaración de prestaciones**.

6.  Seleccione **Formato de declaración de prestaciones** en el panel izquierdo.

7.  En el lado derecho de la pantalla, habrá una ficha desplegable **Versiones**. Seleccione **Importar**.

    ![Ficha desplegable Versiones.](https://user-images.githubusercontent.com/26801678/134203763-f12ef549-e326-400d-ac69-b25fc94af47b.png)

## <a name="generate-the-benefit-statement-as-a-pdf-file"></a>Genere la declaración de prestaciones como un archivo PDF

Por defecto, la **Declaración de prestaciones** se imprimirá como un documento de Microsoft Word. Para imprimir en formato PDF, deberá configurar la opción PDF en **Destino de informes electrónicos**. 

1. Para hacer esto, vaya a **Espacio de trabajo de administración del sistema** > **Informes electrónicos** > **Enlaces relacionados** > **Destino de informes electrónicos**.

1.  Seleccione **Nuevo**.

2.  En el campo **Referencia**, seleccione **Formato de declaración de prestaciones**.

3.  En la ficha desplegable **Destino del archivo**, seleccione **Nuevo**.

4.  En el campo **Nombre**, especifique **Declaración de prestaciones PDF**.

5.  En el campo **Nombre de componente de archivo**, seleccione **Declaración de prestaciones**.

6.  Seleccione la casilla **Convertir a PDF**.

7.  Seleccione **Configuración** desde el elemento del menú. 

    ![Destino del archivo.](https://user-images.githubusercontent.com/26801678/134203881-a3f1ebc3-d816-485d-a53b-026cc29cae64.png)

8.  Seleccione la ficha desplegable **Archivo** y luego seleccione **Habilitado**.

9.  Seleccione **Aceptar**.
   
> [!NOTE]
> La característica de gestión de prestaciones está en un estado de vista previa. Existe un problema conocido al utilizar la configuración de destino de correo electrónico en el informe **Destino de informes electrónicos**. Puede recibir un mensaje de error y el correo no se enviará.

La **Declaración de prestaciones** se puede generar a partir de las siguientes páginas:

-   **Espacio de trabajo de gestión de prestaciones** > **Enlaces** > **Informes** > **Declaración de prestaciones**

-   **Empleados (formulario heredado)** > **Pestaña de información personal** > **Declaración de prestaciones**

-   **Entrada de empleados simplificada** > **Informes de prestaciones** > **Declaración de prestaciones**

-   **Autoservicio para los empleados** > **Prestaciones** > **Ver declaración de prestaciones**

> [!NOTE]
>  Acceso a la **Declaración de prestaciones** en **Autoservicio para los empleados** está controlado por el privilegio **Ver declaración de prestaciones**. Esto está bajo el derecho **Prestaciones de autoservicio para empleados**. Este privilegio se otorga a los empleados de forma predeterminada.

## <a name="report-contents"></a>Contenido del informe

La **Declaración de prestaciones** imprimirá las selecciones de planes confirmados del empleado, incluidos los planes eximidos. En la imagen siguiente se muestra un ejemplo de este informe. 

![Informe de declaración de prestaciones.](https://user-images.githubusercontent.com/26801678/134204058-61baa318-fede-4795-a256-acdf3217f9f9.png)

El informe mostrará el **Plan**, **Opción de cobertura**, **Coste de empleado**, y **Coste del empleador**. El informe también enumerará los dependientes cubiertos. Si el plan tiene beneficiarios asociados, se mostrarán los beneficiarios y su prioridad de distribución y porcentaje.

El informe **Declaración de prestaciones** se puede imprimir para varios empleados al mismo tiempo utilizando la ficha desplegable **Registros para incluir** en la página **Declaración de prestaciones**.
