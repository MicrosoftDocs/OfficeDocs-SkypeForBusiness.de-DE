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
ms.openlocfilehash: 15a238c2517fd295d35d63a8a1d2f4c4e88a76b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="c7824-102">Erstellen von Contact-Objekten für gehostete Exchange um in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7824-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7824-103">_**Letztes Änderungsstand des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="c7824-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="c7824-104">Das folgende Verfahren erläutert die Erstellung von Kontaktobjekten der automatischen Telefonzentrale oder des Teilnehmerzugriffs für gehostetes Exchange Unified Messaging (UM).</span><span class="sxs-lookup"><span data-stu-id="c7824-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="c7824-105">Ausführliche Informationen finden Sie unter [Hosted Exchange Contact Object Management in lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7824-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="c7824-106">Ausführliche Informationen zum Konfigurieren von Kontaktobjekten finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c7824-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="c7824-107">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="c7824-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="c7824-108">Gruppe-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="c7824-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="c7824-109">Bevor lync Server 2013 Contact-Objekte für gehostete Exchange um aktiviert werden können, muss eine Richtlinie für gehostete Voicemail, die für Sie gilt, bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c7824-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="c7824-110">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted Voice Mail Policies in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c7824-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="c7824-111">So erstellen Sie Kontaktobjekte für die automatische Telefonzentrale oder den Teilnehmerzugriff für gehostete Exchange UM-Dienste</span><span class="sxs-lookup"><span data-stu-id="c7824-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="c7824-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="c7824-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c7824-p102">Führen Sie das Cmdlet "New-CsExUmContact" zum Erstellen von Kontaktobjekten aus, die für Ihre Bereitstellung erforderlich sind. Führen Sie beispielsweise folgenden Befehl aus, um ein Kontaktobjekt für die automatische Telefonzentrale und den Teilnehmerzugriff zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="c7824-p102">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment. For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="c7824-115">In diesen Beispielen werden folgende Parameter festgelegt:</span><span class="sxs-lookup"><span data-stu-id="c7824-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="c7824-116">**SipAddress** gibt die SIP-Adresse des Kontaktobjekts an.</span><span class="sxs-lookup"><span data-stu-id="c7824-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="c7824-117">Hierbei muss es sich um eine Adresse handeln, die noch nicht zur Konfiguration eines Benutzer- oder Kontaktobjekts in den Active Directory-Domänendiensten verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c7824-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="c7824-118">Dieser Wert muss das Format "SIP:\<*SIP Address*\>" aufweisen, wie in den vorherigen Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7824-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="c7824-119">**RegistrarPool** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools, in dem der Registrierungsdienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c7824-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="c7824-120">Exchange um Kontaktobjekte können nicht in Pools verschoben werden, die Teil lync Server 2013 Bereitstellungen vor lync Server 2013 sind.</span><span class="sxs-lookup"><span data-stu-id="c7824-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="c7824-121">**OU** gibt die Active Directory-Organisationseinheit an, in der dieses Kontaktobjekt abgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c7824-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="c7824-p104">**DisplayNumber** gibt die Rufnummer des Kontaktobjekts an. Die Rufnummer muss für jedes Kontaktobjekt eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="c7824-p104">**DisplayNumber** specifies the telephone number of the contact object. The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="c7824-p105">**AutoAttendant** gibt an, ob es sich bei diesem Kontaktobjekt um eine automatische Telefonzentrale handelt. Eine automatische Telefonzentrale stellt eine Reihe von Ansagen bereit, über die Anrufer innerhalb des Telefonsystems navigieren und den gewünschten Gesprächspartner erreichen können. Der Wert **False** (Standard) für diesen Parameter weist auf ein Teilnehmerzugriff-Kontaktobjekt hin.</span><span class="sxs-lookup"><span data-stu-id="c7824-p105">**AutoAttendant** specifies whether the Contact object is an Auto Attendant. Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact. A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

