---
title: 'Lync Server 2013: Routing für gehostete Exchange UM-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90cc1112effd0eac0a25614ee50d7008ee1c5e37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Routing für gehostete Exchange UM-Dienste in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Die Exchange um-Routing Anwendung wird auf dem Front-End-Server ausgeführt, um Anrufe an eine lokale Microsoft Exchange Server Unified Messaging (um)-Bereitstellung oder an einen gehosteten Exchange um-Dienst weiterzuleiten.

<div>

## <a name="the-exum-routing-application"></a>Die ExUM-Routing Anwendung

Die lync Server 2013 Exchange um-Routing Anwendung verwendet Informationen aus den Einstellungen des Benutzerkontos und den Richtlinienparametern für gehostete Voicemail, um zu bestimmen, wie Anrufe für gehostete Voicemail weitergeleitet werden, wie im folgenden Diagramm dargestellt.

**Beispiel für eine gemischte Bereitstellung Exchange um-Routing**

![Lokale lync Server Exchange um-Bereitstellung] (images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")

Das Exchange um-Routing kann so konfiguriert werden, dass Anrufe an Benutzer weitergeleitet werden, die für lokalen Exchange um aktiviert sind, für Benutzer, die für gehostete Exchange um aktiviert sind, oder für eine Kombination der beiden.

Nehmen wir beispielsweise an, dass das Postfach und der Exchange um-Dienst von Roy in einer lokalen Exchange-Bereitstellung verwaltet werden.

  - Die Proxyadressinformationen des Benutzerkontos von Roy stellen die Informationen bereit, die von der ExUM-Routing Anwendung zum Weiterleiten von Anrufen an einen lokalen Exchange um-Server verwendet werden.

Alices Postfach und Exchange um-Dienst befinden sich im Rechenzentrum eines gehosteten Exchange-Dienstanbieters. Das Routing für Ihre Exchange um-Anrufe ist wie folgt konfiguriert:

  - Die Werte, die im msExchUCVoiceMailSettings-Attribut des Benutzerkontos von Alice festgesetzt sind, weisen die ExUM-Routing Anwendung an, auf Routing Details in einer gehosteten Voicemail-Richtlinie zu überprüfen.
    
    <div>
    

    > [!NOTE]  
    > Der Wert des Attributs msExchUCVoiceMailSettings kann entweder vom Exchange-Dienstanbieter oder vom lync Server 2013-Administrator eingestellt werden. In dem im vorherigen Diagramm gezeigten Beispiel wurde der Wert (CsHostedVoiceMail = 1) vom lync Server 2013-Administrator so eingerichtet, dass die gehostete Voicemail für Alice aktiviert wurde. Details zu diesem Attribut finden Sie unter <A href="lync-server-2013-hosted-exchange-user-management.md">gehostete Exchange-Benutzerverwaltung in lync Server 2013</A>.

    
    </div>

  - Die Hosted Voicemail-Richtlinie, die dem Benutzerkonto von Alice zugewiesen ist, bietet Routing Details:
    
      - Ziel ist der gehostete Exchange um-Dienstanbieter (LS). ExUm. \<hostedExchangeServer\>. com in diesem Beispiel).
    
      - Organisationen werden durch die Mandanten-IDs identifiziert, bei denen es sich um die Routing-FQDNs für SIP-Nachrichten für Exchange Server-Mandanten handelt, die sich auf LS befinden. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com und Corp.litwareinc.com in diesem Beispiel).
        
        <div>
        

        > [!NOTE]  
        > Der FQDN für Exchange Online lautet exap.um.Outlook.com.

        
        </div>
        
        Ausführliche Informationen finden Sie unter [Richtlinien für gehostete Voicemail in lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).

<div>


> [!NOTE]  
> Wenn in einem Benutzerkonto sowohl das msExchUCVoiceMailSettings-Attribut als auch die um-Proxy Adresseinstellungen vorhanden sind, hat das msExchUCVoiceMailSettings-Attribut Vorrang.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

