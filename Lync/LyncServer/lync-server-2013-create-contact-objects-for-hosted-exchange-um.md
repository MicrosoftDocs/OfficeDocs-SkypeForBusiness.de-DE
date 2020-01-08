---
title: 'Lync Server 2013: Erstellen von Kontaktobjekten für gehostete Exchange UM-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53d5bdfe3b341f534a3e8066fe85be5e93b0a7f7
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Erstellen von Kontaktobjekten für gehostete Exchange UM-Dienste in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Im folgenden Verfahren wird erläutert, wie Sie die Kontaktobjekte der automatischen Telefonzentrale (AA) oder des Abonnenten Zugriffs (SA) für gehostete Exchange Unified Messaging (um) erstellen.

Ausführliche Informationen finden Sie unter [gehostete Exchange-Kontaktobjekt Verwaltung in lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in der Planungsdokumentation.

Details zum Konfigurieren von Kontaktobjekten finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Bevor lync Server 2013-Kontaktobjekte für gehostete Exchange um aktiviert werden können, muss eine für Sie geltende gehostete Voicemail-Richtlinie bereitgestellt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in lync Server 2013</A>.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>So erstellen Sie AA-oder SA-Kontaktobjekte für gehostete Exchange um

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet New-CsExUmContact aus, um alle für Ihre Bereitstellung erforderlichen Kontaktobjekte zu erstellen. Führen Sie beispielsweise die folgenden Schritte aus, um ein AA-und ein SA-Kontaktobjekt zu erstellen:
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    In diesen Beispielen werden die folgenden Parameter angegeben:
    
      - **SipAddress** gibt die SIP-Adresse des Contact-Objekts an. Hierbei muss es sich um eine Adresse handeln, die noch nicht verwendet wurde, um einen Benutzer oder ein Kontaktobjekt in den Active Directory-Domänendiensten zu konfigurieren. Dieser Wert muss das Format "SIP:\<*SIP Address*\>" aufweisen, wie in den vorherigen Beispielen gezeigt.
    
      - **RegistrarPool** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools an, auf dem der Registrierungsdienst ausgeführt wird.
        
        <div class=" ">
        

        > [!NOTE]  
        > Exchange um-Kontaktobjekte können nicht in Pools verschoben werden, die Bestandteil von lync Server 2013-Bereitstellungen vor lync Server 2013 sind.

        
        </div>
    
      - **OU** gibt die Active Directory-Organisationseinheit an, in der sich dieses Kontaktobjekt befindet.
    
      - **DisplayNumber** gibt die Telefonnummer des Kontaktobjekts an. Die Telefonnummer für jedes Kontaktobjekt muss eindeutig sein.
    
      - **Autoattender** gibt an, ob es sich bei dem Kontaktobjekt um eine automatische Telefonzentrale handelt. Die automatische Telefonzentrale bietet eine Reihe von Sprachansagen, mit denen Anrufer in das Telefonsystem navigieren und die Partei erreichen können, mit der Sie Kontakt aufnehmen möchten. Der Wert **false** (Standardeinstellung) für diesen Parameter gibt ein Kontaktobjekt für den Abonnenten Zugriff an.

</div>

</div>

<span> </span>

</div>

</div>

</div>

