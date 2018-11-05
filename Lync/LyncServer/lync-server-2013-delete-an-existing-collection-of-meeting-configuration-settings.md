---
title: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Besprechungen
TOCTitle: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Besprechungen
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49890847
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Besprechungen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Eine Standort- oder eine Benutzerkonfiguration kann gelöscht werden. Die globale Konfiguration kann nicht entfernt werden. Wenn Sie die globale Konfiguration löschen, werden automatisch die Standardwerte wieder hergestellt.

## So löschen Sie eine Standort- oder eine Benutzerbesprechungskonfiguration

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.

4.  Klicken Sie in der Liste der Besprechungskonfigurationen auf die Standort- oder Poolkonfiguration, die Sie löschen möchten, klicken Sie auf "Bearbeiten" und dann auf "Löschen".

## Löschen von Besprechungskonfigurationseinstellungen mit den Lync Server PowerShell-Cmdlets

Besprechungseinstellungen können auch mithilfe der Windows PowerShell dem Remove-CsMeetingConfiguration-Cmdlet gelöscht werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Löschen einer festgelegten Zusammenstellung von Besprechungskonfigurationseinstellungen

  - Dieser Befehl löscht die Besprechungskonfigurationseinstellungen des Standorts Redmond:
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

## Löschen aller Besprechungskonfigurationseinstellungen des Standortbereichs

  - Dieser Befehl löscht alle Besprechungskonfigurationseinstellungen des Standortbereichs:
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

## Löschen aller Besprechungskonfigurationseinstellungen, die standardmäßig anonyme Benutzer zulässt

  - Dieser Befehl löscht alle Einstellungen, die standardmäßig anonyme Benutzer zulassen:
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

Weitere Informationen finden Sie im Hilfethema zum [Remove-CsMeetingConfiguration](ttps://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMeetingConfiguration)-Cmdlet.

