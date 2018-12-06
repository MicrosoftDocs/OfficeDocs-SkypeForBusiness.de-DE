---
title: Löschen einer vorhandenen Konferenzrichtlinie
TOCTitle: Löschen einer vorhandenen Konferenzrichtlinie
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49890789
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer vorhandenen Konferenzrichtlinie

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Führen Sie die folgenden Schritte aus, um eine Konferenzrichtlinie auf Benutzer- oder Standortebene zu löschen.


> [!NOTE]
> Die globale Konferenzrichtlinie kann nicht gelöscht werden.



## So löschen Sie eine Konferenzrichtlinie auf Benutzer- oder Standortebene

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Konferenzrichtlinie**.

4.  Klicken Sie in der Liste der Konferenzrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, klicken Sie auf „Bearbeiten“ und dann auf „Löschen“.

## Entfernen von Konferenzrichtlinien mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Sie können die Trunkkonfigurationseinstellungen auch löschen, indem Sie die Lync Server-Verwaltungsshell und das Cmdlet **Remove-CsConferencingPolicy** verwenden. Sie können dieses Cmdlet über die Verwaltungsshell für Lync Server 2013 oder über eine Remote-Sitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So entfernen Sie eine angegebene Konferenzrichtlinie

  - Mit dem folgenden Befehl wird die Konferenzrichtlinie mit dem Identitätswert "RedmondConferencingPolicy" entfernt:
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

## So entfernen Sie alle auf Benutzerebene angewendeten Konferenzrichtlinien

  - Mit dem folgenden Befehl werden alle Konferenzrichtlinien entfernt, die auf Benutzerebene konfiguriert sind:
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

## So entfernen Sie alle Konferenzrichtlinien, die Aufzeichnungen durch externe Benutzer zulassen

  - Mit dem folgenden Befehl werden alle Konferenzrichtlinien gelöscht, die externen Benutzern das Aufzeichnen der Konferenz erlauben:
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

Ausführliche Informationen finden Sie unter [Remove-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsConferencingPolicy).

