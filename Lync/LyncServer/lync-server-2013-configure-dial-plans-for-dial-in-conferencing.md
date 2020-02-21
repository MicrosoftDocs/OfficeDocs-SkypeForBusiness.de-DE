---
title: 'Lync Server 2013: Konfigurieren von Wählplänen für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a86bf3061c714089ee326a729d0dd43ef267b8e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="84c22-102">Konfigurieren von Wählplänen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84c22-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84c22-103">_**Letztes Änderungsstand des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="84c22-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="84c22-p101">Bei der Bereitstellung von Einwahlkonferenzen müssen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl erstellen oder ändern. Stellen Sie sicher, dass in jedem Satz mit Wähleinstellungen mindestens eine Normalisierungsregel die Telefondurchwahlen in vollständige Rufnummern im E.164-Format konvertiert. Benutzer von Einwahlkonferenzen nehmen an Konferenzen als authentifizierte Unternehmensbenutzer teil, indem sie ihre PIN und die Telefonnummer eingeben. Sie benötigen eine Normalisierungsregel zum Konvertieren von Durchwahlen in vollständige Rufnummern, damit Benutzer bei Eingabe einer Durchwahl authentifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="84c22-p101">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers. Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format. Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="84c22-108">Gehen Sie folgendermaßen vor, um Wähleinstellungen für Einwahlkonferenzen einzurichten:</span><span class="sxs-lookup"><span data-stu-id="84c22-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="84c22-109">Unabhängig davon, ob Sie Enterprise-VoIP bereitstellen oder nicht, ändern Sie den globalen Wählplan so, dass eine Einwahlkonferenz Region hinzugefügt wird, und stellen Sie sicher, dass die Zugriffsnummern für die Einwahl in Normalisierungsregeln korrekt konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="84c22-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="84c22-110">Ausführliche Anweisungen finden Sie unter [Modify a Dial Plan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="84c22-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="84c22-111">Wenn Sie Enterprise-VoIP nicht bereitgestellt haben, erstellen Sie Wählpläne für Ihre Zugriffsnummern für Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="84c22-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="84c22-112">Stellen Sie sicher, dass Sie eine Region für Einwahlkonferenzen angeben.</span><span class="sxs-lookup"><span data-stu-id="84c22-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="84c22-113">Ausführliche Anweisungen finden Sie unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="84c22-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="84c22-114">Wenn Sie Enterprise-VoIP bereitgestellt haben, ändern Sie Enterprise-VoIP-Wählpläne nach Bedarf, um Regionen einzubeziehen und geeignete Normalisierungsregeln für Einwahlnummern zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="84c22-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="84c22-115">Ausführliche Anweisungen finden Sie unter [Modify a Dial Plan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="84c22-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="84c22-116">Sie können auch dedizierte Wähleinstellungen erstellen, die nur für Zugriffsnummern für die Einwahl eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="84c22-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="84c22-117">Ausführliche Anweisungen finden Sie unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="84c22-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="84c22-118">Ausführliche Informationen zu Planungsregionen finden Sie unter [Einwahlkonferenz Anforderungen in lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="84c22-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="84c22-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="84c22-119">In This Section</span></span>

  - [<span data-ttu-id="84c22-120">Anzeigen von Informationen zu Wählplänen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84c22-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="84c22-121">Erstellen von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84c22-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="84c22-122">Ändern von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84c22-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="84c22-123">Definieren von Normalisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84c22-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

