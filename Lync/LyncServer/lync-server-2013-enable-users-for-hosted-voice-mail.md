---
title: 'Lync Server 2013: Aktivieren von Benutzern für gehostete Voicemail'
description: 'Lync Server 2013: Aktivieren von Benutzern für gehostete Voicemails.'
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
ms.openlocfilehash: 3853a70d433c09029a02f2ca6256b5988defdcb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572741"
---
# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="c4823-103">Aktivieren von Benutzern für gehostete Voicemail in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4823-103">Enable users for hosted voice mail in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4823-104">_**Letztes Änderungsstand des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="c4823-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="c4823-105">Führen Sie das Verfahren aus, um lync Server 2013 Benutzer für Voicemail in einem gehosteten Exchange Unified Messaging (um)-Dienst zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c4823-105">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="c4823-106">Ausführliche Informationen finden Sie unter [Hosted Exchange User Management in lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c4823-106">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="c4823-107">Ausführliche Informationen zum Cmdlet " [CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) " finden Sie in der Dokumentation zum lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="c4823-107">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c4823-108">Bevor ein lync Server 2013-Benutzer für gehostete Voicemail aktiviert werden kann, muss eine Richtlinie für gehostete Voicemail, die für Ihr Benutzerkonto gilt, bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c4823-108">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="c4823-109">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted Voice Mail Policies in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c4823-109">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="c4823-110">So aktivieren Sie Benutzer für gehostete Voicemail</span><span class="sxs-lookup"><span data-stu-id="c4823-110">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="c4823-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="c4823-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c4823-112">Führen Sie das Set-CsUser-Cmdlet aus, um das Benutzerkonto für gehostete Voicemail zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c4823-112">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="c4823-113">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c4823-113">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="c4823-114">Im oben stehenden Beispiel werden folgende Parameter festgelegt:</span><span class="sxs-lookup"><span data-stu-id="c4823-114">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="c4823-115">**HostedVoiceMail** ermöglicht das Weiterleiten von Voicemail-anrufen eines Benutzers an gehostete Exchange um.</span><span class="sxs-lookup"><span data-stu-id="c4823-115">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="c4823-116">Außerdem wird Microsoft lync 2013 signalisiert, dass das Symbol "Voicemail anrufen" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c4823-116">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="c4823-p104">**Identity** gibt die Identität des zu ändernden Benutzerkontos an. Der Wert "Identity" kann unter Verwendung eines der folgenden Formate angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="c4823-p104">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="c4823-119">SIP-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="c4823-119">The user's SIP address</span></span>
        
          - <span data-ttu-id="c4823-120">Active Directory-Benutzerprinzipalname des Benutzers</span><span class="sxs-lookup"><span data-stu-id="c4823-120">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="c4823-121">Der Domänen \\ Anmeldename des Benutzers (beispielsweise "Contoso \\ kenmyer")</span><span class="sxs-lookup"><span data-stu-id="c4823-121">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="c4823-122">AD DS-Anzeigename des Benutzers (zum Beispiel "Ken Myer").</span><span class="sxs-lookup"><span data-stu-id="c4823-122">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="c4823-123">Wenn Sie die Display-Name als Identitätswert verwenden, können Sie das \* Platzhalterzeichen Sternchen () verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4823-123">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="c4823-124">Die Identität " \* Smith" gibt beispielsweise alle Benutzer zurück, die eine Display-Name haben, die mit dem Zeichenfolgenwert "Smith" endet.</span><span class="sxs-lookup"><span data-stu-id="c4823-124">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c4823-125">Der Active Directory-SAM-Kontoname eines Benutzers kann nicht als Identitätswert verwendet werden, da dieser Name innerhalb der Gesamtstruktur nicht unbedingt eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="c4823-125">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

