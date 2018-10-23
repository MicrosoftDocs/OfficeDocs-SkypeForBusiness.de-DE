---
title: Verwalten von Skype Room System-Konten
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie Skype Room System-Konten verwalten.
ms.openlocfilehash: 715eda137395d2133b6b19dee4a9d2336923c13b
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699244"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="fb380-103">Verwalten von Skype Room System-Konten</span><span class="sxs-lookup"><span data-stu-id="fb380-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="fb380-104">Lesen Sie dieses Thema und erfahren Sie, wie Sie Skype Room System-Konten verwalten.</span><span class="sxs-lookup"><span data-stu-id="fb380-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="fb380-105">Skype-Chatroom-Systemen v2 ist ein anderes Produkt mit verschiedenen Abhängigkeiten und Bereitstellungsverfahren.</span><span class="sxs-lookup"><span data-stu-id="fb380-105">Skype Room Systems v2 is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="fb380-106">Informationen zu Skype Raum Systemen v2 finden Sie unter Skype Raum Systemen v2 [(Übersicht)](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="fb380-106">For information on Skype Room Systems v2, see the Skype Room Systems v2 [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="fb380-107">Das Systemkonto von Skype Platz zwischen Pools verschieben</span><span class="sxs-lookup"><span data-stu-id="fb380-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="fb380-108">Wenn Sie das Skype Raum Systemkonto (beispielsweise während des Upgrades) aus einem Skype für Business Server-Pool in einen anderen verschieben möchten, verwenden Sie den folgenden Befehl Skype Raum System Konto Pool zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="fb380-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="fb380-109">Deaktivieren Sie das Systemkonto von Skype Raum für Skype für Unternehmensdienste</span><span class="sxs-lookup"><span data-stu-id="fb380-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="fb380-110">Wenn Sie eine vorhandene Skype Raum Systemkonto von Skype für BusinessServices auf einen Skype für Business Server-Pool deaktivieren müssen, verwenden Sie den folgenden Befehl, um das Konto zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="fb380-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="fb380-111">Optional: Erstellen einer Administratorgruppe Skype Raum System in Active Directory</span><span class="sxs-lookup"><span data-stu-id="fb380-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="fb380-112">Jeder Skype Raum System-Client, der die Domäne hinzugefügt kann von einem Domänenbenutzer mit lokalen Administratorrechten auf dem Gerät Skype Raum System PC vollständig verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="fb380-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="fb380-113">Aus diesem Grund können Sie Erstellen einer dedizierten Administratoren Gruppe in Active Directory und geben dieser Gruppe Administratorrechte während Set up des neuen Skype Raum System Computers.</span><span class="sxs-lookup"><span data-stu-id="fb380-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

