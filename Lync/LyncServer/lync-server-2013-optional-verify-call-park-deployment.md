---
title: 'Lync Server 2013: (optional) Überprüfen der Bereitstellung des Anruf Parks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cfc0d62bcfabe1a5bcddfb069d95b18aa0d30d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="e0a15-102">Optional Überprüfen der Bereitstellung des Anruf Parks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0a15-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0a15-103">_**Letztes Änderungsdatum des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="e0a15-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="e0a15-104">Nachdem Sie den Parken von Anrufen installiert und konfiguriert haben, müssen Sie die Konfiguration überprüfen, um sicherzustellen, dass das Parken und Abrufen von anrufen wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e0a15-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="e0a15-105">Überprüfen Sie mindestens Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e0a15-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="e0a15-106">Rufen Sie einen Benutzer an, der den Anruf Park aktiviert hat, und lassen Sie den Anruf vom Nutzer Parken.</span><span class="sxs-lookup"><span data-stu-id="e0a15-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e0a15-107">Wenn Sie den Anruf Park in der VoIP-Richtlinie unmittelbar vor der Durchführung dieses Tests aktiviert haben, muss sich der Benutzer, der den Anruf parkt, von lync Server abmelden und dann wieder anmelden, um die Option "Parken" in der Anrufliste für Anrufe sehen zu können.</span><span class="sxs-lookup"><span data-stu-id="e0a15-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="e0a15-108">Wählen Sie die Orbitnummer aus, um den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="e0a15-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="e0a15-p102">Parken Sie einen weiteren Anruf, lassen Sie die Zeitspanne für die Zeitüberschreitung verstreichen und nehmen Sie den Rückruf nicht entgegen. Überprüfen Sie, ob der Anruf, bei dem eine Zeitüberschreitung aufgetreten ist, ordnungsgemäß an das für **OnTimeoutURI** angegebene Fallbackziel weitergeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="e0a15-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

