---
title: 'Lync Server 2013: Übersicht über den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf3d85b7e3eae8839e3e65e02dde5955c8145c64
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Übersicht über den Zugriff durch externe Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

In dieser Dokumentation wird der Begriff *externer Benutzer* verwendet, um eine große Gruppe von Benutzern zu definieren, die mit Ihrem lync Server 2013 kommunizieren und Benutzer außerhalb der Firewall lync 2013. Externe Benutzer, die Sie autorisieren können, lync Server 2013 mit internen Benutzern zu kommunizieren (also Benutzer, die sich bei lync Server innerhalb der Firewall anmelden) können Folgendes umfassen:

  - **Remote Benutzer**   Benutzer Ihrer Organisation, die sich bei lync Server von außerhalb der Firewall anmelden.

  - **Benutzer von Verbundbenutzern**   , die über ein Konto mit einem vertrauenswürdigen Kunden oder einer Partnerorganisation verfügen, beispielsweise lync Server 2010, lync Server 2013 oder Office Communications Server 2007 R2. Partnerverbund Benutzer können auch mithilfe von xmpp (Extensible Messaging and Presence Protocol) über den XMPP-Proxy auf dem Edgeserver-und XMPP-Gateway im Front-End-Server oder Poolmitglied einer definierten Partnerorganisation sein. Eine definierte Vertrauensstellung, die als Verbund bezeichnet wird, bezieht sich nicht auf eine Active Directory-Domänendienste Vertrauensstellung und hängt nicht von dieser Beziehung ab.
    
    <div>
    

    > [!NOTE]  
    > Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.

    
    </div>

  - **Öffentliche Instant Messaging-Konnektivität Benutzer**   Kontakte, die Ihre Benutzer über öffentliche Instant Messaging-Verbindungsdienste einrichten (Windows Live, Yahoo\! und AOL).

  - **Benutzer von mobilen Benutzern**   , die Mitglieder Ihrer Organisation sind, die ein Smartphone oder ein Tablet mit einem mobilen lync-Client verwenden, melden sich bei ihrer internen Bereitstellung an und können mit den anderen Klassen von Benutzern kommunizieren. Der Mobile Benutzer verwendet Mobilitätsdienste, die über den Reverseproxy veröffentlicht werden, um auf die interne Bereitstellung zuzugreifen. Ausführliche Informationen zu den verfügbaren Features und Funktionen von lync Mobile finden Sie in [https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777)den Vergleichstabellen für mobile Clients unter.

  - **Anonyme Benutzer**   Benutzer, die kein Benutzerkonto im Active Directory-Domänendienste Ihrer Organisation oder in einer unterstützten Verbunddomäne haben, jedoch Einladungen zur Remote Teilnahme an einer lokalen Konferenz erhalten haben.

Die Edge-Bereitstellung bietet externen Zugriff für die folgenden Arten von Kommunikation:

  - **Im-und Anwesenheits**   autorisierte externe Benutzer können an Chat Unterhaltungen und Konferenzen teilnehmen, und Sie können Informationen über den Anwesenheitsstatus eines anderen Benutzers abrufen. Benutzer von öffentlichen Sofortnachrichten-Dienstanbietern können an Chat Unterhaltungen mit einzelnen lync Server-Benutzern in Ihrer Organisation teilnehmen und auf Anwesenheitsinformationen zugreifen, aber Sie können nicht an Chat Konferenzen mit mehreren Teilnehmern teilnehmen, die lync Server verwenden. Es handelt sich um eine strikte Peer-zu-Peer-Kommunikation. Die Dateiübertragung wird für Benutzer von öffentlichen Sofortnachrichten-Dienstanbietern nicht unterstützt, und Audio/Video in Peer-zu-Peer-Kommunikation wird für Windows Messenger 2011-Benutzer, aber nicht für andere Benutzer von öffentlichen Sofortnachrichten-Dienstanbietern unterstützt.
    
    Sowohl SIP-als auch XMPP-Protokolle werden unterstützt. Informationen zum Bereitstellen von Diensten für XMPP finden Sie unter [Planning for SIP, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - **Webkonferenz**   autorisierte externe Benutzer können an Konferenzen teilnehmen, die in ihrer lync Server-Bereitstellung gehostet werden. Remotebenutzern, Verbundbenutzern und anonymen Benutzern kann die Teilnahme an Webkonferenzen ermöglicht werden, Benutzer öffentlicher Sofortnachrichtendienste können jedoch nicht an Konferenzen teilnehmen. Je nach den ausgewählten Optionen können für Webkonferenzen aktivierte Benutzer an der Desktop- und Anwendungsfreigabe teilnehmen und als Besprechungsorganisatoren oder Referenten agieren.

  - **A/V-Konferenzen**   autorisierte externe Benutzer können an Audio-und Videokonferenzen teilnehmen, die ihre lync Server-Bereitstellung hostet. Audio/Video in Peer-zu-Peer-Kommunikation wird für Windows Messenger 2011-Benutzer, jedoch nicht für andere Benutzer von öffentlichen Sofortnachrichten-Dienstanbietern unterstützt.

Um die Kommunikation zu steuern, können Sie eine oder mehrere Richtlinien konfigurieren, die definieren, wie Benutzer innerhalb und außerhalb Ihrer Organisation miteinander kommunizieren. Außerdem können Sie für einzelne interne Benutzer oder für bestimmte Typen externer Benutzer Einstellungen konfigurieren und Richtlinien anwenden, um die Kommunikation mit externen Benutzern zu steuern.

Lync Server 2013 Rollen, die für die Bereitstellung von externem Zugriff verwendet werden:

**Edgeserver**   das Edgeserver ist ein Server oder ein Pool von Servern, auf denen die Dienste ausgeführt werden, die externen Zugriff auf Sofortnachrichten und Anwesenheitsinformationen, Konferenzen, Audio/Video und andere Medien (beispielsweise Dateiübertragungsdienste) ermöglichen. Optional können Sie die Edgeserver so konfigurieren, dass Sie mit anderen lync Server-oder Office Communications Server 2007 R2-Bereitstellungen und anderen XMPP-Bereitstellungen zusammenfasst. Das optionale Feature für die Verbindung mit öffentlichen Chat Diensten wird über den Edgeserver aktiviert und konfiguriert.

**Director**   der Director ist ein optionaler Server-oder Serverpool, der die lync Server 2013 Director-Rolle ausführt, die Benutzeranforderungen vorab authentifiziert und Anforderungen an die Start Front-End-Server oder Front-End-Pool der Benutzer weiterleitet, jedoch keine Benutzerkonten aufweist.

**Reverse Proxy**   ein Reverseproxy ist ein allgemeiner Begriff für spezielle Server, die im internen Netzwerk verfügbare Ressourcen veröffentlichen und Informationen für Clients aus der veröffentlichten Ressource abrufen. Lync Server 2013 verwendet den Reverseproxy zum Veröffentlichen einer Reihe von Features wie Konferenz Besprechungen, Konferenzteilnehmer Speicherorte, Adressbuch, Verteilerlistenerweiterung, Herunterladen von Besprechungsinhalten, Geräte Updates, Mobilitätsdiensten und vielem mehr. Jeder Reverseproxy, der die Anforderungen für die Veröffentlichung der erforderlichen Ressourcenspeicherorte erfüllen kann, kann verwendet werden. Microsoft Forefront Threat Management Gateway (TMG) 2010 wird als Beispiel verwendet, um die erforderlichen Veröffentlichungsregeln zu illustrieren, aber Forefront TMG 2010 ist nicht erforderlich.

<div>


> [!IMPORTANT]  
> Lync Server 2013 unterstützt sowohl IPv4 als auch IPv6. Windows Server&nbsp;2008&nbsp;R2, Windows Server 2012 und Windows Server 2012 R2 verwenden einen dualen Stapel, der sowohl IPv4 als auch IPv6 gleichzeitig verwenden kann. Dies ist aufgrund der Übergangs Natur einer Bereitstellung, die von IPv4 zu IPv6 wechselt, wichtig. IPv4 kann in einigen Bereichen unterstützt werden, in denen in anderen Bereichen der Bereitstellung IPv6 verwendet werden kann. Dies ist besonders wichtig, wenn es um das Internet und interne Bereitstellungen geht. Externe Clients müssen über den Reverseproxy kommunizieren, um Dienste wie Mobilität, Besprechungen, Adressbuch Download und andere zu verwenden. Derzeit unterstützen Forefront Threat Management Gateway 2010 und Internet Security and Acceleration Server 2006 keine IPv6-Adressierung, unabhängig von der Betriebssystemversion, in der Sie bereitgestellt werden. Sie müssen entsprechend in Bezug auf ihre Verwendung von IPv6 und IPv4 planen, da diese sich auf externe Clients beziehen.



</div>

</div>

<span> </span>

</div>

</div>

</div>

