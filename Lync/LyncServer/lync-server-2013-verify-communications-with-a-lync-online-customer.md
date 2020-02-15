---
title: 'Lync Server 2013: Überprüfen der Kommunikation mit einem lync Online-Kunden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dffbb5d8a0e49e19c0fa5487a4af05b7e7f0155
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>Überprüfen der Kommunikation mit einem lync Online Kunden in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-08_

Damit lync-Benutzer in Ihrer Organisation mit Benutzern eines Microsoft lync Online 2010-Kunden kommunizieren können, müssen Sie die folgenden Schritte ausgeführt haben:

  - Erfüllt alle Voraussetzungen. Dies umfasst die Bereitstellung Ihrer internen und Edgeserver, die Aktivierung der Verbundunterstützung für Ihre Organisation und das Einrichten von Benutzerkonten. Ausführliche Informationen finden Sie unter [Voraussetzungen für die Partnerverbund mit einem lync Online Kunden in lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).

  - Konfigurierte Domänenzugriffs Unterstützung in ihrer internen Bereitstellung. Dies umfasst das Erstellen eines Eintrags eines Host Anbieters und das Konfigurieren Ihrer Bereitstellung, um den Zugriff aus der Domäne des lync Online Kunden zuzulassen. Ausführliche Informationen finden Sie unter [Konfigurieren der Verbundunterstützung für eine lync Online Domäne in lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).

  - Konfigurieren Sie Ihre Benutzerkonten für die Unterstützung des Verbunds. Ausführliche Informationen finden Sie unter [Konfigurieren des Benutzerzugriffs für einen Partnerverbund mit einem lync Online-Kunden in lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).

Nachdem Sie alle diese Schritte ausgeführt haben und der Administrator des lync Online 2010-Kunden die gesamte Konfiguration seiner Online Dienste vervollständigt, um den Verbund mit Ihrer Organisation zu unterstützen, überprüfen Sie die Kommunikation durch Testen der Kommunikation zwischen einem internen Benutzer in Ihrer Organisation und ein Benutzer des lync Online Kunden. Wenn die Kommunikation nicht erfolgreich ist, verwenden Sie das Protokollierungs Tool aus dem Edgeserver, um Protokoll-und Ablaufverfolgungsdateien aufzuzeichnen, um das Problem zu beheben. Ausführliche Informationen zur Verwendung des Protokollierungstools finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md) in der Betriebsdokumentation. Ausführliche Informationen zum Protokollierungstool finden Sie in der Dokumentation zum lync Server 2010 Protokollierungstool in der [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)TechNet-Bibliothek unter.

</div>

<span> </span>

</div>

</div>

</div>

