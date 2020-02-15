---
title: 'Lync Server 2013: Bereitstellungsaufgaben für die Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf2366c56c0e749aff208b8471d1db76a1c0ba35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Bereitstellungsaufgaben für die Remoteanrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

In diesem Thema werden die Bereitstellungsaufgaben beschrieben, die Sie ausführen müssen, um die Remoteanrufsteuerung für Benutzer in ihrer lync Server Umgebung zu aktivieren.

<div>


> [!NOTE]  
> Wenn Sie Benutzer migrieren, die zuvor für die Remoteanrufsteuerung in Microsoft Office Communicator 2007 R2 aktiviert wurden, müssen Sie eine zusätzliche Bereitstellungsaufgabe ausführen, bevor Sie mit der Durchführung der in diesem Thema beschriebenen Bereitstellungsaufgaben für die Remoteanrufsteuerung beginnen. Während des Migrationsprozesses für lync Server müssen Einträge für vertrauenswürdige Anwendungen (zuvor als <EM>autorisierte Hosteinträge</EM>bezeichnet) mithilfe der Office Communications Server 2007 R2 Verwaltungstools entfernt werden, je nach Bedarf.<BR>Ausführliche Informationen zum Entfernen von autorisierten Hosts finden Sie unter <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Entfernen eines autorisierten Legacyhosts in lync Server 2013 (optional)</A>.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>Schritt 1: Installieren und Konfigurieren des SIP/CSTA-Gateways zur Kommunikation mit der Nebenstellenanlage

Sie müssen mindestens ein SIP/CSTA-Gateway installieren, das eine Verbindung mit lync Server und der vorhandenen PBX-Anlage (Private Branch Exchange) in Ihrer Umgebung herstellen kann, um den Benutzern Funktionen zur Remoteanrufsteuerung zur Verfügung zu stellen. Ein SIP/CSTA-Gateway ist ein Gateway zwischen SIP und einer computergestützten Telekommunikationsanwendung (Computer-Supported Telecommunications Application, CSTA). Unabhängig davon, ob Sie mehrere Gateways oder nur ein Gateway installieren, kann jeder Benutzer nur für ein Gateway oder eine Nebenstellenanlage konfiguriert werden. Wenn die vorhandene Nebenstellenanlage keine SIP/CSTA-Schnittstelle aufweist, müssen Sie ein SIP/CSTA-Gateway bereitstellen, das die Nebenstellenanlage unterstützen kann – einschließlich Unterstützung für proprietäre herstellerspezifische Signalprotokolle der Nebenstellenanlage. Wenden Sie sich an den jeweiligen Hersteller, um detaillierte Informationen zu den verfügbaren Funktionen zu erhalten.

Wenn Sie bereit sind, ein SIP/CSTA-Gateway bereitzustellen, das in lync Server für die Remoteanrufsteuerung integriert werden kann, konsultieren Sie auch Ihren Gateway-Anbieter oder die Gateway-Dokumentation des Anbieters in Bezug auf die für das Gateway erforderliche Syntax für die folgenden Informationen:

  - Anschlussserver-URI des Gateways

  - Anschluss-URI für Benutzer, die dem Gateway zugewiesen werden

Die oben genannten Einstellungen werden während der Benutzerkonfiguration benötigt und müssen wie vom Gateway erwartet angegeben werden, um ein ordnungsgemäßes Routing und eine ordnungsgemäße Verbindungsherstellung mit der Nebenstellenanlage zu gewährleisten.

Weitere Informationen finden Sie unter Anbieter auf der Website "Microsoft Unified Communications Open Interoperability [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)Program" unter.

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>Schritt 2: Konfigurieren von lync Server zum Weiterleiten von CSTA-Anforderungen an das SIP/CSTA-Gateway

Sie müssen statische Routen in lync Server Pools an die Zieladresse (Server-URI) aller SIP/CSTA-Gateways in Ihrer Bereitstellung erstellen, an die Sie Remote Anruf Steuerungsanforderungen weiterleiten möchten. Sie müssen außerdem für jede Zieladresse einen Eintrag für eine vertrauenswürdige Anwendung erstellen. Wenn Sie das Gateway als vertrauenswürdige Anwendung festlegen, erhält es einen vertrauenswürdigen Status, der als Teil der lync Server Umgebung ausgeführt wird, obwohl es von einem Drittanbieter entwickelt wurde (und ausgeführt wird, was als *externer Dienst* bezeichnet wird, da es sich um einen Dienst handelt, der kein integrierter Bestandteil des Produkts ist). Wenn lync Server eine Verbindung mit dem SIP/CSTA-Gateway über eine TCP-Verbindung (Transmission Control Protocol) anstelle einer TLS-Verbindung (Transport Layer Security) herstellen, müssen Sie auch die Gateway-IP-Adresse mithilfe des Topologie-Generators definieren.

Ausführliche Informationen zum Konfigurieren von statischen Routen finden Sie unter [Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Ausführliche Informationen zum Konfigurieren von Einträgen für vertrauenswürdige Anwendungen finden Sie unter [Konfigurieren eines Eintrags für eine vertrauenswürdige Anwendung für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Ausführliche Informationen zum Definieren einer IP-Adresse für SIP/CSTA-Gateways im Topologie-Generator finden Sie unter [define a SIP/CSTA Gateway IP Address in lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>Schritt 3: Konfigurieren von lync-Benutzern für die Remote Anrufsteuerung

Nachdem Benutzer für lync Server aktiviert wurden, können Sie lync Server-Systemsteuerung oder lync Server-Verwaltungsshell verwenden, um Sie für die Remoteanrufsteuerung zu aktivieren. Sie weisen jedem Benutzer während dieses Bereitstellungsschritts einen Anschlussserver-URI und einen Anschluss-URI zu. Der Anschlussserver-URI ist der SIP-URI des SIP/CSTA-Gateways, das Sie dem Benutzer zuweisen möchten. Der Anschluss-URI ist die eindeutige Rufnummer, die dem Benutzer zugewiesen ist.

Ausführliche Informationen zum Konfigurieren von Benutzern für die Remoteanrufsteuerung finden Sie unter [Aktivieren von lync-Benutzern für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>Schritt 4: Definieren der Normalisierungsregeln für Lync Server-Rufnummern

In Szenarien mit Remoteanrufsteuerung verwendet lync Server Telefonnummern-Normalisierungsregeln zum Umwandeln von Rufnummern, die vom SIP/CSTA-Gateway in das E. 164-Format gesendet werden. Telefonnummern müssen in diesem standardisierten Format vorliegen, damit bestimmte Funktionen für die Remoteanrufsteuerung ordnungsgemäß funktionieren. Die Remote Anrufsteuerung verwendet die gleichen Normalisierungsregeln für Telefonnummern, die Sie für die Normalisierung der Adressbuchdienst-Telefonnummern konfigurieren, die sich von den für Enterprise-VoIP verwendeten Telefonnummern Normalisierungsregeln unterscheiden.

Ausführliche Informationen dazu, wie die Remoteanrufsteuerung Telefonnummern-Normalisierungsregeln verwendet, finden Sie unter [Remoteanrufsteuerung und Normalisierung der Telefonnummer in lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Ausführliche Informationen zu Normalisierungsregeln für Telefonnummern für den Adressbuchdienst finden Sie unter [Verwalten des Adressbuchdiensts in lync Server 2013](lync-server-2013-administering-the-address-book-service.md) Thema in der Betriebsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

