---
title: 'Lync Server 2013: Erstellen von Kontaktobjekten für gehostete Exchange UM-Dienste'
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
ms.openlocfilehash: 358b595fceb05a377c59479b0a08e100bffb318a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="f1e7a-102">Erstellen von Kontaktobjekten für gehostete Exchange UM-Dienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1e7a-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1e7a-103">_**Letztes Änderungsdatum des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="f1e7a-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="f1e7a-104">Im folgenden Verfahren wird erläutert, wie Sie die Kontaktobjekte der automatischen Telefonzentrale (AA) oder des Abonnenten Zugriffs (SA) für gehostete Exchange Unified Messaging (um) erstellen.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="f1e7a-105">Ausführliche Informationen finden Sie unter [gehostete Exchange-Kontaktobjekt Verwaltung in lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="f1e7a-106">Details zum Konfigurieren von Kontaktobjekten finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f1e7a-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="f1e7a-107">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="f1e7a-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="f1e7a-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="f1e7a-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="f1e7a-109">Bevor lync Server 2013-Kontaktobjekte für gehostete Exchange um aktiviert werden können, muss eine für Sie geltende gehostete Voicemail-Richtlinie bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="f1e7a-110">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="f1e7a-111">So erstellen Sie AA-oder SA-Kontaktobjekte für gehostete Exchange um</span><span class="sxs-lookup"><span data-stu-id="f1e7a-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="f1e7a-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f1e7a-113">Führen Sie das Cmdlet New-CsExUmContact aus, um alle für Ihre Bereitstellung erforderlichen Kontaktobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-113">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment.</span></span> <span data-ttu-id="f1e7a-114">Führen Sie beispielsweise die folgenden Schritte aus, um ein AA-und ein SA-Kontaktobjekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f1e7a-114">For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="f1e7a-115">In diesen Beispielen werden die folgenden Parameter angegeben:</span><span class="sxs-lookup"><span data-stu-id="f1e7a-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="f1e7a-116">**SipAddress** gibt die SIP-Adresse des Contact-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="f1e7a-117">Hierbei muss es sich um eine Adresse handeln, die noch nicht verwendet wurde, um einen Benutzer oder ein Kontaktobjekt in den Active Directory-Domänendiensten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="f1e7a-118">Dieser Wert muss das Format "SIP:\<*SIP Address*\>" aufweisen, wie in den vorherigen Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="f1e7a-119">**RegistrarPool** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools an, auf dem der Registrierungsdienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="f1e7a-120">Exchange um-Kontaktobjekte können nicht in Pools verschoben werden, die Bestandteil von lync Server 2013-Bereitstellungen vor lync Server 2013 sind.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="f1e7a-121">**OU** gibt die Active Directory-Organisationseinheit an, in der sich dieses Kontaktobjekt befindet.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="f1e7a-122">**DisplayNumber** gibt die Telefonnummer des Kontaktobjekts an.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-122">**DisplayNumber** specifies the telephone number of the contact object.</span></span> <span data-ttu-id="f1e7a-123">Die Telefonnummer für jedes Kontaktobjekt muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-123">The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="f1e7a-124">**Autoattender** gibt an, ob es sich bei dem Kontaktobjekt um eine automatische Telefonzentrale handelt.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-124">**AutoAttendant** specifies whether the Contact object is an Auto Attendant.</span></span> <span data-ttu-id="f1e7a-125">Die automatische Telefonzentrale bietet eine Reihe von Sprachansagen, mit denen Anrufer in das Telefonsystem navigieren und die Partei erreichen können, mit der Sie Kontakt aufnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-125">Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact.</span></span> <span data-ttu-id="f1e7a-126">Der Wert **false** (Standardeinstellung) für diesen Parameter gibt ein Kontaktobjekt für den Abonnenten Zugriff an.</span><span class="sxs-lookup"><span data-stu-id="f1e7a-126">A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

