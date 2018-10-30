---
title: 'Lync Server 2013: Anzeigen von Konfigurationseinstellungen für das Geräteupdate'
TOCTitle: Anzeigen von Konfigurationseinstellungen für das Geräteupdate
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994059(v=OCS.15)
ms:contentKeyID: 52056433
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Konfigurationseinstellungen für das Geräteupdate in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Sie können die Konfigurationseinstellungen für den Geräteaktualisierungsdienst mit den Cmdlets Lync Server-Verwaltungsshell und **Get-CsDeviceUpdateConfiguration** anzeigen, die Sie über die Verwaltungsshell für Lync Server 2013 oder eine Remotesitzung von Windows PowerShell ausführen können.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.





  - Zum Anzeigen von Informationen zu allen VoIP-Routen geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein und drücken Sie die EINGABETASTE:
    
        Get-CsDeviceUpdateConfiguration
    
    Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

Ausführliche Informationen zu diesem Cmdlet finden Sie im Hilfethema unter [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateConfiguration).

