---
title: 'Lync Server 2013: Kontaktobjektverwaltung für gehostete Exchange-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c67438745ee7cbb9de0ccfdef1d5d8959bb4679c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="b55c0-102">Kontaktobjektverwaltung für gehostete Exchange-Dienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55c0-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b55c0-103">_**Letztes Änderungsdatum des Themas:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="b55c0-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="b55c0-104">Sie müssen ein Kontaktobjekt für jede Nummer der automatischen Telefonzentrale und die Teilnehmerzugriffsnummer in Ihrer standortübergreifenden Bereitstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b55c0-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="b55c0-105">Für die Integration in den Hosted Exchange um kann OCSUMUtil. exe nicht zum Verwalten von Kontaktobjekten verwendet werden, da dies von den Exchange um-Einstellungen von Active Directory abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="b55c0-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="b55c0-106">In einer standortübergreifenden Bereitstellung werden lync Server 2013 und gehostete Exchange um in getrennten Gesamtstrukturen installiert, ohne dass Sie vertrauenswürdig sind.</span><span class="sxs-lookup"><span data-stu-id="b55c0-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="b55c0-107">Aus Sicherheitsgründen haben lync Server 2013-Administratoren keinen direkten Zugriff auf Exchange um-Active Directory-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b55c0-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="b55c0-108">Daher bietet lync Server 2013 ein anderes Modell für die Verwaltung von Kontaktobjekten in einem *freigegebenen SIP-Adressraum* , auf den sowohl lync Server 2013 als auch der gehostete Exchange um-Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="b55c0-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="b55c0-109">Workflow für gehostete Kontaktobjekte</span><span class="sxs-lookup"><span data-stu-id="b55c0-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="b55c0-110">Im folgenden finden Sie die allgemeinen Schritte für die Zusammenarbeit mit Ihrem Hosted Exchange-mandantenadministrator zum Verwalten von Kontaktobjekten:</span><span class="sxs-lookup"><span data-stu-id="b55c0-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="b55c0-111">Der Exchange-Administrator fordert Telefonnummern für den Exchange um-Abonnenten Zugriff und die automatischen Telefonzentralen-Kontaktobjekte an.</span><span class="sxs-lookup"><span data-stu-id="b55c0-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="b55c0-112">Der lync Server 2013-Administrator erstellt für jede Telefonnummer ein Kontaktobjekt und weist jedem Kontaktobjekt eine Richtlinie für gehostete Voicemail zu.</span><span class="sxs-lookup"><span data-stu-id="b55c0-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="b55c0-113">Der lync Server 2013-Administrator stellt die Telefonnummern dem Exchange-Administrator zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b55c0-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="b55c0-114">Der Exchange-Administrator ordnet die Telefonnummern den entsprechenden Exchange um-Wählplänen für automatische Telefonzentralen und den Abonnenten Zugriff zu.</span><span class="sxs-lookup"><span data-stu-id="b55c0-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b55c0-115">Es ist nicht erforderlich, die Einstellungen für den Wählplan von lync Server 2013 für die Kontaktobjekte so zu konfigurieren, wie dies bei lokalen Bereitstellungen der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="b55c0-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="b55c0-116">Konfigurieren von gehosteten Kontaktobjekten</span><span class="sxs-lookup"><span data-stu-id="b55c0-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b55c0-117">Bevor lync Server 2013-Kontaktobjekte für gehostete Exchange um aktiviert werden können, muss eine für Sie geltende gehostete Voicemail-Richtlinie bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b55c0-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="b55c0-118">Die Richtlinie kann globaler, Website ebener oder benutzerbezogener Bereich sein, sofern Sie auf das zu aktivierende Kontaktobjekt angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b55c0-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="b55c0-119">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b55c0-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b55c0-120">Zum Konfigurieren der in einer lokalen Bereitstellung gehosteten Kontaktobjekte für die automatische Telefonzentrale und den Abonnenten Zugriff müssen Sie die folgenden Cmdlets verwenden:</span><span class="sxs-lookup"><span data-stu-id="b55c0-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="b55c0-121">**New-CsExUmContact** erstellt ein neues Kontaktobjekt für gehostete um.</span><span class="sxs-lookup"><span data-stu-id="b55c0-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="b55c0-122">Mit " **CsExUmContact** " wird ein vorhandenes Kontaktobjekt für gehostete Exchange um geändert.</span><span class="sxs-lookup"><span data-stu-id="b55c0-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="b55c0-123">Im folgenden Beispiel wird ein Kontaktobjekt der automatischen Telefonzentrale erstellt:</span><span class="sxs-lookup"><span data-stu-id="b55c0-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="b55c0-124">In diesem Beispiel wird ein neues Exchange um-Kontaktobjekt mit der SIP-Adresse SIP:exumaa1@fabrikam.com erstellt.</span><span class="sxs-lookup"><span data-stu-id="b55c0-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="b55c0-125">Der Name des Pools, in dem der lync Server 2013-Registrierungsdienst ausgeführt wird, lautet RedmondPool.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b55c0-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="b55c0-126">Die Active Directory-Organisationseinheit, in der diese Informationen gespeichert werden, ist ou = ExUmContacts, DC = "litwareinc, DC = com.</span><span class="sxs-lookup"><span data-stu-id="b55c0-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="b55c0-127">Die Telefonnummer des Kontaktobjekts ist 2065554567.</span><span class="sxs-lookup"><span data-stu-id="b55c0-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="b55c0-128">Der Parameter optional – autoattende $true gibt an, dass dieses Objekt ein Kontaktobjekt der automatischen Telefonzentrale ist.</span><span class="sxs-lookup"><span data-stu-id="b55c0-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="b55c0-129">Wenn der-autoattender-Parameter auf "false" festgelegt wird (der Standardwert), wird ein Kontaktobjekt des Teilnehmerzugriffs angegeben.</span><span class="sxs-lookup"><span data-stu-id="b55c0-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="b55c0-130">Ausführliche Informationen zu den Cmdlets New-CsExUmContact und CsExUmContact finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="b55c0-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

