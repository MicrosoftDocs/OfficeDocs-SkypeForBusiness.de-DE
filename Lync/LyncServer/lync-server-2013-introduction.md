---
title: Lync Server 2013 Einführung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 892985a42e11a7f0b3466ad66e35ad5cf6c29ec4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Einführung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

Lync Server 2013 und seine Client Software, beispielsweise lync 2013, ermöglichen es Ihren Benutzern, auf neue Weise eine Verbindung herzustellen und unabhängig von Ihrem physischen Standort eine Verbindung zu halten. Lync und lync Server bieten die unterschiedlichen Möglichkeiten, die Personen in einer einzelnen Clientschnittstelle kommunizieren, werden als einheitliche Plattform bereitgestellt und über eine einzige Verwaltungsinfrastruktur verwaltet.

In dieser Tabelle und den folgenden Abschnitten werden die wichtigsten Funktionsgruppen oder *Arbeitsauslastungen*veranschaulicht, die lync Server für Ihre Benutzer bereitstellt.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Arbeitslast</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Instant Messaging und Anwesenheit</p></td>
<td><p>Instant Messaging (Sofortnachrichten) und Anwesenheitsinformationen helfen Ihren Benutzern, effizient und effektiv miteinander zu kommunizieren.</p>
<p>IM bietet eine Instant Messaging-Plattform mit Unterhaltungs Historie und unterstützt öffentliche Chat-Verbindungen mit Benutzern öffentlicher Chat Netzwerke wie MSN/Windows Live, Yahoo!, AOL und Google Talk.</p>
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
<p>Anwesenheitsinformationen und zeigt die persönliche Verfügbarkeit und Bereitschaft des Benutzers zur Kommunikation durch die Verwendung von allgemeinen Zuständen wie <strong>available</strong> oder <strong>busy</strong>sowie ausführlichere Status wie " <strong>gleich wieder</strong> " und " <strong>nicht stören</strong>" an. Durch diese umfangreichen Anwesenheitsinformationen können andere Benutzer sofort effektive Kommunikationsentscheidungen treffen.</p></td>
</tr>
<tr class="even">
<td><p>Konferenzen</p></td>
<td><p>Lync Server umfasst Unterstützung für Chat Konferenzen, Audiokonferenzen, Webkonferenzen, Videokonferenzen und Anwendungsfreigaben für geplante und spontane Besprechungen. Alle diese Besprechungstypen werden mit einem einzelnen Client unterstützt. Lync Server unterstützt auch Einwahlkonferenzen, sodass Benutzer von Telefon Festnetz-Telefonen am Audioteil von Konferenzen teilnehmen können.</p>
<p>Konferenzen können nahtlos geändert und in Echtzeit erweitert werden. Beispielsweise kann eine einzelne Konferenz nur als Sofortnachrichten zwischen einigen wenigen Benutzern gestartet werden, und Sie können sofort, einfach und ohne Unterbrechung des Unterhaltungs Flusses zu einer Audiokonferenz mit Desktopfreigabe und einer größeren Zielgruppe eskalieren.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise-VoIP</p></td>
<td><p><em>Enterprise</em> -VoIP ist das VoIP-Angebot (Voice over Internet Protocol) in lync Server. Sie bietet eine Sprachoption zum Erweitern oder ersetzen herkömmlicher Nebenstellenanlagen (Private Branch Exchange, Nebenstellenanlage). Zusätzlich zu den vollständigen Telefoniefunktionen einer IP-Nebenstellenanlage ist Enterprise-VoIP in umfangreiche Anwesenheitsinformationen, Chats, Zusammenarbeit und Besprechungen integriert. Funktionen wie Anruf Antwort, halten, fortsetzen, übertragen, weiterleiten und umleiten werden direkt unterstützt, während personalisierte Kurzwahl-Tasten durch Kontaktlisten ersetzt werden und die automatische Sprechanlage durch Sofortnachrichten ersetzt wird.</p>
<p>Enterprise-VoIP unterstützt hohe Verfügbarkeit über die Anrufsteuerung (Call Admission Control, CAC), die Überlebensfähigkeit von Zweigstellen und erweiterte Optionen für die Ausfallsicherheit von Daten.</p></td>
</tr>
<tr class="even">
<td><p>Unterstützung für Remotebenutzer</p></td>
<td><p>Sie können vollständige lync Server Funktionalität für Benutzer bereitstellen, die sich derzeit außerhalb der Firewalls Ihrer Organisation befinden, indem Sie Server mit dem Namen <em>Edgeserver</em> bereitstellen, um eine Verbindung für diese Remotebenutzer bereitzustellen. Diese Remotebenutzer können über einen Computer mit lync 2013, auf dem das Telefon oder eine Weboberfläche installiert ist, eine Verbindung zu Konferenzen herstellen.</p>
<p><em>Durch die bereit</em> Stellung von Edge-Servern können Sie auch mit Partner-oder Herstellerorganisationen zusammenarbeiten. Eine Verbundbeziehung ermöglicht es Ihren Benutzern, Verbundbenutzer in ihre Kontaktlisten einzufügen, Anwesenheitsinformationen und Chatnachrichten mit diesen Benutzern auszutauschen und Sie zu Audioanrufen, Videoanrufen und Konferenzen einzuladen.</p></td>
</tr>
<tr class="odd">
<td><p>Unterstützung für mobile Clients</p></td>
<td><p>Außerdem können Ihre Benutzer mit lync Server Mobilitätsdiensten auf lync-Funktionen zugreifen, wenn Sie unterstützte Apple IOS-, Android-, Windows Phone-oder Nokia-Mobilgeräte verwenden und Aktivitäten wie das Senden und empfangen von Chatnachrichten, das Anzeigen von Kontakten durchführen. und Anzeigen der Anwesenheit. Zudem unterstützen mobile Geräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, Geschäftlich anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit. Push-Benachrichtigungen werden auch für mobile Geräte unterstützt, die Anwendungen, die im Hintergrund ausgeführt werden, nicht unterstützen.</p></td>
</tr>
<tr class="even">
<td><p>Integration in andere Produkte</p></td>
<td><p>Lync Server integriert sich in mehrere andere Produkte, um Ihren Benutzern und Administratoren zusätzliche Vorteile zu bieten.</p>
<p>Besprechungstools sind in Outlook integriert, damit Organisatoren eine Besprechung planen oder eine spontane Konferenz mit einem einzigen Mausklick beginnen können, damit die Teilnehmer sich einfach an die Teilnahme beteiligen können.</p>
<p>Anwesenheitsinformationen sind in Outlook und SharePoint integriert.</p>
<p>Exchange Unified Messaging (um) bietet verschiedene Integrationsfeatures. Benutzer können sehen, ob Sie neue Voicemails in lync Server haben. Sie können auf eine Wiedergabe-Schaltfläche in der Outlook-Nachricht klicken, um die audiovoicemail zu hören, oder eine Transkription der Voicemail in der Benachrichtigungsnachricht anzeigen.</p>
<p>Darüber hinaus werden durch die Ausführung von lync Server 2013 mit Exchange 2013 mehrere neue Features wie ein einheitlicher Kontaktspeicher, auf den Clients beider Produkte zugreifen können, sowie hochauflösende Fotos für Kontakte ermöglicht, die in der Exchange 2013 Datenbank gespeichert sind.</p></td>
</tr>
<tr class="odd">
<td><p>Einfache Bereitstellung</p></td>
<td><p>Zur Unterstützung bei der Planung und Bereitstellung von Servern und Clients stellt lync Server den Topologie-Generator bereit.</p>
<p>Der Topologie-Generator ist eine Installationskomponente von lync Server. Verwenden Sie den Topologie-Generator, um die geplante Topologie zu erstellen, anzupassen und zu veröffentlichen. Darüber hinaus überprüft der Topologie-Generator Ihre Topologie, bevor Sie mit den Serverinstallationen beginnen. Wenn Sie lync Server auf einzelnen Servern installieren, wird der Server vom Installationsprogramm wie in der Topologie weitergeleitet bereitgestellt.</p></td>
</tr>
<tr class="even">
<td><p>Einfache Verwaltung</p></td>
<td><p>Nachdem Sie lync Server bereitgestellt haben, bietet es die folgenden leistungsfähigen und optimierten Verwaltungstools:</p>
<ul>
<li><p>Zentrale Konfigurationsverwaltung, mit der Sie Änderungen zentral verwalten und schnell auf die gesamte Bereitstellung replizieren können.</p></li>
<li><p>Lync Server-Systemsteuerung, eine webbasierte grafische Benutzeroberfläche für Administratoren. Mit dieser webbasierten Benutzeroberfläche können lync Server Administratoren ihre Systeme von einem beliebigen Standort im Unternehmensnetzwerk aus verwalten, ohne dass auf ihren Computern eine spezielle Verwaltungssoftware installiert sein muss.</p></li>
<li><p>Lync Server-Verwaltungsshell Befehlszeilen-Verwaltungstool, das auf der Windows PowerShell-Befehlszeilenschnittstelle basiert. Es bietet einen umfangreichen Befehlssatz für die Verwaltung aller Aspekte des Produkts und ermöglicht es lync Server Administratoren, sich wiederholende Aufgaben mithilfe eines vertrauten Tools zu automatisieren.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Während die Sofortnachrichten-und Anwesenheitsfunktionen in jeder lync Server-Bereitstellung automatisch installiert werden, können Sie auswählen, ob Konferenzen, Enterprise-VoIP und Remotebenutzerzugriff bereitgestellt werden sollen, um Ihre Bereitstellung den Anforderungen Ihrer Organisation anzupassen.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Chat und Anwesenheitsinformationen in lync Server 2013](lync-server-2013-im-and-presence.md)

  - [Konferenzen in lync Server 2013](lync-server-2013-conferencing.md)

  - [Enterprise-VoIP in lync Server 2013](lync-server-2013-enterprise-voice.md)

  - [Skalierbarkeit mit lync Server 2013](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

