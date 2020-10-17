---
title: 'Lync Server 2013: Zuweisen von Richtlinien zu einem Telefon im öffentlichen Bereich'
description: 'Lync Server 2013: Zuweisen von Richtlinien zu einem Telefon im öffentlichen Bereich.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe437ec87ba30eff834239db2b4815adb2d5718c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559821"
---
# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a>Zuweisen von Richtlinien in lync Server 2013 zu einem Telefon im öffentlichen Bereich

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

Nachdem Sie Ihre Richtlinie für Telefone für gemeinsame Bereiche erstellt haben (Weitere Informationen finden Sie unter [Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), können Sie die Richtlinie mithilfe von Windows PowerShell und dem entsprechenden **Grant-CS-** Cmdlet einem Telefon im öffentlichen Bereich zuweisen. Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a>Zuweisen einer Richtlinie zu einem einzelnen Telefon im öffentlichen Bereich

  - Mit dem folgenden Befehl wird die benutzerspezifische VoIP-Richtlinie RedmondVoice dem Telefon für öffentliche Bereiche zugewiesen, das über die Lobby "Identity Building 14" verfügt.
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a>Zuweisen einer Richtlinie zu mehreren Telefonen für gemeinsame Bereiche

  - In diesem Beispiel wird die benutzerspezifische VoIP-Richtlinie RedmondVoice allen für die Verwendung in der Organisation konfigurierten Telefonen für gemeinsame Bereiche zugewiesen.
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

Ausführliche Informationen finden Sie in den Hilfethemen für das [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

