---
title: Migrieren vorhandener Besprechungen und Besprechungsinhalte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Wenn ein Benutzerkonto von einem Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:'
ms.openlocfilehash: c8f87b46054a93af87c938d3da7a2a86be9cb0bf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237998"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="57336-103">Migrieren vorhandener Besprechungen und Besprechungsinhalte</span><span class="sxs-lookup"><span data-stu-id="57336-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="57336-104">Wenn ein Benutzerkonto auf einen Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:</span><span class="sxs-lookup"><span data-stu-id="57336-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="57336-105">**Besprechungen, die der Benutzer bereits geplant**hat.</span><span class="sxs-lookup"><span data-stu-id="57336-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="57336-106">Dazu gehören das Verschieben von Konferenz Verzeichnissen und Konferenzdaten.</span><span class="sxs-lookup"><span data-stu-id="57336-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="57336-107">**Persönliche Identifikationsnummer (PIN) des Benutzers**.</span><span class="sxs-lookup"><span data-stu-id="57336-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="57336-108">Die aktuelle PIN des Benutzers funktioniert weiterhin, bis er abläuft oder der Benutzer eine neue PIN anfordert.</span><span class="sxs-lookup"><span data-stu-id="57336-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="57336-109">Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben.</span><span class="sxs-lookup"><span data-stu-id="57336-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="57336-110">**Besprechungsinhalt**.</span><span class="sxs-lookup"><span data-stu-id="57336-110">**Meeting content**.</span></span> <span data-ttu-id="57336-111">Verwenden Sie den Parameter **-MoveConferenceData** als Teil des Cmdlets **Move-CsUser** , um den während einer Besprechung freigegebenen Inhalt wie PowerPoint, Whiteboard, Anlagen oder Umfragedaten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="57336-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

