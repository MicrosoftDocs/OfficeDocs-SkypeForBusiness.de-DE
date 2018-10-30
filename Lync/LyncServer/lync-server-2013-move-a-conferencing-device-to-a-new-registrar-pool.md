---
title: Verschieben eines Konferenzgeräts in einen neuen Registrierungsstellenpool
TOCTitle: Verschieben eines Konferenzgeräts in einen neuen Registrierungsstellenpool
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994025(v=OCS.15)
ms:contentKeyID: 52056316
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben eines Konferenzgeräts in einen neuen Registrierungsstellenpool

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Verschieben eines Konferenzgeräts in einen neuen Registrierungsstellenpool mithilfe des Cmdlets **Move-CsMeetingRoom**. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




## Verschieben eines Konferenzgeräts in einen neuen Registrierungsstellenpool

  - Zum Verschieben eines Konferenzgeräts müssen Sie die Identität des zu verschiebenden Raums angeben und anschließend für den Target-Parameter den vollqualifizierten Domänennamen (FQDN) des Registrierungsstellenpools festlegen, in den das gerät verschoben wird. Beispiel:
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Move-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsMeetingRoom).

