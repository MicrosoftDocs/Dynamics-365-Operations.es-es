---
title: Diseñar configuraciones para generar informes en los formatos de Office que tengan imágenes incrustadas
description: Este tema describe cómo diseñar las configuraciones que generan documentos electrónicos en formato Excel y Word que contienen imágenes insertadas.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 03a514c5b616d761ef3eb6347e67e645b23eaa1794911775835e77cded4500ac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719354"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Diseñar configuraciones para generar informes en los formatos de Office que tengan imágenes incrustadas

[!include [banner](../../includes/banner.md)]

Para completar los pasos de este procedimiento, primero complete el procedimiento, "ER: Crear un proveedor de configuraciones y marcarlo como activo". Este procedimiento explica cómo diseñar las configuraciones de informes electrónicos (ER) para generar documentos de Microsoft Excel o Word que contienen imágenes incrustadas. En este procedimiento, creará las configuraciones de ER necesarias para la empresa de ejemplo, Litware, Inc. Estos pasos se pueden completar mediante el conjunto de datos de USMF. Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados. Antes de comenzar, debe descargar y guardar los archivos siguientes: 

| Descripción                                          | Nombre de archivo                   |
|------------------------------------------------------|-----------------------------|
| Configuración del modelo datos de ER                          | [Model for cheques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| Configuración del formato de ER                              | [Cheques printing format.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Imagen del logotipo de la empresa                                   | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Imagen de firma                                      | [Signature image.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Imagen de firma alternativa                          | [Signature image 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Plantilla de Microsoft Word para imprimir cheques de pago  | [Consultar plantilla Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a>Comprobar los requisitos previos  
 1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.  
 2. Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como Activo. Si no ve a este proveedor de configuración, complete los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".   
 3. Haga clic en Configuraciones de informes.  
 
## <a name="add-a-new-er-model-configuration"></a>Añada una nueva configuración para el modelo ER  
 1. En lugar de crear un nuevo modelo, puede cargar el archivo de configuración del modelo de ER (modelo para cheques.xml) que se guardó anteriormente. Este archivo contiene el modelo de datos de ejemplo para los cheques de pago y la asignación de modelo de datos a los componentes de datos de la aplicación Dynamics 365 for Operations.   
 2. En las versiones de ficha desplegable, haga clic en Exchange.   
 3. Haga clic en Cargar desde un archivo XML.  
 4. Haga clic en Examinar, y seleccione el modelo para cheques.xml.   
 5. Haga clic en Aceptar  
 6. El modelo cargado se utilizará como origen de datos de la información para generar documentos que contengan imágenes en Excel y Word.  

## <a name="add-a-new-er-format-configuration"></a>Añada una nueva configuración para el formato de ER  
 1. En lugar de crear un nuevo formato, puede cargar el archivo de configuración del formato de ER (formato de impresión de cheques .xml) que guardó anteriormente. Este archivo contiene el diseño de ejemplo de formato para imprimir cheques utilizando el formulario preimpreso y la asignación de este formato al modelo de datos “modelo para cheques”.   
 2. Haga clic en Intercambiar.  
 3. Haga clic en Cargar desde un archivo XML.  
 4. Haga clic en Examinar y seleccione el archivo Cheques printing format.xml.   
 5. Haga clic en Aceptar  
 6. En el árbol, expanda "Modelo para cheques".  
 7. En el árbol, seleccione "Modelo para cheques\Formato de impresión de cheques".  
 8. El formato cargado se utilizará para generar documentos que contengan imágenes en Excel y Word.   

## <a name="configure-er-user-parameters"></a>Configurar los parámetros de usuario de ER  
 1. En el panel de acciones, haga clic en Configuraciones.  
 2. Haga clic en Parámetros de usuario.  
 3. Seleccione Sí en el campo Parámetros de ejecución.  
  Desconecte el indicador de "Ejecución de borrador" para iniciar la versión de borrador del formato seleccionado en lugar del completado.  
 4. Haga clic en Aceptar  

## <a name="configure-cash--bank-management-parameters"></a>Configure los parámetros de administración de efectivo y bancos  
 1. Vaya a Gestión de efectivo y de banco > Cuentas bancarias > Cuentas bancarias.  
 2. Use un filtro rápido para filtrar por el campo Cuenta bancaria, por el valor ''USMF OPER".  
 3. En el panel de acciones, haga clic en Configurar.  
 4. Haga clic en Comprobar.  
 5. Expanda la sección Configuración.  
 6. Haga clic en Editar.  
 7. Seleccione Sí en el campo Logotipo de la empresa.  
 8. Haga clic en Logotipo de la empresa.  
 9. Haga clic en Cambiar.  
 10. Haga clic Examinar y seleccione el archivo que ha descargado anteriormente, Company logo.png.   
 11. Haga clic en Guardar.  
 12. Cierre la página.  
 13. Expanda la sección Firma.  
 14. Seleccione Sí en el campo Imprimir la primera firma.  
 15. Haga clic en Cambiar.  
 16. Haga clic Examinar y seleccione el archivo que ha descargado anteriormente, Signature image.png.   
 17. Expanda la sección Copias.  
 18. En el campo Marca de agua, seleccione una opción.  
 19. Seleccione Sí en el campo Formato de exportación electrónica genérica.  
 20. Seleccione la configuración "Cheques printing form".  
 21. Ahora el formato seleccionado de ER se usará para imprimir los cheques.  
 22. Haga clic en Vincular.  
 23. Haga clic en Nuevo.  
 24. Haga clic en Archivo.  
 25. Haga clic Examinar y seleccione el archivo que ha descargado anteriormente, Signature image 2.png.   
 26. Cierre la página.  
 27. Cierre la página.  
 28. Cierre la página.  
 29. Vaya a Gestión de efectivo y bancos > Configurar > Parámetros de gestión de efectivo y bancos.  
 30. Seleccione Sí en el campo Permitir la creación de validaciones de cuenta en cuentas bancarias inactivas:.  
 31. Haga clic en Guardar.  
 32. Cierre la página.  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
