---
title: 'Lync Server 2013: (optional) Ändern der Tastenzuordnung für DTMF-Befehle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcf6f6b2dd65d9429bf23397baff5bbe072800f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>Optional Ändern der Tastenzuordnung für DTMF-Befehle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-30_

Einwahlkonferenzbenutzer können DTMF-Befehle (Dual-Tone Multi-Frequency) mithilfe der Tasten ihres Telefons ausführen. Mit DTMF-Befehlen können Benutzer, die sich bei einer Konferenz einwählen, Konferenzeinstellungen mit der Telefontastatur steuern (z. B. eigene Person stummschalten bzw. Stummschaltung der eigenen Person aufheben oder Konferenz sperren bzw. entsperren). Sie können Cmdlets verwenden, um die Tastaturzuordnung für die DTMF-Befehle zu ändern. Dieser Schritt ist optional.

<div>


> [!NOTE]  
> Ausführliche Informationen zu diesen Cmdlets und den möglichen DTMF-Optionen finden Sie in lync Server-Verwaltungsshell Dokumentation oder lync Server-Verwaltungsshell Befehlszeilenhilfe.



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>So ändern Sie die Tastaturzuordnung für DTMF-Befehle

1.  Melden Sie sich beim Computer als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Dieses Cmdlet gibt die in Einwahlkonferenzen verwendeten DTMF-Einstellungen zurück.

4.  Führen Sie das folgende Cmdlet aus, und geben Sie für jede Option, die Sie ändern möchten, die gewünschte Taste an:
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Dieses Cmdlet ändert die in Einwahlkonferenzen verwendeten DTMF-Einstellungen.
    
    Beispiel:
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    In diesem Beispiel wird die Taste zur Aktivierung und Deaktivierung von Ankündigungen mit der Taste zur Stummschaltung und Aufhebung der Stummschaltung aller Teilnehmer getauscht. Da für "Identity" kein Wert angegeben ist, werden diese Änderungen auf die globalen DTMF-Einstellungen angewendet.

5.  (Optional) Zum Erstellen zusätzlicher DTMF-Befehlssätze für bestimmte Standorte verwenden Sie das Cmdlet **New-CsDialinConferencingDtmfConfiguration** mit dem Identitätswert eines Standorts. Beim Erstellen neuer DTMF-Einstellungen für Standorte haben die Standorteinstellungen Vorrang vor den globalen Einstellungen. Ausführliche Informationen finden Sie unter lync Server-Verwaltungsshell Dokumentation oder lync Server-Verwaltungsshell Befehlszeilenhilfe.

</div>

</div>

<span> </span>

</div>

</div>

</div>

