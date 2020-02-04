---
title: 'Lync Server 2013: Verwalten von Einstellungen für die Reaktionsgruppe auf Anwendungsebene'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffce659c2c4dc6c91ba4e4935b72c15e4cef4da5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a>Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Zu den Einstellungen auf Anwendungsebene für die Anwendung der Reaktionsgruppe gehören die standardmäßige Musik-in-situ-Konfiguration, die standardmäßige Musik-in-halten-Audiodatei, die Kulanzzeit für den Agent-Rückruf und die Konfiguration des Anruf Kontexts. Pro Pool können Sie nur eine Gruppe von Einstellungen auf Anwendungsebene definieren. Verwenden Sie zum Anzeigen der Einstellungen auf Anwendungsebene das Cmdlet **Get-CsRgsConfiguration**. Wenn Sie die Einstellungen auf Anwendungsebene ändern möchten, verwenden Sie das Cmdlet **Set-CsRgsConfiguration**.

Die Standard-Wartemusik wird wiedergegeben, wenn ein Anruf in der Warteschleife platziert wird, und auch nur dann, wenn keine benutzerdefinierte Wartemusik definiert wurde. Der Anrufkontext ist nur für Warteschleifen verfügbar, die interaktiven Workflows zugeordnet sind. Wenn der Anrufkontext aktiviert ist, kann ein Agent Informationen wie die Wartezeit des Anrufers oder Fragen und Antworten zu einem Workflow anzeigen, wenn der Anruf empfangen wird.

<div>

## <a name="to-modify-response-group-application-level-settings"></a>So ändern Sie die Einstellungen der Reaktionsgruppe auf Anwendungsebene

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    Beispiel:
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    Wenn Sie eine Audiodatei angeben möchten, die als Standard-Wartemusik verwendet werden soll, müssen Sie zunächst die Audiodatei importieren. Beispiel:
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[Satz-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[Importieren-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

