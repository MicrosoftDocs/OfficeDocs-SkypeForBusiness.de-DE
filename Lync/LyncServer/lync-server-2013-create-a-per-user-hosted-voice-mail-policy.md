---
title: 'Lync Server 2013: Erstellen einer pro Benutzer gehosteten Voicemail-Richtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535515fd11c0cb736b5b6fb4b70d041ea3af8a3c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Erstellen einer pro Benutzer gehosteten Voicemail-Richtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Eine Richtlinie *pro Benutzer* kann nur Auswirkungen auf einzelne Benutzer, Gruppen und Kontaktobjekte haben. Wenn Sie eine Richtlinie pro Benutzer bereitstellen möchten, müssen Sie die Richtlinie explizit einem oder mehreren Benutzern, Gruppen oder Kontaktobjekten zuweisen. Ausführliche Informationen finden Sie unter [Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie in lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Ausführliche Informationen zum Arbeiten mit Richtlinien für gehostete Voicemail pro Benutzer finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - [Neu – CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Satz-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>So erstellen Sie eine pro Benutzer gehostete Voicemail-Richtlinie

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet New-CsHostedVoicemailPolicy aus, um die Richtlinie zu erstellen. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    Im vorherigen Beispiel wird eine gehostete Voicemail-Richtlinie mit benutzerspezifischem Bereich erstellt, und die folgenden Parameter werden festgelegt:
    
      - **Identity** gibt einen eindeutigen Bezeichner für die Richtlinie an, der den Bereich umfasst. Bei einer Richtlinie mit benutzerspezifischem Gültigkeitsbereich wird dieser Parameterwert als einfache Zeichenfolge angegeben, beispielsweise "" "," "".
    
      - **Ziel** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange um-Diensts an. Dieser Parameter ist optional, aber wenn Sie versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers keinen Zielwert hat, schlägt die Aktivierung fehl.
    
      - **Beschreibung** enthält optionale beschreibende Informationen zur Richtlinie.
    
      - **Organisation** gibt eine durch trennzeichengetrennte Liste der Exchange-Mandanten an, die lync Server 2013-Benutzer sind. Jeder Mandant muss als FQDN dieses Mandanten für den gehosteten Exchange um-Dienst angegeben werden.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie in lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

