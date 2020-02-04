---
title: Aktivieren der Remoteanrufsteuerung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190f4e56a291ce48b5cd18b2dcd3e1b3461e3d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>Aktivieren der Remoteanrufsteuerung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Die Remote Anrufsteuerung ermöglicht Benutzern, Ihre Desktop-PBX-Telefone (Private Branch Exchange) mithilfe von lync Server 2013 zu steuern. Wenn Sie die Remoteanrufsteuerung in ihrer Legacyumgebung bereitgestellt haben und lync Server 2013 migrieren möchten, müssen Sie die folgenden Aufgaben ausführen:

1.  Installieren Sie ein SIP/CSTA-Gateway, und konfigurieren Sie es für die Kommunikation mit Ihrer Telefonanlage. Sie müssen diesen Schritt ausführen, wenn Sie den lync Server 2013-Pilot Pool bereitstellen.

2.  Nachdem Sie Ihre Topologie zusammengeführt und ihre Richtlinien und Einstellungen migriert haben, konfigurieren Sie lync Server 2013 so, dass CSTA-Anforderungen an das SIP/CSTA-Gateway weitergeleitet werden. Dieser Schritt ist ein manueller Schritt, der der automatisierten Migration folgt. Gehen Sie wie folgt vor, um Routing für CSTA-Anforderungen zu konfigurieren:
    
      - Entfernen Sie Legacy Authorized Host-Einträge (so genannte *Trusted Server-Einträge* in lync Server 2013). Wenn Sie Benutzer aus Ihrer Legacy Bereitstellung migrieren, müssen Sie sicherstellen, dass Sie alle vorhandenen autorisierten Hosteinträge entfernen, die Sie für das SIP/CSTA-Gateway erstellt haben, bevor Sie neue Einträge für vertrauenswürdige Anwendungen im lync Server 2013-Pilot Pool konfigurieren. Details zum Entfernen von Legacy autorisierten Hosteinträgen finden Sie unter [Entfernen eines autorisierten Hosteintrags](remove-an-authorized-host-entry.md).
    
      - Konfigurieren Sie eine statische Route für die Remoteanrufsteuerung. Sie können eine statische Route für einzelne Pools konfigurieren, die die Remoteanrufsteuerung unterstützen sollen, oder Sie können eine globale statische Route so konfigurieren, dass jeder Pool, der nicht mit einer statischen Route auf Poolebene konfiguriert ist, die globale statische Route verwendet. Details zum Konfigurieren der statischen Route finden Sie unter [Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in der Bereitstellungsdokumentation.
    
      - Konfigurieren Sie einen Eintrag für die vertrauenswürdige Anwendung für die Remoteanrufsteuerung in jedem Pool, für den Sie die Remoteanrufsteuerung unterstützen möchten. Details zum Konfigurieren eines Eintrags für vertrauenswürdige Anwendungen finden Sie unter [Konfigurieren eines Eintrags für eine vertrauenswürdige Anwendung für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in der Bereitstellungsdokumentation.

3.  Wenn Sie ein SIP/CSTA-Gateway bereitgestellt haben, das Transmission Control Protocol (TCP) zum Herstellen einer Verbindung mit lync Server 2013 verwendet, definieren Sie die IP-Adresse des Gateways im Topologie-Generator. Details zum Definieren der IP-Adresse finden Sie unter [Definieren einer SIP/CSTA-Gateway-IP-Adresse in lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in der Bereitstellungsdokumentation.

4.  Konfigurieren Sie lync 2013-Benutzer für die Remoteanrufsteuerung, indem Sie die Remoteanrufsteuerung aktivieren und einen URI (Uniform Resource Identifier) und einen Leitungs-URI zuweisen. Wenn Sie Benutzer aus Ihrer Legacy Bereitstellung zu lync Server 2013 migrieren, werden die Einstellungen für die Remoteanrufsteuerung zusammen mit den anderen Benutzereinstellungen migriert.

5.  Wenn Sie die Normalisierungsregeln für Adressbuch-Telefonnummern in Ihrer Legacy Bereitstellung angepasst haben, müssen Sie nach Abschluss der automatisierten Migration von Richtlinien und Einstellungen einige manuelle Aufgaben ausführen, um die angepassten Normalisierungsregeln zu migrieren. Wenn Sie die Normalisierungsregeln nicht angepasst haben, wird das Adressbuch zusammen mit der restlichen Topologie migriert. Details zum manuellen Migrieren von benutzerdefinierten Normalisierungsregeln finden Sie unter [Migrieren des Adressbuchs](migrate-address-book_1.md).

</div>

<span> </span>

</div>

</div>

</div>

