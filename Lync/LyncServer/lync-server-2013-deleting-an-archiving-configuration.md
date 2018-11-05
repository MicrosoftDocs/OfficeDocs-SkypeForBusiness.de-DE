---
title: Löschen einer Archivierungskonfiguration
TOCTitle: Löschen einer Archivierungskonfiguration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205167(v=OCS.15)
ms:contentKeyID: 49295021
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer Archivierungskonfiguration

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Standort- oder Poolkonfigurationen können gelöscht werden. Das Entfernen der globalen Konfiguration ist nicht möglich. Wenn Sie die globale Konfiguration löschen, wird sie automatisch auf die Standardwerte zurückgesetzt. Ausführliche Informationen zur Implementierung der Archivierungskonfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungskonfigurationen, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation.

## So löschen Sie eine Standort- oder Poolkonfiguration für die Archivierung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie in der Liste der Archivierungskonfigurationen auf die zu löschende Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

5.  Klicken Sie auf **Commit**.

## Entfernen der Archivierungskonfigurationseinstellungen mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Archivierungskonfigurationseinstellungen können ebenfalls mithilfe der Windows PowerShell und des Cmdlets "Remove-CsArchivingConfiguration" gelöscht werden. Dieses Cmdlet kann über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

## Entfernen einer bestimmten Sammlung mit Archivierungskonfigurationseinstellungen

  - Mithilfe des folgenden Befehls werden die auf den Standort Redmond angewendeten Archivierungskonfigurationseinstellungen entfernt:
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

## Entfernen aller auf Standortebene angewendeten Archivierungskonfigurationseinstellungen

  - Mithilfe dieses Befehls werden alle Archivierungskonfigurationseinstellungen entfernt, die auf Standortebene angewendet werden:
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

## Entfernen der Archivierungskonfigurationseinstellungen basierend auf einem angegebenen Eigenschaftswert

  - Mithilfe dieses Befehls werden alle Archivierungskonfigurationseinstellungen entfernt, für die die Exchange-Archivierung deaktiviert wurde:
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

Weitere Informationen dazu finden Sie im Hilfethema für das Cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsArchivingConfiguration).

## Siehe auch

#### Konzepte

[Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Weitere Ressourcen

[Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

