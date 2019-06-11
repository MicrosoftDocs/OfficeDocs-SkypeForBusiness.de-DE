---
title: 'Lync Server 2013: Topologien und Komponenten für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 537eda14f2587e06bd8a1112f2a6a44299b0b78e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Topologien und Komponenten für Mobilität in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Zur Unterstützung von lync Mobile-Anwendungen auf mobilen Geräten bietet lync Server 2013 drei Dienste: lync Server 2013 MCX Mobility Service, lync Server 2013 AutoErmittlungsdienst und lync Server 2013-Push-Benachrichtigungsdienst. Die kumulativen Updates für lync Server 2013: Februar 2013 fügt einen kostenlosen, aber erweiterten Dienst für lync 2013-Mobile Clients hinzu – Mobilitätsunterstützung durch die Verwendung der Unified Communications Web-API oder UCWA. In diesem Abschnitt werden diese Komponenten kurz beschrieben und die lync Server 2013-Topologien identifiziert, die die Mobilität unterstützen.

<div>


> [!NOTE]  
> Mobilitätsdienste stehen auch in hybridbereitstellungen zur Verfügung. Sie müssen keine Dienste zur Unterstützung der Mobilität bereitstellen, wenn Ihre Benutzer online sind. Sie müssen eine Einstellung für den AutoErmittlungsdienst definieren, damit Mobile Benutzer ihre Online Identität finden können.



</div>

<div>


> [!IMPORTANT]  
> Wenn Sie eine externe Benutzerkonnektivität planen (beispielsweise Föderation, Zugriff auf externe Benutzer oder Mobilitätsfeatures), müssen Sie Edgeserver mit dem Standard Edition-Server und dem Front-End-Server oder dem Front-End-Pool verwenden. Der Standard Edition-Server und der Front-End-Server oder der Front-End-Pool verfügen nicht über die erforderlichen Komponenten, um externen Benutzern den Zugriff auf Ihre interne Bereitstellung zu ermöglichen, oder für die interne Bereitstellung, um mit Ihren externen Benutzern zu kommunizieren. Für alle Szenarien, die externe Benutzer einbeziehen, die mit internen Benutzern zusammenarbeiten oder mit Ihnen kommunizieren, einschließlich Mobilität, müssen Sie mindestens einen Edgeserver und einen Reverse-Proxy bereitstellen.<BR>Bei der <EM>Push-Benachrichtigung</EM> wird ein Föderations für die lync Online-Dienste verwendet, die das Push Notification Clearing House (PNCH) hostet. Die Push-Benachrichtigung bezieht sich auf die akustischen Benachrichtigungen, auf dem Bildschirm angezeigten Benachrichtigungen (Text) und auf Abzeichen, die von Anwendungen auf das Apple iPhone, iPad und Windows Phone übertragen werden, wenn das Mobile Gerät inaktiv ist. PNCH empfängt Push-Benachrichtigungen von lync Server. Wenn PNCH eine Benachrichtigung über eine Nachricht erhält, leitet PNCH eine Benachrichtigung an mobile Clients über den Apple Push Notification Services oder den lync Server 2013-Push-Benachrichtigungsdienst weiter, der auf dem mobilen Client basiert, für den die Nachricht vorgesehen ist. PNCH ist ein erforderlicher Dienst für diese mobilen Clients. Um eine Föderation zu lync online zu finden, verwendet PNCH Edgeserver und Zertifikate, um Vertraulichkeit und Authentifizierung, Richtlinien und ordnungsgemäß konfigurierte DNS-Einträge (Domain Name System) zu gewährleisten. Die Nokia Symbian-und Android-basierten lync Mobile-Clients verwenden PNCH nicht. Details zum Planen und Bereitstellen von Edgeserver finden Sie unter <A href="lync-server-2013-planning-for-external-user-access.md">Planen des Zugriffs externer Benutzer in lync Server 2013</A> und <A href="lync-server-2013-deploying-external-user-access.md">Bereitstellen des Zugriffs externer Benutzer in lync Server 2013</A>.<BR>Die lync 2013-mobilen Clients für Apple-Geräte, die mit den kumulativen Updates für lync Server 2013 eingeführt wurden: Februar 2013 verwenden keine Push-Benachrichtigung mehr oder das Clearing House für Push-Benachrichtigungen (PNCH). Mobile lync 2013-Clients auf Windows Phone verwenden weiterhin die Push-Benachrichtigung und die (PNCH).



</div>

<div>

## <a name="mobility-components"></a>Mobilitätskomponenten

Die Dienste, die Mobilität unterstützen, sind wie folgt:

  - **Lync Server 2013 Unified Communications Web API (UCWA)**   bietet Dienste für die Echtzeitkommunikation mit mobilen und Webclients in lync Server 2013. Wenn Sie die kumulativen Updates für lync Server 2013: Februar 2013 auf dem Front-End-Server und Director bereitstellen, erstellt die Installation ein virtuelles Verzeichnis in den internen und externen Webdiensten (Ucwa). Eine Webkomponente, die Teil des virtuellen Verzeichnisses Ucwa ist, akzeptiert Anrufe von Ucwa-aktivierten Clients. Die Client-apps kommunizieren über eine Ruhe-Schnittstelle für Anwesenheit, Kontakte, Instant Messaging, VoIP, Videokonferenzen und Zusammenarbeit. UCWA verwendet einen P-get-basierten Kanal, um Ereignisse wie einen eingehenden Anruf, eine eingehende Sofortnachricht oder eine Nachricht an die Client-App zu senden.
    
    <div>
    

    > [!NOTE]  
    > <EM>Ruhe</EM> Zustands-oder Repräsentations Statusübertragung, ist ein Software-Architekturstil für verteilte Systeme, der in vielen Formen weit verbreitet und für die Anforderungen von Webdiensten im Allgemeinen gut geeignet ist.

    
    </div>

  - **Lync Server 2013 Mobility Service (MCX)**   dieser Dienst unterstützt lync-Funktionen wie Instant Messaging (im), Anwesenheitsinformationen und Kontakte auf mobilen Geräten. Der Mobilitätsdienst ist auf jedem Front-End-Server in jedem Pool installiert, der die lync-Funktionalität auf mobilen Geräten unterstützt. Wenn Sie lync Server 2013 installieren, wird ein neues virtuelles Verzeichnis (MCX) sowohl auf der internen Website als auch auf der externen Website auf Ihren Front-End-Servern erstellt.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 mit den kumulierten Updates für lync Server 2013: Februar 2013 unterstützt sowohl den Mobilitätsdienst, der im kumulativen Update für lync Server 2010 eingeführt wurde: November 2011, allgemein bekannt als MCX, und die UCWA-Webkomponente. Die Kombination dieser beiden Mobilitätsdienste bietet Interoperabilität und die Verwendung von Benutzern mit lync 2010 Mobile-und lync 2013-mobilen Clients auf lync Server 2013.

    
    </div>

  - **Lync Server 2013-AutoErmittlungsdienst**   dieser Dienst identifiziert den Standort des Benutzers und ermöglicht es mobilen Geräten und anderen lync-Clients, Ressourcen zu finden, wie etwa die internen und externen URLs für lync Server 2013-Webdienste und die URL für die MCX oder UCWA – ungeachtet des Netzwerkspeicherorts. Bei der automatischen Ermittlung werden hart codierte Host Namen (lyncdiscoverinternal für Benutzer im Netzwerk; lyncdiscover für Benutzer außerhalb des Netzwerks) und die SIP-Domäne des Benutzers verwendet. Sowohl Clientverbindungen über HTTP als auch über HTTPS werden unterstützt.
    
    Der AutoErmittlungsdienst ist auf jedem Front-End-Server und auf jedem Director in jedem Pool installiert, der die lync-Funktionalität auf mobilen Geräten unterstützen soll. Wenn Sie den AutoErmittlungsdienst installieren, wird ein neues virtuelles Verzeichnis (autodiscover) sowohl auf der internen Website als auch auf der externen Website sowohl auf Front-End-Servern als auch auf Directors erstellt.
    
    <div>
    

    > [!NOTE]  
    > Der AutoErmittlungsdienst wird hier aufgelistet, da er bei der Bereitstellung von mobilen Clientdiensten eine wichtige Komponente bleibt. Die Rolle der AutoErmittlung in lync Server 2013 wurde erweitert, um Dienste für alle Clients bereitzustellen. Ausführliche Informationen zur Planung des AutoErmittlungsdiensts finden Sie unter <A href="lync-server-2013-planning-for-autodiscover.md">Planen der AutoErmittlung in lync Server 2013</A>.

    
    </div>

  - **Push-Benachrichtigungsdienst**   dieser Dienst ist ein Cloud-basierter Dienst, der sich im lync Online-Rechenzentrum befindet. Wenn die lync Mobile-Anwendung auf einem unterstützten Apple IOS-Gerät oder Windows Phone inaktiv ist, kann Sie nicht auf neue Ereignisse reagieren, beispielsweise auf eine neue Chat-Einladung (im), eine verpasste Sofortnachricht, einen verpassten Anruf oder eine Voicemail, da diese Geräte nicht unterstützt werden. Mobile Anwendungen, die im Hintergrund ausgeführt werden. In diesen Fällen wird eine Benachrichtigung über das neue Ereignis – so genannte *Push-Benachrichtigung*– an das Mobile Gerät gesendet. Der Mobilitätsdienst sendet die Benachrichtigung an den cloudbasierten Push-Benachrichtigungsdienst, der die Benachrichtigung dann entweder an den Apple Push Notification Service (APNS) (für unterstützte Apple IOS-Geräte) oder an den Microsoft Push Notification Service (MPNS ) (für Windows Phone), das Sie dann an das Mobile Gerät sendet. Der Benutzer kann dann auf dem mobilen Gerät auf die Benachrichtigung Antworten, um die Anwendung zu aktivieren.
    
    Das lync 2010 Mobile auf Apple-und Windows Phone-Geräten verwendet Push-Benachrichtigungen. Der lync 2013-Mobile Client für Apple-Geräte, der mit den kumulativen Updates für lync Server 2013 eingeführt wurde: Februar 2013 verwendet keine Push-Benachrichtigung mehr oder das PNCH (Push Notification Clearing House).

Das folgende Diagramm zeigt, wie der Push-Benachrichtigungsdienst in eine lync Server 2013-Topologie passt, die UCWA-und lync 2013-Mobile Clients verwendet.

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae] (images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Der MCX-Dienst, der in das kumulative Update für lync Server 2010: November 2011 eingeführt wurde, bietet Dienste für lync 2010-Mobile Clients. Das folgende Diagramm veranschaulicht den Push-Benachrichtigungsdienst für eine Topologie mit MCX-und lync 2010-mobilen Clients.

![3081634e-60e7-4348-b24e-bbbf05a90f5f] (images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>Unterstützte Topologien

Durch Anwenden der kumulierten Updates für lync Server 2013: Februar 2013 werden die UCWA-Webkomponenten hinzugefügt, um die Mobilität für lync 2013-Mobile Clientfeatures in den folgenden Topologien zu unterstützen:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

Der Edgeserver kann ein lync Server 2010 Edge-Server sein.

Eine lync Server 2013-Bereitstellung ohne die kumulativen Updates für lync Server 2013: Februar 2013 verwendet den MCX-Mobilitätsdienst und kann nur Dienste für lync 2010 Mobile bereitstellen.

<div>


> [!IMPORTANT]  
> Der Mobilitätsdienst wird auf Front-End-Servern unterstützt, die mit der Vermittlungs Server Rolle mit zwei Netzwerkschnittstellen verbunden sind, Sie müssen jedoch die erforderlichen Schritte zum Konfigurieren der Schnittstellen ausführen. Sie müssen die IP-Adressen der jeweiligen Schnittstelle zuweisen, die als Vermittlungsserver kommuniziert, und die Netzwerkschnittstellen-IP-Adresse, die als Front-End-Server kommunizieren soll. Sie können dies in Topology Builder durchführen, indem Sie die richtige IP-Adresse für jeden Dienst auswählen, anstatt die standardmäßig <STRONG>alle konfigurierten IP-Adressen zu verwenden</STRONG>.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Planen der AutoErmittlung in lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

