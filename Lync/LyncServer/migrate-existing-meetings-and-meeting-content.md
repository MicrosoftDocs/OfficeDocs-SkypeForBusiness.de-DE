---
title: Migrieren vorhandener Besprechungen und Besprechungsinhalte
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d811a9e66f368752107020de48e5e09dd641115
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="f0e5d-102">Migrieren vorhandener Besprechungen und Besprechungsinhalte</span><span class="sxs-lookup"><span data-stu-id="f0e5d-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0e5d-103">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f0e5d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f0e5d-104">Wenn ein Benutzerkonto von lync Server 2010 auf einen lync Server 2013 Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:</span><span class="sxs-lookup"><span data-stu-id="f0e5d-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="f0e5d-p101">**Vom Benutzer bereits geplante Besprechungen**: Dies beinhaltet das Verschieben von Konferenzverzeichnissen und Konferenzdaten.</span><span class="sxs-lookup"><span data-stu-id="f0e5d-p101">**Meetings already scheduled by the user**. This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="f0e5d-p102">**Die persönliche Identifikationsnummer (PIN) des Benutzers**: Die aktuelle PIN des Benutzers ist weiterhin solange gültig, bis sie abläuft oder der Benutzer eine neue PIN anfordert.</span><span class="sxs-lookup"><span data-stu-id="f0e5d-p102">**User’s personal identification number (PIN)**. The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="f0e5d-109">Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben:</span><span class="sxs-lookup"><span data-stu-id="f0e5d-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="f0e5d-p103">**Besprechungsinhalte**: Um den während einer Besprechung freigegebenen Inhalt zu verschieben, z. B. PowerPoint- oder Whiteboard-Inhalt, Anlagen oder Umfragedaten, verwenden Sie den **-MoveConferenceData**-Parameter als Teil des **Move-CsUser**-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f0e5d-p103">**Meeting content**. In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

