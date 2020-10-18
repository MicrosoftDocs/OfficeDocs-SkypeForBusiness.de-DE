---
title: Lync Server 2013 Server Rollen
description: Lync Server 2013 Server Rollen.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ee4636e602e5bfb8ce6eacdccb3d190f5728d1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580191"
---
# <a name="server-roles-in-lync-server-2013"></a>Server Rollen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

Jeder Server, auf dem lync Server ausgeführt wird, führt mindestens eine *Serverrolle*aus. Eine Serverrolle ist eine definierte Gruppe von lync Server Funktionalitäten, die von diesem Server bereitgestellt werden. Sie müssen nicht alle verfügbaren Serverrollen in Ihrem Netzwerk bereitstellen. Installieren Sie lediglich die Serverrollen, die erforderliche Funktionalität bereitstellen.

Selbst wenn Sie mit den Serverrollen in lync Server nicht vertraut sind, kann das Planungs Tool Sie auf der Grundlage der gewünschten Features zur optimalen Lösung für die bereitzustellenden Server führen. Dieser Abschnitt bietet eine kurze Übersicht über die Serverrollen und die allgemeinen Funktionen, die diese bereitstellen:

  - Standard Edition-Server

  - Front-End-Server und Back-End-Server

  - Edgeserver

  - Vermittlungsserver

  - Director

  - Front-End-Server für beständigen Chat

  - Beständiger Chatspeicher (Back-End-Server für beständigen Chat)

  - Kompatibilitätsspeicher für beständigen Chat (Back-End-Server zur Kompatibilität für beständigen Chat)

Um Skalierbarkeit und hohe Verfügbarkeit zu bieten, können Sie für die meisten Serverrollen *Pools* mit mehreren Servern bereitstellen, auf denen dieselbe Serverrolle ausgeführt wird. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Bei den meisten pooltypen in lync Server müssen Sie einen Lastenausgleich bereitstellen, um den Datenverkehr zwischen den verschiedenen Servern im Pool zu verteilen. Lync Server unterstützt sowohl Domain Name System (DNS) Lastenausgleich als auch Hardwaregeräte zum Lastenausgleich.

<div>

## <a name="standard-edition-server"></a>Standard Edition-Server

Der Standard Edition-Server eignet sich für kleine Organisationen und für Pilotprojekte großer Organisationen. Viele der Features von lync Server, einschließlich der erforderlichen Datenbanken, können auf einem einzelnen Server ausgeführt werden. Auf diese Weise können Sie lync Server Funktionalität zu niedrigeren Kosten Nutzen, jedoch keine echte Hochverfügbarkeitslösung anbieten.

Standard Edition-Server können Sie Instant Messaging (Sofortnachrichten), Anwesenheitsinformationen, Konferenzen und Enterprise-VoIP verwenden, die alle auf einem einzigen Server auszuführen sind.

Verwenden Sie lync Server Enterprise Edition für eine hoch verfügbare Lösung.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>Front-End-Server und Back-End-Server

In lync Server Enterprise Edition ist der Front-End-Server die Haupt Server Rolle und führt viele grundlegende lync Server Funktionen aus. Die Front-End-Server, zusammen mit den Back-End-Servern, sind die einzigen Server Rollen, die in einer lync Server Enterprise Edition-Bereitstellung erforderlich sind.

Bei einem *Front-End-Pool* handelt es sich um einen Satz von Front-End-Servern mit identischer Konfiguration, die gemeinsam zur Bereitstellung von Diensten für eine gemeinsame Benutzergruppe eingesetzt werden. Ein Pool mit mehreren Servern, auf denen dieselbe Rolle ausgeführt wird, bietet Skalierbarkeit und Failoverfunktionen.

Der Front-End-Server bietet u. a. die folgenden Funktionen:

  - Benutzerauthentifizierung und -registrierung

  - Anwesenheitsinformationen und Visitenkartenaustausch

  - Adressbuchdienste und Verteilerlistenerweiterung

  - Sofortnachrichtenfunktionalität, einschließlich Sofortnachrichtenkonferenzen mit mehreren Teilnehmern

  - Webkonferenzen, PSTN-Einwahlkonferenzen und A/V-Konferenzen (sofern bereitgestellt)

  - Anwendungshosting für beide Anwendungen, die in lync Server enthalten sind (beispielsweise Konferenzzentrale und Reaktionsgruppenanwendung) und Anwendungen von Drittanbietern

  - Optional eine Überwachungsfunktion, um Nutzungsinformationen in Form von Kommunikationsdatensätzen und Daten zu Anruffehlern zu erfassen. Diese Informationen liefern Metriken zur Qualität der Medien (Audio und Video), die Ihr Netzwerk für Enterprise-VoIP-Anrufe und A/V-Konferenzen durchlaufen.

  - Webkomponenten zu unterstützten webbasierten Aufgaben wie Webplaner und Join Launcher.

  - Optional eine Archivierung der Sofortnachrichtenkommunikation und Besprechungsinhalte, um rechtliche Vorgaben einzuhalten. Ausführliche Informationen finden Sie unter [Planning for Archiving in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.
    
    In lync Server 2010 und früheren Versionen waren Überwachung und Archivierung getrennte Server Rollen, die nicht auf Front-End-Server nebeneinander standen.

  - Optional, sofern der beständige Chat aktiviert ist, Webdienste für den beständigen Chat für die Chatroom-Verwaltung und Webdienste für den beständigen Chat für das Hochladen/Herunterladen von Dateien.

Front-End-Pools bilden außerdem den primären Speicher für Benutzer- und Konferenzdaten. Die Informationen zu den einzelnen Benutzern werden auf drei Front-End-Servern im Pool repliziert und auf den Back-End-Servern gesichert.

Darüber hinaus wird in einer Front-End-Pool in der Bereitstellung auch der *zentrale Verwaltungs Server*ausgeführt, der grundlegende Konfigurationsdaten für alle Server verwaltet und bereitstellt, auf denen lync Server ausgeführt wird. Der zentrale Verwaltungs Server bietet auch lync Server-Verwaltungsshell-und Dateiübertragungsfunktionen.

Bei den Back-End-Servern handelt es sich um Datenbankserver mit Microsoft SQL Server, die die Datenbankdienste für die Front-End-Pool bereitstellen. Die Back-End-Server dienen als Sicherungsspeicher für die Benutzer-und Konferenzdaten des Pools und sind die primären Speicher für andere Datenbanken wie die Reaktionsgruppen Datenbank. Sie können einen einzelnen Back-End-Server verwenden, aber eine Lösung, die SQL Server Spiegelung verwendet, wird für ein Failover empfohlen. Back-End-Server führen keine lync Server Software aus.

<div>


> [!IMPORTANT]  
> Es wird nicht empfohlen, abstimmen lync Server Datenbanken mit anderen Datenbanken zu verwenden. Andernfalls können Verfügbarkeit und Leistung beeinträchtigt werden.



</div>

Die in den Datenbanken auf einem Back-End-Server gespeicherten Daten umfassen Anwesenheitsinformationen, die Kontaktlisten der Benutzer, Konferenzdaten (einschließlich dauerhafter Daten zum Zustand aller aktuellen Konferenzen) sowie Konferenzplanungsdaten.

</div>

<div>

## <a name="edge-server"></a>Edgeserver

Edgeserver ermöglicht Ihren Benutzern die Kommunikation und Zusammenarbeit mit Benutzern außerhalb der Firewalls der Organisation. Zu diesen externen Benutzern können die eigenen Benutzer der Organisation gehören, die derzeit extern arbeiten, Benutzer aus Verbundpartner Organisationen und externe Benutzer, die eingeladen wurden, an Konferenzen teilzunehmen, die in ihrer lync Server-Bereitstellung gehostet werden. Edgeserver ermöglicht auch die Konnektivität mit öffentlichen Instant Messaging-Verbindungs Diensten, einschließlich Windows Live, AOL, Yahoo \! und Google Talk.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum heruntergefahren hat. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</P></LI></UL>



</div>

Bei der Bereitstellung des Edgeservers werden außerdem die Mobilitätsdienste aktiviert, mit denen die Lync-Funktionalität auf mobilen Geräten unterstützt wird. Benutzer können mit unterstützten mobilen Geräten (Apple iOS, Android, Windows Phone oder Nokia) Aktionen ausführen wie Senden und Empfangen von Sofortnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit. Zudem unterstützen mobile Geräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, Geschäftlich anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit. Das Mobilitätsfeature unterstützt auch *Pushbenachrichtigungen* für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen. Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist.

Die Edgeserver umfassen außerdem einen vollständig integrierten XMPP-Proxy (Extensible Messaging and Presence Protocol), wobei das XMPP-Gateway auf den Front-End-Servern integriert ist. Sie können diese XMPP-Komponenten so konfigurieren, dass Ihre lync Server 2013-Benutzer Kontakte von XMPP-basierten Partnern (wie Google Talk) für Chatnachrichten und Anwesenheitsinformationen hinzufügen können.

Ausführliche Informationen finden Sie unter [Planning for external User Access in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation.

</div>

<div>

## <a name="mediation-server"></a>Vermittlungsserver

Vermittlungsserver ist eine notwendige Komponente für die Implementierung von Enterprise-VoIP und Einwahlkonferenzen. Vermittlungsserver übersetzt das signalisieren und in einigen Konfigurationen Medien zwischen der internen lync Server-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage oder einem SIP-Trunk (Session Initiation Protocol). Sie können den Vermittlungsserver gemeinsam mit dem Front-End-Sever auf demselben Server oder getrennt in einem eigenständigen Vermittlungsserverpool ausführen.

Ausführliche Informationen finden Sie unter [Vermittlungsserver-Komponente in lync Server 2013](lync-server-2013-mediation-server-component.md) in der Planungsdokumentation.

</div>

<div>

## <a name="director"></a>Director

Directors können lync Server Benutzeranforderungen authentifizieren, aber keine Benutzerkonten zu Hause oder Anwesenheits-oder Konferenzdienste bereitstellen. Directors sind zur Verbesserung der Sicherheit insbesondere in Bereitstellungen nützlich, in denen der Zugriff durch externe Benutzer aktiviert ist. Der Director kann Anforderungen authentifizieren, bevor sie an interne Server weitergeleitet werden. Bei Denial-of-Service-Angriffen enden die Angriffe beim Director und erreichen nicht die Front-End-Server. Ausführliche Informationen finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>Server Rollen für beständigen Chat

Durch den beständigen Chat können Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen, die langfristig erhalten bleiben. Auf dem Front-End-Server für beständigen Chat wird der beständige Chatdienst ausgeführt. Auf dem Back-End-Server für beständigen Chat werden die Chatverlaufsdaten sowie Informationen zu Kategorien und Chatrooms gespeichert. Auf dem optionalen Back-End-Server zur Kompatibilität für den beständigen Chat können Chatinhalte sowie Kompatibilitätsereignisse zum Zweck der Einhaltung von Bestimmungen gespeichert werden.

Server, auf denen lync Server Standard Edition ausgeführt wird, können auch beständigen Chat auf demselben Server ausführen. Sie können den Front-End-Server für beständigen Chat nicht mit Enterprise Edition-Front-End-Server collocate.

Ausführliche Informationen finden Sie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Vermittlungsserver Komponente in lync Server 2013](lync-server-2013-mediation-server-component.md)  


[Planen der Archivierung in lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Planen des Zugriffs durch externe Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Planen von Servern für beständigen Chat in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

