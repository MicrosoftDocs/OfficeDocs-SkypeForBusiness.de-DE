---
title: Empfohlen Erstellen von Konferenz Verzeichnissen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f4a0dbd2caf7e9a04354e0b0670dcbb47adb1b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="db39b-102">Empfohlen Erstellen von Konferenz Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="db39b-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db39b-103">_**Letztes Änderungsstand des Themas:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="db39b-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="db39b-104">Konferenzverzeichnisse verwalten eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer für die Teilnahme an einer Konferenz bei Verwendung von lync 2013 verwendet, und der numerischen Konferenz-ID, die ein Teilnehmer für Einwahlkonferenzen verwendet, um an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="db39b-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="db39b-105">Das Format der Konferenz-ID lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="db39b-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="db39b-106">Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="db39b-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="db39b-107">Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="db39b-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="db39b-108">Wenn diese Richtlinie eingehalten wird, bleiben die Konferenz-IDs in der Regel kurz.</span><span class="sxs-lookup"><span data-stu-id="db39b-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="db39b-109">Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) 9 überschreitet, wird die Länge der Konferenz-ID jedoch erweitert, um zusätzliche Konferenzen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="db39b-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="db39b-110">Erstellen eines Konferenz Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="db39b-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="db39b-111">Geben Sie in lync Server-Verwaltungsshell das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="db39b-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="db39b-112">Im folgenden Beispiel wird ein Konferenzverzeichnis mit der Identität 42 erstellt, die im Pool ATL-CS-001.litwareinc.com gehostet wird:</span><span class="sxs-lookup"><span data-stu-id="db39b-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db39b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db39b-113">See Also</span></span>


[<span data-ttu-id="db39b-114">Anforderungen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db39b-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="db39b-115">New-CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="db39b-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

