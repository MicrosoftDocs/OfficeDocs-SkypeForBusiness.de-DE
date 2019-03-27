---
title: Migrieren vorhandener Besprechungen und Besprechungsinhalte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Wenn ein Benutzerkonto aus an einen Skype für Business Server 2019 Server verschoben wird, werden die folgende Informationen zusammen mit dem Benutzerkonto verschoben:'
ms.openlocfilehash: bf10fa6b4ad4d555ce80dee5ec4e4a6584020ac7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874661"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="41600-103">Migrieren vorhandener Besprechungen und Besprechungsinhalte</span><span class="sxs-lookup"><span data-stu-id="41600-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="41600-104">Wenn ein Benutzerkonto in ein Skype für Business Server 2019 Server verschoben wird, werden die folgende Informationen zusammen mit dem Benutzerkonto verschoben:</span><span class="sxs-lookup"><span data-stu-id="41600-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="41600-105">**Vom Benutzer bereits geplante Besprechungen**.</span><span class="sxs-lookup"><span data-stu-id="41600-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="41600-106">Dazu gehören die konferenzverzeichnisse und Konferenzdaten verschieben.</span><span class="sxs-lookup"><span data-stu-id="41600-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="41600-107">**Persönliche Identifikationsnummer (PIN) des Benutzers**.</span><span class="sxs-lookup"><span data-stu-id="41600-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="41600-108">Aktuelle PIN des Benutzers ist weiterhin solange gültig, bis sie abläuft oder der Benutzer eine neue PIN anfordert.</span><span class="sxs-lookup"><span data-stu-id="41600-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="41600-109">Die folgenden Benutzerkontoinformationen werden nicht auf dem neuen Server verschoben.</span><span class="sxs-lookup"><span data-stu-id="41600-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="41600-110">**Der Inhalt der Besprechung**.</span><span class="sxs-lookup"><span data-stu-id="41600-110">**Meeting content**.</span></span> <span data-ttu-id="41600-111">Zum Verschieben des Inhalts während einer Besprechung freigegeben wie PowerPoint, Whiteboard, Anlagen oder Umfrage-Daten den **MoveConferenceData -** Parameter als Teil der **Move-CsUser** -Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="41600-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

