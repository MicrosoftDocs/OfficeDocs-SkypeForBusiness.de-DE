---
title: Migrieren vorhandener Besprechungen und Besprechungsinhalte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38b4f374aef66fa95d49b2330a07f9def4135328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="722b1-102">Migrieren vorhandener Besprechungen und Besprechungsinhalte</span><span class="sxs-lookup"><span data-stu-id="722b1-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="722b1-103">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="722b1-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="722b1-104">Wenn ein Benutzerkonto von lync Server 2010 auf einen lync Server 2013-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:</span><span class="sxs-lookup"><span data-stu-id="722b1-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="722b1-105">**Besprechungen, die der Benutzer bereits geplant**hat.</span><span class="sxs-lookup"><span data-stu-id="722b1-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="722b1-106">Dazu gehören das Verschieben von Konferenz Verzeichnissen und Konferenzdaten.</span><span class="sxs-lookup"><span data-stu-id="722b1-106">This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="722b1-107">**Persönliche Identifikationsnummer (PIN) des Benutzers**.</span><span class="sxs-lookup"><span data-stu-id="722b1-107">**User’s personal identification number (PIN)**.</span></span> <span data-ttu-id="722b1-108">Die aktuelle PIN des Benutzers funktioniert weiterhin, bis er abläuft oder der Benutzer eine neue PIN anfordert.</span><span class="sxs-lookup"><span data-stu-id="722b1-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="722b1-109">Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben.</span><span class="sxs-lookup"><span data-stu-id="722b1-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="722b1-110">**Besprechungsinhalt**.</span><span class="sxs-lookup"><span data-stu-id="722b1-110">**Meeting content**.</span></span> <span data-ttu-id="722b1-111">Verwenden Sie den Parameter **-MoveConferenceData** als Teil des Cmdlets **Move-CsUser** , um den während einer Besprechung freigegebenen Inhalt zu verschieben, beispielsweise PowerPoint, Whiteboard, Anlagen oder Umfragedaten.</span><span class="sxs-lookup"><span data-stu-id="722b1-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

