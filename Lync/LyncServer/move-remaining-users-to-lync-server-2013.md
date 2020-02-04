---
title: Verschieben der verbleibenden Benutzer zu Lync Server 2013
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
ms.openlocfilehash: 4d60b3ba622e88978a8bbf555972c95979e8f8c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Verschieben der verbleibenden Benutzer zu Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell können Sie Benutzer zur neuen lync Server 2013-Bereitstellung verschieben. Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu lync Server 2013 zu gewährleisten. Details zu den Voraussetzungen für die Durchführung der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration.md). Detaillierte Anweisungen zum Verschieben von Benutzern finden Sie unter [Phase 4: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> Sie können das Snap-in Active Directory-Benutzer und-Computer oder die lync Server 2010-Verwaltungstools nicht verwenden, um Benutzer aus ihrer Legacyumgebung in lync Server 2013 zu verschieben.



</div>

Wenn Sie einen Benutzer in einen lync Server 2013-Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist.

<div>


> [!IMPORTANT]  
> Dazu gehören die vom Legacy Benutzer erstellten aktiven Besprechungen. Wenn ein älterer Benutzer beispielsweise eine Konferenz für <STRONG>Meine Besprechung</STRONG> konfiguriert hat, steht diese Konferenz nach dem Verschieben des Benutzers weiterhin im neuen lync Server 2013-Pool zur Verfügung. Die Details für den Zugriff auf die Besprechung sind weiterhin dieselbe <STRONG>Konferenz-URL und Konferenz-ID</STRONG>. Der einzige Unterschied besteht darin, dass die Konferenz jetzt im lync Server 2013-Pool und nicht im lync Server 2010-Pool gehostet wird.



</div>

<div>


> [!NOTE]  
> Für Homing-Benutzer in lync Server 2013 müssen keine aktualisierten Clients gleichzeitig bereitgestellt werden. Neue Funktionen stehen Benutzern nur zur Verfügung, wenn Sie ein Upgrade auf die neue Client Software durchgeführt haben.



</div>

<div>

## <a name="post-migration-task"></a>Aufgabe der nach der Migration

1.  Nachdem Sie die Benutzer verschoben haben, überprüfen Sie die konferenzrichtlinie, die Ihnen zugewiesen ist.

2.  Um sicherzustellen, dass Besprechungen, die von Benutzern verwaltet werden, die in lync Server 2013 verwaltet werden, nahtlos mit Verbundbenutzern funktionieren, die sich in lync Server 2010 befinden, sollten die den migrierten Benutzern zugewiesenen Konferenzrichtlinien anonymen Teilnehmern ermöglichen.

3.  Konferenzrichtlinien, die anonymen Teilnehmern erlauben, **können Teilnehmern erlauben, anonyme Benutzer einzuladen** , die in der lync Server 2013-Systemsteuerung ausgewählt sind, und **AllowAnonymousParticipantsInMeetings** in der Ausgabe des Cmdlets **Get-CsConferencingPolicy** in der lync Server-Verwaltungsshell auf **true** festgelegt.

4.  Details zum Konfigurieren von Konferenzrichtlinien mithilfe der lync Server-Verwaltungsshell finden Sie unter Dokumentation zu CsConferencingPolicy in der lync Server [-](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) Verwaltungsshell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

