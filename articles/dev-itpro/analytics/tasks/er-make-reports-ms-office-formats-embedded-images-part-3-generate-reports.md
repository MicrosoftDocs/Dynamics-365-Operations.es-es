--- 
title: "Generar informes en los formatos de Office que tengan imágenes incrustadas"
description: "En los pasos siguientes se explica cómo un usuario con rol de \"Administrador de sistema\" o \"Desarrollador de informes electrónicos\" puede diseñar configuraciones de informe electrónico (ER) para generar documentos electrónicos en formatos de MS Office (Excel y Word) que contienen imágenes incrustadas."
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 5ef7ec2f8b5b7fdf456ebb71b863e620ae21e6b5
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a>Generar informes en los formatos de Office que tengan imágenes incrustadas

[!include [task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de "Administrador de sistema" o "Desarrollador de informes electrónicos" puede diseñar configuraciones de informe electrónico (ER) para generar documentos electrónicos en formatos de MS Office (Excel y Word) que contienen imágenes incrustadas.

En este ejemplo, usará configuraciones de ER creadas para una empresa de ejemplo "Litware, Inc".  Para completar estos pasos, primero debe completar los pasos de la guía de tareas "ER crea informes en los formatos de MS Office con imágenes incrustadas (Parte 2: Revisar configuraciones)”. Estos pasos se pueden llevar a cabo en la empresa "USMF".


## <a name="run-format-with-initial-model-mapping"></a>Ejecutar formato con asignación de modelo inicial
1. Vaya a Gestión de efectivo y de banco > Cuentas bancarias > Cuentas bancarias.
2. Use un filtro rápido para filtrar por el campo Cuenta bancaria, por el valor ''USMF OPER".
3. En el panel de acciones, haga clic en Configurar.
4. Haga clic en Comprobar.
5. Haga clic en Imprimir prueba.
    * Ejecute el formato para probar.  
6. Seleccione Sí en el campo Formato de cheque negociable.
7. Haga clic en Aceptar
    * Revise el resultado creado. Tenga en cuenta que el logotipo de la empresa se mostrará en el informe junto con la firma de la persona autorizada. La imagen de firma se obtiene en el campo del tipo de datos “Contenedor” del registro de diseño de cheques que está asociado a la cuenta bancaria seleccionada.  
8. Expanda la sección Copias.
9. Haga clic en Editar.
10. En el campo de marca de agua, introduzca "Imprimir marca de agua como Anulada".
    * Cambie la configuración del diseño de la marca de agua para mostrar el texto de la marca de agua en la generación de documentos en un elemento de forma de Excel.  
11. Haga clic en Imprimir prueba.
12. Haga clic en Aceptar
    * Revise el resultado creado. Tenga en cuenta que la marca de agua se mostrará en el informe creado de acuerdo a la opción de selección.  
13. Cierre la página.
14. En el panel Acción, haga clic en Administrar pagos.
15. Haga clic en Cheques.
16. Haga clic en Mostrar filtros.
17. Aplique los filtros siguientes: escriba un valor de filtro de "381","385","389" en el campo "Número de cheque” con el operador de filtro “es uno de”.
18. En la lista, marque todas las filas.
19. Haga clic en Imprimir copia de cheque.
    * Ejecute el formato para reimprimir los cheques seleccionados.  
    * Revise el resultado creado. Observe que se han vuelto a imprimir los cheques seleccionados. El logotipo de la empresa y las etiquetas no se imprimen ya que se muestran en el formulario preimpreso.  

## <a name="modify-the-mapping-of-the-imported-data-model"></a>Modificar la asignación del modelo de datos importado
1. Cierre la página.
2. Cierre la página.
3. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
4. En el árbol, seleccione "Modelo para cheques".
5. Haga clic en Diseñador.
6. Haga clic en Asignar modelo a origen de datos.
7. Haga clic en Diseñador.
    * Cambiaremos el enlace del elemento de la firma del modelo de datos para obtener la imagen de firma a partir del archivo que se ha adjuntado al registro del diseño de cheques que está asociado a la cuenta bancaria seleccionada.  
8. Desactive Mostrar detalles.
9. En el árbol, expanda "Diseño".
10. En el árbol, expanda "Diseño\firma".
11. En el árbol, seleccione "diseño\firma\imagen = cuentadecheque."<Relaciones".DiseñoChequeBancario.Firma1Bmp'.
12. En el árbol, expanda "cuentadecheque".
13. En el árbol, expanda "cuentadecheque\<Relaciones".
14. En el árbol, expanda "cuentadecheque\<Relaciones\DiseñodeChequeBancario".
15. En el árbol, expanda "cuentadecheque\<Relaciones\DiseñodeChequeBancario\<Relaciones".
16. En el árbol, expanda "cuentadecheque\<Relaciones\DiseñodeChequeBancario\<Relaciones\<Documentos'.
17. En el árbol, seleccione 'cuentadecheque\<Relaciones\DiseñodeChequeBancario\<Relaciones\<Documentos\obtenerContenidodeArchivocomoContenedor()'.
18. Haga clic en Enlazar.
19. Haga clic en Guardar.
20. Cierre la página.
21. Cierre la página.
22. Cierre la página.
23. Cierre la página.

## <a name="run-format-using-the-adjusted-model-mapping"></a>Ejecutar formato con la asignación de modelo ajustado
1. Vaya a Gestión de efectivo y de banco > Cuentas bancarias > Cuentas bancarias.
2. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Cuenta bancaria, con un valor de 'USMF OPER'.
3. En el panel de acciones, haga clic en Configurar.
4. Haga clic en Comprobar.
5. Haga clic en Imprimir prueba.
6. Haga clic en Aceptar
    * Revise el resultado creado. Tenga en cuenta que la imagen de los datos adjuntos de la gestión de documentos se muestra como la firma de una persona autorizada.  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a>Use el documento de MS Word como plantilla en el formato importado
1. Cierre la página.
2. Cierre la página.
3. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
4. En el árbol, expanda "Modelo para cheques".
5. En el árbol, seleccione "Modelo para cheques\Formato de impresión de cheques".
6. Haga clic en Diseñador.
7. Haga clic en Archivos adjuntos.
8. Haga clic Eliminar.
9. Haga clic en Sí.
10. Haga clic en Nuevo.
11. Haga clic en Archivo.
    * Haga clic en Examinar y seleccione el archivo “Cheque template Word.docx" descargado previamente.  
12. Cierre la página.
13. En el campo Plantilla, especifique o seleccione un valor.
14. Haga clic en Guardar.
15. Cierre la página.
16. Haga clic en Editar.
17. Seleccione Sí en el campo Borrador de ejecución.
18. Cierre la página.
19. Vaya a Gestión de efectivo y de banco > Cuentas bancarias > Cuentas bancarias.
20. Use un filtro rápido para filtrar por el campo Cuenta bancaria, por el valor ''USMF OPER".
21. Haga clic en Comprobar.
22. Haga clic en Imprimir prueba.
23. Haga clic en Aceptar
    * Revise el resultado creado. Tenga en cuenta que el resultado se ha generado como documento de MS Word con las imágenes incrustadas que presentan el logotipo de la empresa, la firma de una persona autorizada y el texto seleccionado de la marca de agua.  


