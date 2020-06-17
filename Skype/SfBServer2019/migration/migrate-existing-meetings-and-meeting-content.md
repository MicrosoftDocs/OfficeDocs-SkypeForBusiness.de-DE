---
title: Migrieren vorhandener Besprechungen und Besprechungsinhalte
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Wenn ein Benutzerkonto von auf einen Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:'
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752687"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="5c63f-103">Migrieren vorhandener Besprechungen und Besprechungsinhalte</span><span class="sxs-lookup"><span data-stu-id="5c63f-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="5c63f-104">Wenn ein Benutzerkonto auf einen Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:</span><span class="sxs-lookup"><span data-stu-id="5c63f-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="5c63f-105">**Besprechungen, die bereits vom Benutzer geplant wurden**.</span><span class="sxs-lookup"><span data-stu-id="5c63f-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="5c63f-106">Dies umfasst das Verschieben von Konferenz Verzeichnissen und Konferenzdaten.</span><span class="sxs-lookup"><span data-stu-id="5c63f-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="5c63f-107">**Die persönliche Identifikationsnummer (PIN) des Benutzers**.</span><span class="sxs-lookup"><span data-stu-id="5c63f-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="5c63f-108">Die aktuelle PIN des Benutzers bleibt so lange funktionsfähig, bis er abläuft oder der Benutzer eine neue PIN anfordert.</span><span class="sxs-lookup"><span data-stu-id="5c63f-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="5c63f-109">Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben:</span><span class="sxs-lookup"><span data-stu-id="5c63f-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="5c63f-110">**Besprechungsinhalt**.</span><span class="sxs-lookup"><span data-stu-id="5c63f-110">**Meeting content**.</span></span> <span data-ttu-id="5c63f-111">Verwenden Sie den **-MoveConferenceData-** Parameter als Teil des Cmdlets " **CsUser** ", um die während einer Besprechung freigegebenen Inhalte wie PowerPoint, Whiteboard, Anlagen oder abrufdaten zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="5c63f-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

