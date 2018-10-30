---
title: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Clientversionen
TOCTitle: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Clientversionen
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ898480(v=OCS.15)
ms:contentKeyID: 52056364
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Clientversionen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Sie die für einen Standort konfigurierten Clientkonfigurationseinstellungen entfernen möchten, können Sie dies in der Systemsteuerung für Lync Server 2013 oder in der Verwaltungsshell für Lync Server 2013 durchführen.

## So entfernen Sie Clientkonfigurationseinstellungen mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Clientversionskonfiguration**.

4.  Wählen Sie den Standort aus, klicken Sie auf **Bearbeiten** und **Löschen** und dann auf **OK**.

## Entfernen der von Konfigurationseinstellungen für Clientversionen mithilfe von Windows PowerShell-Cmdlets

Sie können Konfigurationseinstellungen für Clientversionen mithilfe des Cmdlets **Remove-CsClientVersionConfiguration** anzeigen. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So entfernen Sie eine bestimmte Auflistung von Konfigurationseinstellungen für Clientversionen

  - Mit dem folgenden Befehl werden die Konfigurationseinstellungen für Clientversionen entfernt, die für den Standort Redmond gelten:
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

## So entfernen Sie alle Konfigurationseinstellungen für Clientversionen auf Standortebene

  - Mit diesem Befehl werden alle Konfigurationseinstellungen für Clientversionen entfernt, die auf Standortebene konfiguriert sind:
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

## So entfernen Sie alle Konfigurationseinstellungen für Clientversionen basierend auf dem Wert der Eigenschaft "DefaultAction"

  - Mit diesem Befehl werden alle Konfigurationseinstellungen für Clientversionen gelöscht, bei denen für die Standardaktion "Blockieren" festgelegt wurde:
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Remove-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionConfiguration).

