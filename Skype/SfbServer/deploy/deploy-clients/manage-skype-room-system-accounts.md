---
title: Verwalten von Skype Room System-Konten
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie Skype Room System-Konten verwalten.
ms.openlocfilehash: 86fb7356586c006e8d9f0831d98c9ceba5979180
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893371"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="29c74-103">Verwalten von Skype Room System-Konten</span><span class="sxs-lookup"><span data-stu-id="29c74-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="29c74-104">Lesen Sie dieses Thema und erfahren Sie, wie Sie Skype Room System-Konten verwalten.</span><span class="sxs-lookup"><span data-stu-id="29c74-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="29c74-105">Microsoft-Teams Chatrooms ist ein anderes Produkt mit verschiedenen Abhängigkeiten und Bereitstellungsverfahren.</span><span class="sxs-lookup"><span data-stu-id="29c74-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="29c74-106">Informationen zu Microsoft-Teams Chatrooms finden Sie unter [Übersicht über die Verwaltung](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)in der Microsoft-Teams Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="29c74-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="29c74-107">Das Systemkonto von Skype Platz zwischen Pools verschieben</span><span class="sxs-lookup"><span data-stu-id="29c74-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="29c74-108">Wenn Sie das Skype Raum Systemkonto (beispielsweise während des Upgrades) aus einem Skype für Business Server-Pool in einen anderen verschieben möchten, verwenden Sie den folgenden Befehl Skype Raum System Konto Pool zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="29c74-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="29c74-109">Deaktivieren Sie das Systemkonto von Skype Raum für Skype für Unternehmensdienste</span><span class="sxs-lookup"><span data-stu-id="29c74-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="29c74-110">Wenn Sie eine vorhandene Skype Raum Systemkonto von Skype für BusinessServices auf einen Skype für Business Server-Pool deaktivieren müssen, verwenden Sie den folgenden Befehl, um das Konto zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="29c74-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="29c74-111">Optional: Erstellen einer Administratorgruppe Skype Raum System in Active Directory</span><span class="sxs-lookup"><span data-stu-id="29c74-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="29c74-112">Jeder Skype Raum System-Client, der die Domäne hinzugefügt kann von einem Domänenbenutzer mit lokalen Administratorrechten auf dem Gerät Skype Raum System PC vollständig verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="29c74-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="29c74-113">Aus diesem Grund können Sie Erstellen einer dedizierten Administratoren Gruppe in Active Directory und geben dieser Gruppe Administratorrechte während Set up des neuen Skype Raum System Computers.</span><span class="sxs-lookup"><span data-stu-id="29c74-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

