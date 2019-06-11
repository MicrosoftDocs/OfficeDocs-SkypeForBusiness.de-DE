---
title: 'Lync Server 2013: Erforderliche Komponenten für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895f2d4837eb465f0eead2b70cf1d603504699ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Erforderliche Komponenten für den Zugriff durch externe Benutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-29_

Die meisten Edgekomponenten werden in einem Umkreisnetzwerk bereitgestellt. Die folgenden Komponenten bilden die Edge-Topologie des Umkreisnetzwerks. Sofern nicht anders angegeben, sind die Komponenten Teil der [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) und befinden sich im Umkreisnetzwerk. Zu den Edgekomponenten gehören:

  - Edge Servers

  - Reverse proxies

  - Firewalls

  - Directors (optional und logisch im internen Netzwerk angeordnet)

  - Lastenausgleich für skalierte Edgetopologien (entweder DNS-Lastenausgleich oder Hardwaregerät zum Lastenausgleich)
    
    <div>
    

    > [!IMPORTANT]  
    > Das Verfahren, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden, wird nicht unterstützt. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden.

    
    </div>

<div>

## <a name="edge-servers"></a>Edgeservers

Die Edgeserver senden und empfangen Netzwerkdatenverkehr für die Dienste, die von externen Benutzern bereitgestellt werden. Der Edgeserver führt die folgenden Dienste aus:

  - **Access**   -Edgedienst der Access-Edgedienst stellt einen einzigen vertrauenswürdigen Verbindungspunkt für ausgehende und eingehende SIP-Datenverkehr (Session Initiation Protocol) bereit.

  - **Webkonferenz-Edgedienst**   der Webkonferenz-Edgedienst ermöglicht es externen Benutzern, an Besprechungen teilzunehmen, die auf Ihrer internen lync Server 2013-Bereitstellung gehostet werden.

  - **A/v**   -Edgedienst der a/v-Edgedienst ermöglicht externen Benutzern die Bereitstellung von Audio, Video, Anwendungsfreigabe und Dateiübertragung. Ihre Benutzer können Besprechungen mit externen Teilnehmern Audio und Video hinzufügen, und Sie können in Punkt-zu-Punkt-Sitzungen mithilfe von Audio und/oder Video direkt mit einem externen Benutzer kommunizieren. Der A/V-Edgedienst bietet auch Unterstützung für die Desktopfreigabe und Dateiübertragung.

  - **XMPP-Proxydienst**   der XMPP-Proxydienst akzeptiert und sendet Nachrichten zu und von konfigurierten XMPP-Verbundpartnern.

Autorisierte externe Benutzer können auf die Edgeserver zugreifen, um eine Verbindung mit ihrer internen lync Server 2013-Bereitstellung herzustellen, aber die Edgeserver bieten keine Möglichkeit für einen anderen Zugriff auf das interne Netzwerk.

<div>


> [!NOTE]  
> Edgeserver werden für die Bereitstellung von Verbindungen für aktivierte lync-Clients und andere Microsoft Edge-Server bereitgestellt (wie in Verbundszenarien). Sie sind nicht dafür vorgesehen, Verbindungen von anderen Endpunkt Client-oder Servertypen zu ermöglichen. Der XMPP-Gatewayserver kann bereitgestellt werden, um Verbindungen mit konfigurierten XMPP-Partnern zu ermöglichen. Der Edge-Server und das XMPP-Gateway können nur Endpunkt Verbindungen von diesen Client-und Verbundtypen unterstützen.



</div>

</div>

<div>

## <a name="reverse-proxy"></a>Reverseproxy

Der Reverseproxy ist für Folgendes erforderlich:

  - So ermöglichen Sie Benutzern das Herstellen einer Verbindung mit Besprechungen oder Einwahlkonferenzen mithilfe einfacher URLs

  - So aktivieren Sie externe Benutzer zum Herunterladen von Besprechungsinhalten

  - So aktivieren Sie externe Benutzer zum Erweitern von Verteilergruppen

  - So ermöglichen Sie Benutzern das Abrufen eines benutzerbasierten Zertifikats für die Clientzertifikat basierte Authentifizierung

  - So aktivieren Sie Remotebenutzer zum Herunterladen von Dateien vom Adressbuch Server oder zum Übermitteln von Abfragen an den Adressbuch-Webabfrage Dienst

  - So ermöglichen Sie es Remotebenutzern, Updates für Client-und Geräte Software zu erhalten

  - So aktivieren Sie mobile Geräte, um Front-End-Server, die Mobilitätsdienste anbieten, automatisch zu erkennen

  - So aktivieren Sie Push-Benachrichtigungen auf mobilen Geräten über die Office 365-oder Apple Push Notification Services

Weitere Informationen zu Reverse-Proxys und den Anforderungen, die umgekehrte Proxys erfüllen müssen, finden Sie in den Details unter [Konfigurationsanforderungen für Reverse Proxy in lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).

<div>


> [!NOTE]  
> Externe Benutzer benötigen keine VPN-Verbindung (virtuelles privates Netzwerk) mit Ihrer Organisation, um an der Kommunikation mit lync Server 2013 teilzunehmen. Wenn Sie in Ihrer Organisation VPN-Technologie implementiert haben und Ihre Benutzer das VPN für lync verwenden, können Mediendatenverkehr (wie Videokonferenzen) beeinträchtigt werden. Sie sollten die Bereitstellungeines Mediums für Mediendatenverkehr in Frage stellen, um die Verbindung mit dem AV Edge-Dienst direkt herzustellen und das VPN zu umgehen. Ausführliche Informationen finden Sie im NextHop-Blog Artikel "Aktivieren von <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>lync Media zur Umgehung eines VPN-Tunnels" unter.



</div>

</div>

<div>

## <a name="firewall"></a>Firewall

Sie können Ihre Edge-Topologie nur mit einer externen Firewall oder mit externen und internen Firewalls bereitstellen. Zu den Szenarien-Architekturen gehören zwei Firewalls. Die Verwendung von zwei Firewalls ist die empfohlene Vorgehensweise, da Sie ein striktes Routing von einem Netzwerkrand zum anderen gewährleistet und ihre interne Bereitstellung hinter zwei Firewall-Ebenen schützt.

</div>

<div>

## <a name="director"></a>Director

Bei einem Director handelt es sich um eine separate, optionale Serverrolle in lync Server 2013, in der keine Benutzerkonten zu Hause sind, oder Anwesenheits-oder Konferenzdienste bereitstellen. Sie fungiert als interner Server für den nächsten Hop, auf dem ein Edgeserver eingehenden SIP-Datenverkehr für interne Server weiterleitet. Der Director authentifiziert eingehende Anforderungen und leitet Sie an den privaten Pool oder Server des Benutzers weiter. Durch die Vorauthentifizierung beim Director können Sie Anforderungen aus Benutzerkonten, die für die Bereitstellung unbekannt sind, ablegen.

Ein Director hilft beim Isolieren von Standard Edition-Servern und Front-End-Servern in Enterprise Edition-Front-End-Pools vor böswilligem Datenverkehr wie DOS-Attacken (Denial-of-Service). Wenn das Netzwerk bei einem solchen Angriff mit einem ungültigen externen Datenverkehr überflutet wird, endet der Datenverkehr beim Director. Ausführliche Informationen zur Verwendung von Directors finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Anforderungen an das Hardwaregerät zum Lastenausgleich für Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

