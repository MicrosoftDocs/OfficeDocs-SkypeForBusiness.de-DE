---
title: 'Lync Server 2013: Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2202e1b4c03eb25d12e46c3a533313a54bc76c4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847892"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="9688f-102">Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9688f-102">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="9688f-103">Das Bereitstelleneiner oder mehrerer pro Benutzer gehosteter Voicemail-Richtlinien ist optional.</span><span class="sxs-lookup"><span data-stu-id="9688f-103">Deploying one or more per-user hosted voice mail policies is optional.</span></span> <span data-ttu-id="9688f-104">Wenn Sie Richtlinien für einzelne Benutzer bereitstellen, müssen Sie diese explizit Benutzern, Gruppen oder Kontaktobjekten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9688f-104">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="9688f-105">Details zum Zuweisen oder Entfernen der Zuweisung von Richtlinien für gehostete Voicemail pro Benutzer finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="9688f-105">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="9688f-106">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="9688f-106">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="9688f-107">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="9688f-107">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="9688f-108">So weisen Sie eine pro Benutzer gehostete Voicemail-Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="9688f-108">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="9688f-109">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="9688f-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9688f-110">Führen Sie das Cmdlet Grant-CsHostedVoicemailPolicy aus, um die Richtlinie für pro Benutzer gehostete Voicemail einzelnen Benutzern, Gruppen und Kontaktobjekten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="9688f-110">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects.</span></span> <span data-ttu-id="9688f-111">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="9688f-111">For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="9688f-112">In diesem Beispiel wurde dem Benutzer Ken Myers die Richtlinie für die gehostete Voicemail-e-Mail zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9688f-112">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="9688f-113">**Identity** gibt das zu ändernde Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="9688f-113">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="9688f-114">Der Identity-Wert kann mit einem der folgenden Formate angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="9688f-114">The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="9688f-115">Die SIP-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="9688f-115">The user's SIP address</span></span>
    
      - <span data-ttu-id="9688f-116">Name des Active Directory-Benutzerprinzipals des Benutzers</span><span class="sxs-lookup"><span data-stu-id="9688f-116">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="9688f-117">Der Domänen\\Anmeldename des Benutzers (beispielsweise contoso\\kenmyer)</span><span class="sxs-lookup"><span data-stu-id="9688f-117">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="9688f-118">Der Anzeige Name des Active Directory-Domänen Dienstes des Benutzers (beispielsweise Ken Myers).</span><span class="sxs-lookup"><span data-stu-id="9688f-118">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="9688f-119">Wenn Sie den Anzeigenamen als Identitätswert verwenden, können Sie das Platzhalterzeichen Sternchen\*() verwenden.</span><span class="sxs-lookup"><span data-stu-id="9688f-119">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="9688f-120">Die Identität "\* Smith" gibt beispielsweise alle Benutzer zurück, die einen Anzeigenamen aufweisen, der mit dem Zeichenfolgenwert "Smith" endet.</span><span class="sxs-lookup"><span data-stu-id="9688f-120">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="9688f-121">Der Name des Active Directory-SAM-Kontos des Benutzers kann nicht als Identitätswert verwendet werden, da der Name des SAM-Kontos in der Gesamtstruktur nicht unbedingt eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="9688f-121">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


