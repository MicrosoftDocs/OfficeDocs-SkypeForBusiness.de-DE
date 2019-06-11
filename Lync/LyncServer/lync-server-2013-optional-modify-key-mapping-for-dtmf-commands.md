---
title: 'Lync Server 2013: (Optional) Ändern der Tastenzuordnung für DTMF-Befehle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1a9fbe17a07403fbf0195026d44b490680973e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>(Optional) Ändern der Tastenzuordnung für DTMF-Befehle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Benutzer von Einwahlkonferenzen können auf der Telefontastatur auf Tasten drücken, um DTMF-Befehle (Dual-Tone Multi-Frequency) durchzuführen. Mit DTMF-Befehlen können Benutzer, die sich bei einer Konferenz einwählen, Konferenzeinstellungen (wie Muting und Aufheben der Stummschaltung oder sperren und Entsperren der Konferenz) über die Tastatur auf dem Telefon steuern. Sie können Cmdlets verwenden, um die für die DTMF-Befehle verwendeten Tasten zu ändern. Dieser Schritt ist optional.

<div>


> [!NOTE]  
> Details zu diesen Cmdlets und den möglichen DTMF-Optionen finden Sie unter Dokumentation zur lync Server-Verwaltungsshell oder Befehlszeilenhilfe zur lync Server-Verwaltungsshell.



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>So ändern Sie die Tastenzuordnung von DTMF-Befehlen

1.  Melden Sie sich bei dem Computer als Mitglied der **RTCUniversalServerAdmins** -Gruppe oder als Mitglied der Rolle **CS-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Dieses Cmdlet gibt die DTMF-Einstellungen zurück, die für Einwahlkonferenzen verwendet werden.

4.  Führen Sie das folgende Cmdlet aus, und geben Sie den zu bedruckenden Schlüssel für jede Option an, die Sie ändern möchten:
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Mit diesem Cmdlet werden die DTMF-Einstellungen geändert, die für Einwahlkonferenzen verwendet werden.
    
    Beispiel:
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    In diesem Beispiel wird die gedrückte Taste getauscht, um Ankündigungen zu aktivieren oder zu deaktivieren, und die Taste, die gedrückt wird, um alle Teilnehmer stummzuschalten und die Stummschaltung aufzuheben. Da keine Identität angegeben wird, gelten diese Änderungen für die globalen DTMF-Einstellungen.

5.  (Optional) Zum Erstellen zusätzlicher DTMF-Befehlssätze für bestimmte Standorte verwenden Sie das Cmdlet **New-CsDialinConferencingDtmfConfiguration** mit dem Identitätswert eines Standorts. Beim Erstellen neuer DTMF-Einstellungen für Standorte haben die Standorteinstellungen Vorrang vor den globalen Einstellungen. Ausführliche Informationen finden Sie unter Dokumentation zur lync Server-Verwaltungsshell oder Befehlszeilenhilfe zur lync Server-Verwaltungsshell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

