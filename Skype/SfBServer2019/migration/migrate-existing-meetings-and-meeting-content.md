---
title: Migrieren Sie vorhandener Besprechungen und Besprechungsinhalten
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Wenn ein Benutzerkonto aus an einen Skype für Business Server 2019 Server verschoben wird, werden die folgende Informationen zusammen mit dem Benutzerkonto verschoben:'
ms.openlocfilehash: 03ccad0498af777c7d93765af7df2baf5da51f83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030371"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="4b47e-103">Migrieren Sie vorhandener Besprechungen und Besprechungsinhalten</span><span class="sxs-lookup"><span data-stu-id="4b47e-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="4b47e-104">Wenn ein Benutzerkonto in ein Skype für Business Server 2019 Server verschoben wird, werden die folgende Informationen zusammen mit dem Benutzerkonto verschoben:</span><span class="sxs-lookup"><span data-stu-id="4b47e-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="4b47e-105">**Vom Benutzer bereits geplante Besprechungen**.</span><span class="sxs-lookup"><span data-stu-id="4b47e-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="4b47e-106">Dazu gehören die konferenzverzeichnisse und Konferenzdaten verschieben.</span><span class="sxs-lookup"><span data-stu-id="4b47e-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="4b47e-107">**Persönliche Identifikationsnummer (PIN) des Benutzers**.</span><span class="sxs-lookup"><span data-stu-id="4b47e-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="4b47e-108">Aktuelle PIN des Benutzers ist weiterhin solange gültig, bis sie abläuft oder der Benutzer eine neue PIN anfordert.</span><span class="sxs-lookup"><span data-stu-id="4b47e-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="4b47e-109">Die folgenden Benutzerkontoinformationen werden nicht auf dem neuen Server verschoben.</span><span class="sxs-lookup"><span data-stu-id="4b47e-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="4b47e-110">**Der Inhalt der Besprechung**.</span><span class="sxs-lookup"><span data-stu-id="4b47e-110">**Meeting content**.</span></span> <span data-ttu-id="4b47e-111">Zum Verschieben des Inhalts während einer Besprechung freigegeben wie PowerPoint, Whiteboard, Anlagen oder Umfrage-Daten den **MoveConferenceData -** Parameter als Teil der **Move-CsUser** -Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b47e-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

