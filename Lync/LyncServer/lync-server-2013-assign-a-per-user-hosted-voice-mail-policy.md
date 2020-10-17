---
title: 'Lync Server 2013: Zuweisen einer Hosted Voice Mail-Richtlinie pro Benutzer'
description: 'Lync Server 2013: weisen Sie eine gehostete Voicemail-Richtlinie pro Benutzer zu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559891"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Zuweisen einer Richtlinie für gehostete Voicemail pro Benutzer in lync Server 2013

 


Die Bereitstellung einer oder mehrerer Benutzerrichtlinien für gehostete Voicemail ist optional. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie diese Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen.

Ausführliche Informationen zum Zuweisen oder Entfernen der Zuweisung von Richtlinien für gehostete Voicemails pro Benutzer finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>So weisen Sie eine Benutzerrichtlinie für gehostete Voicemail zu

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Grant-CsHostedVoicemailPolicy" aus, um die Benutzerrichtlinie für gehostete Voicemail einzelnen Benutzern, Gruppen oder Kontaktobjekten zuzuweisen. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    In diesem Beispiel wird die Richtlinie für gehostete Voicemail "ExRedmond" dem Benutzer Ken Myer zugewiesen.
    
    **Identity** gibt die Identität des zu ändernden Benutzerkontos an. Der Wert "Identity" kann unter Verwendung eines der folgenden Formate angegeben werden:
    
      - SIP-Adresse des Benutzers
    
      - Active Directory-Benutzerprinzipalname des Benutzers
    
      - Der Domänen \\ Anmeldename des Benutzers (beispielsweise "Contoso \\ kenmyer")
    
      - AD DS-Anzeigename des Benutzers (zum Beispiel "Ken Myer"). Wenn Sie die Display-Name als Identitätswert verwenden, können Sie das \* Platzhalterzeichen Sternchen () verwenden. Die Identität " \* Smith" gibt beispielsweise alle Benutzer zurück, die eine Display-Name haben, die mit dem Zeichenfolgenwert "Smith" endet.
    

    > [!NOTE]  
    > Der Active Directory-SAM-Kontoname eines Benutzers kann nicht als Identitätswert verwendet werden, da dieser Name innerhalb der Gesamtstruktur nicht unbedingt eindeutig ist.


