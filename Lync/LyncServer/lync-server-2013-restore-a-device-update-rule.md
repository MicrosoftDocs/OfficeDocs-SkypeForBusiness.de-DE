---
title: Wiederherstellen einer Geräteaktualisierungsregel
TOCTitle: Wiederherstellen einer Geräteaktualisierungsregel
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994061(v=OCS.15)
ms:contentKeyID: 52056412
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen einer Geräteaktualisierungsregel

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können eine Geräteupdateregel auf Geräten in Ihrer Bereitstellung deinstallieren, indem Sie die Regel wiederherstellen. Durch das Wiederherstellen einer Geräteupdateregel wird sowohl das Update deinstalliert als auch wieder die vorherige Version dieser Regel installiert.

Sie können eine Geräteupdateregel entweder mithilfe der Lync Server-Systemsteuerung oder über die Windows PowerShell wiederherstellen.

## So stellen Sie Geräteupdateregeln mithilfe der Lync Server-Systemsteuerung wieder her

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Geräteupdate**.

4.  Führen Sie auf der Seite **Geräteupdate** einen der folgenden Schritte aus:
    
      - Wählen Sie eine Regel aus, um sie wiederherzustellen.
    
      - Zum Wiederherstellen aller Regeln klicken Sie auf **Bearbeiten** und dann auf **Alle auswählen**.

5.  Klicken Sie im Menü **Aktion** auf **Wiederherstellen**.

## Wiederherstellen von Geräteupdateregeln mit Windows PowerShell-Cmdlets

Geräteupdateregeln können auch mit der Windows PowerShell und dem **Restore-CsDeviceUpdateRule**-Cmdlet wiederhergestellt werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



## So stellen Sie auf einem Server eine einzelne Geräteupdateregel wieder her

  - Mit dem folgenden Befehl wird die Geräteupdateregel "d5ce3c10-2588-420a-82ac-dc2d9b1222ff9" auf dem Webserver "atl-cs-001.litwareinc.com" wiederhergestellt:
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## So stellen Sie auf einem Server alle Geräteupdateregeln wieder her

  - Mit diesem Befehl werden alle Geräteupdateregeln auf dem Webserver "atl-cs-001.litwareinc.com" wiederhergestellt:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Restore-CsDeviceUpdateRule).

