---
title: 'Lync Server 2013: neue Features für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 526daf4359cec022b71476dc4abaa67c52e8409a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Neue Features für den Zugriff durch externe Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-17_

In lync Server 2013 werden neue Features vorgestellt, die die Features und Kommunikationsmethoden für Ihre Benutzer erweitern. Darüber hinaus führt lync Server 2013 Änderungen an vorhandenen Diensten durch, um die für Ihre Organisation verfügbaren Dienste besser zu integrieren und zu erweitern. Im folgenden finden Sie eine Zusammenfassung der Änderungen, die sich auf die Planung und Bereitstellung von lync Server 2013 Edgeserver Diensten auswirken können.

  - **Unterstützung für IPv6-Adressierungs**   lync Server 2013 unterstützt die IPv6-Adressierung für alle Edgeserver Dienste. Wenn Sie IPv6-Adressen für die Schnittstellen über die Konfiguration in Windows Server bereitgestellt haben, können Sie IPv6-Adressen in ihrer Edgeserver Konfiguration über die IP-Adresskonfiguration im Topologie-Generator verwenden.
    
    <div>
    

    > [!IMPORTANT]  
    > Die Verwendung von IPv6-Adressen in lync Server 2013 hängt von der Unterstützung von IPv6 in Routern und Firewalls ab, die Ihre Organisation bereitstellt, sowie von der Unterstützung durch Ihren Internet Dienstanbieter.

    
    </div>

  - **Xmpp (Extensible Messaging and Presence Protocol)**   lync Server 2013 stellt einen vollständig integrierten XMPP-Proxy (auf den Edgeserver bereitgestellt) und ein XMPP-Gateway auf Ihren Front-End-Servern vor. Sie können einen XMPP-Verbund als optionale Komponente bereitstellen. Wenn Sie den XMPP-Proxy und das XMPP-Gateway hinzufügen und konfigurieren, können Ihre Microsoft lync 2013-Benutzer Kontakte von XMPP-basierten Partnern für Chatnachrichten und Anwesenheitsinformationen hinzufügen.
    
    <div>
    

    > [!NOTE]  
    > Derzeit bieten die XMPP-Dienste in lync Server 2013 nur Chatnachrichten und Anwesenheitsinformationen zwischen lync-Clients und XMPP-basierten Kontakten.

    
    </div>

  - **Mobilitätsdienste für mobile Clients**   , die in einem Kunden Update für lync Server 2010 eingeführt wurden, ermöglichen Mobilitätsdienste in lync Server 2013 Microsoft lync Mobile-Clients auf Mobiltelefonen und Tablet-Geräten, die unterstützte Apple IOS-, Android-, Windows Phone-oder Nokia Mobile-Geräte verwenden, zum Ausführen solcher Aktivitäten wie senden und empfangen von Sofortnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit. Zudem unterstützen Mobilgeräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, geschäftlich Anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit.
    
    <div>
    

    > [!NOTE]  
    > Die Mobilitätsdienste verwenden den Reverseproxy und veröffentlichte Dienste, die auf Ihren Front-End-Servern bereitgestellt sind. Änderungen an Edgeservern sind nicht erforderlich.

    
    </div>

  - **Directors sind eine optionale Rolle**   , die die Rolle des Director-Servers in der lync Server 2013-Topologie nicht geändert wurde. Er hostet weiterhin Webdienste, führt eine Vorabauthentifizierung eingehender Benutzeranfragen durch und leitet externe Benutzer an ihren Pool weiter. Wenn Sie den Director von einer empfohlenen Rolle in eine optionale Rolle ändern, verringert sich nicht der Wert des Directors, sondern es wird die Verringerung der Serveranzahl und anderer Hardwareanforderungen (beispielsweise Hardwarelastenausgleichs für den Director) ohne unterstrichen betont. kompromittieren von Features und Funktionen. Da die Front-End-Server dieselbe Aufgabe wie der Director ausführen können und keine Auswirkungen auf die bereitgestellten Dienste haben, können Sie optional Directors bereitstellen, wenn Sie sich für entscheiden. Sie können den Director sicher mit Sicherheit ausschließen, dass die Front-End-Server dieselben Dienste an ihrer Stelle bereitstellen werden.

<div>

## <a name="see-also"></a>Siehe auch


[Planen und Konfigurieren von IPv6 in lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[Planen des Zugriffs durch externe Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Planen des XMPP-Verbunds (Extensible Messaging and Presence Protocol) in lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

