---
title: 'Lync Server 2013: Serverrollen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b8c5b052defcdc1d60ef9900c283f9f50b3809
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Serverrollen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Jeder Server, auf dem lync Server ausgeführt wird, führt mindestens eine *Serverrolle*aus. Eine Serverrolle ist ein definierter Satz von lync Server-Funktionen, die von diesem Server bereitgestellt werden. Sie müssen nicht alle verfügbaren Serverrollen in Ihrem Netzwerk bereitstellen. Installieren Sie lediglich die Serverrollen, die die erforderliche Funktionalität enthalten.

Auch wenn Sie mit den Serverrollen in lync Server nicht vertraut sind, kann das Planungs Tool Sie auf der Grundlage der gewünschten Features zur besten Lösung für die Server führen, die Sie bereitstellen müssen. Dieser Abschnitt enthält eine kurze Übersicht über die Serverrollen und die allgemeinen Features, die Sie bereitstellen:

  - Standard Edition-Server

  - Front-End-Server und Back-End-Server

  - Edgeserver

  - Vermittlungsserver

  - Director

  - Front-End-Server für beständigen Chat

  - Beständiger Chat Speicher (beständiger Chat-Back-End-Server)

  - Kompatibilitäts Speicher für beständigen Chat (Kompatibilitäts-Compliance-Back-End-Server)

Um Skalierbarkeit und hohe Verfügbarkeit zu bieten, können Sie für die meisten Serverrollen *Pools* mit mehreren Servern bereitstellen, auf denen dieselbe Serverrolle ausgeführt wird. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Bei den meisten Typen von Pools in lync Server müssen Sie ein Lastenausgleichsmodul bereitstellen, um den Datenverkehr zwischen den verschiedenen Servern im Pool zu verbreiten. Lync Server unterstützt sowohl DNS (Domain Name System)-Lastenausgleich als auch Hardwarelastenausgleichs.

<div>

## <a name="standard-edition-server"></a>Standard Edition-Server

Der Standard Edition-Server ist für kleine Organisationen und für Pilotprojekte großer Organisationen konzipiert. Damit können viele der Features von lync Server, einschließlich der erforderlichen Datenbanken, auf einem einzelnen Server ausgeführt werden. Dies ermöglicht Ihnen, lync Server-Funktionen zu einem niedrigeren Preis zu nutzen, bietet jedoch keine echte Lösung mit hoher Verfügbarkeit.

Der Standard Edition-Server ermöglicht Ihnen die Verwendung von Instant Messaging (im), Anwesenheitsfunktionen, Konferenzen und Enterprise-VoIP, die alle auf einem Server ausgeführt werden.

Verwenden Sie für eine Lösung mit hoher Verfügbarkeit die lync Server Enterprise Edition.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>Front-End-Server und Back-End-Server

In lync Server Enterprise Edition ist der Front-End-Server die Hauptserver Rolle und führt viele grundlegende lync-Serverfunktionen aus. Der Front-End-Server ist zusammen mit den Back-End-Servern die einzige Server Rolle, die für eine lync Server Enterprise Edition-Bereitstellung erforderlich ist.

Bei einem *Front-End-Pool* handelt es sich um einen Satz von Front-End-Servern, die identisch konfiguriert sind und zusammenarbeiten, um Dienste für eine gemeinsame Gruppe von Benutzern bereitzustellen. Ein Pool mit mehreren Servern, auf denen dieselbe Rolle ausgeführt wird, bietet Skalierbarkeit und Failoverfunktionen.

Der Front-End-Server enthält Folgendes:

  - Benutzerauthentifizierung und-Registrierung

  - Anwesenheitsinformationen und Kontaktkarten Austausch

  - Erweiterung von Adressbuchdiensten und Verteilerlisten

  - Chat-Funktionen, einschließlich mehrteiliger Chat Konferenzen

  - Webkonferenzen, PSTN-Einwahlkonferenzen und a/V-Konferenzen (falls bereitgestellt)

  - Anwendungshosting, für beide Anwendungen, die in lync Server enthalten sind (beispielsweise Konferenzzentrale und reaktionsgruppenanwendung) und Anwendungen von Drittanbietern

  - Optional eine Überwachungsfunktion, um Nutzungsinformationen in Form von Kommunikationsdatensätzen und Daten zu Anruffehlern zu erfassen. Diese Informationen enthalten Metriken zur Qualität der Medien (Audio und Video), die in Ihrem Netzwerk für Enterprise-Sprachanrufe und A/V-Konferenzen durchlaufen werden.

  - Webkomponenten zu unterstützten webbasierten Aufgaben wie Webplaner und Join Launcher.

  - Optional eine Archivierung der Chatnachrichtenkommunikation und Besprechungsinhalte, um rechtliche Vorgaben einzuhalten. Ausführliche Informationen finden Sie unter [Planen der Archivierung in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.
    
    In lync Server 2010 und früheren Versionen waren Überwachung und Archivierung getrennte Server Rollen, nicht auf dem Front-End-Server.

  - Optional, sofern der beständige Chat aktiviert ist, Webdienste für den beständigen Chat für die Chatroom-Verwaltung und Webdienste für den beständigen Chat für das Hochladen/Herunterladen von Dateien.

Front-End-Pools bilden außerdem den primären Speicher für Benutzer- und Konferenzdaten. Die Informationen zu den einzelnen Benutzern werden auf drei Front-End-Servern im Pool repliziert und auf den Back-End-Servern gesichert.

Darüber hinaus führt ein Front-End-Pool in der Bereitstellung auch den *zentralen Verwaltungs Server*aus, der grundlegende Konfigurationsdaten für alle Server mit lync Server verwaltet und bereitstellt. Der zentrale Verwaltungs Server bietet auch die lync Server-Verwaltungsshell und die Dateiübertragungsfunktionen.

Die Back-End-Server sind Datenbankserver mit Microsoft SQL Server, die die Datenbankdienste für den Front-End-Pool bereitstellen. Die Back-End-Server dienen als Sicherungsspeicher für die Benutzer-und Konferenzdaten des Pools und sind die primären Speicher für andere Datenbanken wie die Datenbank der Reaktionsgruppe. Sie können einen einzelnen Back-End-Server verwenden, aber für Failover empfiehlt sich eine Lösung, die die SQL Server-Spiegelung verwendet. Back-End-Server führen keine lync Server-Software aus.

<div>


> [!IMPORTANT]  
> Es wird nicht empfohlen, abstimmen lync Server-Datenbanken mit anderen Datenbanken zu verwenden. Andernfalls können Verfügbarkeit und Leistung beeinträchtigt werden.



</div>

Die in den Datenbanken auf einem Back-End-Server gespeicherten Daten umfassen Anwesenheitsinformationen, die Kontaktlisten der Benutzer, Konferenzdaten (einschließlich dauerhafter Daten zum Zustand aller aktuellen Konferenzen) sowie Konferenzplanungsdaten.

</div>

<div>

## <a name="edge-server"></a>Edgeserver

Edge-Server ermöglicht Ihren Benutzern die Kommunikation und Zusammenarbeit mit Benutzern außerhalb der Firewalls der Organisation. Diese externen Benutzer können die eigenen Benutzer der Organisation einbeziehen, die derzeit an einem externen Standort arbeiten, Benutzer aus Föderationspartner Organisationen und externe Benutzer, die eingeladen wurden, an Konferenzen teilzunehmen, die in ihrer lync Server-Bereitstellung gehostet werden. Edge-Server ermöglicht auch die Konnektivität mit öffentlichen Chat Diensten wie Windows Live, AOL, Yahoo\!und Google Talk.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger, bis der Dienst das Datum beendet hat. Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist. Messenger. Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</P></LI></UL>



</div>

Durch die Bereitstellung von Edge Server werden auch Mobilitätsdienste aktiviert, die die lync-Funktionalität auf mobilen Geräten unterstützen. Benutzer können mit unterstützten mobilen Geräten (Apple iOS, Android, Windows Phone oder Nokia) Aktionen wie Senden und Empfangen von Chatnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit ausführen. Darüber hinaus unterstützen Mobile Geräte einige Enterprise-VoIP-Features, wie beispielsweise klicken, um an einer Konferenz teilzunehmen, über Arbeit anzurufen, eine Rufnummer zu erreichen, Voicemail und verpasste Anrufe zu tätigen. Die Mobilitätsfunktion unterstützt auch *Pushbenachrichtigungen* für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen. Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist.

Die Edgeserver umfassen außerdem einen vollständig integrierten XMPP-Proxy (Extensible Messaging and Presence Protocol), wobei das XMPP-Gateway auf den Front-End-Servern integriert ist. Sie können diese XMPP-Komponenten so konfigurieren, dass Ihre lync Server 2013-Benutzer Kontakte aus XMPP-basierten Partnern (wie Google Talk) für Sofortnachrichten und Anwesenheitsinformationen hinzufügen können.

Ausführliche Informationen finden Sie unter [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation.

</div>

<div>

## <a name="mediation-server"></a>Vermittlungsserver

Mediation Server ist eine notwendige Komponente für die Implementierung von Enterprise-VoIP und Einwahlkonferenzen. Der Vermittlungs Server übersetzt Signalisierungen und in einigen Konfigurationen Medien zwischen Ihrer internen lync Server-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network), IP-PBX oder einem SIP-Trunk (Session Initiation Protocol). Sie können den Vermittlungsserver auf dem gleichen Server wie dem Front-End-Server ausführen oder in einen eigenständigen vermittlungsserverpool unterteilt.

Ausführliche Informationen finden Sie in der Planning-Dokumentation unter [Mediation Server Component in lync Server 2013](lync-server-2013-mediation-server-component.md) .

</div>

<div>

## <a name="director"></a>Director

Directors können lync Server-Benutzeranforderungen authentifizieren, jedoch keine Benutzerkonten oder Anwesenheits-oder Konferenzdienste. Directors sind zur Verbesserung der Sicherheit insbesondere in Bereitstellungen nützlich, in denen der Zugriff durch externe Benutzer aktiviert ist. Der Director kann Anforderungen authentifizieren, bevor sie an interne Server weitergeleitet werden. Bei Denial-of-Service-Angriffen enden die Angriffe beim Director und erreichen nicht die Front-End-Server. Ausführliche Informationen finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>Server Rollen für beständigen Chat

Durch den beständigen Chat können Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen, die langfristig erhalten bleiben. Auf dem Front-End-Server für beständigen Chat wird der beständige Chatdienst ausgeführt. Auf dem Back-End-Server für beständigen Chat werden die Chatverlaufsdaten sowie Informationen zu Kategorien und Chatrooms gespeichert. Auf dem optionalen Back-End-Server zur Kompatibilität für den beständigen Chat können Chatinhalte sowie Kompatibilitätsereignisse zum Zweck der Einhaltung von Bestimmungen gespeichert werden.

Auf Servern mit lync Server Standard Edition kann auch beständiger Chat auf demselben Server ausgeführt werden. Der Front-End-Server für beständigen Chat mit Enterprise Edition-Front-End-Server kann nicht collocate werden.

Ausführliche Informationen finden Sie unter [Planen des beständigen Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Vermittlungsserver Komponente in lync Server 2013](lync-server-2013-mediation-server-component.md)  


[Planen der Archivierung in Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Szenarien für den Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

