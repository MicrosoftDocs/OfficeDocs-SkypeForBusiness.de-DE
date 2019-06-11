---
title: 'Lync Server 2013: Bereitstellungsaufgaben für die Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63c9cba56ccedf3559b1e9f1da1ee58cc03e195
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Bereitstellungsaufgaben für die Remoteanrufsteuerung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

In diesem Thema werden die Bereitstellungsaufgaben beschrieben, die Sie ausführen müssen, um die Remoteanrufsteuerung für Benutzer in ihrer lync Server-Umgebung zu aktivieren.

<div>


> [!NOTE]  
> Wenn Sie Benutzer migrieren, die zuvor für die Remoteanrufsteuerung in Microsoft Office Communicator 2007 R2 aktiviert wurden, müssen Sie eine zusätzliche Bereitstellungsaufgabe ausführen, bevor Sie mit der Durchführung der in diesem Thema beschriebenen Bereitstellungsaufgaben für Remoteanrufsteuerung beginnen. Während des Migrationsvorgangs zu lync Server müssen vertrauenswürdige Anwendungs Einträge (vormals als <EM>autorisierte Hosteinträge</EM>bezeichnet) mithilfe der Verwaltungstools von Office Communications Server 2007 R2 entfernt werden.<BR>Details zum Entfernen autorisierter Hosts finden Sie unter <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Entfernen eines autorisierten Legacyhosts in lync Server 2013 (optional)</A>.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>Schritt 1: Installieren und Konfigurieren des SIP/CSTA-Gateways für die Kommunikation mit Ihrer Telefonanlage

Sie müssen mindestens ein SIP/CSTA-Gateway installieren, das eine Verbindung mit lync Server und der vorhandenen PBX-Anlage (Private Branch Exchange) in Ihrer Umgebung herstellen kann, um Ihren Benutzern Funktionen zur Remoteanrufsteuerung zur Verfügung zu stellen. Ein SIP/CSTA-Gateway ist ein Gateway zwischen SIP und einer computergestützten Telekommunikations Anwendung (CSTA). Unabhängig davon, ob Sie mehrere Gateways oder nur eine installieren, kann jeder Benutzer mit nur einem Gateway oder einer Telefonanlage konfiguriert werden. Wenn Ihre vorhandene Telefonanlage keine SIP-CSTA-Schnittstelle aufweist, stellen Sie sicher, dass Sie ein SIP/CSTA-Gateway bereitstellen, das die Telefonanlage unterstützt, einschließlich der Unterstützung für herstellerspezifische Signalisierungsprotokolle für proprietäre Telefonanlagen. Detaillierte Informationen zu den Funktionen finden Sie in den einzelnen Anbietern direkt.

Wenn Sie bereit sind, ein SIP/CSTA-Gateway bereitzustellen, das in lync Server für die Remoteanrufsteuerung integriert werden kann, konsultieren Sie auch Ihren Gateway-Anbieter oder die Gateway-Dokumentation des Anbieters hinsichtlich der Syntax, die das Gateway für die folgenden Informationen benötigt:

  - Leitungsserver-URI des Gateways

  - Leitungs-URI für Benutzer, die dem Gateway zugewiesen werden

Die vorherigen Einstellungen sind während der Benutzerkonfiguration erforderlich und müssen vom Gateway so angegeben werden, dass es ordnungsgemäß weitergeleitet und mit der Telefonanlage verbunden werden kann.

Sie können auf der Website Microsoft Unified Communications Open Interoperability Program unter [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)auf Anbieter verweisen.

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>Schritt 2: Konfigurieren von lync Server zum Weiterleiten von CSTA-Anforderungen an das SIP/CSTA-Gateway

Sie müssen statische Routen in lync Server-Pools an die Zieladresse (Server-URI) aller SIP/CSTA-Gateways in Ihrer Bereitstellung erstellen, an die Sie Remote Anruf Steuerungsanforderungen weiterleiten möchten. Sie müssen auch einen Eintrag für vertrauenswürdige Anwendungen erstellen, der den einzelnen Zieladressen entspricht. Wenn Sie das Gateway als vertrauenswürdige Anwendung festgelegt haben, wird der vertrauenswürdige Status für die Ausführung als Teil der lync Server-Umgebung gewährt, obwohl es von einem Drittanbieter entwickelt wurde (und den als *externen Dienst* bezeichneten Dienst ausführt, da es sich um einen Dienst handelt, der kein integrierter Teil des Produkts). Wenn lync Server eine Verbindung mit dem SIP/CSTA-Gateway über eine TCP-Verbindung (Transmission Control Protocol) anstelle einer TLS-Verbindung (Transport Layer Security) herstellen soll, müssen Sie auch die Gateway-IP-Adresse mithilfe von Topology Builder definieren.

Details zum Konfigurieren von statischen Routen finden Sie unter [Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Details zum Konfigurieren von Einträgen für vertrauenswürdige Anwendungen finden Sie unter [Konfigurieren eines vertrauenswürdigen Anwendungseintrags für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Details zum Definieren einer IP-Adresse für SIP/CSTA-Gateways im Topologie-Generator finden Sie unter [Definieren einer IP-Adresse für SIP/CSTA-Gateways in lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>Schritt 3: Konfigurieren von lync-Benutzern für die Remote Anrufsteuerung

Nachdem Benutzer für lync Server aktiviert wurden, können Sie die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell verwenden, um Sie für die Remoteanrufsteuerung zu aktivieren. Während dieses bereitstellungsschritts weisen Sie jedem Benutzer einen Leitungsserver-URI und einen Leitungs-URI zu. Der URI des Leitungs Servers ist der SIP-URI des SIP/CSTA-Gateways, das Sie dem Benutzer zuweisen möchten. Der Leitungs-URI ist die eindeutige Telefonnummer, die dem Benutzer zugewiesen ist.

Details zum Konfigurieren von Benutzern für die Remoteanrufsteuerung finden Sie unter [Aktivieren von lync-Benutzern für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>Schritt 4: Definieren der Normalisierungsregeln für lync Server-Telefonnummern

In Szenarien für die Remoteanrufsteuerung verwendet lync Server Telefonnummern-Normalisierungsregeln, um Telefonnummern zu konvertieren, die vom SIP/CSTA-Gateway zum E. 164-Format empfangen werden. Telefonnummern müssen in diesem standardisierten Format vorliegen, damit bestimmte Funktionen für die Remoteanrufsteuerung ordnungsgemäß funktionieren. Die Remote Anrufsteuerung verwendet die gleichen Regeln für die Telefonnummernnormalisierung, die Sie für die Normalisierung der Telefonnummern für den Adressbuchdienst konfigurieren, die sich von den für Enterprise-VoIP verwendeten Regeln für die Telefonnummer unterscheiden.

Ausführliche Informationen dazu, wie die Remoteanrufsteuerung Telefonnummern-Normalisierungsregeln verwendet, finden Sie unter [Remoteanrufsteuerung und Normalisierung der Telefonnummern in lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Details zu den Normalisierungsregeln für Telefonnummern für den Adressbuchdienst finden Sie unter [Verwalten des Adressbuchdiensts in lync Server 2013](lync-server-2013-administering-the-address-book-service.md) in der Betriebsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

