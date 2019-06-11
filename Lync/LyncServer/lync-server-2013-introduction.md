---
title: 'Lync Server 2013: Einführung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df182c8d58d6f1e60b164fbb28299945f6a8cba3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Einführung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Lync Server 2013 und seine Client Software, wie lync 2013, ermöglichen es Ihren Benutzern, auf neue Weise eine Verbindung herzustellen und unabhängig von ihrem physikalischen Standort in Verbindung zu bleiben. Lync und lync Server vereinen die unterschiedlichen Möglichkeiten, wie Personen in einer einzelnen Clientschnittstelle kommunizieren, als einheitliche Plattform bereitgestellt werden und über eine einzige Verwaltungsinfrastruktur verwaltet werden.

Diese Tabelle und die folgenden Abschnitte veranschaulichen die wichtigsten Funktionsgruppen oder *Arbeits*Auslastungen, die lync Server für Ihre Benutzer bereitstellt.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Workload</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chat und Anwesenheit</p></td>
<td><p>Instant Messaging (im) und Anwesenheitsinformationen helfen Ihren Benutzern, sich gegenseitig effizient und effektiv zu finden und zu kommunizieren.</p>
<p>Chat bietet eine Instant Messaging-Plattform mit Konversationsprotokoll und unterstützt die Konnektivität öffentlicher Chats mit Benutzern öffentlicher Chat Netzwerke wie MSN/Windows Live, Yahoo!, AOL und Google Talk.</p>
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
<p>Anwesenheitsinformationen und zeigt die persönliche Verfügbarkeit und Bereitschaft des Benutzers zur Kommunikation über die Verwendung von allgemeinen Zuständen wie " <strong>verfügbar</strong> " oder " <strong>beschäftigt</strong>" sowie detailliertere Zustände wie " <strong>seien Sie gleich zurück</strong> " und "nicht stören" an. <strong> </strong>. Diese umfangreichen Anwesenheitsinformationen ermöglichen es anderen Benutzern, sofort effektive Kommunikationsentscheidungen zu treffen.</p></td>
</tr>
<tr class="even">
<td><p>Konferenzen</p></td>
<td><p>Lync Server bietet Unterstützung für Chat Konferenzen, Audiokonferenzen, Webkonferenzen, Videokonferenzen und Anwendungsfreigabe sowohl für geplante als auch für spontane Besprechungen. Alle diese Besprechungstypen werden mit einem einzelnen Client unterstützt. Lync Server unterstützt auch Einwahlkonferenzen, damit Benutzer von PSTN-Telefonen (Public Switched Telephone Network) am Audioteil von Konferenzen teilnehmen können.</p>
<p>Konferenzen können nahtlos in Echtzeit geändert und vergrößert werden. So kann beispielsweise eine einzelne Konferenz nur als Sofortnachricht zwischen wenigen Benutzern beginnen und zu einer Audiokonferenz mit Desktopfreigabe und einer größeren Zielgruppe sofort, einfach und ohne Unterbrechung des Konversations Flusses eskaliert werden.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise-VoIP</p></td>
<td><p><em>Enterprise</em> -VoIP ist das VoIP-Angebot (Voice over Internet Protocol) in lync Server. Sie bietet eine Sprachoption zum verbessern oder ersetzen herkömmlicher PBX-Systeme (Private Branch Exchange). Zusätzlich zu den vollständigen Telefoniefunktionen einer IP-Telefonanlage ist Enterprise-VoIP mit umfangreichen Anwesenheitsfunktionen, Chats, Zusammenarbeit und Besprechungen integriert. Funktionen wie Anrufannahme, halten, fortsetzen, übertragen, weiterleiten und umleiten werden direkt unterstützt, während personalisierte Kurzwahl-Tasten durch Kontaktlisten ersetzt werden und die automatische Sprechanlage durch Chat ersetzt wird.</p>
<p>Enterprise-VoIP unterstützt eine höhere Verfügbarkeit durch Anrufsteuerung (Anrufannahme Steuerung), Überlebensfähigkeit von Zweigstellen und erweiterte Optionen für die Datensicherheit.</p></td>
</tr>
<tr class="even">
<td><p>Unterstützung für Remotebenutzer</p></td>
<td><p>Sie können vollständige lync Server-Funktionen für Benutzer bereitstellen, die sich derzeit außerhalb der Firewalls Ihrer Organisation <em></em> befinden, indem Sie Server mit dem Namen Edgeserver bereitstellen, um eine Verbindung für diese Remotebenutzer bereitzustellen. Diese Remotebenutzer können mithilfe eines PCs, auf dem lync 2013 installiert ist, dem Smartphone oder einem Webinterface eine Verbindung mit Konferenzen herstellen.</p>
<p>Durch die Bereitstellung von Edgeserver <em></em> können Sie auch mit Partner-oder Anbieter Organisationen zusammenarbeiten. Eine Verbundbeziehung ermöglicht es Ihren Benutzern, Verbundbenutzer in ihre Kontaktlisten zu versetzen, Anwesenheitsinformationen und Sofortnachrichten mit diesen Benutzern zu austauschen und Sie zu Audioanrufen, Videoanrufen und Konferenzen einzuladen.</p></td>
</tr>
<tr class="odd">
<td><p>Support für mobile Clients</p></td>
<td><p>Außerdem können Ihre Benutzer mit den lync Server-Mobilitätsdiensten auf die lync-Funktionalität zugreifen, wenn Sie unterstützte Apple IOS-, Android-, Windows Phone-oder Nokia Mobile-Geräte verwenden und solche Aktivitäten wie das Senden und empfangen von Sofortnachrichten, das Anzeigen von Kontakten ausführen. und Anwesenheitsanzeige. Darüber hinaus unterstützen Mobile Geräte einige Enterprise-VoIP-Features, wie beispielsweise klicken, um an einer Konferenz teilzunehmen, über Arbeit anzurufen, eine Rufnummer zu erreichen, Voicemail und verpasste Anrufe zu tätigen. Push-Benachrichtigungen werden auch für mobile Geräte unterstützt, die Anwendungen, die im Hintergrund ausgeführt werden, nicht unterstützen.</p></td>
</tr>
<tr class="even">
<td><p>Integration mit anderen Produkten</p></td>
<td><p>Lync Server ist in mehrere andere Produkte integriert, um Ihren Benutzern und Administratoren zusätzliche Vorteile zu bieten.</p>
<p>Besprechungstools sind in Outlook integriert, damit die Organisatoren eine Besprechung planen oder eine spontane Konferenz mit einem einzigen Mausklick starten können, damit Sie den Teilnehmern einfach beitreten können.</p>
<p>Anwesenheitsinformationen sind in Outlook und SharePoint integriert.</p>
<p>Exchange Unified Messaging (um) bietet mehrere Integrationsfeatures. Benutzer können sehen, ob Sie über neue Voicemails in lync Server verfügen. Sie können in der Outlook-Nachricht auf eine Wiedergabe-Schaltfläche klicken, um die Voicemail zu hören, oder eine Transkription der Voicemail in der Benachrichtigungsmeldung anzeigen.</p>
<p>Darüber hinaus ermöglicht das Ausführen von lync Server 2013 mit Exchange 2013 verschiedene neue Features, wie beispielsweise ein einheitlicher Kontaktspeicher, auf den Clients beider Produkte zugreifen können, sowie Fotos mit hoher Auflösung für Kontakte, die in der Exchange 2013-Datenbank gespeichert sind.</p></td>
</tr>
<tr class="odd">
<td><p>Einfache Bereitstellung</p></td>
<td><p>Um Ihnen beim Planen und Bereitstellen von Servern und Clients zu helfen, stellt lync Server den Topologie-Generator bereit.</p>
<p>Der Topologie-Generator ist eine Installationskomponente von lync Server. Sie verwenden den Topologie-Generator zum Erstellen, anpassen und Veröffentlichen Ihrer geplanten Topologie. Darüber hinaus wird Ihre Topologie überprüft, bevor Sie mit Server Installationen beginnen. Wenn Sie lync Server auf einzelnen Servern installieren, wird der Server von dem Installationsprogramm wie in der Topologie weitergeleitet bereitgestellt.</p></td>
</tr>
<tr class="even">
<td><p>Einfache Verwaltung</p></td>
<td><p>Nachdem Sie lync Server bereitgestellt haben, bietet es die folgenden leistungsfähigen und optimierten Verwaltungstools:</p>
<ul>
<li><p>Zentrales Konfigurationsmanagement, mit dem Sie Änderungen zentral verwalten und diese schnell auf die gesamte Bereitstellung replizieren können.</p></li>
<li><p>Lync Server Control Panel, eine Web-basierte grafische Benutzeroberfläche für Administratoren. Mit dieser webbasierten Benutzeroberfläche können lync Server-Administratoren ihre Systeme von einem beliebigen Standort im Unternehmensnetzwerk aus verwalten, ohne dass spezielle Verwaltungssoftware auf ihren Computern installiert werden muss.</p></li>
<li><p>Befehlszeilen-Verwaltungstool der lync Server-Verwaltungsshell, das auf der Windows PowerShell-Befehlszeilenschnittstelle basiert. Es bietet einen umfassenden Befehlssatz für die Verwaltung aller Aspekte des Produkts und ermöglicht es lync Server-Administratoren, sich wiederholende Aufgaben mithilfe eines vertrauten Tools zu automatisieren.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Während die Chat-und Anwesenheitsfeatures automatisch in jeder lync Server-Bereitstellung installiert werden, können Sie auswählen, ob Konferenz, Enterprise-VoIP und Remotebenutzerzugriff bereitgestellt werden sollen, um die Bereitstellung an die Anforderungen Ihrer Organisation anzupassen.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Chat und Anwesenheit in Lync Server 2013](lync-server-2013-im-and-presence.md)

  - [Konferenzen in Lync Server 2013](lync-server-2013-conferencing.md)

  - [Enterprise-VoIP in Lync Server 2013](lync-server-2013-enterprise-voice.md)

  - [Skalierbarkeit mit Lync Server 2013](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

