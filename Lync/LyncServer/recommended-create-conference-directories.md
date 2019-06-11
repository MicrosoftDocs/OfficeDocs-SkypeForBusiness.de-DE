---
title: Erstellen von Konferenzverzeichnissen (empfohlen)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e912beac1eeffe3214f8a8d638926d84f547a270
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="29e9c-102">Erstellen von Konferenzverzeichnissen (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="29e9c-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29e9c-103">_**Letztes Änderungsdatum des Themas:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="29e9c-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="29e9c-104">Konferenzverzeichnisse verwalten eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer für die Teilnahme an einer Konferenz bei Verwendung von lync 2013 verwendet, und der numerischen Konferenz-ID, die ein Teilnehmer für Einwahlkonferenzen verwendet, um an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="29e9c-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="29e9c-105">Das Format der Konferenz-ID lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="29e9c-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="29e9c-106">Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="29e9c-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="29e9c-107">Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="29e9c-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="29e9c-108">Mit dieser Richtlinie können die Konferenz-IDs in der Regel klein gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="29e9c-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="29e9c-109">Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) 9 übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="29e9c-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="29e9c-110">Erstellen eines Konferenz Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="29e9c-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="29e9c-111">Geben Sie in der lync Server-Verwaltungsshell das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="29e9c-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="29e9c-112">Im folgenden Beispiel wird ein Konferenzverzeichnis mit der Identität 42, die auf dem Pool ATL-CS-001.litwareinc.com gehostet wird, erstellt:</span><span class="sxs-lookup"><span data-stu-id="29e9c-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29e9c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29e9c-113">See Also</span></span>


[<span data-ttu-id="29e9c-114">Anforderungen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29e9c-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="29e9c-115">New-CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="29e9c-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

