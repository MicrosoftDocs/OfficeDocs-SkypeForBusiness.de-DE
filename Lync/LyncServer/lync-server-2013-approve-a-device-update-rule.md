---
title: Genehmigen einer Geräteaktualisierungsregel
TOCTitle: Genehmigen einer Geräteaktualisierungsregel
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994053(v=OCS.15)
ms:contentKeyID: 52056415
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Genehmigen einer Geräteaktualisierungsregel

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Nachdem Sie eine Geräteaktualisierungsregel importieren, wird sie auf Ihren Testgeräten installiert. Wenn der Test erfolgreich ist und Sie das Update in Ihrer Organisation einführen möchten, genehmigen Sie es entweder mithilfe der Lync Server-Systemsteuerung oder der Windows PowerShell.

## So genehmigen Sie eine Geräteaktualisierungsregel mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Führen Sie auf der Seite **Geräteupdate** einen der folgenden Schritte aus:
    
      - Wählen Sie eine Regel aus, um sie zu genehmigen.
    
      - Zum Genehmigen aller Regeln klicken Sie auf **Bearbeiten** und dann auf **Alle auswählen**.

4.  Klicken Sie auf **Aktion** und anschließend auf **Genehmigen**.

## Genehmigen einer Geräteaktualisierungsregel mithilfe von Windows PowerShell-Cmdlets

Geräteaktualisierungsregeln können auch mithilfe der Windows PowerShell und dem Cmdlet **Approve-CsDeviceUpdateRule** genehmigt werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



## So genehmigen Sie eine einzelne Geräteaktualisierungsregel

  - Mit dem folgenden Befehl wird die Geräteaktualisierungsregel "d5ce3c10-2588-420a-82ac-dc2d9b1222ff9" genehmigt, die sich auf dem Webserver "atl-cs-001.litwareinc.com" befindet:
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

## So genehmigen Sie mehrere Geräteaktualisierungsregeln

  - Mit diesem Befehl werden alle Geräteaktualisierungsregeln für markeneigene Microsoft-Geräte genehmigt:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Approve-CsDeviceUpdateRule).

## Siehe auch

#### Aufgaben

[Importieren von Geräteaktualisierungsregeln](lync-server-2013-import-device-update-rules.md)  
[Wiederherstellen einer Geräteaktualisierungsregel](lync-server-2013-restore-a-device-update-rule.md)

