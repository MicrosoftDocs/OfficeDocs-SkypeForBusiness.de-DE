---
title: Optional Aktivieren und Deaktivieren von Konferenz Anmeldungen und Abwesenheits Ankündigungen
description: Optional Aktivieren und Deaktivieren von Konferenz Anmeldungen und Abwesenheits Ankündigungen
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
ms.openlocfilehash: 70cd6b452a44d7d40f23d5ca96b6e4b7b063d2ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565781"
---
# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>Optional Aktivieren und Deaktivieren von Konferenz Anmeldungen und Abwesenheits Ankündigungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-30_

Wenn Einwahlbenutzer einer Konferenz beitreten oder diese verlassen, können die Konferenzankündigungsanwendung Ihren Eingang oder ihren Ausgang ankündigen, indem Sie einen Signalton abgeben oder ihre Namen sagen. Sie können die Funktionsweise von Ankündigungen ändern, indem Sie Cmdlets ausführen. Dieser Schritt ist optional.

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>So ändern Sie das Verhalten der Konferenz Mitgliedschaft und Abwesenheits Ankündigung

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingConfiguration
    
    Dieses Cmdlet ruft Informationen darüber ab, ob Teilnehmer ihren Namen aufzeichnen müssen, wenn Sie einer Konferenz beitreten, und wie lync Server reagiert, wenn Teilnehmer einer Einwahlkonferenz beitreten oder diese verlassen.

4.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**     Legt fest, ob anonyme Teilnehmer aufgefordert werden, Ihren Namen vor dem Betreten der Konferenz aufzuzeichnen. Der Standardwert ist "$true", was bedeutet, dass anonyme Teilnehmer aufgefordert werden, Ihren Namen anzugeben, wenn Sie einer Konferenz beitreten. (Authentifizierte Teilnehmer notieren ihren Namen nicht, da stattdessen Ihr Anzeigename verwendet wird.)
    
    **EntryExitAnnouncementsEnabledByDefault**     Gibt an, ob Ankündigungen standardmäßig aktiviert oder deaktiviert werden. Der Standardwert ist "$false", was bedeutet, dass es standardmäßig keine Ankündigungen gibt, wenn Teilnehmer einer Konferenz beitreten oder diese verlassen. Der Besprechungsorganisator kann diese Einstellung beim Planen einer Besprechung außer Kraft setzen.
    
    **EntryExitAnnouncementsType**     Gibt die Aktion an, die ausgeführt wird, wenn ein Teilnehmer einer Konferenz Beitritt oder diese verlässt, für die Ankündigungen aktiviert sind. Der Standardwert ist "UseNames", was bedeutet, dass eine Ansage ähnlich der folgenden vorliegt: "Ken Myers hat der Konferenz beigetreten, wenn Ankündigungen aktiviert sind.
    
    Sie können diese Einstellungen auf globaler Ebene oder auf Standortebene konfigurieren. Auf Standortebene konfigurierte Einstellungen haben Vorrang vor den auf globaler Ebene konfigurierten Einstellungen.
    
    Zum Beispiel:
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    In diesem Beispiel werden die Einstellungen auf Standortebene für Redmond konfiguriert. Ankündigungen sind aktiviert, aber die Teilnehmer werden nicht aufgefordert, Ihren Namen zu sagen, wenn Sie an einer Konferenz teilnehmen. Ein Signalton wird abgespielt, wenn Teilnehmer eine Konferenz betreten oder verlassen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

