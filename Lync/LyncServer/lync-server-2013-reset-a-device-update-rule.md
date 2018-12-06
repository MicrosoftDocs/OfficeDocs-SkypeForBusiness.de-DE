---
title: Zurücksetzen einer Geräteaktualisierungsregel
TOCTitle: Zurücksetzen einer Geräteaktualisierungsregel
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994069(v=OCS.15)
ms:contentKeyID: 52056459
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zurücksetzen einer Geräteaktualisierungsregel

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Sie mit der Funktionsweise eines Updates auf den Testgeräten nicht zufrieden sind, können Sie die Geräteupdateregel zurücksetzen. Dadurch wird der ausstehende Status der Regel entfernt und das Update von den Testgeräten entfernt.

Sie können eine Geräteupdateregel entweder mithilfe von Lync Server-Systemsteuerung oder Windows PowerShell entfernen.


> [!NOTE]
> Um eine bereits genehmigte (d.&nbsp;h. eingeführte) Regel zu entfernen, müssen Sie sie einfach nur wiederherstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-restore-a-device-update-rule.md">Wiederherstellen einer Geräteaktualisierungsregel</A>.



## So setzen Sie eine Geräteupdateregel mithilfe von Lync Server-Systemsteuerung zurück

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Geräteupdate**.

4.  Führen Sie auf der Seite **Geräteupdate** einen der folgenden Schritte aus:
    
      - Um eine Regel zurückzusetzen, wählen Sie die zurückzusetzende Regel aus.
    
      - Zum Zurücksetzen aller Regeln klicken Sie im Menü **Bearbeiten** auf **Alle auswählen**.
    
      - Um alle Regeln für eine Marke zurückzusetzen, verwenden Sie das Spaltenmenü **Marke**.

5.  Klicken Sie auf **Aktion**, und klicken Sie dann auf **Ausstehende Updates abbrechen**.
    

    > [!TIP]
    > Wenn Sie ganz sicher sind, dass Sie die abgebrochenen Geräteupdateregeln nie wieder einführen möchten, können Sie sie löschen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-remove-a-device-update-rule.md">Entfernen einer Geräteaktualisierungsregel</A>.



## Zurücksetzen einer Geräteupdateregel mithilfe von Windows PowerShell-Cmdlets

Geräteupdateregeln können auch mit der Windows PowerShell und dem **Reset-CsDeviceUpdateRule**-Cmdlet zurückgesetzt werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



## So setzen Sie eine bestimmte Geräteupdateregel zurück

  - Mit dem folgenden Befehl wird die Geräteupdateregel "d5ce3c10-2588-420a-82ac-dc2d9b1222ff9" auf dem Webserver "atl-cs-001.litwareinc.com" zurückgesetzt:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## So setzen Sie auf einem Server alle Geräteupdateregeln zurück

  - Mit diesem Befehl werden alle Geräteupdateregeln auf dem Webserver "atl-cs-001.litwareinc.com" zurückgesetzt:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

## So setzen Sie alle Geräteupdateregeln für eine bestimmte Marke zurück

  - In diesem Beispiel werden alle Geräteupdates mit der Marke Microsoft in der gesamten Organisation zurückgesetzt:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Reset-CsDeviceUpdateRule).

## Siehe auch

#### Aufgaben

[Genehmigen einer Geräteaktualisierungsregel](lync-server-2013-approve-a-device-update-rule.md)

