---
title: 'Lync Server 2013: Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie'
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
ms.openlocfilehash: 95413733a9b23ce1f749ebb16521a3349b00165d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722955"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie in lync Server 2013

 


Das Bereitstelleneiner oder mehrerer pro Benutzer gehosteter Voicemail-Richtlinien ist optional. Wenn Sie Richtlinien für einzelne Benutzer bereitstellen, müssen Sie diese explizit Benutzern, Gruppen oder Kontaktobjekten zuweisen.

Details zum Zuweisen oder Entfernen der Zuweisung von Richtlinien für gehostete Voicemail pro Benutzer finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>So weisen Sie eine pro Benutzer gehostete Voicemail-Richtlinie zu

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet Grant-CsHostedVoicemailPolicy aus, um die Richtlinie für pro Benutzer gehostete Voicemail einzelnen Benutzern, Gruppen und Kontaktobjekten zuzuweisen. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    In diesem Beispiel wurde dem Benutzer Ken Myers die Richtlinie für die gehostete Voicemail-e-Mail zugewiesen.
    
    **Identity** gibt das zu ändernde Benutzerkonto an. Der Identity-Wert kann mit einem der folgenden Formate angegeben werden:
    
      - Die SIP-Adresse des Benutzers
    
      - Name des Active Directory-Benutzerprinzipals des Benutzers
    
      - Der Domänen\\Anmeldename des Benutzers (beispielsweise contoso\\kenmyer)
    
      - Der Anzeige Name des Active Directory-Domänen Dienstes des Benutzers (beispielsweise Ken Myers). Wenn Sie den Anzeigenamen als Identitätswert verwenden, können Sie das Platzhalterzeichen Sternchen\*() verwenden. Die Identität "\* Smith" gibt beispielsweise alle Benutzer zurück, die einen Anzeigenamen aufweisen, der mit dem Zeichenfolgenwert "Smith" endet.
    

    > [!NOTE]  
    > Der Name des Active Directory-SAM-Kontos des Benutzers kann nicht als Identitätswert verwendet werden, da der Name des SAM-Kontos in der Gesamtstruktur nicht unbedingt eindeutig ist.


