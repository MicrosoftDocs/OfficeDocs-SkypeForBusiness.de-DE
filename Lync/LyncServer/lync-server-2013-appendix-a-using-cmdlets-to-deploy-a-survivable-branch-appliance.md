---
title: 'Lync Server 2013: Anhang a: Verwenden von Cmdlets zum Bereitstellen eines Survivable Branch Appliance'
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
ms.openlocfilehash: 107bc5f9b39b1d62db0cba6960b60307c82831fb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>Anhang a: Verwenden von Cmdlets zum Bereitstellen eines Survivable Branch Appliance in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-07_

In diesem Thema wird beschrieben, wie Sie eine Survivable Branch Appliance mithilfe der lync Server-Verwaltungsshell bereitstellen. Führen Sie dieses Verfahren am zentralen Standort aus.

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>So stellen Sie einen Survivable Branch Appliance Remote bereit

1.  Führen Sie das Verfahren unter [Hinzufügen von Zweigstellenstandorten zu Ihrer Topologie in lync Server 2013 aus](lync-server-2013-add-branch-sites-to-your-topology.md) , um eine neue Zweigstelle hinzuzufügen.

2.  Fügen Sie den Zweigstellenstandort zur Domäne hinzu.

3.  Fügen Sie die Gruppe "RTCUniversalSBATechnicians" zur lokalen Administratorgruppe hinzu.

4.  Starten Sie den Server neu, und melden Sie sich als Mitglied der Gruppe "RTCUniversalSBATechnicians" an.

5.  Geben Sie im lync Server-Verwaltungsshell die folgenden Befehle ein, und ersetzen Sie die Platzhalter durch die richtigen Informationen für Ihre Organisation:
    
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

