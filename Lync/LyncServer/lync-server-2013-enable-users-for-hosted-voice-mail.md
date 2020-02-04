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
ms.openlocfilehash: 8e0ce9ee4da6ee0a36e5e5f0028371aab8af523f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Aktivieren von Benutzern für gehostete Voicemail in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Führen Sie das Verfahren zum Aktivieren von lync Server 2013-Benutzern für Voicemail in einem gehosteten Exchange Unified Messaging (um)-Dienst aus.

Ausführliche Informationen finden Sie unter [gehostete Exchange-Benutzerverwaltung in lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in der Planungsdokumentation.

Details zum Cmdlet " [setCsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) " finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.

<div>


> [!IMPORTANT]  
> Bevor ein lync Server 2013-Benutzer für gehostete Voicemail aktiviert werden kann, muss eine gehostete Voicemail-Richtlinie bereitgestellt werden, die für Ihr Benutzerkonto gilt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>So aktivieren Sie Benutzer für gehostete Voicemails

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Satz-CsUser" aus, um das Benutzerkonto für gehostete Voicemail zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **HostedVoiceMail** ermöglicht es, dass die Voicemail-Anrufe eines Benutzers an den Hosted Exchange um weitergeleitet werden. Außerdem signalisiert Microsoft lync 2013, dass die Anzeige "Voicemail anrufen" leuchtet.
    
      - **Identity** gibt das zu ändernde Benutzerkonto an. Der Identity-Wert kann mit einem der folgenden Formate angegeben werden:
        
          - Die SIP-Adresse des Benutzers
        
          - Name des Active Directory-Benutzerprinzipals des Benutzers
        
          - Der Domänen\\Anmeldename des Benutzers (beispielsweise contoso\\kenmyer)
        
          - Der Anzeige Name des Active Directory-Domänen Dienstes des Benutzers (beispielsweise Ken Myers). Wenn Sie den Anzeigenamen als Identitätswert verwenden, können Sie das Platzhalterzeichen Sternchen\*() verwenden. Die Identität "\* Smith" gibt beispielsweise alle Benutzer zurück, die einen Anzeigenamen aufweisen, der mit dem Zeichenfolgenwert "Smith" endet.
        
        <div>
        

        > [!NOTE]  
        > Der Name des Active Directory-SAM-Kontos des Benutzers kann nicht als Identitätswert verwendet werden, da der Name des SAM-Kontos in der Gesamtstruktur nicht unbedingt eindeutig ist.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

