---
title: Aktivieren der Remoteanrufsteuerung
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc382eea0f59719432e11731c6b82c393f751b16
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>Aktivieren der Remoteanrufsteuerung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Die Remote Anrufsteuerung ermöglicht Benutzern das Steuern ihrer PBX-Telefone (Desktop Private Branch Exchange) mithilfe von lync Server 2013. Wenn Sie die Remoteanrufsteuerung in ihrer Vorgänger Umgebung bereitgestellt haben und diese lync Server 2013 migrieren möchten, müssen Sie die folgenden Aufgaben ausführen:

1.  Installieren Sie ein SIP/CSTA-Gateway, und konfigurieren Sie es für die Kommunikation mit dem Festnetztelefon. Sie müssen diesen Schritt ausführen, wenn Sie Ihren lync Server 2013 Pilot-Pool bereitstellen.

2.  Nachdem Sie Ihre Topologie zusammengeführt und ihre Richtlinien und Einstellungen migriert haben, konfigurieren Sie lync Server 2013, um CSTA-Anforderungen an das SIP/CSTA-Gateway weiterzuleiten. Es handelt sich hierbei um einen manuellen Schritt nach der automatischen Migration. Führen Sie zur Konfiguration des Routings für CSTA-Anforderungen Folgendes aus:
    
      - Entfernen Sie Legacy-Autorisierungs Hosteinträge (als *vertrauenswürdige Server Einträge* in lync Server 2013 bezeichnet). Wenn Sie Benutzer von Ihrer Legacy Bereitstellung migrieren, müssen Sie sicherstellen, dass Sie alle vorhandenen autorisierten Hosteinträge entfernen, die Sie für das SIP/CSTA-Gateway erstellt haben, bevor Sie neue Einträge für vertrauenswürdige Anwendungen im lync Server 2013 Pilot-Pool konfigurieren. Ausführliche Informationen zum Entfernen von autorisierten Legacy-Hosteinträgen finden Sie unter [Entfernen eines autorisierten Hosteintrags](remove-an-authorized-host-entry.md).
    
      - Konfigurieren einer statischen Route für die Remoteanrufsteuerung. Sie können eine statische Route für einzelne Pools konfigurieren, die die Remoteanrufsteuerung unterstützen sollen, oder Sie können eine globale statische Route konfigurieren, sodass für jeden Pool, der nicht mit einer statischen Route auf Poolebene konfiguriert ist, die globale statische Route verwendet wird. Ausführliche Informationen zum Konfigurieren der statischen Route finden Sie unter [Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in der Bereitstellungsdokumentation.
    
      - Konfigurieren Sie einen Eintrag einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in jedem Pool, der die Remoteanrufsteuerung unterstützen soll. Ausführliche Informationen zum Konfigurieren eines Eintrags für eine vertrauenswürdige Anwendung finden Sie unter [Konfigurieren eines Eintrags für eine vertrauenswürdige Anwendung für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in der Bereitstellungsdokumentation.

3.  Wenn Sie ein SIP/CSTA-Gateway bereitgestellt haben, das TCP (Transmission Control Protocol) zum Herstellen einer Verbindung mit lync Server 2013 verwendet, definieren Sie die IP-Adresse des Gateways im Topologie-Generator. Ausführliche Informationen zum Definieren der IP-Adresse finden Sie unter [define a SIP/CSTA Gateway IP Address in lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in der Bereitstellungsdokumentation.

4.  Konfigurieren Sie lync 2013 Benutzer für die Remoteanrufsteuerung, indem Sie die Remoteanrufsteuerung aktivieren und einen Anschlussserver-URI (Uniform Resource Identifier) und einen Anschluss-URI zuweisen. Wenn Sie Benutzer aus Ihrer Legacy Bereitstellung in lync Server 2013 migrieren, werden die Einstellungen für die Remoteanrufsteuerung zusammen mit den anderen Benutzereinstellungen migriert.

5.  Wenn Sie die Normalisierungsregeln für Rufnummern im Adressbuch in Ihrer Vorversionsbereitstellung angepasst haben, müssen Sie nach der automatischen Migration der Richtlinien und Einstellungen einige manuelle Aufgaben durchführen, um die angepassten Normalisierungsregeln zu migrieren. Wenn Sie die Normalisierungsregeln nicht angepasst haben, wird das Adressbuch mit der restlichen Topologie migriert. Ausführliche Informationen über die manuelle Migration benutzerdefinierter Normalisierungsregeln finden Sie unter [Migrate Address Book](migrate-address-book_1.md).

</div>

<span> </span>

</div>

</div>

</div>

