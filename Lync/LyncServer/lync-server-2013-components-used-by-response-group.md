---
title: 'Lync Server 2013: Von Reaktionsgruppen verwendete Komponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f52ceb18c355f6d867b5b3b4485434df83683d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Von Reaktionsgruppen verwendete Komponenten in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-11_

Die reaktionsgruppenanwendung wird automatisch aktiviert, wenn Sie Enterprise-VoIP bereitstellen. In diesem Abschnitt werden die Komponenten beschrieben, die die reaktionsgruppenanwendung unterstützen.

<div>

## <a name="response-group-components"></a>Komponenten der Reaktionsgruppe

Die folgenden Microsoft lync Server 2013-Komponenten unterstützen die reaktionsgruppenanwendung:

  - **Application Service**   Application Service bietet eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen, beispielsweise der Reaktionsgruppe. Der Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jedem Standard Edition-Server installiert.

  - **Reaktionsgruppenanwendung**   die Antwortgruppen Anwendung ist eine der Unified Communications-Anwendungen, die vom Anwendungsdienst gehostet werden. Sie wird automatisch einbezogen, wenn Sie die Reaktionsgruppe bereitstellen. Die Antwortgruppen Anwendung leitet eingehende Anrufe an Gruppen von Agents weiter und Warteschlangen.

  - **Sprachpaket**   ein Sprachpaket ist erforderlich, um Text-zu-Sprache-und Spracherkennung zu unterstützen. Diese Sprachtechnologien werden zum Konfigurieren von Nachrichten verwendet, beispielsweise für die Willkommensnachricht oder für andere Ansagen sowie für Fragen und Antworten der interaktiven Sprachantwort (Interactive Voice Response, IVR). Standardmäßig werden die 26 unterstützten Sprachpakete installiert, wenn Sie lync Server 2013 bereitstellen.

  - **** Audiodateien Audiodateien werden für Nachrichten und Musik im Wartebereich verwendet.   

  - **Datei**   Speicher-Reaktionsgruppe verwendet den Dateispeicher zum Speichern von Audiodateien. Mehrere Antwortgruppen Pools können dieselbe Instanz des Dateispeichers verwenden.

  - **Reaktionsgruppen-Konfigurationstool**   das Reaktionsgruppen-Konfigurationstool ist ein webbasiertes Tool, das zum Erstellen und Konfigurieren von Reaktionsgruppen verwendet wird. Beim Installieren von Webdiensten ist das Tool für die Reaktionsgruppen Konfiguration enthalten.

  - **Microsoft lync Server 2013-System**   Steuerung Sie können die lync Server-Systemsteuerung verwenden, um Agentengruppen und-Warteschlangen für Reaktionsgruppen einzurichten und zu konfigurieren.

  - **Lync Server-Verwaltungsshell**   alle Einstellungen der Reaktionsgruppe können mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.

  - ****   Formelle Agents für Microsoft lync 2013 (Agents, die sich bei der Gruppe anmelden müssen, bevor Sie Anrufe für die Gruppe annehmen können) verwenden Sie lync 2013, um sich bei der Gruppe anzumelden und sich abzumelden. Wenn eine Agentengruppe für formelle Agents konfiguriert ist, klicken die Agents auf ein Menüelement in lync 2013, um Internet Explorer zu öffnen und eine Webseite-Konsole für die Anmeldung bei der Gruppe anzuzeigen.

  - **Web**Services-Webdienste sind für das Reaktionsgruppen-Konfigurations Tool, die Anmelde-und Abmelde Konsole des Agents, die lync Server-Systemsteuerung und den Client-Webdienst der Reaktionsgruppe erforderlich.   

  - **Antwortgruppen-Client-Web-Service**   Response Group-Anwendung bietet einen Client-Webdienst, der von Drittanbieter-Anwendungen verwendet werden kann, um Informationen zu Agents, Agentengruppen Mitgliedschaft, Agent-Anmeldestatus, Anrufstatus für Gruppen abzurufen, und die Gruppen, die anonyme Anrufe unterstützen. Lync 2013 und lync 2010 Attendant verwenden den Client-Webdienst der Reaktionsgruppe, um die Liste der Antwortgruppen abzurufen, die von Agents für anonyme Anrufe verwendet werden können. Der Client-Webdienst ist bei der Installation von Webdiensten enthalten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

