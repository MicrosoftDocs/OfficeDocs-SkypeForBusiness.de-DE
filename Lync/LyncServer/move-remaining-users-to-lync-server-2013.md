---
title: Verbleibenden Benutzer in lync Server 2013 verlagern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 966182705fd3f18bfa10d1d6042e1c3c94204e9e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500212"
---
# <a name="move-remaining-users-to-lync-server-2013"></a>Verbleibenden Benutzer in lync Server 2013 verlagern

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-29_

Sie können Benutzer mithilfe von lync Server-Systemsteuerung oder lync Server-Verwaltungsshell zur neuen lync Server 2013-Bereitstellung migrieren. Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu lync Server 2013 sicherzustellen. Ausführliche Informationen zu den Voraussetzungen für die Ausführung der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration.md). Ausführliche Anweisungen zum Verschieben von Benutzern finden Sie unter [Phase 4: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> Sie können nicht das Snap-in Active Directory Benutzer und Computer oder die lync Server 2010 Verwaltungstools verwenden, um Benutzer aus ihrer Legacyumgebung in lync Server 2013 zu versetzen.



</div>

Wenn Sie einen Benutzer in einen lync Server 2013 Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist.

<div>


> [!IMPORTANT]  
> Hierzu gehören die aktiven Besprechungen, die der Benutzer der Vorgängerversion erstellt hat. Wenn beispielsweise ein älterer Benutzer eine " <STRONG>Meine Besprechung</STRONG> "-Konferenz konfiguriert hat, ist diese Konferenz weiterhin im neuen lync Server 2013 Pool verfügbar, nachdem der Benutzer verschoben wurde. Die Details für den Zugriff auf diese Besprechung sind die gleiche <STRONG>Konferenz-URL und Konferenz-ID</STRONG> wie vorher. Der einzige Unterschied besteht darin, dass die Konferenz nun im lync Server 2013 Pool und nicht im lync Server 2010-Pool gehostet wird.



</div>

<div>


> [!NOTE]  
> Für das Homing von Benutzern in lync Server 2013 müssen keine aktualisierten Clients gleichzeitig bereitgestellt werden. Neue Funktionen stehen den Benutzern nur dann zur Verfügung, wenn sie ein Upgrade auf die neue Clientsoftware durchgeführt haben.



</div>

<div>

## <a name="post-migration-task"></a>Aufgaben nach der Migration

1.  Überprüfen Sie nach dem Verschieben der Benutzer die ihnen zugeordnete Konferenzrichtlinie.

2.  Um sicherzustellen, dass Besprechungen, die von Benutzern organisiert werden, die auf lync Server 2013 verwaltet werden, nahtlos mit Verbundbenutzern zusammenarbeiten, die in lync Server 2010 verwaltet werden, sollte die konferenzrichtlinie, die den migrierten Benutzern zugewiesen ist, anonyme Teilnehmer zulassen.

3.  Konferenzrichtlinien, die anonymen Teilnehmern erlauben, **ermöglichen Teilnehmern das einladen anonymer Benutzer** , die in lync Server 2013 Systemsteuerung ausgewählt wurden, und **AllowAnonymousParticipantsInMeetings** in der Ausgabe des Cmdlets **Get-CsConferencingPolicy** in der lync Server-Verwaltungsshell auf **true** festgelegt.

4.  Ausführliche Informationen zum Konfigurieren der konferenzrichtlinie mithilfe lync Server-Verwaltungsshell finden Sie unter [Festlegen von CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in der lync Server-Verwaltungsshell-Dokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

