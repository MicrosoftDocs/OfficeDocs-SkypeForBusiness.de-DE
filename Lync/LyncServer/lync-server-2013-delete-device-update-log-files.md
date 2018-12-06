---
title: Löschen von Protokolldateien für die Geräteaktualisierung
TOCTitle: Löschen von Protokolldateien für die Geräteaktualisierung
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994039(v=OCS.15)
ms:contentKeyID: 52056365
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen von Protokolldateien für die Geräteaktualisierung

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Der Geräteaktualisierungswebdienst speichert eine umfassende Auflistung von Protokolldateien. Diese Auflistung enthält sowohl Protokolle der durch den Dienst selbst durchgeführten Überwachung als auch Protokolldateien, die von Clientgeräten hochgeladen wurden. Damit der Server nicht durch Geräteaktualisierungswebdienst-Protokolle überfüllt wird, sollten Sie Protokolldateien nach einigen Tagen löschen. Legen Sie die Anzahl der Tage basierend auf der Updateaktivitäten und der Anzahl von Clientgeräten in Ihrer Organisation fest. Verwenden Sie dazu die Lync Server-Systemsteuerung oder die Lync Server-Verwaltungsshell.

## So löschen Sie Geräteaktualisierungsprotokolle mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Geräteprotokollkonfiguration**.

3.  Doppelklicken Sie auf der Seite **Geräteprotokollkonfiguration** auf die Konfiguration, die Sie ändern möchten.

4.  Geben Sie im Dialogfeld **Protokolleinstellungen bearbeiten** in **Speicherung von Protokolldateien in Tagen (1-365)** eine Anzahl von Tagen an.

5.  Klicken Sie auf **Commit**. Alle Dateien, die sich länger als die angegebene Anzahl von Tagen auf dem Server befinden, werden gelöscht. Diese Einstellung gilt für diese Konfiguration, bis Sie sie ändern.

## Löschen von Geräteaktualisierungsprotokollen mithilfe der Windows PowerShell-Cmdlets

Geräteaktualisierungsprotokolle können Sie mithilfe von Windows PowerShell und dem Cmdlet **Clear-CsDeviceUpdateLog** löschen. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



## So löschen Sie Geräteaktualisierungsprotokolle auf einem Server

  - Mit dem folgenden Befehl wird das Geräteaktualisierungsprotokoll auf dem Webserver "atl-cs-001.litwareinc.com" gelöscht. Alle Protokolleinträge, die älter als 10 Tage sind (der durch den DaysBack-Parameter angegebene Wert) werden aus dem Protokoll entfernt.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

## So löschen Sie alle Geräteaktualisierungsprotokolle

  - Mit diesem Befehl werden veraltete Einträge (in diesem Beispiel Einträge, die älter als 10 Tage sind) aus allen in Ihrer Organisation verwendeten Geräteaktualisierungsprotokollen entfernt.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/en-us/powershell/module/skype/Clear-CsDeviceUpdateLog).

