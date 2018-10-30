---
title: Entfernen einer Geräteaktualisierungsregel
TOCTitle: Entfernen einer Geräteaktualisierungsregel
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994066(v=OCS.15)
ms:contentKeyID: 52056413
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen einer Geräteaktualisierungsregel

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Sie eine Geräteupdateregel entfernen, wird diese endgültig aus der Warteschlange für Geräteupdates entfernt.

Das Entfernen einer Regel unterscheidet sich von der Deinstallation eines Updates auf den Geräten in Ihrer Bereitstellung oder auf Testgeräten. Zum Deinstallieren eines genehmigten Updates in Ihrer Bereitstellung führen Sie eine *Wiederherstellung* der Geräteupdateregel durch. Ausführliche Informationen finden Sie unter [Wiederherstellen einer Geräteaktualisierungsregel](lync-server-2013-restore-a-device-update-rule.md). Um ein nicht genehmigtes Update auf den Testgeräten zu deinstallieren, führen Sie eine *Zurücksetzung* der Regel durch. Ausführliche Informationen finden Sie unter [Zurücksetzen einer Geräteaktualisierungsregel](lync-server-2013-reset-a-device-update-rule.md).

Sie können eine Geräteupdateregel entweder mithilfe von Lync Server-Systemsteuerung oder Windows PowerShell entfernen.

## So entfernen Sie Geräteupdateregeln mit Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Geräteupdate**.

4.  Führen Sie auf der Seite **Geräteupdate** einen der folgenden Schritte aus:
    
      - Um eine Regel zu entfernen, wählen Sie die zu löschende Regel aus.
    
      - Zum Entfernen aller Regeln klicken Sie im Menü **Bearbeiten** auf **Alles auswählen**.

5.  Klicken Sie auf **Bearbeiten** und anschließend auf **Löschen**.

## Entfernen von Geräteupdateregeln mit Windows PowerShell-Cmdlets

Geräteupdateregeln können auch mit der Windows PowerShell und dem **Remove-CsDeviceUpdateRule**-Cmdlet entfernt werden. Dieses Cmdlet kann entweder über dieVerwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So entfernen Sie eine einzelne Geräteupdateregel von einem Server

  - Der folgende Befehl entfernt die Geräteupdateregel "d5ce3c10-2588-420a-82ac-dc2d9b1222ff9" vom Webserver auf "atl-cs-001.litwareinc.com".
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## So entfernen Sie alle Geräteupdateregeln von einem Server

  - Dieser Befehl entfernt alle Geräteupdateregeln vom Webserver auf "atl-cs-001.litwareinc.com".
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDeviceUpdateRule).

## Siehe auch

#### Aufgaben

[Genehmigen einer Geräteaktualisierungsregel](lync-server-2013-approve-a-device-update-rule.md)

