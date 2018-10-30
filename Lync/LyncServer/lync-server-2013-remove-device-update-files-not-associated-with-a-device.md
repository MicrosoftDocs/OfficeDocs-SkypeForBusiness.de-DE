---
title: Entfernen von Geräteaktualisierungsdateien, die keinem Gerät zugeordnet sind
TOCTitle: Entfernen von Geräteaktualisierungsdateien, die keinem Gerät zugeordnet sind
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994084(v=OCS.15)
ms:contentKeyID: 52056482
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen von Geräteaktualisierungsdateien, die keinem Gerät zugeordnet sind

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Jedes Mal, wenn neue Geräteupdates in das System hochgeladen werden, wird eine entsprechende Geräteupdateregel erstellt. Diesen neuen Geräteupdateregeln wird standardmäßig der Status "Ausstehend" zugewiesen. Dies bedeutet, dass die Regeln auf Testgeräte, nicht jedoch auf Produktionsgeräte heruntergeladen und auf ihnen installiert werden können. Dies bietet Ihnen die Möglichkeit, die Updates zu testen, bevor sie Benutzern zur Verfügung gestellt werden. Basierend auf den Tests können Sie Updates entweder akzeptieren und bereitstellen oder ablehnen und löschen. Wenn Sie ein Update ablehnen, wird die Verknüpfung des Geräteupdates mit der Geräteupdateregel aufgehoben.


Geräteupdatedateien, die nicht mehr mit einem Gerät verknüpft sind, können mit der Windows PowerShell und dem **Clear-CsDeviceUpdateFile**-Cmdlet entfernt werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




  - Mit dem folgenden Befehl werden beispielsweise Geräteupdateregeln, die nicht mehr mit einem Gerät verknüpft sind, vom Webserver "atl-cs-001.litwareinc.com" entfernt:
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/en-us/powershell/module/skype/Clear-CsDeviceUpdateFile).

