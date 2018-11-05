---
title: Zuweisen von Richtlinien an ein Telefon in einem öffentlichen Bereich
TOCTitle: Zuweisen von Richtlinien an ein Telefon in einem öffentlichen Bereich
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994082(v=OCS.15)
ms:contentKeyID: 52056483
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen von Richtlinien an ein Telefon in einem öffentlichen Bereich

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Nachdem Sie eine Richtlinie für Telefone in öffentlichen Bereichen erstellt haben (ausführliche Informationen finden Sie unter [Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), können Sie die Richtlinie mit der Windows PowerShell und dem entsprechenden **Grant-Cs**-Cmdlet einem Telefon für öffentliche Bereich zuweisen. Diese Cmdlets können entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Zuweisen einer Richtlinie zu einem einzelnen Telefon in einem öffentlichen Bereich

  - Mit dem folgenden Befehl wird die benutzerspezifische VoIP-Richtlinie "RedmondVoice" dem Telefon im öffentlichen Bereich zugewiesen, das die Identität "Building 14 Lobby" hat.
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

## Zuweisen einer Richtlinie zu mehreren Telefonen in einem öffentlichen Bereich

  - In diesem Beispiel wird die benutzerspezifische VoIP-Richtlinie "RedmondVoice" allen Telefonen im öffentlichen Bereich zugewiesen, die für die Verwendung in der Organisation konfiguriert wurden.
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

Einzelheiten dazu finden Sie in den Hilfethemen zum Cmdlet [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy).

## Siehe auch

#### Weitere Ressourcen

[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)

