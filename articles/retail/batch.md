<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="batch.md" target-language="es-ES">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>batch.e70006.4456fc3d5bc4547fa8211642b11ca6df455fa187.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>4456fc3d5bc4547fa8211642b11ca6df455fa187</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>aec1dcd44274e9b8d0770836598fde5533b7b569</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/03/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\batch.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Improved handling of batch-tracked items</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Control administrado de artículos con seguimiento por lotes</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the improvements that have been made to the handling of batches for batch-tracked items during the Retail statement posting process.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">En este tema se describe las mejoras que se han realizado al control de los lotes para los artículos con seguimiento por lotes durante el proceso de registro de extracto comercial.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Improved handling of batch-tracked items</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Control administrado de artículos con seguimiento por lotes</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>In Microsoft Dynamics 365 for Retail Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">En el punto de venta (PDV) de Microsoft Dynamics 365 for Retail, los números de lotes no se pueden obtener para los artículos con seguimiento por lotes en el momento de la venta.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Sin embargo, para las configuraciones específicas, cuando se registran las ventas en las sedes a través del registro de extractos o pedidos de clientes, el sistema de Microsoft Dynamics espera que existan números de lotes válidos para artículos con seguimiento por lotes y que se usarán durante el proceso de facturación.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Si hay números de lotes válidos disponibles para los productos, el proceso de facturación de pedidos de clientes y el proceso de facturación de pedidos de ventas del registro de extractos los usan.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">De lo contrario, el proceso de facturación de pedidos de clientes no puede registrar y el usuario del PDV recibe un mensaje de error.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Statement posting then goes into an error state.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">El registro de extractos entra a continuación en un estado de error.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>This error state occurs even when negative inventory has been turned on for the products.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Este estado de error se produce cuando se ha activado inventario negativo para los productos.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Improvements that have been made in Microsoft Dynamics for Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Las mejoras que se han realizado en Microsoft Dynamics for Retail versión 10.0.4 y posteriores ayudan a garantizar que, cuando se activa inventario negativo para artículos con seguimiento por lotes, no se bloquean la facturación de pedidos de clientes y la facturación de pedidos de ventas a través del registro de extractos para esos artículos si el inventario es 0 (cero) o un número de lote no está disponible.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">La nueva funcionalidad usa un id. de lote predeterminado para las líneas de ventas cuando los números de lotes no están disponibles.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>To define the default batch ID that is used for customer orders, on the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Customer orders<ept id="p2">**</ept> tab, on the <bpt id="p3">**</bpt>Order<ept id="p3">**</ept> FastTab, set the <bpt id="p4">**</bpt>Default batch id<ept id="p4">**</ept> field.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Para definir el id. de lote predeterminado que se usa para pedidos de cliente, en la página <bpt id="p1">**</bpt>Parámetros comerciales<ept id="p1">**</ept>, en la pestaña <bpt id="p2">**</bpt>Pedidos de cliente<ept id="p2">**</ept>, en la ficha desplegable <bpt id="p3">**</bpt>Pedido<ept id="p3">**</ept>, establezca el campo de <bpt id="p4">**</bpt>id. de lote predeterminado<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>To define the default batch ID that is used for sales order invoicing through statement posting, on the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Posting<ept id="p2">**</ept> tab, on the <bpt id="p3">**</bpt>Inventory update<ept id="p3">**</ept> FastTab, set the <bpt id="p4">**</bpt>Default batch id<ept id="p4">**</ept> field.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Para definir el id. de lote predeterminado que se usa para facturación de pedidos de ventas a través del registro de extractos, en la página <bpt id="p1">**</bpt>Parámetros comerciales<ept id="p1">**</ept>, en la pestaña <bpt id="p2">**</bpt>Registro<ept id="p2">**</ept>, en la ficha desplegable <bpt id="p3">**</bpt>Actualización del inventario<ept id="p3">**</ept>, establezca el campo de <bpt id="p4">**</bpt>id. de lote predeterminado<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Esta funcionalidad solo está disponible cuando el almacenamiento avanzado está activado para los artículos y el almacén de la tienda específicos.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">En una versión posterior, la funcionalidad también se admitirá para escenarios donde no se use la gestión avanzada de almacenes.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>