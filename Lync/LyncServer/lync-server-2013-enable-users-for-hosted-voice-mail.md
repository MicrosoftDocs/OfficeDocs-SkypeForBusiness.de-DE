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

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="e5427-102">Aktivieren von Benutzern für gehostete Voicemail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5427-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5427-103">_**Letztes Änderungsdatum des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="e5427-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="e5427-104">Führen Sie das Verfahren zum Aktivieren von lync Server 2013-Benutzern für Voicemail in einem gehosteten Exchange Unified Messaging (um)-Dienst aus.</span><span class="sxs-lookup"><span data-stu-id="e5427-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="e5427-105">Ausführliche Informationen finden Sie unter [gehostete Exchange-Benutzerverwaltung in lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e5427-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="e5427-106">Details zum Cmdlet " [setCsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) " finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e5427-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e5427-107">Bevor ein lync Server 2013-Benutzer für gehostete Voicemail aktiviert werden kann, muss eine gehostete Voicemail-Richtlinie bereitgestellt werden, die für Ihr Benutzerkonto gilt.</span><span class="sxs-lookup"><span data-stu-id="e5427-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="e5427-108">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e5427-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="e5427-109">So aktivieren Sie Benutzer für gehostete Voicemails</span><span class="sxs-lookup"><span data-stu-id="e5427-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="e5427-110">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="e5427-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e5427-111">Führen Sie das Cmdlet "Satz-CsUser" aus, um das Benutzerkonto für gehostete Voicemail zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e5427-111">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="e5427-112">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e5427-112">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="e5427-113">Im oben stehenden Beispiel werden folgende Parameter festgelegt:</span><span class="sxs-lookup"><span data-stu-id="e5427-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="e5427-114">**HostedVoiceMail** ermöglicht es, dass die Voicemail-Anrufe eines Benutzers an den Hosted Exchange um weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e5427-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="e5427-115">Außerdem signalisiert Microsoft lync 2013, dass die Anzeige "Voicemail anrufen" leuchtet.</span><span class="sxs-lookup"><span data-stu-id="e5427-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="e5427-116">**Identity** gibt das zu ändernde Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="e5427-116">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="e5427-117">Der Identity-Wert kann mit einem der folgenden Formate angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="e5427-117">The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="e5427-118">Die SIP-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="e5427-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="e5427-119">Name des Active Directory-Benutzerprinzipals des Benutzers</span><span class="sxs-lookup"><span data-stu-id="e5427-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="e5427-120">Der Domänen\\Anmeldename des Benutzers (beispielsweise contoso\\kenmyer)</span><span class="sxs-lookup"><span data-stu-id="e5427-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="e5427-121">Der Anzeige Name des Active Directory-Domänen Dienstes des Benutzers (beispielsweise Ken Myers).</span><span class="sxs-lookup"><span data-stu-id="e5427-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="e5427-122">Wenn Sie den Anzeigenamen als Identitätswert verwenden, können Sie das Platzhalterzeichen Sternchen\*() verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5427-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="e5427-123">Die Identität "\* Smith" gibt beispielsweise alle Benutzer zurück, die einen Anzeigenamen aufweisen, der mit dem Zeichenfolgenwert "Smith" endet.</span><span class="sxs-lookup"><span data-stu-id="e5427-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e5427-124">Der Name des Active Directory-SAM-Kontos des Benutzers kann nicht als Identitätswert verwendet werden, da der Name des SAM-Kontos in der Gesamtstruktur nicht unbedingt eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="e5427-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

