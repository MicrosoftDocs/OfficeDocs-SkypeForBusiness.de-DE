---
title: 'Lync Server 2013: Erstellen einer Richtlinie für gehostete Voicemail-Benutzer pro Benutzer'
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
ms.openlocfilehash: 4e13002fa83215c5c1aade627cb6e7ea86cf0a04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Erstellen Sie eine benutzerbasierte Richtlinie für gehostete Voicemail in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-24_

Eine Richtlinie auf *Benutzerebene* wirkt sich ausschließlich auf einzelne Benutzer, Gruppen und Kontaktobjekte aus. Zum Bereitstellen einer Richtlinie auf Benutzerebene müssen Sie die Richtlinie explizit auf einen oder mehrere Benutzer, Gruppen oder Kontaktobjekte anwenden. Ausführliche Informationen finden Sie unter [assign a User Hosted Voice Mail Policy in lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Ausführliche Informationen zum Arbeiten mit benutzerseitigen Richtlinien für gehostete Voicemail finden Sie in der lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Gruppe-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>So erstellen Sie eine Richtlinie für gehostete Voicemail auf Benutzerebene

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "New-CsHostedVoicemailPolicy" aus, um die Richtlinie zu erstellen.  Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    In diesem Beispiel wird eine Richtlinie für gehostete Voicemail auf Benutzerebene erstellt. Hierbei werden die folgenden Parameter festgelegt:
    
      - **Identity** gibt eine eindeutige ID für die Richtlinie an, die den Bereich einschließt. Für eine Richtlinie auf Benutzerebene wird dieser Parameterwert als einfache Zeichenfolge angegeben, z. B. "ExRedmond".
    
      - **Destination** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange UM-Diensts an. Dieser Parameter ist optional. Wenn Sie jedoch versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers nicht auf "Destination" festgelegt ist, tritt bei der Aktivierung ein Fehler auf.
    
      - **Description** stellt eine optionale Beschreibung zur Richtlinie bereit.
    
      - **Organization** gibt eine durch trennzeichengetrennte Liste der Exchange-Mandanten an, die lync Server 2013 Benutzer zu Hause sind. Für jeden Mandanten muss der vollqualifizierte Domänenname des Mandanten im gehosteten Exchange-Dienst angegeben werden.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zuweisen einer Richtlinie für gehostete Voicemail pro Benutzer in lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

