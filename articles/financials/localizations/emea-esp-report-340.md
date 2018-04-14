---
title: "Informe 340 para España"
description: "En este tema se ofrece información acerca de cómo configurar y generar el informe 340 para España."
author: ShylaThompson
manager: AnnBe
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Spain
ms.author: epodkolz
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 82351988757372acf397a3c48d7402234c994095
ms.openlocfilehash: ff375f1a6a97de6a87961d8cd0ec128ce37ff730
ms.contentlocale: es-es
ms.lasthandoff: 02/08/2018

---

# <a name="report-340"></a>Informe 340

[!INCLUDE [banner](../includes/banner.md)]

El informe 340 reemplazó dos informes anteriores (las estatutarias Libretas de ventas y las estatutarias Libretas de compras) que todas las empresas españolas enviaban como copias impresas a las autoridades fiscales españolas. El nuevo informe se puede cargar en la página web de las autoridades fiscales o se puede enviar mediante un paquete de software que está disponible de forma gratuita por parte de las autoridades fiscales.

El informe 340 contiene información sobre todas las facturas e impuestos relacionados con las facturas que una empresa emitió o recibió durante un período específico. El informe 340 debe enviarse a las autoridades fiscales durante los primeros 20 días después el período de notificación. El período de notificación puede ser un mes o un trimestre, en función del tamaño de la empresa.

## <a name="entries-that-are-included-in-report-340"></a>Entradas que se incluyen en el informe 340

El informe 340 incluye las siguientes entradas:

- **Entradas de ventas**: entradas de líneas de informes de impuesto sobre el valor añadido (IVA) que corresponden a facturas de ventas y facturas de proyectos. Estos registros son facturas emitidas de **Tipo 2**.
- **Notas de crédito de ventas (facturas correctivas)**: entradas de líneas de informes de IVA que corresponden a facturas correctivas.
- **Entradas de compra**: entradas de líneas de informes de IVA que corresponden a facturas de compra. Estos registros son facturas recibidas de **Tipo 2**.
- **Notas de crédito de compras**: entradas de líneas de informes de IVA que corresponden a facturas correctivas.
- **Facturas automáticas y notas de crédito automáticas**: entradas de líneas de informes de IVA que corresponden a facturas y notas de crédito que se crean automáticamente cuando los bienes o servicios son prestados por un proveedor de la Unión Europea (UE).
- **Facturas que incluyen cargo de equivalencia**: el cargo de equivalencia es un tipo de impuesto español.
- **Facturas que incluyen varios IVA% o porcentaje de cargo de equivalencia (CE%)**: entradas de facturas que tienen más de un porcentaje de IVA o porcentaje de cargo de equivalencia (CE).

## <a name="generate-a-spanish-vat-book-and-export-the-report-340-ascii-file"></a>Generar un libro de IVA español y exportar el archivo ASCII del informe 340

1. Seleccione **Impuestos** &gt; **Configuración** &gt; **Impuestos** &gt; **Libros de IVA españoles**.
2. En los campos **Libro de IVA** y **Descripción**, introduzca un nombre y una descripción para el libro de IVA.
3. En el campo **Código de secuencia numérica**, seleccione un código de secuencia numérica.
4. En la ficha desplegable **Configuración**, seleccione el botón **Añadir** y, a continuación, siga estos pasos para configurar códigos de impuestos en las transacciones de impuestos que se van a incluir en el informe:

    1. En el campo **Código de impuestos**, seleccione un código de impuestos.
    2. En el campo **Código de cargo de equivalencia**, seleccione el CE, si fuera necesario.
    3. Establezca la opción **IVA no deducible** en **Sí** para activar el IVA no deducible para un código de impuestos.

        > [!NOTE]
        > No se permite a los compradores deducir el IVA no deducible de su propia obligatoriedad del IVA.

    4. Establezca la opción **Cargo invertido** en **Sí** para activar cargos invertidos para un código de impuestos.

        > [!NOTE]
        > Los cargos invertidos forman parte de la ley de IVA. En algunos casos, los bienes o servicios son prestado por una empresa extranjera. Si se activan cargos invertidos, el IVA de estos bienes y servicios lo paga la empresa destinataria, no la empresa extranjera.

5. Seleccione el botón **Informes de IVA españoles** para abrir la página **Informes de IVA españoles** .
6. Seleccione el botón **Crear nuevo** para crear un nuevo informe. En la página **Lista de IVA español**, relleno los campos **Libro de IVA**, **Descripción**, **Período de liquidación**, **Desde fecha** e **Iniciar numeración**, y siga estos pasos:

    1. En el campo **Método de numeración**, seleccione un valor.
    2. Establezca la opción **Declaración sustitutiva** en **Sí** para sustituir la declaración anterior.
    3. En el campo **Número de declaración anterior**, introduzca el número de 13 dígitos de la declaración anterior.

        > [!NOTE]
        > El campo **Número de declaración anterior** se puede editar si la opción **Declaración sustitutiva** tiene **Sí**.

7. Seleccione **Aceptar** para volver a la página **Informes de IVA españoles**. El sistema introduce la información de la página **Lista de IVA español** en la página **Informes de IVA españoles**. No puede modificar los valores de los campos **Período de liquidación**, **Método de numeración** y **Desde fecha** en la página **Informes de IVA españoles**.
8. En la pestaña **General**, siga estos pasos:

   1. En el campo **Tipo de presentación**, seleccione el tipo de medio para va a usar para exportar el archivo:

      - **Telemático**: cargue el informe en el sitio web de las autoridades fiscales o envíe el informe mediante el software gratuito provisto por las autoridades fiscales.
        - **CD-R**: envía el informe a las autoridades fiscales en un CD-ROM.
        - **Informe**

        > [!NOTE]
        > Seleccione **Telemático** o **CD-R**. Si selecciona **Informe**, recibe un mensaje de error.

   2. Establezca la opción **Notificado** en **Sí** para generar el informe final.
   3. En el campo **Persona de contacto**, introduzca el nombre de la persona de contacto.
   4. En el campo **Teléfono**, introduzca el número de teléfono de la persona de contacto.
   5. En el campo **Documento**, introduzca el número de documento de cuatro dígitos. Si introduce un número que contiene menos de cuatro dígitos, se agregan ceros iniciales para crear un número de cuatro dígitos. Por ejemplo, si especifica **1**, el sistema convierte automáticamente el valor **0001** y guarda el nuevo valor.
   6. En el campo **Electrónico**, introduzca el código electrónico de 16 dígitos. Este número es obligatorio y lo proporciona las autoridades fiscales.

9. Seleccione el botón **Totales** para abrir la página **Totales** . En esta página, puede ver los siguientes valores:

    - **Número de operaciones**: el número total de ventas o de cuentas por cobrar del grupo del campo **Entregas** y el número total de compras o cuentas a pagar en el grupo del campo **Adquisiciones**.
    - **Importe**: el importe total de las ventas o cuentas por cobrar en el grupo del campo **Entregas** y el importe total de compras o cuentas a pagar en el grupo del campo **Adquisiciones**.

10. Seleccione el botón **Líneas de informes de IVA** para abrir la página **Líneas de informes de IVA** . En esta página, puede ver los detalles de las transacciones de IVA. Puede eliminar o excluir las líneas del informe si no se han informado al exportar el informe.
11. Seleccione el botón **Salida** y seleccione **Imprimir** o **Exportar a archivo ASCII**. Si seleccionó **Exportar a archivo ASCII**, a continuación, complete los siguientes pasos: 

    > [!NOTE]
    > Si el informe de IVA no contiene ninguna transacción, recibirá un mensaje de error.
    > Antes de ejecutar el siguiente paso, compruebe la información en la pestaña **General**. Debe rellenar la información en los grupos de campos **Información de contacto** y **Número de documento**. De lo contrario, recibiría el mensaje de error. 
    
    1. En la página **Exportar a ASCII**, seleccione el archivo que desea exportar y, a continuación, seleccione **Aceptar**. La legislación tributaria prohíbe la exportación de archivos ASCII de los años anteriores a 2009. Sin embargo, puede imprimir registros de los años anteriores a 2009.
    2. En la página **Libro de registro de IVA español**, en el campo **Asignación de formato**, seleccione el formato.

    La información se recupera de la página **Líneas de informes de IVA**.

## <a name="file-format"></a>Formato de archivo

El formato del archivo de texto del informe 340 cumple con los requisitos normativos y contiene los siguientes tipos de registro:

- **Tipo 1**: el registro **Tipo 1** contiene información acerca de la empresa que envía el informe 340. Este empresa es conocida como *deponente*. La información se recupera de la tabla de información de la empresa y de la página **Libros de IVA españoles** .
- **Tipo 2**: el informe debe incluir al menos un registro de **Tipo 2**. **Tipo 2**: los registros contienen información sobre los bienes y servicios que se compraron y vendieron durante el período especificado. La información del cliente y el proveedor se recupera de los registros del cliente y el proveedor.

> [!NOTE]
> Si no hay registros de **Tipo - 2**, el archivo no se genera.

## <a name="validate-the-file-format-and-submit-the-report-340-file-to-the-tax-authorities"></a>Valide el formato de archivo y envíe el archivo del informe 340 a las autoridades fiscales

Puede validar el formato de archivo mediante uno de los siguientes métodos:

- Cargar el archivo en el [sitio web de las autoridades fiscales](https://www5.aeat.es/es13/h/iemodelk.html?mod=9340). Puede probar el archivo en una página determinada del sitio. Sin embargo, debe disponer de un certificado electrónico válido.

    > [!NOTE]
    > Los certificados electrónicos se emiten solo a ciudadanos españoles.

- Cargue el archivo mediante el software gratuito proporcionado por las autoridades fiscales.

