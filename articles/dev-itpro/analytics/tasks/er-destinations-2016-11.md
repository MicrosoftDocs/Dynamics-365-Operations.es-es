--- 
title: "Configurar destinos de informes electrónicos (ER)"
description: "Este procedimiento muestra cómo configurar y usar diferentes destinos para componentes de salida de informes electrónicos, como una carpeta o un archivo."
author: NickSelin
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: afe9d397872b9328b59f4036049ab53b3bba2aec
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="configure-destinations-for-electronic-reporting-er"></a>Configurar destinos de informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar y usar diferentes destinos para componentes de salida de informes electrónicos, como una carpeta o un archivo. La empresa de datos de demostración utilizada para crear este procedimiento es DEMF. Alemania es el país o región de la dirección principal de la entidad jurídica. Sin embargo, puede usar cualquier entidad jurídica para este procedimiento. 

El formato que se usa en este ejemplo es ISO20022 Transferencia de crédito, pero puede usar cualquier formato que ya haya importado. Tenga en cuenta que este procedimiento es un ejemplo de una configuración de destino y archivo único. Encontrará más información acerca de la gestión de destinos de informes electrónicos en Ayuda de Dynamics 365 for Finance and Operations.

1. Vaya a Administración de la organización > Informes electrónicos > Destino de informes electrónicos.
2. Haga clic en Nuevo para crear un nuevo conjunto de destinos para un formato.
3. En el campo Referencia, seleccione un formato para el que desea configurar destinos.
    * Si no tiene un valor para seleccionarlo, significa que no ha importado ninguna configuración de formato de informes electrónicos. Debe importar una configuración de formato antes de configurar destinos.  
4. Haga clic en Nuevo para crear un nuevo destino de archivo.
    * Tenga en cuenta que puede crear un destino de archivo para cada componente de salida del mismo formato, como una carpeta o un archivo. Podrá habilitar y deshabilitar destinos de forma independiente en los ajustes.  
5. En el campo Nombre, especifique el nombre sencillo del componente de salida.
    * Se recomienda usar nombres significativos, como "Archivo de pago" o "Informe de control". Estos nombres se presentarán a los usuarios en tiempo de ejecución de la configuración junto con la configuración del destino.  
6. En el Nombre de archivo, seleccione un archivo o una carpeta específicos para el formato.
7. Haga clic en Configuración.
8. Seleccione Sí en el campo Habilitado.
    * La casilla Habilitada de cada ficha habilita y deshabilita cada destino por separado. En este ejemplo, habilitará el envío de un archivo de salida a un destinatario de correo cuando se genere el archivo.  
9. Haga clic en Editar para configurar los destinatarios de correo electrónico.
10. Haga clic en Agregar.
11. Haga clic en Correo electrónico de administración de impresión.
12. En el campo Origen de correo electrónico, seleccione una opción.
    * Puede seleccionar diferentes tipos de origen de correo electrónico, como un cliente o un tipo de proveedor. Esto define el tipo de argumento que devolverá la fórmula de la cuenta de origen del correo electrónico. La fórmula de la cuenta de origen del correo electrónico, descrita en el paso siguiente, es donde enlazará un origen de correo electrónico. Seleccione Proveedor si la fórmula devolverá una cuenta de proveedor. Use Proveedor si está usando el ejemplo de configuración ISO 20022 Transferencia de crédito.  
13. Haga clic en el botón Enlazar origen de correo electrónico.
14. En la Fórmula, especifique una referencia específica de documento para el tipo de parte que ha seleccionado anteriormente.
    * En lugar de escribir, puede encontrar un nodo del origen de datos que represente la cuenta de la parte y hacer clic en el botón Agregar origen de datos para actualizar la fórmula. Por ejemplo, si utiliza la configuración ISO 20022 Transferencia de crédito, el nodo que representa una cuenta de proveedor es "$PaymentsForCoveringLetter".Creditor.Identification.SourceID. De lo contrario, especifique cualquier valor de cadena, como "DE-001", para guardar una fórmula.  
15. Haga clic en Guardar.
16. Cierre la página.
17. Haga clic en Editar para configurar los detalles de contacto de la parte.
18. Seleccione Sí en el campo Contacto principal.
    * Puede usar diferentes opciones para indicar qué tipo de contacto de la parte se debe usar como dirección de correo electrónico para este destino. En este ejemplo usaremos el contacto principal.  
19. Haga clic en Aceptar
20. Haga clic en Aceptar
21. En el campo Asunto, escriba un valor.
22. Haga clic en Aceptar

