---
title: Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in Lync Server 2013
TOCTitle: Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in Lync Server 2013
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49890884
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Die Einstellungen auf Anwendungsebene für Reaktionsgruppenanwendung beinhalten die Konfiguration der Standard-Wartemusik, die Audiodatei für die Standard-Wartemusik, die Kulanzfrist für den Agentrückruf und die Konfiguration des Anrufkontexts. Pro Pool können Sie nur eine Gruppe von Einstellungen auf Anwendungsebene definieren. Verwenden Sie zum Anzeigen der Einstellungen auf Anwendungsebene das Cmdlet **Get-CsRgsConfiguration**. Wenn Sie die Einstellungen auf Anwendungsebene ändern möchten, verwenden Sie das Cmdlet **Set-CsRgsConfiguration**.

Die Standard-Wartemusik wird wiedergegeben, wenn ein Anruf in der Warteschleife platziert wird, und auch nur dann, wenn keine benutzerdefinierte Wartemusik definiert wurde. Der Anrufkontext ist nur für Warteschleifen verfügbar, die interaktiven Workflows zugeordnet sind. Wenn der Anrufkontext aktiviert ist, kann ein Agent Informationen wie die Wartezeit des Anrufers oder Fragen und Antworten zu einem Workflow anzeigen, wenn der Anruf empfangen wird.

## So ändern Sie Reaktionsgruppe-Einstellungen auf Anwendungsebene

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie in der Befehlszeile den folgenden Befehl aus:
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    Beispiel:
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    Wenn Sie eine Audiodatei angeben möchten, die als Standard-Wartemusik verwendet werden soll, müssen Sie zunächst die Audiodatei importieren. Beispiel:
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

## Siehe auch

#### Weitere Ressourcen

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[Set-CsRgsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsConfiguration)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)

