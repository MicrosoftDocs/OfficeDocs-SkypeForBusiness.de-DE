---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Geräteaktualisierungen
TOCTitle: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Geräteaktualisierungen
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994029(v=OCS.15)
ms:contentKeyID: 52056343
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Geräteaktualisierungen

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Konfigurationseinstellungen für Geräteaktualisierungen können (nur auf Standortebene) mithilfe der Windows PowerShell und des Cmdlets **New-CsDeviceUpdateConfiguration** erstellt und mithilfe des Cmdlets **Set-CsDeviceUpdateConfiguration** geändert werden. Diese Cmdlets können entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




## So erstellen Sie Konfigurationseinstellungen für Geräteaktualisierungen, die die Standardwerte verwenden

  - Mit diesem Befehl wird ein neuer Satz von Konfigurationseinstellungen für Geräteaktualisierungen für den Standort "Redmond" erstellt:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    Da im vorherigen Befehl keine weiteren Parameter außer dem obligatorischen Identity-Parameter angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet.

## So ändern Sie bei der Erstellung von Konfigurationseinstellungen für Geräteaktualisierungen einen einzelnen Eigenschaftswert

  - Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an. Um beispielsweise eine Auflistung von Konfigurationseinstellungen für Geräteaktualisierungen zu erstellen, mit der alte Protokolldateien nach 21 Tagen gelöscht werden, müssen Sie einen Befehl wie den folgenden verwenden:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

## So ändern Sie bei der Erstellung von Konfigurationseinstellungen für Geräteaktualisierungen mehrere Eigenschaftswerte

  - Wenn Sie mehrere Eigenschaftswerte ändern möchten, schließen Sie mehrere Parameter ein. Mit diesem Befehl wird beispielsweise das Protokollleerungsintervall auf 21 Tage und das Protokolllöschungsintervall auf 30 Minuten festgelegt:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

Ausführliche Informationen zum Ändern der vorhandenen Konfigurationseinstellungen für Geräteaktualisierungen finden Sie im Hilfethema zum Cmdlet [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsDeviceUpdateConfiguration). Ausführliche Informationen zum Erstellen von Auflistungen von Konfigurationseinstellungen finden Sie im Hilfethema zum Cmdlet [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsDeviceUpdateConfiguration).

