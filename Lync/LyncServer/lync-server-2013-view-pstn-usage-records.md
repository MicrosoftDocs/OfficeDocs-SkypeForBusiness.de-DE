---
title: 'Lync Server 2013: Anzeigen von PSTN-Verwendungsdatensätzen'
TOCTitle: Anzeigen von PSTN-Verwendungsdatensätzen
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398458(v=OCS.15)
ms:contentKeyID: 49294220
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von PSTN-Verwendungsdatensätzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Ein PSTN-Verwendungsdatensatz gibt eine Anrufklasse (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche) an, die von den verschiedenen Benutzern oder Benutzergruppen in einer Organisation getätigt werden dürfen. Ausführliche Informationen finden Sie unter [PSTN-Verwendungsdatensätze in Lync Server 2013](lync-server-2013-pstn-usage-records.md) in der Planungsdokumentation.

## So zeigen Sie einen PSTN-Verwendungsdatensatz in der Lync Server-Systemsteuerungan

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **PSTN-Verwendung** .

4.  Markieren Sie auf der Seite **PSTN-Verwendung** den PSTN-Verwendungsdatensatz, die Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details anzeigen** .
    

    > [!NOTE]
    > Auf einer schreibgeschützten Seite des ausgewählten PSTN-Verwendungsdatensatzes werden die zugehörigen Routen und VoIP-Richtlinien angezeigt.



## Anzeigen von PSTN-Nutzungsinformationen mithilfe von Windows PowerShell-Cmdlets

Sie können PSTN-Nutzungen auch mit der Windows PowerShell und dem **Get-CsPstnUsage**-Cmdlet anzeigen. Dieses Cmdlet kann entweder von der Verwaltungsshell für Lync Server 2013 aus oder in einer Remotesitzung der Windows PowerShellAusführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876). ausgeführt werden.

## So zeigen Sie PSTN-Verwendungsinformationen mithilfe des Windows PowerShell-Cmdlets an

  - Zum Anzeigen von Informationen über alle PSTN-Nutzungen geben Sie in der Lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsPstnUsage
    
    Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

Ausführliche Informationen finden Sie unter [Get-CsPstnUsage](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPstnUsage).

## Siehe auch

#### Aufgaben

[Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

