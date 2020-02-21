---
title: Verbleibenden Benutzer in lync Server 2013 verlagern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ded313a9c46617716bf7c25884dbb0ed9bcce5d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Verbleibenden Benutzer in lync Server 2013 verlagern

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-26_

Sie können Benutzer mithilfe von lync Server-Systemsteuerung oder lync Server-Verwaltungsshell zur neuen lync Server 2013-Bereitstellung migrieren. Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu lync Server 2013 sicherzustellen. Ausführliche Informationen zu den Voraussetzungen für die Ausführung der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration_1.md). Ausführliche Anweisungen zum Verschieben von Benutzern finden Sie unter [Phase 6: Verschieben von Benutzern in den Pilot Pool](phase-6-move-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> Sie können nicht das Snap-in Active Directory Benutzer und Computer oder die Microsoft Office Communications Server 2007 R2 Verwaltungstools verwenden, um Benutzer aus ihrer Legacyumgebung in lync Server 2013 zu versetzen.



</div>

<div>


> [!IMPORTANT]  
> Die Verwendung des <STRONG>Move-CsLegacyUser</STRONG>-Cmdlets setzt voraus, dass Benutzernamen im korrekten Format ohne vorangestellte oder nachgestellte Leerzeichen vorliegen. Sie können ein Benutzerkonto nicht mithilfe des <STRONG>Move-CsLegacyUser</STRONG>-Cmdlets verschieben, wenn der Name vorangestellte oder nachgestellte Leerzeichen enthält.



</div>

Wenn Sie einen Benutzer in einen lync Server 2013 Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist.

<div>


> [!IMPORTANT]  
> Hierzu gehören die aktiven Besprechungen, die der Benutzer der Vorgängerversion erstellt hat. Wenn beispielsweise ein älterer Benutzer eine " <STRONG>Meine Besprechung</STRONG> "-Konferenz konfiguriert hat, ist diese Konferenz nach dem Verschieben des Benutzers weiterhin im neuen lync Server 2013 Pool verfügbar. Die Details für den Zugriff auf diese Besprechung sind die gleiche <STRONG>Konferenz-URL und Konferenz-ID</STRONG> wie vorher. Der einzige Unterschied besteht darin, dass die Konferenz nun im lync Server 2013 Pool und nicht in Office Communications Server 2007 R2 Pool gehostet wird.



</div>

<div>


> [!NOTE]  
> Für das Homing von Benutzern in lync Server 2013 müssen keine aktualisierten Clients gleichzeitig bereitgestellt werden. Neue Funktionen stehen den Benutzern nur dann zur Verfügung, wenn sie ein Upgrade auf die neue Clientsoftware durchgeführt haben.



</div>

<div>

## <a name="post-migration-task"></a>Aufgaben nach der Migration

1.  Überprüfen Sie nach dem Verschieben der Benutzer die ihnen zugeordnete Konferenzrichtlinie.

2.  Um sicherzustellen, dass Besprechungen, die von Benutzern organisiert werden, die auf lync Server 2013 verwaltet werden, nahtlos mit Verbundbenutzern zusammenarbeiten, die in Office Communications Server 2007 R2 verwaltet werden, sollte die konferenzrichtlinie, die den migrierten Benutzern zugewiesen ist, anonyme Teilnehmer zulassen.

3.  Konferenzrichtlinien, die anonymen Teilnehmern erlauben, **ermöglichen Teilnehmern das einladen anonymer Benutzer** , die in lync Server 2013 Systemsteuerung ausgewählt wurden, und **AllowAnonymousParticipantsInMeetings** in der Ausgabe des Cmdlets **Get-CsConferencingPolicy** in der lync Server-Verwaltungsshell auf **true** festgelegt.

4.  Ausführliche Informationen zum Konfigurieren der konferenzrichtlinie mithilfe lync Server-Verwaltungsshell finden Sie unter [Festlegen von CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in der lync Server-Verwaltungsshell-Dokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

