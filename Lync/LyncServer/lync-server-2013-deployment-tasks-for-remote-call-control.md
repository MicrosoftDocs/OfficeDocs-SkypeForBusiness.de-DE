---
title: 'Lync Server 2013: Bereitstellungsaufgaben für die Remoteanrufsteuerung'
TOCTitle: Bereitstellungsaufgaben für die Remoteanrufsteuerung
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558624(v=OCS.15)
ms:contentKeyID: 49293392
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellungsaufgaben für die Remoteanrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Im vorliegenden Thema werden die Bereitstellungsaufgaben beschrieben, die Sie zum Aktivieren der Remoteanrufsteuerung (Remote Call Control, RCC) für Benutzer in Ihrer Lync Server-Umgebung ausführen müssen.


> [!NOTE]
> Wenn Sie Benutzer migrieren, die zuvor für die Remoteanrufsteuerung in Microsoft Office Communicator 2007 R2 oder Lync Server aktiviert waren, müssen Sie zusätzliche Bereitstellungsaufgaben ausführen, bevor Sie mit den Bereitstellungsaufgaben für die Remoteanrufsteuerung beginnen können, die in diesem Thema beschrieben werden. Während der Migration zu nm-ocs-14-2nd müssen Einträge für vertrauenswürdige Anwendungen (vormals als <EM>Einträge für autorisierte Hosts</EM> bezeichnet) mithilfe der Verwaltungstools für Office Communications Server 2007 R2 oder nm-ocs-13-2nd entfernt werden.<BR>Ausführliche Informationen zum Entfernen von Einträgen für autorisierte Hosts finden Sie unter <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Entfernen eines autorisierten Legacyhosts in Lync Server 2013 (optional)</A>.



## Schritt 1: Installieren und Konfigurieren des SIP/CSTA-Gateways zur Kommunikation mit der Nebenstellenanlage

Sie müssen mindestens ein SIP/CSTA-Gateway installieren, das sich sowohl mit Lync Server als auch mit der vorhandenen Nebenstellenanlage (Private Branch Exchange, PBX) in Ihrer Umgebung verbinden kann, um Funktionen der Remoteanrufsteuerung für Ihre Benutzer bereitzustellen. Ein SIP/CSTA-Gateway ist ein Gateway zwischen SIP und einer computergestützten Telekommunikationsanwendung (Computer-Supported Telecommunications Application, CSTA). Unabhängig davon, ob Sie mehrere Gateways oder nur ein Gateway installieren, kann jeder Benutzer nur für ein Gateway oder eine Nebenstellenanlage konfiguriert werden. Wenn die vorhandene Nebenstellenanlage keine SIP/CSTA-Schnittstelle aufweist, müssen Sie ein SIP/CSTA-Gateway bereitstellen, das die Nebenstellenanlage unterstützen kann - einschließlich Unterstützung für proprietäre herstellerspezifische Signalprotokolle der Nebenstellenanlage. Wenden Sie sich an den jeweiligen Hersteller, um detaillierte Informationen zu den verfügbaren Funktionen zu erhalten.

Wenn Sie zur Implementierung eines SIP/CSTA-Gateways bereit sind, das zum Bereitstellen der Remoteanrufsteuerung in Lync Server integriert werden kann, erkundigen Sie sich beim Gatewayhersteller oder prüfen Sie anhand der Gatewaydokumentation, welche Syntax für die folgenden Informationen erforderlich ist:

  - Anschlussserver-URI des Gateways

  - Anschluss-URI für Benutzer, die dem Gateway zugewiesen werden

Die oben genannten Einstellungen werden während der Benutzerkonfiguration benötigt und müssen wie vom Gateway erwartet angegeben werden, um ein ordnungsgemäßes Routing und eine ordnungsgemäße Verbindungsherstellung mit der Nebenstellenanlage zu gewährleisten.

Informationen zu Herstellern finden Sie auf der Microsoft-Webseite " Unified Communications Open Interoperability Program \\endash Lync Server" unter <http://go.microsoft.com/fwlink/?linkid=203309>.

## Schritt 2: Konfigurieren von Lync Server für das Routing von CSTA-Anforderungen an das SIP/CSTA-Gateway

Sie müssen für Lync Server-Pools statische Routen zur Zieladresse (Server-URI) aller SIP/CSTA-Gateways in Ihrer Bereitstellung erstellen, an die Sie Anforderungen zur Remoteanrufsteuerung routen möchten. Sie müssen außerdem für jede Zieladresse einen Eintrag für eine vertrauenswürdige Anwendung erstellen. Wenn Sie das Gateway als vertrauenswürdige Anwendung zuweisen, wird das Gateway als vertrauenswürdig erkannt und kann auch dann als Bestandteil der Lync Server-Umgebung ausgeführt werden, wenn es von einem Drittanbieter entwickelt wurde (und als *externer Dienst* ausgeführt wird, da es sich nicht um eine integrierte Komponente des Produkts handelt). Wenn Lync Server sich nicht über eine TLS-Verbindung (Transport Layer Security), sondern über eine TCP-Verbindung (Transmission Control Protocol) mit dem SIP/CSTA-Gateway verbindet, müssen Sie darüber hinaus mit dem Topologie-Generator die IP-Adresse des Gateways definieren.

Ausführliche Informationen zum Konfigurieren von statischen Routen finden Sie unter [Konfigurieren einer statischen Route für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Ausführliche Informationen zum Konfigurieren von Einträgen für vertrauenswürdige Anwendungen finden Sie unter [Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Ausführliche Informationen zum Definieren einer IP-Adresse für ein SIP/CSTA-Gateway im Topologie-Generator finden Sie unter [Definieren der IP-Adresse für ein SIP/CSTA-Gateway in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

## Schritt 3: Konfigurieren von Lync-Benutzern für die Remoteanrufsteuerung

Nachdem die Benutzer für Lync Server aktiviert wurden, können Sie sie unter Verwendung der Lync Server-Systemsteuerung oder der Lync Server-Verwaltungsshell für die Remoteanrufsteuerung aktivieren. Sie weisen jedem Benutzer während dieses Bereitstellungsschritts einen Anschlussserver-URI und einen Anschluss-URI zu. Der Anschlussserver-URI ist der SIP-URI des SIP/CSTA-Gateways, das Sie dem Benutzer zuweisen möchten. Der Anschluss-URI ist die eindeutige Rufnummer, die dem Benutzer zugewiesen ist.

Ausführliche Informationen zum Konfigurieren von Benutzern für die Remoteanrufsteuerung finden Sie unter [Aktivieren von Lync-Benutzern für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

## Schritt 4: Definieren der Normalisierungsregeln für Lync Server-Rufnummern

In Szenarien mit Remoteanrufsteuerung verwendet Lync Server Normalisierungsregeln, um vom SIP/CSTA-Gateway empfangene Rufnummern in das E.164-Format zu konvertieren. Rufnummern müssen in diesem standardisierten Format vorliegen, damit bestimmte Funktionen der Remoteanrufsteuerung ordnungsgemäß arbeiten. Die Remoteanrufsteuerung verwendet dieselben Normalisierungsregeln für Rufnummern, die Sie für die Normalisierung von Rufnummern durch den Adressbuchdienst konfigurieren. Die Normalisierungsregeln für Rufnummern für Enterprise-VoIP unterscheiden sich hingegen.

Ausführliche Informationen zur Verwendung von Normalisierungsregeln für Rufnummern durch die Remoteanrufsteuerung finden Sie unter [Remoteanrufsteuerung und Normalisieren von Rufnummern in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Ausführliche Informationen zur Verwendung von Normalisierungsregeln für Rufnummern durch den Adressbuchdienst finden Sie unter [Verwalten des Adressbuchdiensts in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) in der Betriebsdokumentation.

