---
title: 'Lync Server 2013: von der Reaktionsgruppe verwendete Komponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bfefeabc1c9f64a4f1bf9fa794b269fbdcb0650
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Von der Reaktionsgruppe in lync Server 2013 verwendete Komponenten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-11_

Das Reaktionsgruppenanwendung wird automatisch aktiviert, wenn Sie Enterprise-VoIP bereitstellen. In diesem Abschnitt werden die Komponenten beschrieben, die den Reaktionsgruppenanwendung unterstützen.

<div>

## <a name="response-group-components"></a>Reaktionsgruppenkomponenten

Die folgenden Microsoft lync Server 2013 Komponenten unterstützen das Reaktionsgruppenanwendung:

  - **Anwendungsdienst**   Anwendungsdienst stellt eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen wie Reaktionsgruppe bereit. Das Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jeder Standard Edition-Server installiert.

  - **Reaktionsgruppenanwendung**   das Reaktionsgruppenanwendung ist eine der Unified Communications-Anwendungen, die von Anwendungsdienst gehostet werden. Sie wird automatisch bei der Bereitstellung der Reaktionsgruppe einbezogen. Das Reaktionsgruppenanwendung leitet eingehende Anrufe an Gruppen von Agents weiter und Warteschlangen.

  - **Sprachpaket**   ein Sprachpaket ist für die Unterstützung von Text-zu-Sprache-und Spracherkennung erforderlich. Diese Sprachtechnologien werden zum Konfigurieren von Nachrichten verwendet, beispielsweise für die Willkommensnachricht oder für andere Ansagen sowie für Fragen und Antworten der interaktiven Sprachantwort (Interactive Voice Response, IVR). Standardmäßig werden die 26 unterstützten Sprachpakete installiert, wenn Sie lync Server 2013 bereitstellen.

  - **Audiodateien**Audiodateien werden für Nachrichten und Wartemusik verwendet.   

  - **Dateispeicher**   Reaktionsgruppe verwendet den Dateispeicher zum Speichern von Audiodateien. Mehrere Reaktionsgruppen Pools können dieselbe Instanz des Dateispeichers verwenden.

  - **Reaktionsgruppen-Konfigurationstool**   das Reaktionsgruppen-Konfigurationstool ist ein webbasiertes Tool, mit dem Reaktionsgruppen erstellt und konfiguriert werden. Das Tool zum Konfigurieren von Reaktionsgruppen ist enthalten, wenn Sie Webdienste installieren.

  - **Microsoft lync Server 2013-System**   Steuerung können Sie lync Server-Systemsteuerung zum Einrichten und Konfigurieren von Agentgruppen und Warteschlangen für Reaktionsgruppen verwenden.

  - **Lync Server-Verwaltungsshell**   alle Einstellungen für Reaktionsgruppen können mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.

  - **Microsoft lync 2013**   formelle Agents (Agents, die sich bei der Gruppe anmelden müssen, bevor Sie Anrufe für die Gruppe annehmen können) verwenden Sie lync 2013, um sich bei der Gruppe anzumelden und abzumelden. Wenn eine Agentgruppe für formelle Agents konfiguriert ist, klicken die Agents auf ein Menüelement in lync 2013, um Internet Explorer zu öffnen und eine Webseiten Konsole zum ein-und Ausloggen der Gruppe anzuzeigen.

  - **Webdienste**   Webdienste ist für das Konfigurations Tool für Reaktionsgruppen, die Anmelde-und Abmelde Konsole, die lync Server-Systemsteuerung und den Client-Webdienst für Reaktionsgruppen erforderlich.

  - **Client-Webdienst für Reaktionsgruppen**   Reaktionsgruppenanwendung stellt einen Client-Webdienst bereit, der von Drittanbieteranwendungen zum Abrufen von Informationen zu Agents, zur Agent-Gruppenmitgliedschaft, zum Agent-Anmeldestatus, zum Anrufstatus für Gruppen und zu den Gruppen, die anonyme Anrufe unterstützen, verwendet werden kann. Lync 2013 und lync 2010 Attendant den Client-Webdienst für Reaktionsgruppen verwenden, um die Liste der Reaktionsgruppen abzurufen, mit denen Agents anonyme Anrufe tätigen können. Der Clientwebdienst ist in der Installation der Webdienste enthalten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

