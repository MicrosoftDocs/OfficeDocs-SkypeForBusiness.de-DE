---
title: 'Lync Server 2013: Erstellen von Contact-Objekten für gehostete Exchange um'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 051b7f483ec3e3a59d5025c670b63b97765016b5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532302"
---
# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Erstellen von Contact-Objekten für gehostete Exchange um in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-24_

Das folgende Verfahren erläutert die Erstellung von Kontaktobjekten der automatischen Telefonzentrale oder des Teilnehmerzugriffs für gehostetes Exchange Unified Messaging (UM).

Ausführliche Informationen finden Sie unter [Hosted Exchange Contact Object Management in lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in der Planungsdokumentation.

Ausführliche Informationen zum Konfigurieren von Kontaktobjekten finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Gruppe-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Bevor lync Server 2013 Contact-Objekte für gehostete Exchange um aktiviert werden können, muss eine Richtlinie für gehostete Voicemail, die für Sie gilt, bereitgestellt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted Voice Mail Policies in lync Server 2013</A>.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>So erstellen Sie Kontaktobjekte für die automatische Telefonzentrale oder den Teilnehmerzugriff für gehostete Exchange UM-Dienste

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "New-CsExUmContact" zum Erstellen von Kontaktobjekten aus, die für Ihre Bereitstellung erforderlich sind. Führen Sie beispielsweise folgenden Befehl aus, um ein Kontaktobjekt für die automatische Telefonzentrale und den Teilnehmerzugriff zu erstellen:
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    In diesen Beispielen werden folgende Parameter festgelegt:
    
      - **SipAddress** gibt die SIP-Adresse des Kontaktobjekts an. Hierbei muss es sich um eine Adresse handeln, die noch nicht zur Konfiguration eines Benutzer- oder Kontaktobjekts in den Active Directory-Domänendiensten verwendet wurde. Dieser Wert muss das Format "SIP:" aufweisen \<*SIP address*\> , wie in den vorherigen Beispielen gezeigt.
    
      - **RegistrarPool** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools, in dem der Registrierungsdienst ausgeführt wird.
        
        <div class=" ">
        

        > [!NOTE]  
        > Exchange um Kontaktobjekte können nicht in Pools verschoben werden, die Teil lync Server 2013 Bereitstellungen vor lync Server 2013 sind.

        
        </div>
    
      - **OU** gibt die Active Directory-Organisationseinheit an, in der dieses Kontaktobjekt abgelegt wird.
    
      - **DisplayNumber** gibt die Rufnummer des Kontaktobjekts an. Die Rufnummer muss für jedes Kontaktobjekt eindeutig sein.
    
      - **AutoAttendant** gibt an, ob es sich bei diesem Kontaktobjekt um eine automatische Telefonzentrale handelt. Eine automatische Telefonzentrale stellt eine Reihe von Ansagen bereit, über die Anrufer innerhalb des Telefonsystems navigieren und den gewünschten Gesprächspartner erreichen können. Der Wert **False** (Standard) für diesen Parameter weist auf ein Teilnehmerzugriff-Kontaktobjekt hin.

</div>

</div>

<span> </span>

</div>

</div>

</div>

