---
title: 'Lync Server 2013: Ändern der Global Hosted Voice Mail-Richtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12ddff40f3a04ed4bfb0d8205eac732ef3ad7198
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Ändern der Global Hosted Voice Mail-Richtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-24_

Die *Global* Hosted Voice Mail-Richtlinie wird mit lync Server 2013 installiert. Sie können diese Richtlinie Ihren Anforderungen entsprechend ändern, Sie können sie jedoch weder umbenennen noch löschen. Wenn Sie die globale Richtlinie ändern möchten, verwenden Sie das Cmdlet "Set-CsHostedVoicemailPolicy", um die Parameter auf die für Ihre spezielle Bereitstellung geeigneten Werte zu setzen.

Ausführliche Informationen zum Cmdlet " [CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) " finden Sie in der Dokumentation zum lync Server-Verwaltungsshell.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>So ändern Sie die globale Richtlinie für gehostete Voicemail

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Set-CsHostedVoicemailPolicy" aus, um die Parameter der globalen Richtlinie für Ihre Umgebung festzulegen. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Da dieser Befehl nicht den Identity-Parameter der Richtlinie angibt, legt Windows PowerShell Befehlszeilenschnittstelle die folgenden Werte für die Global Hosted Voicemail-Richtlinie fest:
    
      - **Destination** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Exchange UM-Diensts an. Dieser Parameter ist optional. Wenn Sie jedoch versuchen, einen Benutzer für gehostete Voicemail zu aktivieren, und die zugewiesene Richtlinie des Benutzers nicht auf "Destination" festgelegt ist, tritt bei der Aktivierung ein Fehler auf.
    
      - **Organization** gibt eine durch trennzeichengetrennte Liste der Exchange-Mandanten an, die lync Server Benutzer zu Hause sind. Für jeden Mandanten muss der vollqualifizierte Domänenname des Mandanten im gehosteten Exchange-Dienst angegeben werden.
    
    <div>
    

    > [!NOTE]  
    > Im vorherigen Cmdlet-Beispiel ersetzt der Wert "corp1.litwareinc.com" einen beliebigen Wert, der im Parameter "Organization" möglicherweise bereits vorhanden ist. Wenn die Richtlinie beispielsweise bereits eine durch Trennzeichen getrennte Liste mit Organisationen enthält, wird die gesamte Liste ersetzt. Wenn Sie nicht die gesamte Liste ersetzen, sondern der Liste eine Organisation hinzufügen möchten, führen Sie einen Befehl wie den folgenden aus.

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

