---
title: 'Lync Server 2013: Topologien und Komponenten für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ccce5823e997cafc5e8c8e7555df18bc67d1fe6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Topologien und Komponenten für Mobilität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Zur Unterstützung von mobilen lync-Anwendungen auf mobilen Geräten bietet lync Server 2013 drei Dienste an: lync Server 2013 MCX-Mobilitätsdienst, lync Server 2013 AutoErmittlungsdienst und lync Server 2013 Push-Benachrichtigungsdienst. Die kumulativen Updates für lync Server 2013: Februar 2013 fügt einen kostenlosen, aber erweiterten Dienst für lync 2013 Mobile Clients hinzu – Mobilitätsunterstützung durch die Verwendung der Unified Communications-WebAPI oder UCWA. In diesem Abschnitt werden diese Komponenten kurz beschrieben und die lync Server 2013 Topologien identifiziert, die die Mobilität unterstützen.

<div>


> [!NOTE]  
> Mobilitätsdienste sind auch in hybriden Bereitstellungen verfügbar. Sie müssen keine Dienste zur Unterstützung der Mobilität bereitstellen, falls die Benutzer online verwaltet werden. Sie müssen eine Einstellung für den AutoErmittlungsdienst definieren, damit Mobile Benutzer ihre Online Identität finden können.



</div>

<div>


> [!IMPORTANT]  
> Wenn Sie eine externe Benutzerkonnektivität planen (beispielsweise Partnerverbund, externer Benutzer Zugriff oder Mobilitätsfunktionen), müssen Sie Edgeserver mit Standard Edition-Server und dem Front-End-Server oder Front-End-Pool verwenden. Die Standard Edition-Server und die Front-End-Server oder Front-End-Pool verfügen nicht über die erforderlichen Komponenten, um externen Benutzern den Zugriff auf Ihre interne Bereitstellung zu ermöglichen, oder um die interne Bereitstellung für die Kommunikation mit Ihren externen Benutzern. Für alle Szenarien, die externe Benutzer einschließen, die mit internen Benutzern zusammenarbeiten oder kommunizieren, einschließlich Mobilität, müssen Sie mindestens eine Edgeserver und einen Reverseproxy bereitstellen.<BR><EM>Push Notification</EM> verwendet einen Typ von Verbund für die lync Online Dienste, die das Push Notification Clearing House (PNCH) hosten. Push Notification bezieht sich auf die Sound Warnungen, Warnungen auf dem Bildschirm (Text) und Abzeichen, die von Anwendungen auf das Apple iPhone, iPad und Windows Phone geschoben werden, wenn das Mobile Gerät inaktiv ist. PNCH empfängt Push-Benachrichtigungen von lync Server. Wenn PNCH eine Benachrichtigung über eine Nachricht erhält, leitet PNCH eine Benachrichtigung an mobile Clients über den Apple Push Notification Services oder lync Server 2013 Push Notification Service weiter, basierend auf dem mobilen Client, für den die Nachricht bestimmt ist. PNCH ist ein erforderlicher Dienst für diese mobile Clients. Um eine Föderation mit lync online zu erhalten, verwendet PNCH Edgeserver und Zertifikate, um Vertraulichkeit und Authentifizierung, Richtlinien und ordnungsgemäß konfigurierte DNS-Einträge (Domain Name System) sicherzustellen. Nokia Symbian und Android-basierte lync Mobile-Clients verwenden nicht PNCH. Ausführliche Informationen zum Planen und Bereitstellen von Edgeserver finden Sie unter <A href="lync-server-2013-planning-for-external-user-access.md">Planen des Zugriffs durch externe Benutzer in lync Server 2013</A> und <A href="lync-server-2013-deploying-external-user-access.md">Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013</A>.<BR>Die lync 2013 Mobile Clients für Apple-Geräte, die mit den kumulativen Updates für lync Server 2013 eingeführt wurden: Februar 2013 nicht mehr die Push-Benachrichtigung oder das Push Notification Clearing House (PNCH) verwenden. Lync 2013 Mobile Clients auf Windows Phone weiterhin Push-Benachrichtigung und die (PNCH) verwenden.



</div>

<div>

## <a name="mobility-components"></a>Mobilitätskomponenten

Die folgenden Dienste unterstützen Mobilität:

  - **Lync Server 2013 Unified Communications Web API (UCWA)**   bietet Dienste für die Echtzeitkommunikation mit mobilen und Webclients in lync Server 2013. Wenn Sie die kumulativen Updates für lync Server 2013 bereitstellen: 2013 Februar bis zum Front-End-Server und Director erstellt die Installation ein virtuelles Verzeichnis in den internen und externen Webdiensten (Ucwa). Eine Webkomponente, die Teil des virtuellen Ucwa-Verzeichnisses ist, akzeptiert Anrufe von Ucwa-aktivierten Clients. Die Client-apps kommunizieren über eine Rest-Schnittstelle für Anwesenheit, Kontakte, Instant Messaging, VoIP, Videokonferenzen und Zusammenarbeit. UCWA verwendet einen P-get-basierten Kanal, um Ereignisse wie einen eingehenden Anruf, eine eingehende Sofortnachricht oder eine Nachricht an die Client-App zu senden.
    
    <div>
    

    > [!NOTE]  
    > <EM>Rest</EM> -oder Darstellungs Zustands Übertragung ist ein Softwarearchitekturstil für verteilte Systeme, der in vielen Formen weit verbreitet ist und für die Anforderungen von Webdiensten allgemein geeignet ist.

    
    </div>

  - **Lync Server 2013 Mobilitätsdienst (MCX)**   dieser Dienst unterstützt lync-Funktionen wie Instant Messaging (Sofortnachrichten), Anwesenheitsinformationen und Kontakte auf mobilen Geräten. Der Mobilitätsdienst wird auf jedem Front-End-Server in jedem Pool installiert, der lync-Funktionen auf mobilen Geräten unterstützen soll. Wenn Sie lync Server 2013 installieren, wird ein neues virtuelles Verzeichnis (MCX) sowohl unter der internen Website als auch auf der externen Website auf Ihren Front-End-Servern erstellt.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 mit den kumulativen Updates für lync Server 2013: Februar 2013 unterstützt sowohl den Mobilitätsdienst, der im kumulativen Update für lync Server 2010 eingeführt wurde: November 2011, allgemein bekannt als MCX, und die UCWA-Webkomponente. Die Kombination dieser beiden Mobilitätsdienste bietet Interoperabilität und die Verwendung von Benutzern mit lync 2010 Mobile und lync 2013 mobilen Clients auf lync Server 2013.

    
    </div>

  - **Lync Server 2013 AutoErmittlungsdienst**   dieser Dienst identifiziert den Speicherort des Benutzers und ermöglicht es mobilen Geräten und anderen lync-Clients, Ressourcen wie die internen und externen URLs für lync Server 2013 Webdienste und die URL für die MCX oder UCWA unabhängig vom Netzwerkstandort zu finden. Bei der automatischen Ermittlung werden hart codierte Hostnamen ("lyncdiscoverinternal" für Benutzer innerhalb des Netzwerks; lyncdiscover für Benutzer außerhalb des Netzwerks) und die SIP-Domäne des Benutzers verwendet. Es unterstützt Clientverbindungen, die entweder http oder HTTPS verwenden.
    
    Der AutoErmittlungsdienst wird auf jedem Front-End-Server und jedem Director in jedem Pool installiert, der lync-Funktionen auf mobilen Geräten unterstützen soll. Wenn Sie den AutoErmittlungsdienst installieren, wird ein neues virtuelles Verzeichnis (AutoErmittlung) sowohl unter der internen Website als auch auf der externen Website sowohl auf Front-End-Servern als auch in Directors erstellt.
    
    <div>
    

    > [!NOTE]  
    > Der AutoErmittlungsdienst wird hier aufgelistet, da er bei der Bereitstellung von mobilen Clientdiensten eine wichtige Komponente bleibt. Die Rolle der AutoErmittlung in lync Server 2013 wurde erweitert, um Dienste für alle Clients bereitzustellen. Ausführliche Informationen zur Planung für den AutoErmittlungsdienst finden Sie unter <A href="lync-server-2013-planning-for-autodiscover.md">Planning for AutoErmittlung in lync Server 2013</A>.

    
    </div>

  - **Push-Benachrichtigungsdienst**   dieser Dienst ist ein Cloud-basierter Dienst, der sich im Rechenzentrum lync Online befindet. Wenn die Mobile lync-Anwendung auf einem unterstützten Apple IOS-Gerät oder Windows Phone inaktiv ist, kann Sie nicht auf neue Ereignisse reagieren, beispielsweise auf eine neue sofortnachrichteneinladung, eine verpasste Sofortnachricht, einen verpassten Anruf oder eine Voicemail, da diese Geräte keine Unterstützung für Mobile Anwendungen, die im Hintergrund ausgeführt werden. In diesen Fällen wird eine Benachrichtigung des neuen Ereignisses, das als *Push-Benachrichtigung*bezeichnet wird, an das Mobile Gerät gesendet. Der Mobilitätsdienst sendet die Benachrichtigung an den cloudbasierten Push-Benachrichtigungsdienst, der die Benachrichtigung dann entweder an den Apple Push Notification Service (APNS) (für unterstützte Apple IOS-Geräte) oder an den Microsoft Push Notification Service sendet (MPNS ) (für Windows Phone), der Sie dann an das Mobile Gerät sendet. Der Benutzer kann dann auf dem mobilen Gerät auf die Benachrichtigung Antworten, um die Anwendung zu aktivieren.
    
    Die lync 2010 Mobile auf Apple-und Windows Phone-Geräten verwenden Push-Benachrichtigungen. Der lync 2013 Mobile Client für Apple-Geräte, die mit den kumulativen Updates für lync Server 2013 eingeführt wurden: Februar 2013 verwendet keine Push-Benachrichtigung mehr oder das Push Notification Clearing House (PNCH).

Das folgende Diagramm zeigt, wie der Push-Benachrichtigungsdienst in eine lync Server 2013 Topologie passt, in der UCWA und lync 2013 Mobile Clients verwendet werden.

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Eingeführt im kumulativen Update für lync Server 2010: November 2011 stellt der MCX-Dienst Dienste für lync 2010 Mobile-Clients bereit. Das folgende Diagramm veranschaulicht den Push-Benachrichtigungsdienst, der für eine Topologie mithilfe von MCX und lync 2010 Mobile Clients gilt.

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>Unterstützte Topologien

Bei der Anwendung der kumulativen Updates für lync Server 2013: Februar 2013 werden die UCWA-Webkomponenten hinzugefügt, um die Mobilität für lync 2013 Mobile Clientfeatures in den folgenden Topologien zu unterstützen:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

Die Edgeserver kann eine lync Server 2010 Edgeserver sein.

Eine lync Server 2013-Bereitstellung ohne kumulative Updates für lync Server 2013: Februar 2013 verwendet den MCX-Mobilitätsdienst und kann nur für lync 2010 Mobile Dienste bereitstellen.

<div>


> [!IMPORTANT]  
> Der Mobilitätsdienst wird auf Front-End-Servern unterstützt, die mit der Vermittlungsserver Rolle mit zwei Netzwerkschnittstellen verbunden sind, Sie müssen jedoch geeignete Schritte ausführen, um die Schnittstellen zu konfigurieren. Sie müssen die IP-Adressen der spezifischen Schnittstelle zuweisen, die als Vermittlungsserver kommunizieren wird, und die Netzwerkschnittstellen-IP, die als Front-End-Server kommunizieren soll. Dies können Sie im Topologie-Generator tun, indem Sie die richtige IP-Adresse für jeden Dienst auswählen, anstatt die standardmäßigen <STRONG>use all configured IP Addresss</STRONG>zu verwenden.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen des Zugriffs durch externe Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Bereitstellen von externem Benutzer Zugriff in lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Planen der AutoErmittlung in lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

