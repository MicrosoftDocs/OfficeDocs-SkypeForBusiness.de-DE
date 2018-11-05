---
title: Aktivieren oder Deaktivieren eines Konferenzgeräts
TOCTitle: Aktivieren oder Deaktivieren eines Konferenzgeräts
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994070(v=OCS.15)
ms:contentKeyID: 52056462
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren eines Konferenzgeräts

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Konferenzgeräte können mit den Cmdlets **Enable-CsMeetingRoom** und **Disable-CsMeetingRoom** aktiviert und deaktiviert werden. Diese Cmdlets können entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




## Aktivieren eines Konferenzgeräts

  - Verwenden Sie zum Aktivieren eines Konferenzgeräts das **Enable-CsMeetingRoom**-Cmdlet. Beim Aktivieren eines Konferenzgeräts müssen Sie Folgendes einfügen: a) die Identität des Konferenzgeräts, b) den Registrierungsstellenpool, in dem das Raumkonto verwaltet wird, und c) die SIP-Adresse, die diesem Konto zugewiesen wird.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## Deaktivieren eines Konferenzgeräts

  - Zum Deaktivieren eines Konferenzgeräts verwenden Sie das **Disable-CsMeetingRoom**-Cmdlet. Stellen Sie sicher, dass Sie die Identität des zu deaktivierenden Konferenzgeräts angeben:
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

Einzelheiten dazu finden Sie in den Hilfethemen zu den Cmdlets [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom) und [Disable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsMeetingRoom).

