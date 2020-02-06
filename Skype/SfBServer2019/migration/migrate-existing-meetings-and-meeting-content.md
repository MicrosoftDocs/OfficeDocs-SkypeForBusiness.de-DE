---
title: Migrieren vorhandener Besprechungen und Besprechungsinhalte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Wenn ein Benutzerkonto von einem Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:'
ms.openlocfilehash: 6394ebf798560ce5a13fe7ba931076364257decc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813473"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="4ad7b-103">Migrieren vorhandener Besprechungen und Besprechungsinhalte</span><span class="sxs-lookup"><span data-stu-id="4ad7b-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="4ad7b-104">Wenn ein Benutzerkonto auf einen Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:</span><span class="sxs-lookup"><span data-stu-id="4ad7b-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="4ad7b-105">**Besprechungen, die der Benutzer bereits geplant**hat.</span><span class="sxs-lookup"><span data-stu-id="4ad7b-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="4ad7b-106">Dazu gehören das Verschieben von Konferenz Verzeichnissen und Konferenzdaten.</span><span class="sxs-lookup"><span data-stu-id="4ad7b-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="4ad7b-107">**Persönliche Identifikationsnummer (PIN) des Benutzers**.</span><span class="sxs-lookup"><span data-stu-id="4ad7b-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="4ad7b-108">Die aktuelle PIN des Benutzers funktioniert weiterhin, bis er abläuft oder der Benutzer eine neue PIN anfordert.</span><span class="sxs-lookup"><span data-stu-id="4ad7b-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="4ad7b-109">Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben.</span><span class="sxs-lookup"><span data-stu-id="4ad7b-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="4ad7b-110">**Besprechungsinhalt**.</span><span class="sxs-lookup"><span data-stu-id="4ad7b-110">**Meeting content**.</span></span> <span data-ttu-id="4ad7b-111">Verwenden Sie den Parameter **-MoveConferenceData** als Teil des Cmdlets **Move-CsUser** , um den während einer Besprechung freigegebenen Inhalt wie PowerPoint, Whiteboard, Anlagen oder Umfragedaten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="4ad7b-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

