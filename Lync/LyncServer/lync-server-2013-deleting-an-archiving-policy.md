---
title: Löschen einer Archivierungsrichtlinie
TOCTitle: Löschen einer Archivierungsrichtlinie
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520989(v=OCS.15)
ms:contentKeyID: 49293874
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer Archivierungsrichtlinie

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Benutzer- und Standortrichtlinien können gelöscht werden. Die globale Richtlinie kann nicht entfernt werden. Wenn Sie die globale Richtlinie löschen, wird die Richtlinie von Lync Server 2013 automatisch auf die Standardwerte zurückgesetzt.


> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, steuern Exchange-Richtlinien das Aktivieren der Archivierung für Benutzer, die in Exchange 2013 verwaltet werden, und legen die Postfächer auf "In-Place Hold" fest. Nähere Informationen dazu finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung beim Verwenden von Exchange Server-Integration</A>.



## So löschen Sie eine Benutzer- oder Standortrichtlinie für die Archivierung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.

4.  Klicken Sie in der Liste der Archivierungsrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, auf **Bearbeiten** und dann auf **Löschen**.

5.  Klicken Sie auf **Commit**.

## Entfernen von Archivierungsrichtlinien mit den Cmdlets von Lync Server-Verwaltungsshell

Archivierungsrichtlinien können auch mit Windows PowerShell und mit dem Cmdlet **Remove-CsArchivingPolicy** gelöscht werden. Dieses Cmdlet kann über Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Entfernen einer angegebenen Archivierungsrichtlinie

  - **Remove-CsArchivingPolicy** löscht beispielsweise die Richtlinie mit der Identität "site:Redmond". Wenn Sie eine auf Standortebene konfigurierte Richtlinie löschen, werden Benutzer, die zuvor durch die Standortrichtlinie verwaltet wurden, automatisch durch die globale Archivierungsrichtlinie verwaltet. Mit dem folgenden Befehl wird die Archivierung für den Standort "Redmond" entfernt:
    
        Remove-CsArchivingPolicy -Identity site:Redmond

## Entfernen aller auf der Benutzerbasis angewendeten Archivierungsrichtlinien

  - Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, die auf der Benutzerbasis festgelegt wurden:
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

## Entfernen aller Archivierungsrichtlinien mit Deaktivierung der internen Archivierung

  - Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, bei denen die interne Archivierung deaktiviert wurde:
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsArchivingPolicy).

## Siehe auch

#### Weitere Ressourcen

[Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

