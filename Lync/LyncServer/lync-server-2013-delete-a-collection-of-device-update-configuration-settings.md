---
title: Löschen einer Auflistung von Konfigurationseinstellungen für Geräteaktualisierungen
TOCTitle: Löschen einer Auflistung von Konfigurationseinstellungen für Geräteaktualisierungen
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994019(v=OCS.15)
ms:contentKeyID: 52056296
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer Auflistung von Konfigurationseinstellungen für Geräteaktualisierungen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Konfigurationseinstellungen für Geräteaktualisierungen können auch mithilfe der Windows PowerShell und dem Cmdlet **Remove-CsdeviceUpdateConfiguration** gelöscht werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## So entfernen Sie eine bestimmte Auflistung von Konfigurationseinstellungen für Geräteaktualisierungen

  - Mit diesem Befehl werden die Konfigurationseinstellungen für Geräteaktualisierungen entfernt, die für den Standort Redmond gelten:
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

## So entfernen Sie alle Konfigurationseinstellungen für Geräteaktualisierungen auf Standortebene

  - Mit diesem Befehl werden alle Konfigurationseinstellungen für Geräteaktualisierungen auf Standortebene gelöscht:
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

## So entfernen Sie Konfigurationseinstellungen für Geräteaktualisierungen basierend auf dem Wert der Eigenschaft "LogCleanUpInterval"

  - Mit dem folgenden Befehl werden alle Konfigurationseinstellungen für Geräteaktualisierungen gelöscht, bei denen das Protokollleerungsintervall auf mehr als 10 Tage festgelegt ist (10.00:00:00):
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDeviceUpdateConfiguration).

