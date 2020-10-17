---
title: 'Lync Server 2013: Verwalten von Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00736a94cc383a362a3f952519acc603c5beefab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507192"
---
# <a name="managing-response-groups-in-lync-server-2013"></a>Verwalten von Reaktionsgruppen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2018-02-01_

Reaktionsgruppen sind eine Anrufverwaltungsfunktion, mit der Sie Anrufe für einen bestimmten Bereich (z. B. ein Helpdesk) in der Warteschleife platzieren und anschließend an eine zuständige Personengruppe namens *Agents* weiterleiten können.

Um die Reaktionsgruppen zu verwalten, konfigurieren Sie Agentgruppen, Warteschlangen und Workflows. Diese legen fest, wie ein Anruf vom Zeitpunkt der Tätigung bis hin zur Beantwortung durch einen Agent verarbeitet wird.

<div>


> [!NOTE]  
> Wenn Sie mehr als 300 Workflows in einem einzelnen Pool in ihrer Reaktionsgruppen Bereitstellung haben, ist es besser, lync Server-Verwaltungsshell-Cmdlets zum Erstellen der Workflows zu verwenden. Wenn Sie das Reaktionsgruppen-Konfigurationstool zum Erstellen von Workflows für einen Pool mit mehr als 300 Workflows verwenden, wird für das Laden der Webseite sehr viel Zeit benötigt. Die Anzahl der Agents, die indirekt Workflows über die Warteschlangen zugeordnet sind, wirkt sich auch proportional auf das Laden von Seiten aus.



</div>

Die Themen in diesem Abschnitt bieten schrittweise Anleitungen für Aufgaben, die Sie ausführen können, um die Reaktionsgruppenanwendung in Ihrer Bereitstellung anzupassen und zu verwalten.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Verwalten von Reaktionsgruppen-Agentgruppen in lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)

  - [Verwalten von Warteschlangen für Reaktionsgruppen in lync Server 2013](lync-server-2013-managing-response-group-queues.md)

  - [Verwalten von Workflows für Reaktionsgruppen in lync Server 2013](lync-server-2013-managing-response-group-workflows.md)

  - [Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in lync Server 2013](lync-server-2013-managing-application-level-response-group-settings.md)

  - [Verschieben von Reaktionsgruppen in einen neuen Pool in lync Server 2013](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [Verwalten von Reaktionsgruppen in lync Server 2013 während eines Notfalls](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

