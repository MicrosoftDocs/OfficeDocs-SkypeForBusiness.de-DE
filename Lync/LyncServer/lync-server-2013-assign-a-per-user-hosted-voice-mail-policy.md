---
title: 'Lync Server 2013: Zuweisen einer Hosted Voice Mail-Richtlinie pro Benutzer'
description: 'Lync Server 2013: weisen Sie eine gehostete Voicemail-Richtlinie pro Benutzer zu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559891"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="232ea-103">Zuweisen einer Richtlinie für gehostete Voicemail pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="232ea-103">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="232ea-p101">Die Bereitstellung einer oder mehrerer Benutzerrichtlinien für gehostete Voicemail ist optional. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie diese Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="232ea-p101">Deploying one or more per-user hosted voice mail policies is optional. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="232ea-106">Ausführliche Informationen zum Zuweisen oder Entfernen der Zuweisung von Richtlinien für gehostete Voicemails pro Benutzer finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="232ea-106">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="232ea-107">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="232ea-107">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="232ea-108">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="232ea-108">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="232ea-109">So weisen Sie eine Benutzerrichtlinie für gehostete Voicemail zu</span><span class="sxs-lookup"><span data-stu-id="232ea-109">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="232ea-110">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="232ea-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="232ea-p102">Führen Sie das Cmdlet "Grant-CsHostedVoicemailPolicy" aus, um die Benutzerrichtlinie für gehostete Voicemail einzelnen Benutzern, Gruppen oder Kontaktobjekten zuzuweisen. Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="232ea-p102">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects. For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="232ea-113">In diesem Beispiel wird die Richtlinie für gehostete Voicemail "ExRedmond" dem Benutzer Ken Myer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="232ea-113">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="232ea-p103">**Identity** gibt die Identität des zu ändernden Benutzerkontos an. Der Wert "Identity" kann unter Verwendung eines der folgenden Formate angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="232ea-p103">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="232ea-116">SIP-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="232ea-116">The user's SIP address</span></span>
    
      - <span data-ttu-id="232ea-117">Active Directory-Benutzerprinzipalname des Benutzers</span><span class="sxs-lookup"><span data-stu-id="232ea-117">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="232ea-118">Der Domänen \\ Anmeldename des Benutzers (beispielsweise "Contoso \\ kenmyer")</span><span class="sxs-lookup"><span data-stu-id="232ea-118">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="232ea-119">AD DS-Anzeigename des Benutzers (zum Beispiel "Ken Myer").</span><span class="sxs-lookup"><span data-stu-id="232ea-119">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="232ea-120">Wenn Sie die Display-Name als Identitätswert verwenden, können Sie das \* Platzhalterzeichen Sternchen () verwenden.</span><span class="sxs-lookup"><span data-stu-id="232ea-120">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="232ea-121">Die Identität " \* Smith" gibt beispielsweise alle Benutzer zurück, die eine Display-Name haben, die mit dem Zeichenfolgenwert "Smith" endet.</span><span class="sxs-lookup"><span data-stu-id="232ea-121">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="232ea-122">Der Active Directory-SAM-Kontoname eines Benutzers kann nicht als Identitätswert verwendet werden, da dieser Name innerhalb der Gesamtstruktur nicht unbedingt eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="232ea-122">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


