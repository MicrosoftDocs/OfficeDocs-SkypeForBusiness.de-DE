---
title: 'Lync Server 2013: Privatbenutzer auf einem Survivable Branch Appliance oder Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: add711ca547648a6071a22fee6a0bcd0eeb0f6c0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528202"
---
# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Privatbenutzer auf einem Survivable Branch Appliance oder Server in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-12-10_

Der Vorgang des Benutzer Verweises auf einem Survivable Branch Appliance oder einem Survivable Branch Server ähnelt dem Verfahren, bei dem Benutzer auf eine Front-End-Pool gereferenzt werden. Führen Sie die Survivable Branch Appliance-oder Survivable Branch Server-Prozedur am zentralen Standort aus.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Für Privatbenutzer auf Survivable Branch Appliance oder Survivable Branch Server

1.  Bevor Sie Benutzer in die Survivable Branch Server oder Survivable Branch Server verschieben, öffnen Sie die lync Server-Verwaltungsshell, und führen Sie dann die folgenden Aktionen aus:
    
      - Führen Sie das Cmdlet **Test-CsPstnOutboundCall** aus, um sicherzustellen, dass die Survivable Branch Server ausgeführt wird und dass die PSTN-Konnektivität (Public Switched Telephone Network) konfiguriert ist. Wenn Sie die Eigenschaften des PSTN-Gateways ändern müssen, verwenden Sie das Cmdlet " **CsPstnGateway**".
    
      - Führen Sie das Cmdlet **Get-CsVoicePolicy** aus, um sicherzustellen, dass die Benutzer, die im Survivable Branch Server verwaltet werden, über die entsprechende VoIP-Routing Richtlinie verfügen. Wenn Sie die VoIP-Richtlinie ändern müssen, verwenden Sie das Cmdlet " **CsVoicePolicy**".
    
      - Führen Sie das Cmdlet **Get-CsVoicemailReroutingConfiguration** aus, um zu überprüfen, ob die Einstellungen für das Umleiten von Voicemail konfiguriert sind. Wenn Sie die Einstellungen für das Umleiten von Voicemail ändern müssen, verwenden Sie das Cmdlet " **CsVoicemailReroutingConfiguration**".

2.  Führen Sie im lync Server-Verwaltungsshell das Cmdlet " **CsUser** " aus, um Benutzer von Privatbenutzern zu migrieren.

<div>


> [!NOTE]  
> Sie können auch lync Server-Systemsteuerung verwenden, um Voraussetzungen und private Benutzer zu überprüfen.



</div>

<div>


> [!NOTE]  
> Benutzer, die in einer lync Server Survivable Branch Appliance verwaltet werden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

