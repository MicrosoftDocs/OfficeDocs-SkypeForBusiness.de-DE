---
title: 'Lync Server 2013: Einrichten von Reverseproxyservern'
TOCTitle: Einrichten von Reverseproxyservern
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398069(v=OCS.15)
ms:contentKeyID: 49292977
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten von Reverseproxyservern für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Für Microsoft Lync Server 2013-Edgeserverbereitstellungen ist ein HTTPS-Reverseproxy im Umkreisnetzwerk erforderlich, damit externe Clients auf die Lync Server 2013-Webdienste (in Office Communications Server als *Webkomponenten* bezeichnet) auf dem Director und im Homepool des Benutzers zugreifen können. Beispielsweise ist für die folgenden Funktionen ein externer Zugriff über einen Reverseproxy erforderlich:

  - Herunterladen von Besprechungsinhalten durch externe Benutzer

  - Erweitern von Verteilergruppen durch externe Benutzer

  - Herunterladen von Dateien aus dem Adressbuchdienst durch Remotebenutzer

  - Zugriff auf den Lync Web App-Client

  - Zugriff auf die Webseite mit Einstellungen für Einwahlkonferenzen

  - Herstellen einer Verbindung mit dem Geräteaktualisierungs-Webdienst und Abrufen von Updates durch externe Geräte

  - Ermöglichen, dass mobile Anwendungen die Mobilitäts-URLs (Mcx-URLs) aus dem Internet automatisch ermitteln und verwenden können

  - Ermöglichen, dass der Lync 2013-Client, die Windows Store-App für Lync und der Lync 2013 Mobile-Client die LyncDiscover-URLs (AutoErmittlungs-URLs) finden und UCWA (Unified Communications-Web-API) verwenden können

Es wird empfohlen, den HTTP-Reverseproxy zum Veröffentlichen aller Webdienste in sämtlichen Pools zu konfigurieren. Durch das Veröffentlichen von "https:// *ExternalFQDN* /\*" werden alle virtuellen IIS-Verzeichnisse für einen Pool veröffentlicht. Sie benötigen eine Veröffentlichungsregel für jeden Standard Edition-Server, Front-End-Pool, Director oder Directorpool in Ihrer Organisation.

Darüber hinaus müssen Sie die einfachen URLs veröffentlichen. Wenn die Organisation einen Director oder Directorpool hat, fängt der HTTP-Reverseproxy HTTP/HTTPS-Anforderungen an die einfachen URLs ab und leitet sie an das virtuelle Verzeichnis der externen Webdienste auf dem Director oder Directorpool weiter. Wenn Sie keinen Director bereitgestellt haben, müssen Sie einen Pool zur Verarbeitung von Anforderungen für einfache URLs festlegen. (Wenn es sich hierbei nicht um den Homepool des Benutzers handelt, wird eine Weiterleitung an die Webdienste im Homepool des Benutzers durchgeführt.) Die einfachen URLs können durch eine dedizierte Webveröffentlichungsregel verarbeitet werden, oder Sie können sie zu den öffentlichen Namen der Webveröffentlichungsregel für den Director hinzufügen. Außerdem müssen Sie die externe AutoErmittlungsdienst-URL veröffentlichen.

Sie können Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration Server (ISA) 2006 SP1 oder Internet Information Server 7.0, 7.5 oder 8.0 mit Routing von Anwendungsanforderungen (IIS ARR) als Reverseproxy verwenden. Die ausführliche Schrittanleitung in diesem Abschnitt beschreibt, wie Sie Forefront Threat Management Gateway 2010 konfigurieren. Die Schritte zum Konfigurieren von ISA Server 2006 sind damit fast identisch. Zusätzlich wird eine Anleitung für IIS ARR bereitgestellt. Wenn Sie einen anderen Reverseproxy verwenden, finden Sie weitere Informationen in der Dokumentation zu diesem Produkt. Ordnen Sie die darin definierten Anforderungen den entsprechenden Funktionen anderer Reverseproxys zu.


> [!IMPORTANT]
> Internet Information Server mit Routing von Anwendungsanforderungen (IIS ARR) ist eine vollständig getestete und unterstützte Option für ein Implementieren eines Reverseproxys für Lync Server 2010 und Lync Server 2013. Im November 2012 hat Microsoft den Lizenzvertrieb von ForeFront Threat Management Gateway 2010 bzw. TMG eingestellt. TMG ist nach wie vor ein vollständig unterstütztes Produkt und kann weiterhin mit Appliances erworben werden, die von Drittanbietern verkauft werden. Darüber hinaus bieten viele Drittanbieterhardwaregeräte zum Lastenausgleich sowie -firewalls Reverseproxyunterstützung. Wenn Sie mit einem solchen Hardwaregerät oder einer solchen Firewall arbeiten, sollten Sie Ihren Lieferanten nach speziellen Anweisungen fragen, wie dessen Produkt konfiguriert werden muss, damit es Reverseproxyunterstützung für Lync Server bietet. Außerdem können Sie die Drittanbieter anzeigen, die Dokumentationen für ihre Produkte an Microsoft übermittelt haben. Unterstützung wird vom jeweiligen Drittanbieter für seine Lösung bereitgestellt. Wenn Sie die Drittanbieter sehen möchten, die Lösungen bereitstellen, lesen Sie <A href="http://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.



In den folgenden Themen und Verfahren werden Forefront Threat Management Gateway 2010 und IIS ARR als Grundlage für die Schritte zur Bereitstellung und Konfiguration verwendet.

  - [Konfigurieren von Webfarm-FQDNs für Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Konfigurieren von Netzwerkadaptern in Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Anfordern und Konfigurieren eines Zertifikats für den HTTP-Reverseproxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool in Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse in Lync Server 2013](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Erstellen von DNS-Einträgen für Reverseproxyserver in Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Überprüfen des Zugriffs über den Reverseproxy in Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

## Vorbereitung

Für die erfolgreiche Bereitstellung von Forefront Threat Management Gateway 2010 als Reverseproxy müssen Sie einen Server einrichten und konfigurieren, indem Sie die Voraussetzungen und Hardwareanforderungen beachten, die in der Forefront Threat Management Gateway 2010-Dokumentation angegeben sind. Sehen Sie sich vor dem Fortfahren die Informationen zur richtigen Konfiguration der Hardware und Installation von Forefront Threat Management Gateway 2010 auf dem Server in der folgenden Themengruppe an.

  - [Forefront Threat Management Gateway (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - [Forefront TMG 2010-Hardwareempfehlungen](http://go.microsoft.com/fwlink/?linkid=291293)

Damit Sie IIS ARR erfolgreich als Reverseproxy bereitstellen können, sollten Sie sich die folgenden Themen ansehen, um die Hardware und die erforderliche Software zu konfigurieren.

  - Wenn Sie IIS unter Windows Server 2008 oder Windows Server 2008 R2 installieren möchten, sollten Sie [Installieren von IIS 7 unter Windows Server 2008 oder Windows Server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296) lesen.

  - Wenn Sie IIS unter Windows Server 2012 installieren möchten, sollten Sie [Installieren von IIS 8 unter Windows Server 2012](http://go.microsoft.com/fwlink/?linkid=291297) lesen.

  - Informationen zum Installieren von IIS unter Windows Server 2012 R2 finden Sie unter [Installieren von IIS 8.5 unter Windows Server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)

  - Wenn Sie die IIS-Erweiterung für das Routing von Anwendungsanforderungen herunterladen möchten, folgen Sie den Anweisungen unter [Routing von Anwendungsanforderungen](http://go.microsoft.com/fwlink/?linkid=291298).

  - Die Anleitungen zur Installation des Routings von Anwendungsanforderungen (ARR) finden Sie unter [Installieren des Routings von Anwendungsanforderungen Version 2](http://go.microsoft.com/fwlink/?linkid=291299).
    

  > [!NOTE]
  > Die momentan veröffentlichten Anleitungen gelten für ARR 2.0. Hinsichtlich der Installation der Erweiterung gibt es keine Unterschiede zwischen den beiden Versionen.


