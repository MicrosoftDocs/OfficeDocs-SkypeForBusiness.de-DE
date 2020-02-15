---
title: 'Lync Server 2013: Aktivieren von Benutzern für gehostete Voicemail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7287f31a4dc0e43b0108ce666e9c65f51f75f2d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Aktivieren von Benutzern für gehostete Voicemail in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-24_

Führen Sie das Verfahren aus, um lync Server 2013 Benutzer für Voicemail in einem gehosteten Exchange Unified Messaging (um)-Dienst zu aktivieren.

Ausführliche Informationen finden Sie unter [Hosted Exchange User Management in lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in der Planungsdokumentation.

Ausführliche Informationen zum Cmdlet " [CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) " finden Sie in der Dokumentation zum lync Server-Verwaltungsshell.

<div>


> [!IMPORTANT]  
> Bevor ein lync Server 2013-Benutzer für gehostete Voicemail aktiviert werden kann, muss eine Richtlinie für gehostete Voicemail, die für Ihr Benutzerkonto gilt, bereitgestellt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted Voice Mail Policies in lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>So aktivieren Sie Benutzer für gehostete Voicemail

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "CsUser" aus, um das Benutzerkonto für gehostete Voicemail zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **HostedVoiceMail** ermöglicht das Weiterleiten von Voicemail-anrufen eines Benutzers an gehostete Exchange um. Außerdem wird Microsoft lync 2013 signalisiert, dass das Symbol "Voicemail anrufen" angezeigt wird.
    
      - **Identity** gibt die Identität des zu ändernden Benutzerkontos an. Der Wert "Identity" kann unter Verwendung eines der folgenden Formate angegeben werden:
        
          - SIP-Adresse des Benutzers
        
          - Active Directory-Benutzerprinzipalname des Benutzers
        
          - Der Domänen\\Anmeldename des Benutzers (beispielsweise "Contoso\\kenmyer")
        
          - AD DS-Anzeigename des Benutzers (zum Beispiel "Ken Myer"). Wenn Sie den Anzeigenamen als Identitätswert verwenden, können Sie das Platzhalterzeichen Sternchen\*() verwenden. Die Identität "\* Smith" gibt beispielsweise alle Benutzer zurück, die einen Anzeigenamen haben, der mit dem Zeichenfolgenwert "Smith" endet.
        
        <div>
        

        > [!NOTE]  
        > Der Active Directory-SAM-Kontoname eines Benutzers kann nicht als Identitätswert verwendet werden, da dieser Name innerhalb der Gesamtstruktur nicht unbedingt eindeutig ist.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

