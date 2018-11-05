---
title: 'Lync Server 2013: Erforderliche Komponenten für den Zugriff durch externe Benutzer'
TOCTitle: Erforderliche Komponenten für den Zugriff durch externe Benutzer
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425779(v=OCS.15)
ms:contentKeyID: 49293531
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erforderliche Komponenten für den Zugriff durch externe Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Die meisten Edgekomponenten werden in einem Umkreisnetzwerk bereitgestellt. Die Edgetopologie des Umkreisnetzwerks umfasst die folgenden Komponenten. Sofern nicht anders vermerkt, sind die Komponenten Bestandteil der [Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) und befinden sich im Umkreisnetzwerk. Zu den Edgekomponenten gehören:

  - Edgeserver

  - Reverseproxys

  - Firewalls

  - Directors (optional und logisch im internen Netzwerk angeordnet)

  - Lastenausgleich für skalierte Edgetopologien (entweder DNS-Lastenausgleich oder Hardwaregerät zum Lastenausgleich)
    

    > [!IMPORTANT]
    > Es wird nicht unterstützt, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden.



## Edgeserver

Die Edgeserver senden und empfangen Netzwerkdatenverkehr von externen Benutzern für die Dienste, die von der internen Bereitstellung angeboten werden. Auf dem Edgeserver werden die folgenden Dienste ausgeführt:

  - **Zugriffs-Edgedienst**   Der Zugriffs-Edgedienst stellt einen einzelnen vertrauenswürdigen Verbindungspunkt für ausgehenden und eingehenden SIP-Datenverkehr (Session Initiation Protocol) bereit.

  - **Webkonferenz-Edgedienst**   Der Webkonferenz-Edgedienst ermöglicht externen Benutzern, an Besprechungen teilzunehmen, die in der internen Lync Server 2013-Bereitstellung gehostet werden.

  - **A/V-Edgedienst**   Der A/V-Edgedienst ermöglicht Audio, Video, Anwendungsfreigabe und Dateiübertragungen für externe Benutzer. Ihre Benutzer können Audio- und Videodaten zu Besprechungen hinzufügen, an denen externe Benutzer teilnehmen. Außerdem können Benutzer über Audio und/oder Video in Direktsitzungen mit einem externen Benutzer direkt kommunizieren. Der A/V-Edgedienst bietet außerdem Unterstützung für Desktopfreigabe und Dateiübertragung.

  - **XMPP-Proxydienst**   Der XMPP-Proxydienst akzeptiert und sendet XMPP (Extensible Messaging and Presence Protocol)-Nachrichten von bzw. an konfigurierte XMPP-Verbundpartner.

Autorisierte externe Benutzer können auf die Edgeserver zugreifen, um eine Verbindung mit der internen Lync Server 2013-Bereitstellung herzustellen, aber die Edgeserver stellen keinen anderen Zugriff auf das interne Netzwerk bereit.


> [!NOTE]
> Edgeserver dienen dazu, die Kommunkation mit aktivierten Lync-Clients und anderen Microsoft Edgeservern (z.&nbsp;B. bei Verbünden) zu ermöglichen. Verbindungen von anderen Endpunktclients oder Servertypen sind mit ihnen nicht möglich. Der XMPP-Gatewayserver kann für die Kommunikation mit konfigurierten XMPP-Partnern eingesetzt werden. Edgeserver und das XMPP-Gateway unterstützen ausschließlich Endpunktverbindungen von diesen Client- und Verbundtypen.



## Reverseproxy

Der Reverseproxy ermöglicht Folgendes:

  - Teilnahme an Besprechungen und Einwahlkonferenzen über einfache URLs

  - Herunterladen von Besprechungsinhalten durch externe Benutzer

  - Erweiterung von Verteilergruppen durch externe Benutzer

  - Abrufen eines benutzerbasierten Zertifikats für die auf Clientzertifikaten basierende Authentifizierung

  - Herunterladen von Dateien vom Adressbuchserver oder Senden von Abfragen an den Adressbuch-Webabfragedienst durch Remotebenutzer

  - Abrufen von Updates für Client- und Gerätesoftware durch Remotebenutzer

  - Automatische Ermittlung von Front-End-Servern, die Mobilitätsdienste anbieten, durch mobile Geräte

  - Ermöglichen von Pushbenachrichtigungen an mobile Geräte über Office 365- oder Apple-Pushbenachrichtigungsdienste

Zusätzliche Informationen zu Reverseproxys und den Voraussetzungen, die diese erfüllen müssen, finden Sie unter den Details in [Konfigurationsanforderungen für Reverseproxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).


> [!NOTE]
> Externe Benutzer benötigen eine keine VPN-Verbindung mit Ihrer Organisation, um mithilfe von Lync Server 2013 an Kommunikationen teilzunehmen. Wenn Sie VPN-Technologie in Ihrer Organisation implementiert haben und die Benutzer das VPN für Lync verwenden, kann sich dies negativ auf den Netzwerkdatenverkehr (z.&nbsp;B. Videokonferenzen) auswirken. Sie sollten eine Möglichkeit dafür schaffen, dass der Mediendatenverkehr eine direkte Verbindung mit dem A/V-Edgedienst herstellen und das VPN umgehen kann. Detailliere Informationen finden Sie im NextHop Blog-Artikel "Enabling Lync Media to Bypass a VPN Tunnel" unter <A href="http://go.microsoft.comcom/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.



## Firewall

Sie können Ihre Edgetopologie mit nur einer externen Firewall oder sowohl mit einer externen als auch einer internen Firewall bereitstellen. Die Szenarioarchitekturen enthalten zwei Firewalls. Die Verwendung von zwei Firewalls ist der empfohlene Ansatz, da bei dieser Architektur ein strenges Routing von einem Netzwerkedge zum anderen sichergestellt wird. Darüber hinaus wird das interne Netzwerk durch zwei Firewallebenen geschützt.

## Director

Ein Director ist eine separate, optionale Serverrolle in Lync Server 2013, die keine Benutzerkonten verwaltet oder Anwesenheits- oder Konferenzdienste bereitstellt. Stattdessen fungiert der Director als interner Server für den nächsten Hop, an den ein Edgeserver eingehenden SIP-Datenverkehr weiterleitet, der für interne Server bestimmt ist. Der Director führt eine Vorauthentifizierung der eingehenden Anforderungen durch und leitet diese an den Home-Pool oder Homeserver des Benutzers weiter.

Ein Director ist nützlich, um die Standard Edition-Server und Front-End-Server in den Enterprise Edition-Front-End-Pools von bösartigem Datenverkehr wie Denial-of-Service-Angriffen zu isolieren. Wenn das Netzwerk bei einem solchen Angriff mit ungültigem externen Datenverkehr überflutet wird, endet der Datenverkehr beim Director. Detaillierte Informationen zur Verwendung von Directors finden Sie unter [Szenarien für den Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

## Siehe auch

#### Konzepte

[Anforderungen an das Hardwaregerät zum Lastenausgleich für Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)

