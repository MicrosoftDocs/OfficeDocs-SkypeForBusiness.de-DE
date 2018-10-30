---
title: Löschen einer vorhandenen Clientversionsrichtlinie
TOCTitle: Löschen einer vorhandenen Clientversionsrichtlinie
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ923064(v=OCS.15)
ms:contentKeyID: 52056420
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer vorhandenen Clientversionsrichtlinie

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Sie eine zuvor konfigurierte Clientversionsrichtlinie löschen möchten, können Sie diese über die Systemsteuerung für Lync Server 2013 oder die Verwaltungsshell für Lync Server 2013 löschen.

## So löschen Sie Clientversionsrichtlinien mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Clientversionsrichtlinie**.

4.  Wählen Sie auf der Seite **Clientversionsrichtlinie** die Clientversionsrichtlinie(n) aus, die Sie löschen möchten. Klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

## Löschen von Clientversionsrichtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können Clientversionsrichtlinien mithilfe des **Remove-CsClientVersionPolicy**-Cmdlets löschen. Dieses Cmdlet kann entweder von der Verwaltungsshell für Lync Server 2013 aus oder in einer Remotesitzung der Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So entfernen Sie eine bestimmte Clientversionsrichtlinie

  - Mit diesem Befehl wird die Clientversionsrichtlinie gelöscht, die auf den Standort "Redmond" angewendet wird:
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

## So entfernen Sie alle Clientversionsrichtlinien, die auf Standortebene angewendet wurden

  - Mit diesem Befehl werden alle Clientversionsrichtlinien entfernt, die auf Standortebene konfiguriert sind:
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

## So entfernen Sie die Clientversionsrichtlinien, die keinen bestimmten Benutzer-Agent enthalten

  - Und mit diesem Befehl werden alle Clientversionsrichtlinien entfernt, die keine Regel für den Windows Phone Lync (WPLync)-Benutzer-Agent enthalten:
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Remove-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionPolicy).

