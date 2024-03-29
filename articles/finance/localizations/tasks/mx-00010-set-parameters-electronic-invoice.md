---
title: MX-00010 Definir parámetros para una factura electrónica
description: Este procedimiento muestra cómo configurar una factura electrónica y la cuenta de PAC para obtener la aprobación y el sello digital.
author: AdamTrukawka
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: EInvoiceCFDIPACTable_MX, EInvoiceParameters_MX, DigitalCertificateLookup
ms.openlocfilehash: f01c0600d4210b6abdc1e7b3c4080e0d3c6d7dbf
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273732"
---
# <a name="mx-00010-set-parameters-for-an-electronic-invoice"></a>MX-00010 Definir parámetros para una factura electrónica

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo configurar una factura electrónica y la cuenta de PAC para obtener la aprobación y el sello digital. Este procedimiento solo se puede completar con entidades jurídicas con dirección principal en México. Este procedimiento se creó con los datos de demostración de la empresa MXMF. Los certificados que se utilizan para cifrar el mensaje XML deben haberse instalado anteriormente, y el archivo XSD de esquema se debe haber copiado en la aplicación también antes de comenzar este procedimiento.


## <a name="set-up-pac-accounts"></a>Configuración de cuentas de PAC
1. Vaya a Clientes > Facturas > Facturas electrónicas > Cuentas de PAC.
2. Haga clic en Nuevo.
3. En el campo Cuenta de PAC, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. En el campo Número de RFC, escriba el número de RFC de su proveedor de PAC.
6. Haga clic en Guardar.
7. Haga clic en Nuevo.
8. En el campo del entorno, seleccione el tipo de entorno desde dónde se ejecutan los servicios web.
    * Consulte con su proveedor de PAC sobre la disponibilidad de entornos de prueba y producción.  
9. En el campo Dirección de Internet, escriba la dirección del servicio web de su proveedor de PAC.
10. En el campo Servicio web, seleccione Solicitar sello.
    * El servicio web de solicitud de sello se utiliza para solicitar la firma digital.  
11. En el campo Nombre del método, especifique el nombre de la operación que se usa para solicitar la aprobación de una factura electrónica.
    * Póngase en contacto con su proveedor de PAC para obtener el nombre de la operación.  
12. Haga clic en Nuevo.
13. En el campo Entorno, seleccione el tipo de entorno desde dónde se ejecutan los servicios web.
    * Consulte con su proveedor de PAC sobre la disponibilidad de entornos de prueba y producción.  
14. En el campo Dirección de Internet, escriba la dirección de los servicios web de su proveedor de PAC.
15. En el campo Servicio web, seleccione Cancelar.
16. En el campo Nombre del método, especifique el método usado para la operación de cancelación.
    * Este es el nombre de la operación que se usa en el proceso de servicios web para cancelar una factura electrónica. Póngase en contacto con su proveedor de PAC para obtener el nombre de la operación.  

## <a name="set-up-electronic-invoice-parameters"></a>Configuración de parámetros de facturas electrónicas
1. Vaya a Clientes > Facturas > Facturas electrónicas > Parámetros de facturas electrónicas.
2. Active o desactive la casilla Habilitar CFDI (factura electrónica).
    * Para esta tarea, cambie el control deslizante a Sí.  
3. En el campo Certificado, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Versión CFDI, seleccione una opción.
    * Puede comprobar la versión disponible actual del esquema CFDI en el sitio web de la administración pública.  
6. En el campo Archivo de esquema XML de CFDI, especifique la ruta y el nombre de archivo de esquema XML de CFDI.
7. En el campo Entorno, seleccione una opción.
8. En el campo Certificado PAC, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, busque y seleccione el registro deseado.
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. En el campo Cuenta de PAC, haga clic en el botón desplegable para abrir la búsqueda.
12. En la lista, haga clic en el vínculo de la fila seleccionada.
13. Active o desactive la casilla Enviar correo.
14. En el campo Id. de correo electrónico, haga clic en el botón desplegable para abrir la búsqueda.
15. En la lista, haga clic en el vínculo de la fila seleccionada.
16. Active o desactive la casilla Enviar archivo de informe: PDF.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
