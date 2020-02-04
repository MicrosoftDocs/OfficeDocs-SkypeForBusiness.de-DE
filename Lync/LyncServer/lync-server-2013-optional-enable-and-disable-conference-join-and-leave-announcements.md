---
title: (Optional) Aktivieren und Deaktivieren von Konferenzankündigungen beim Beitreten und Verlassen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b8e75a0d2ed81a515540f2a8a1811998a85d44c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>(Optional) Aktivieren und Deaktivieren von Konferenzankündigungen beim Beitreten und Verlassen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Wenn Einwahlbenutzer an einer Konferenz teilnehmen oder Sie verlassen, kann die APP für Konferenz Ankündigungen deren ein-oder Ausstieg ankündigen, indem Sie einen Ton abspielen oder ihre Namen sagen. Sie können ändern, wie Ankündigungen funktionieren, indem Sie Cmdlets ausführen. Dieser Schritt ist optional.

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>So ändern Sie das Verhalten von Ankündigungen beim Beitreten oder Verlassen einer Konferenz

1.  Melden Sie sich bei dem Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der Rolle **CS-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingConfiguration
    
    Mit diesem Cmdlet werden Informationen darüber abgerufen, ob Teilnehmer ihren Namen beim beitreten zu einer Konferenz aufzeichnen müssen und wie lync Server antwortet, wenn Teilnehmer an einer Einwahlkonferenz teilnehmen oder diese hinterlassen.

4.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   legt fest, ob anonyme Teilnehmer aufgefordert werden, Ihren Namen aufzuzeichnen, bevor Sie die Konferenz betreten. Der Standardwert ist "$true", was bedeutet, dass anonyme Teilnehmer aufgefordert werden, Ihren Namen anzugeben, wenn Sie einer Konferenz beitreten. (Authentifizierte Teilnehmer zeichnen ihren Namen nicht auf, da stattdessen der Anzeigename verwendet wird.)
    
    **EntryExitAnnouncementsEnabledByDefault**   gibt an, ob Ankündigungen standardmäßig aktiviert oder deaktiviert werden. Der Standardwert ist "$false", was bedeutet, dass standardmäßig keine Ankündigungen vorhanden sind, wenn Teilnehmer an einer Konferenz teilnehmen oder eine Konferenz beenden. Der Besprechungsorganisator kann diese Einstellung beim Planen einer Besprechung außer Kraft setzen.
    
    **EntryExitAnnouncementsType**   gibt die Aktion an, die ausgeführt wird, wenn ein Teilnehmer eine Konferenz anschließt oder verlässt, für die Ankündigungen aktiviert sind. Der Standardwert ist "UseNames", was bedeutet, dass eine Ankündigung ähnlich der folgenden lautet: "Ken Myers hat sich der Konferenz angeschlossen", wenn Ankündigungen aktiviert sind.
    
    Sie können diese Einstellungen auf globaler oder Standortebene konfigurieren. Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen.
    
    Beispiel:
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    In diesem Beispiel werden die Einstellungen für den Website Bereich für Redmond konfiguriert. Die Ankündigungsfunktion ist aktiviert, Teilnehmer müssen jedoch nicht ihren Namen sagen, wenn sie einer Konferenz beitreten. Ein Signalton wird wiedergegeben, wenn Teilnehmer eine Konferenz betreten oder belegen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

