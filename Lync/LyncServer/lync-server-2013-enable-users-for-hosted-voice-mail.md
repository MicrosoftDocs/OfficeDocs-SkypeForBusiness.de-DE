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
ms.openlocfilehash: 836edd026e6b80404b9a85a3d5a0f53fa2ba574a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="7c35c-102">Aktivieren von Benutzern für gehostete Voicemail in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c35c-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c35c-103">_**Letztes Änderungsstand des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="7c35c-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="7c35c-104">Führen Sie das Verfahren aus, um lync Server 2013 Benutzer für Voicemail in einem gehosteten Exchange Unified Messaging (um)-Dienst zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7c35c-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="7c35c-105">Ausführliche Informationen finden Sie unter [Hosted Exchange User Management in lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7c35c-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="7c35c-106">Ausführliche Informationen zum Cmdlet " [CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) " finden Sie in der Dokumentation zum lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="7c35c-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7c35c-107">Bevor ein lync Server 2013-Benutzer für gehostete Voicemail aktiviert werden kann, muss eine Richtlinie für gehostete Voicemail, die für Ihr Benutzerkonto gilt, bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7c35c-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="7c35c-108">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted Voice Mail Policies in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7c35c-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="7c35c-109">So aktivieren Sie Benutzer für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="7c35c-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="7c35c-110">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7c35c-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7c35c-111">Führen Sie das Cmdlet "CsUser" aus, um das Benutzerkonto für gehostete Voicemail zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7c35c-111">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="7c35c-112">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7c35c-112">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="7c35c-113">Im oben stehenden Beispiel werden folgende Parameter festgelegt:</span><span class="sxs-lookup"><span data-stu-id="7c35c-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="7c35c-114">**HostedVoiceMail** ermöglicht das Weiterleiten von Voicemail-anrufen eines Benutzers an gehostete Exchange um.</span><span class="sxs-lookup"><span data-stu-id="7c35c-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="7c35c-115">Außerdem wird Microsoft lync 2013 signalisiert, dass das Symbol "Voicemail anrufen" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7c35c-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="7c35c-p104">**Identity** gibt die Identität des zu ändernden Benutzerkontos an. Der Wert "Identity" kann unter Verwendung eines der folgenden Formate angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="7c35c-p104">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="7c35c-118">SIP-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="7c35c-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="7c35c-119">Active Directory-Benutzerprinzipalname des Benutzers</span><span class="sxs-lookup"><span data-stu-id="7c35c-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="7c35c-120">Der Domänen\\Anmeldename des Benutzers (beispielsweise "Contoso\\kenmyer")</span><span class="sxs-lookup"><span data-stu-id="7c35c-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="7c35c-121">AD DS-Anzeigename des Benutzers (zum Beispiel "Ken Myer").</span><span class="sxs-lookup"><span data-stu-id="7c35c-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="7c35c-122">Wenn Sie den Anzeigenamen als Identitätswert verwenden, können Sie das Platzhalterzeichen Sternchen\*() verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c35c-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="7c35c-123">Die Identität "\* Smith" gibt beispielsweise alle Benutzer zurück, die einen Anzeigenamen haben, der mit dem Zeichenfolgenwert "Smith" endet.</span><span class="sxs-lookup"><span data-stu-id="7c35c-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7c35c-124">Der Active Directory-SAM-Kontoname eines Benutzers kann nicht als Identitätswert verwendet werden, da dieser Name innerhalb der Gesamtstruktur nicht unbedingt eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="7c35c-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

