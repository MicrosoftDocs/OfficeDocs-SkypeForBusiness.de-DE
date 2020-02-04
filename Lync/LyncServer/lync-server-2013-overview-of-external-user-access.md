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
ms.openlocfilehash: 1007dfb330aaa21dbac269f606102c51712c9bf7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Übersicht über den Zugriff durch externe Benutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

In dieser Dokumentation verwenden wir den Begriff *externer Benutzer* , um eine große Kategorie von Benutzern zu definieren, die von außerhalb der Firewall mit ihren lync Server 2013-und lync 2013-Benutzern kommunizieren. Externe Benutzer, die Sie für die Kommunikation mit lync Server 2013 mit internen Benutzern autorisieren können (das heißt, Benutzer, die sich bei lync Server innerhalb der Firewall anmelden), können Folgendes umfassen:

  - **Remote Benutzer**   Benutzer Ihrer Organisation, die sich von außerhalb der Firewall bei lync Server anmelden.

  - **Benutzer von Verbundbenutzern**   , die über ein Konto bei einem vertrauenswürdigen Kunden oder einer Partnerorganisation wie lync Server 2010, lync Server 2013 oder Office Communications Server 2007 R2 verfügen Federated-Benutzer können auch Mitglieder von definierten Partnerorganisationen sein, die mithilfe des XMPP-Proxys auf dem Edge-Server und dem XMPP-Gateway auf dem Front-End-Server oder-Pool über den XMPP-Proxy und das Presence-Protokoll (XMPP) verfügen. Eine definierte Vertrauensstellung, die so genannte Föderation, bezieht sich nicht auf eine Vertrauensstellung von Active Directory-Domänendiensten und hängt nicht davon ab.
    
    <div>
    

    > [!NOTE]  
    > Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.

    
    </div>

  - **Öffentliche Instant Messaging-Konnektivität Benutzer**   Kontakte, die Ihre Benutzer über öffentliche Instant Messaging-Verbindungsdienste einrichten (Windows Live, Yahoo\! und AOL).

  - **Benutzer von mobilen Benutzern**   , die Mitglieder Ihrer Organisation sind, die ein Smartphone oder ein Tablet mit einem lync Mobile-Client verwenden, sich bei ihrer internen Bereitstellung anmelden und mit den anderen Benutzergruppen kommunizieren können. Der Mobile Benutzer verwendet Mobilitätsdienste, die über den Reverse Proxy veröffentlicht werden, um auf die interne Bereitstellung zuzugreifen. Details zu den Features und Funktionen, die für lync Mobile verfügbar sind, finden Sie in [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777)den Vergleichstabellen für mobile Clients unter.

  - **Anonyme Benutzer**   Benutzer, die nicht über ein Benutzerkonto in den Active Directory-Domänendiensten Ihrer Organisation oder in einer unterstützten Föderationsdomäne verfügen, aber Einladungen zur Remote Teilnahme an einer lokalen Konferenz erhalten haben.

Ihre Edge-Bereitstellung bietet externen Zugriff für die folgenden Kommunikationsarten:

  - **Im-und Anwesenheits**   autorisierte externe Benutzer können an Chat Unterhaltungen und Konferenzen teilnehmen, und Sie können Informationen über den Anwesenheitsstatus der anderen Person erhalten. Benutzer von öffentlichen Chat Dienstanbietern können an Chat Unterhaltungen mit einzelnen lync Server-Benutzern in Ihrer Organisation teilnehmen und auf Anwesenheitsinformationen zugreifen, aber Sie können mit lync Server nicht an Chat Konferenzen teilnehmen. Es handelt sich um eine strikte Peer-to-Peer-Kommunikation. Die Dateiübertragung wird für Benutzer von öffentlichen Chat Dienstanbietern nicht unterstützt, und Audio/Video in Peer-zu-Peer-Kommunikation wird für Windows Messenger 2011-Benutzer, aber nicht für andere Benutzer von öffentlichen Chatdienst Anbietern unterstützt.
    
    Sowohl SIP-als auch XMPP-Protokolle werden unterstützt. Informationen zum Bereitstellen von Diensten für XMPP finden Sie unter [Planen von SIP, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - **Autorisierte Webkonferenzen**   externe Benutzer können an Konferenzen teilnehmen, die in ihrer lync Server-Bereitstellung gehostet werden. Remote Benutzer, verbundene Benutzer und anonyme Benutzer können für die Teilnahme an Webkonferenzen aktiviert werden, aber öffentliche Chat-Benutzer können nicht an Konferenzen teilnehmen. Je nach den von Ihnen ausgewählten Optionen können Webkonferenzen aktivierte Benutzer an der Desktop-und Anwendungsfreigabe teilnehmen und als Besprechungsorganisatoren oder Referenten fungieren.

  - **A/V-Konferenz**   autorisierte externe Benutzer können an Audio-und Videokonferenzen teilnehmen, die ihre lync Server-Bereitstellung hostet. Audio/Video in der Peer-to-Peer-Kommunikation wird für Windows Messenger 2011-Benutzer, aber nicht für andere Benutzer von öffentlichen Chat Dienstanbietern unterstützt.

Um die Kommunikation zu steuern, können Sie eine oder mehrere Richtlinien konfigurieren, die definieren, wie Benutzer innerhalb und außerhalb Ihrer Organisation miteinander kommunizieren. Sie können auch Einstellungen konfigurieren und Richtlinien für einzelne interne Benutzer oder bestimmte Typen externer Benutzer anwenden, um die Kommunikation mit externen Benutzern zu steuern.

Lync Server 2013-Rollen, die für den externen Zugriff verwendet werden:

**Edgeserver**   der Edgeserver ist ein Server oder ein Pool von Servern, auf denen die Dienste ausgeführt werden, die den externen Zugriff auf Chat und Anwesenheit, Konferenzen, Audio/Video und andere Medien (beispielsweise Dateiübertragungsdienste) ermöglichen. Optional können Sie den Edgeserver für die Föderation mit anderen lync Server-oder Office Communications Server 2007 R2-Bereitstellungen und anderen XMPP-Bereitstellungen konfigurieren. Das optionale Feature für die öffentliche Chat Verbindung wird über den Edgeserver aktiviert und konfiguriert.

**Director**   der Director ist ein optionaler Server-oder Serverpool, auf dem die lync Server 2013 Director-Rolle ausgeführt wird, mit der Benutzeranforderungen vorab authentifiziert und Anforderungen an den Start-Front-End-Server oder den Front-End-Pool der Benutzer weitergeleitet werden, jedoch keine Benutzerkonten zu Hause sind.

**Reverse Proxy**   ein Reverseproxy ist ein allgemeiner Ausdruck für spezialisierte Server, die im internen Netzwerk verfügbare Ressourcen veröffentlichen und Informationen für Clients aus der veröffentlichten Ressource abrufen. Lync Server 2013 verwendet den Reverseproxy zum Veröffentlichen einer Reihe von Features, wie Konferenz Besprechungen, Konferenz-Join-Speicherorte, Adressbuch, Erweiterung der Verteilerliste, Herunterladen von Besprechungsinhalten, Geräte Updates, Mobilitätsdienste und vieles mehr. Alle Reverse-Proxys, die die Anforderungen für die Veröffentlichung der erforderlichen Ressourcenspeicherorte erfüllen können, können verwendet werden. Microsoft Forefront Threat Management Gateway (TMG) 2010 wird als Beispiel verwendet, um die Veröffentlichungsregeln zu illustrieren, aber Forefront TMG 2010 ist nicht erforderlich.

<div>


> [!IMPORTANT]  
> Lync Server 2013 unterstützt IPv4 und IPv6. Windows Server&nbsp;2008&nbsp;R2, Windows Server 2012 und Windows Server 2012 R2 verwenden einen dualen Stapel, der gleichzeitig IPv4 und IPv6 verwenden kann. Dies ist wichtig, da eine Bereitstellung, die von IPv4 zu IPv6 wechselt, übergangsweise ist. IPv4 kann in einigen Bereichen unterstützt werden, in denen in anderen Bereichen der Bereitstellung IPv6 verwendet werden kann. Dies ist besonders wichtig, wenn es um das Internet und interne Bereitstellungen geht. Externe Clients müssen über den Reverse-Proxy kommunizieren, um Dienste wie Mobilität, Besprechungen, Adressbuch Download und andere zu verwenden. Derzeit unterstützen Forefront Threat Management Gateway 2010 und Internet Security and Acceleration Server 2006 keine IPv6-Adressierung, unabhängig von der Betriebssystemversion, auf der Sie bereitgestellt werden. Sie müssen in Bezug auf ihre Verwendung von IPv6 und IPv4 entsprechend planen, während Sie sich auf externe Clients beziehen.



</div>

</div>

<span> </span>

</div>

</div>

</div>

