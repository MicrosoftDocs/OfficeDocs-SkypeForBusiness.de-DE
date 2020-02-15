---
title: 'Lync Server 2013: erforderliche Komponenten für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e225f63da97ea48d98a5a2540a6b35a9c63c08f2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Erforderliche Komponenten für den Zugriff durch externe Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-29_

Die meisten Edge-Komponenten werden in einem Umkreisnetzwerk bereitgestellt. Die folgenden Komponenten bilden die Edge-Topologie des Umkreisnetzwerks. Sofern nicht anders angegeben, sind die Komponenten Teil der [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) und befinden sich im Umkreisnetzwerk. Zu den Edge-Komponenten zählen folgende:

  - Edgeserver

  - Reverse-Proxies

  - Firewalls

  - Directors (optional und logisch im internen Netzwerk gespeichert)

  - Lastenausgleich für skalierte Edge-Topologien (entweder DNS-Lastenausgleich oder ein Hardwaregerät zum Lastenausgleich)
    
    <div>
    

    > [!IMPORTANT]  
    > Es wird nicht unterstützt, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden.

    
    </div>

<div>

## <a name="edge-servers"></a>Edgeserver

Die Edgeserver senden und empfangen Netzwerkdatenverkehr für die Dienste, die von externen Benutzern von der internen Bereitstellung angeboten werden. Im Edgeserver werden die folgenden Dienste ausgeführt:

  - **Zugriffs-Edgedienst**   das Zugriffs-Edgedienst stellt einen einzelnen vertrauenswürdigen Verbindungspfad für ausgehenden und eingehenden SIP-Datenverkehr (Session Initiation Protocol) bereit.

  - **Webkonferenz-Edgedienst**   das Webkonferenz-Edgedienst ermöglicht externen Benutzern, an Besprechungen teilzunehmen, die in ihrer internen lync Server 2013-Bereitstellung gehostet werden.

  - **A/V-Edgedienst**   der A/V-Edgedienst können Audio-, Video-, Anwendungsfreigabe und Dateiübertragung für externe Benutzer verfügbar gemacht werden. Ihre Benutzer können Besprechungen, die externe Teilnehmer einschließen, Audio und Video hinzufügen, und Sie können über Audio und/oder Video direkt mit einem externen Benutzer in den "Points-to-Points"-Sitzungen kommunizieren. Die A/V-Edgedienst bietet auch Unterstützung für Desktopfreigabe und Dateiübertragung.

  - **XMPP-Proxydienst**   der XMPP-Proxydienst akzeptiert und sendet XMPP-Nachrichten (Extensible Messaging and Presence Protocol) an und von konfigurierten XMPP-Verbundpartnern.

Autorisierte externe Benutzer können auf die Edgeserver zugreifen, um eine Verbindung mit ihrer internen lync Server 2013-Bereitstellung herzustellen, aber die Edgeserver bieten keine Möglichkeit für einen anderen Zugriff auf das interne Netzwerk.

<div>


> [!NOTE]  
> Edgeserver werden bereitgestellt, um Verbindungen für aktivierte lync-Clients und andere Microsoft-Edgeserver (wie in Verbundszenarien) bereitzustellen. Sie sind nicht für Verbindungen von anderen Endpunkt Client-oder Servertypen ausgelegt. Der XMPP-Gatewayserver kann bereitgestellt werden, um Verbindungen mit konfigurierten XMPP-Partnern zu ermöglichen. Der Edgeserver und das XMPP-Gateway können nur Endpunkt Verbindungen von diesen Client-und Verbundtypen unterstützen.



</div>

</div>

<div>

## <a name="reverse-proxy"></a>Reverseproxy

Für Folgendes ist der Reverseproxy erforderlich:

  - So ermöglichen Sie Benutzern das Herstellen einer Verbindung mit Besprechungen oder Einwahlkonferenzen mithilfe einfacher URLs

  - So ermöglichen Sie externen Benutzern das Herunterladen von Besprechungsinhalten

  - So aktivieren Sie externe Benutzer zum Erweitern von Verteilergruppen

  - So ermöglichen Sie dem Benutzer das Abrufen eines benutzerbasierten Zertifikats für die Clientzertifikat basierte Authentifizierung

  - So ermöglichen Sie Remotebenutzern das Herunterladen von Dateien vom Adressbuch Server oder das Übermitteln von Abfragen an die Adressbuch-Webabfragedienst

  - So ermöglichen Sie Remotebenutzern das Abrufen von Updates für Client-und Geräte Software

  - So aktivieren Sie mobile Geräte zum automatischen ermitteln von Front-End-Servern, die Mobilitätsdienste anbieten

  - So aktivieren Sie Push-Benachrichtigungen für mobile Geräte über die Office 365 oder Apple Push Notification Services

Weitere Informationen zu Reverse-Proxies und den Anforderungen, die Reverse-Proxies erfüllen müssen, finden Sie in den Details unter [Konfigurationsanforderungen für Reverse Proxy in lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).

<div>


> [!NOTE]  
> Externe Benutzer benötigen keine VPN-Verbindung (Virtual Private Network) zu Ihrer Organisation, um mit lync Server 2013 an einer Kommunikation teilzunehmen. Wenn Sie VPN-Technologie in Ihrer Organisation implementiert haben und Ihre Benutzer das VPN für lync verwenden, kann der Mediendatenverkehr (beispielsweise Videokonferenzen) beeinträchtigt werden. Sie sollten einen Mittel für den Mediendatenverkehr bereitstellen, um eine Verbindung mit dem AV-Edgedienst direkt herzustellen und das VPN zu umgehen. Ausführliche Informationen finden Sie im NextHop-Blog-Artikel "Aktivieren von <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>lync Media zur Umgehung eines VPN-Tunnels" unter.



</div>

</div>

<div>

## <a name="firewall"></a>Firewall

Sie können Ihre Edge-Topologie nur mit einer externen Firewall oder sowohl mit externen als auch mit internen Firewalls bereitstellen. Die Szenario-Architekturen umfassen zwei Firewalls. Die Verwendung von zwei Firewalls ist die empfohlene Vorgehensweise, da Sie ein striktes Routing von einem Netzwerk-Edge zum anderen gewährleistet und ihre interne Bereitstellung hinter zwei Firewall-Ebenen schützt.

</div>

<div>

## <a name="director"></a>Director

Ein Director ist eine separate, optionale Serverrolle in lync Server 2013, die keine Benutzerkonten aufweist, oder Anwesenheits-oder Konferenzdienste bereitstellen. Er dient als interner nächster Hop-Server, an den ein Edgeserver eingehenden SIP-Datenverkehr für interne Server weiterleitet. Der Director authentifiziert eingehende Anforderungen und leitet Sie an den privaten Pool oder Server des Benutzers weiter. Durch Vorauthentifizierung beim Director können Sie Anforderungen von Benutzerkonten ablegen, die der Bereitstellung unbekannt sind.

Ein Director hilft bei der Isolierung von Standard Edition-Servern und Front-End-Servern in Enterprise Edition-Front-End-Pools vor bösartigem Datenverkehr wie Denial-of-Service-Angriffen (DOS). Wenn das Netzwerk bei einem solchen Angriff mit ungültigem externem Datenverkehr überflutet wird, endet der Datenverkehr beim Director. Ausführliche Informationen zur Verwendung von Directors finden Sie unter [Scenarios for the Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Anforderungen an das Hardware Gerät zum Lastenausgleich für lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

