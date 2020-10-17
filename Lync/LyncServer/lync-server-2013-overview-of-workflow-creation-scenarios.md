---
title: 'Lync Server 2013: Übersicht über Szenarien zur Erstellung von Workflows'
description: 'Lync Server 2013: Übersicht über Szenarien zur Erstellung von Workflows.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a38627e7abb058be2050c0db0b46fa06dfd75287
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557411"
---
# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a>Übersicht über Szenarien zur Erstellung von Workflows in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-17_

Beim Erstellen von Workflows stehen zwei mögliche Szenarien zur Verfügung:

  - **Der Administrator erstellt und konfiguriert den Workflow**: Das Mitglied der Rolle "CsResponseGroupAdministrator" (oder einer gleichwertigen Rolle) erstellt und aktiviert den Workflow und alle Elemente im Workflow, z. B. die Agentgruppen, Warteschlangen, Feiertage und Geschäftszeiten, Wartemusik usw.

  - **Der Administrator erstellt den Workflow und der Manager konfiguriert die Optionen**: Das Mitglied der Rolle "CsResponseGroupAdministrator" (oder einer gleichwertigen Rolle) definiert den primären SIP-URI und den Anzeigenamen, weist Mitglieder der Rolle "CsResponseGroupManager" zu, wählt eine Warteschlange aus und aktiviert den Workflow. Das CsResponseGroupManager-Mitglied kann sich dann anmelden und die Konfiguration des Workflows bearbeiten, indem es Agentgruppen erstellt und die Gruppe ebenfalls der Warteschlange zuweist und die Telefonnummer, Feiertage und Geschäftszeiten, Wartemusik usw. konfiguriert.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einen verwalteten Workflow erstellen möchten, müssen Sie den Workflow als aktiv erstellen. Nach dem Speichern eines aktiven, verwalteten Workflows können Sie den Workflow ändern und deaktivieren.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

