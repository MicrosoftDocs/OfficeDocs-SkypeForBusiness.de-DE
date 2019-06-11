---
title: 'Lync Server 2013: Neue Funktionen für den externen Benutzerzugriff'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d365c4e32c5eaebbd0368cd85b41be7886a59df
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Neue Funktionen für den externen Benutzerzugriff in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-17_

Lync Server 2013 führt neue Features ein, die die Features und Kommunikationsmethoden für Ihre Benutzer erweitern. Darüber hinaus führt lync Server 2013 Änderungen an vorhandenen Diensten durch, um die Dienste, die für Ihre Organisation verfügbar sind, besser zu integrieren und zu erweitern. Es folgt eine Zusammenfassung der Änderungen, die sich auf die Planung und Bereitstellung von lync Server 2013-Edgeserver-Diensten auswirken können.

  - **Unterstützung für die IPv6-Adressierung**   lync Server 2013 unterstützt die IPv6-Adressierung für alle Edgeserver-Dienste. Wenn Sie IPv6-Adressen für die Schnittstellen über die Konfiguration in Windows Server bereitgestellt haben, können Sie IPv6-Adressen in ihrer Edge-Server-Konfiguration über die IP-Adressenkonfiguration im Topologie-Generator verwenden.
    
    <div>
    

    > [!IMPORTANT]  
    > Die Verwendung von IPv6-Adressen in lync Server 2013 hängt von der Unterstützung von IPv6 in Routern und Firewalls ab, die von Ihrer Organisation bereitgestellt werden, sowie vom Support durch Ihren Internet Dienstanbieter.

    
    </div>

  - **Mit dem Extensible Messaging and Presence Protocol (XMPP)**   lync Server 2013 wird ein vollständig integrierter XMPP-Proxy (auf den Edge-Servern bereitgestellt) und ein auf den Front-End-Servern bereitgestelltes XMPP-Gateway eingeführt. Sie können die XMPP-Föderation als optionale Komponente bereitstellen. Durch das Hinzufügen und Konfigurieren des XMPP-Proxys und des XMPP-Gateways können Ihre Microsoft lync 2013-Benutzer Kontakte aus XMPP-basierten Partnern für Sofortnachrichten (im) und Anwesenheitsinformationen hinzufügen.
    
    <div>
    

    > [!NOTE]  
    > Derzeit bieten die XMPP-Dienste in lync Server 2013 nur Sofortnachrichten und Anwesenheitsinformationen zwischen lync-Clients und XMPP-basierten Kontakten.

    
    </div>

  - **Mobilitätsdienste für mobile Clients**   , die in einem Kunden Update für lync Server 2010 eingeführt wurden, Mobilitätsdienste in lync Server 2013 ermöglichen Microsoft lync Mobile-Clients auf Mobiltelefonen und Tablet-Geräten mit unterstützten Apple IOS, Android, Windows Smartphone oder Nokia Mobile Geräte, um solche Aktivitäten wie das Senden und empfangen von Sofortnachrichten, das Anzeigen von Kontakten und das Anzeigen von Anwesenheitsinformationen durchzuführen. Darüber hinaus unterstützen Mobile Geräte einige Enterprise-VoIP-Features, wie beispielsweise klicken, um an einer Konferenz teilzunehmen, über Arbeit zu anrufen, eine Rufnummer zu erreichen, Voicemail und Benachrichtigungen über verpasste Anrufe zu erhalten.
    
    <div>
    

    > [!NOTE]  
    > Die Mobilitätsdienste verwenden den Reverse-Proxy und veröffentlichte Dienste, die auf Ihren Front-End-Servern bereitgestellt werden. Für Edgeserver sind keine Änderungen erforderlich.

    
    </div>

  - **Directors sind eine optionale Rolle**   , die die Rolle des Director-Servers in der lync Server 2013-Topologie nicht geändert hat. Sie hostet weiterhin Webdienste, authentifiziert eingehende Benutzeranforderungen vor und leitet externe Benutzer an Ihren privaten Pool weiter. Das Ändern des Directors von einer empfohlenen Rolle zu einer optionalen Rolle vermindert nicht den Wert des Directors, sondern hebt die Verringerung der Serveranzahl und anderer Hardwareanforderungen (beispielsweise Hardwarelastenausgleichs für den Director) ohne Kompromisse bei Features und Funktionen. Da die Front-End-Server dieselbe Aufgabe wie der Director ausführen können, ohne dass dies Auswirkungen auf die bereitgestellten Dienste hat, können Sie optional Directors bereitstellen, wenn Sie sich dafür entscheiden. Sie können den Director mit Sicherheit ausschließen, dass die Front-End-Server die gleichen Dienste an deren Ort bereitstellen.

<div>

## <a name="see-also"></a>Siehe auch


[Planen und Konfigurieren von IPv6 in lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Planen der erweiterbaren Messaging-und Anwesenheits Protokoll (XMPP)-Föderation in lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

