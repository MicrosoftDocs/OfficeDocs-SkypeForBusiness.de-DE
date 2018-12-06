---
title: Importieren von Geräteaktualisierungsregeln
TOCTitle: Importieren von Geräteaktualisierungsregeln
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994056(v=OCS.15)
ms:contentKeyID: 52056404
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importieren von Geräteaktualisierungsregeln

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Geräteaktualisierungsregeln können nur mithilfe der Windows PowerShell und dem Cmdlet **Import-CsDeviceUpdate** importiert werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




## So importieren Sie Geräteaktualisierungsregeln auf einem einzelnen Webserver

  - Mit dem folgenden Befehl werden Geräteaktualisierungsregeln auf dem Webserver "atl-cs-001.litwareinc.com" importiert:
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

## So importieren Sie Geräteaktualisierungsregeln auf allen Ihren Webservern

  - In diesem Beispiel werden Geräteaktualisierungsregeln auf allen in Ihrer Organisation bereitgestellten Webservern importiert. Damit dieser Befehl funktioniert, muss der Ordner "\\\\atl-fs-001.litwareinc.com\\Updates" freigegeben und auf allen Webservern verfügbar sein.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Import-CsDeviceUpdate](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsDeviceUpdate).

## Siehe auch

#### Aufgaben

[Anzeigen von Informationen zu Geräteaktualisierungsregeln](lync-server-2013-view-information-about-device-update-rules.md)  
[Genehmigen einer Geräteaktualisierungsregel](lync-server-2013-approve-a-device-update-rule.md)

