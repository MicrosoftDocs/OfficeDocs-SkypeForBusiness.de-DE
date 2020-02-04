---
title: 'Lync Server 2013: Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server'
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
ms.openlocfilehash: 0c6cca9528e884807f6180d8c99b143eb0041211
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-12-10_

Der Vorgang zum Durchführen von Benutzern auf einer überlebensfähigen Branch-Appliance oder einem Überlebenden Verzweigungs Server ähnelt dem Verfahren zum Durchführen von Benutzern in einem Front-End-Pool. Führen Sie das Survivable Branch Appliance-oder Survivable Branch Server-Verfahren am zentralen Standort aus.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Für private Benutzer auf Survivable Branch Appliance oder Survivable Branch Server

1.  Öffnen Sie die lync Server-Verwaltungsshell, bevor Sie Benutzer auf den Überlebenden Verzweigungs Server oder Überlebenden Verzweigungs Server verschieben, und führen Sie dann die folgenden Aktionen aus:
    
      - Führen Sie das Cmdlet **Test-CsPstnOutboundCall** aus, um zu überprüfen, ob der überlebensfähige Verzweigungs Server ausgeführt wird und ob die PSTN-Konnektivität (Public Switched Telephone Network) konfiguriert ist. Wenn Sie die Eigenschaften des PSTN-Gateways ändern müssen, verwenden Sie das Cmdlet **Satz-CsPstnGateway**.
    
      - Führen Sie das Cmdlet **Get-CsVoicePolicy** aus, um zu überprüfen, ob die Benutzer, die auf dem Überlebenden Verzweigungs Server verwaltet werden, über die entsprechende VoIP-Routing Richtlinie verfügen. Wenn Sie die VoIP-Richtlinie ändern müssen, verwenden Sie das Cmdlet **Satz-CsVoicePolicy**.
    
      - Führen Sie das Cmdlet **Get-CsVoicemailReroutingConfiguration** aus, um zu überprüfen, ob die Einstellungen für Voicemail-Umleitungen konfiguriert sind. Wenn Sie die Einstellungen für das Ändern der Voicemail-Einstellungen ändern müssen, verwenden Sie das Cmdlet **-Cmdlet-Satz-CsVoicemailReroutingConfiguration**.

2.  Führen Sie in der lync Server-Verwaltungsshell das Cmdlet **Move-CsUser** aus, um private Benutzer zu verschieben.

<div>


> [!NOTE]  
> Sie können auch die lync Server-Systemsteuerung verwenden, um Voraussetzungen und private Benutzer zu überprüfen.



</div>

<div>


> [!NOTE]  
> Benutzer, die sich in einer Überlebenden lync Server-Branch-Appliance befinden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

