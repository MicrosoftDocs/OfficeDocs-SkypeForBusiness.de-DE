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
ms.openlocfilehash: 544c431257dea20db729e80dd1d9acc565da8201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="997d5-102">Konfigurieren von Wählplänen für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="997d5-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="997d5-103">_**Letztes Änderungsdatum des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="997d5-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="997d5-104">Bei der Bereitstellung von Einwahlkonferenzen müssen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="997d5-104">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="997d5-105">Stellen Sie sicher, dass mindestens eine Normalisierungsregel in den einzelnen Wähleinstellungen Telefonerweiterungen in vollständige Telefonnummern im E. 164-Format umwandelt.</span><span class="sxs-lookup"><span data-stu-id="997d5-105">Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format.</span></span> <span data-ttu-id="997d5-106">Benutzer von Einwahlkonferenzen nehmen an Konferenzen als authentifizierte Unternehmensbenutzer teil, indem sie ihre PIN und die Telefonnummer eingeben.</span><span class="sxs-lookup"><span data-stu-id="997d5-106">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="997d5-107">Sie benötigen eine Normalisierungsregel zum Konvertieren von Durchwahlen in vollständige Rufnummern, damit Benutzer bei Eingabe einer Durchwahl authentifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="997d5-107">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="997d5-108">Gehen Sie wie folgt vor, um Wählpläne für Einwahlkonferenzen einzurichten:</span><span class="sxs-lookup"><span data-stu-id="997d5-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="997d5-109">Unabhängig davon, ob Sie Enterprise-VoIP bereitstellen oder nicht, fügen Sie zu den Wähleinstellungen eine Region für Einwahlkonferenzen hinzu und stellen Sie sicher, dass Ihre Einwahlnummern einwandfrei von einer Normalisierungsregel umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="997d5-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="997d5-110">Ausführliche Anweisungen finden Sie unter [Ändern von Wähleinstellungen in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="997d5-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="997d5-111">Wenn Sie Enterprise-VoIP nicht bereitstellen, erstellen Sie Wählpläne für Ihre Einwahlnummern.</span><span class="sxs-lookup"><span data-stu-id="997d5-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="997d5-112">Fügen Sie auf jeden Fall eine Region für Einwahlkonferenzen hinzu.</span><span class="sxs-lookup"><span data-stu-id="997d5-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="997d5-113">Ausführliche Anweisungen finden Sie unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="997d5-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="997d5-114">Wenn Sie Enterprise-VoIP bereitgestellt haben, ändern Sie Enterprise-sprach Wählpläne nach Bedarf, um Regionen einzubeziehen und geeignete Normalisierungsregeln für Einwahl Zugriffsnummern zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="997d5-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="997d5-115">Ausführliche Anweisungen finden Sie unter [Ändern von Wähleinstellungen in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="997d5-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="997d5-116">Sie können auch dedizierte Wählpläne erstellen, die nur für Einwahl Zugriffsnummern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="997d5-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="997d5-117">Ausführliche Anweisungen finden Sie unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="997d5-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="997d5-118">Details zu Planungsregionen finden Sie unter [Anforderungen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="997d5-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="997d5-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="997d5-119">In This Section</span></span>

  - [<span data-ttu-id="997d5-120">Anzeigen von Wähl Planinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="997d5-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="997d5-121">Erstellen eines Wählplans in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="997d5-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="997d5-122">Ändern eines Wählplans in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="997d5-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="997d5-123">Definieren von Normalisierungsregeln in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="997d5-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

