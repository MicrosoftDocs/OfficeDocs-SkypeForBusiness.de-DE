---
title: 'Lync Server 2013: Anhang A: Verwenden von Cmdlets zur Bereitstellung einer Survivable Branch Appliance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2da84e03cc05607a47f1fe5af4a8b7987946df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>Anhang A: Verwenden von Cmdlets zur Bereitstellung einer Survivable Branch Appliance in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-07_

In diesem Thema wird beschrieben, wie Sie eine Survivable Branch-Appliance mithilfe der lync Server-Verwaltungsshell bereitstellen. Führen Sie dieses Verfahren am zentralen Standort aus.

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>So stellen Sie eine Survivable Branch Appliance Remote bereit

1.  Führen Sie die Schritte unter [Hinzufügen von Zweigstellen zu Ihrer Topologie in lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) aus, um eine neue Verzweigungs Website hinzuzufügen.

2.  Teilnehmen an der Zweigstelle der Domäne

3.  Fügen Sie die Gruppe RTCUniversalSBATechnicians der lokalen Gruppe Administratoren hinzu.

4.  Starten Sie den Server neu, und melden Sie sich als Mitglied der RTCUniversalSBATechnicians-Gruppe an.

5.  Geben Sie in der lync Server-Verwaltungsshell die folgenden Befehle ein, und ersetzen Sie die Platzhalter durch die richtigen Informationen für Ihre Organisation:
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

