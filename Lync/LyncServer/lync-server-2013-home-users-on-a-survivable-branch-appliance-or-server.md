---
title: 'Lync Server 2013: Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server'
TOCTitle: Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413066(v=OCS.15)
ms:contentKeyID: 49295978
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-12-10_

Das Verwalten von Benutzern auf einer Survivable Branch-Anwendung oder einem Survivable Branch-Server ähnelt der Verwaltung von Benutzern in einem Front-End-Pool. Führen Sie das Verfahren für eine Survivable Branch-Anwendung oder einen Survivable Branch-Server am zentralen Standort aus.

## So platzieren Sie Benutzer zur Verwaltung auf einer Survivable Branch Appliance oder einem Survivable Branch Server

1.  Öffnen Sie vor dem Verschieben von Benutzern auf einen Survivable Branch-Server oder einen Survivable Branch Server die Lync Server-Verwaltungsshell, und führen Sie alle nachfolgend genannten Schritte aus:
    
      - Führen Sie das **Test-CsPstnOutboundCall**-Cmdlet aus, um sicherzustellen, dass der Survivable Branch-Server ausgeführt wird und die PSTN-Anbindung (Public Switched Telephone Network, Festnetz) konfiguriert ist. Wenn Sie die Eigenschaften des PSTN-Gateways ändern müssen, verwenden Sie das **Set-CsPstnGateway**-Cmdlet.
    
      - Überprüfen Sie mithilfe des **Get-CsVoicePolicy**-Cmdlets, ob für die Benutzer, die auf dem Survivable Branch-Server verwaltet werden sollen, die richtige VoIP-Routingrichtlinie vorhanden ist. Wenn Sie die VoIP-Richtlinie ändern müssen, verwenden Sie das **Set-CsVoicePolicy**-Cmdlet.
    
      - Stellen Sie mithilfe des **Get-CsVoicemailReroutingConfiguration**-Cmdlets sicher, dass die Einstellungen für die Voicemailumleitung konfiguriert sind. Wenn Sie die Einstellungen für die Voicemailumleitung ändern müssen, verwenden Sie das **Set-CsVoicemailReroutingConfiguration**-Cmdlet.

2.  Führen Sie in der Lync Server-Verwaltungsshell das **Move-CsUser**-Cmdlet aus, um Benutzer zu verschieben.


> [!NOTE]
> Sie können auch die Lync Server-Systemsteuerung verwenden, um die Voraussetzungen zu überprüfen und Benutzer zu platzieren.



## Siehe auch

#### Weitere Ressourcen

[Test-CsPstnOutboundCall](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser)

