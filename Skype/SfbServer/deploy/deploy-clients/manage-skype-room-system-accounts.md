---
title: Verwalten von Skype Room System-Konten
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie Skype Room System-Konten verwalten.
ms.openlocfilehash: b6d61f4ddc9fe5e296ffd98b685e1000151d5db2
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768658"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="85b9b-103">Verwalten von Skype Room System-Konten</span><span class="sxs-lookup"><span data-stu-id="85b9b-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="85b9b-104">Lesen Sie dieses Thema und erfahren Sie, wie Sie Skype Room System-Konten verwalten.</span><span class="sxs-lookup"><span data-stu-id="85b9b-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="85b9b-105">Microsoft Teams Rooms ist ein anderes Produkt mit unterschiedlichen Abhängigkeiten und Bereitstellungsverfahren.</span><span class="sxs-lookup"><span data-stu-id="85b9b-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="85b9b-106">Informationen zu Microsoft Teams-Räumen finden Sie in der Übersicht zur Microsoft Teams rooms- [Verwaltung](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span><span class="sxs-lookup"><span data-stu-id="85b9b-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="85b9b-107">Verschieben des Skype Room-System Kontos zwischen Pools</span><span class="sxs-lookup"><span data-stu-id="85b9b-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="85b9b-108">Wenn Sie das Skype Room-Systemkonto von einem Skype for Business Server-Pool in einen anderen verschieben möchten (beispielsweise bei Upgrades), verwenden Sie den folgenden Befehl, um den Pool des Skype Room-Systemkontos zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="85b9b-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="85b9b-109">Deaktivieren des Skype Room-System Kontos für Skype for Business-Dienste</span><span class="sxs-lookup"><span data-stu-id="85b9b-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="85b9b-110">Wenn Sie ein vorhandenes Skype Room-System Konto über Skype for Business-Dienste in einem Skype for Business Server-Pool deaktivieren möchten, verwenden Sie den folgenden Befehl, um das Konto zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="85b9b-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="85b9b-111">Optional: Erstellen einer Skype Room-System Administratorgruppe in Active Directory</span><span class="sxs-lookup"><span data-stu-id="85b9b-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="85b9b-112">Jeder Skype Room-System Client, der der Domäne Beitritt, kann von einem Domänenbenutzer mit lokalen Administratorrechten auf dem Skype Room System Appliance-PC vollständig verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="85b9b-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="85b9b-113">Aus diesem Grund können Sie eine dedizierte Administratorengruppe in Active Directory erstellen und dieser Gruppe während der Einrichtung des neuen Skype Room-System Computers Administratorrechte erteilen.</span><span class="sxs-lookup"><span data-stu-id="85b9b-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

