---
title: Verwalten von Skype Room Systems-Konten
ms.author: v-cichur
author: cichur
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
description: In diesem Thema erfahren Sie, wie Sie Skype Room System-Konten verwalten.
ms.openlocfilehash: e6b905b065badb729ccc9281d63ba050fc032ef2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093293"
---
# <a name="manage-skype-room-system-accounts"></a>Verwalten von Skype Room Systems-Konten
 
In diesem Thema erfahren Sie, wie Sie Skype Room System-Konten verwalten. 

> [!NOTE]
> Microsoft Teams Rooms ist ein anderes Produkt mit unterschiedlichen Abhängigkeiten und Bereitstellungsverfahren. Informationen zu Microsoft Teams Rooms finden Sie unter Microsoft Teams Rooms [management overview](/microsoftteams/rooms/rooms-manage).
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Verschieben des Skype Room System-Kontos zwischen Pools

Wenn Sie das Skype Room System-Konto von einem Skype for Business Server-Pool in einen anderen verschieben müssen (z. B. bei Upgrades), verwenden Sie den folgenden Befehl, um den Skype Room System-Kontopool zu verschieben: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Deaktivieren des Skype Room System-Kontos für Skype for Business-Dienste

Wenn Sie ein vorhandenes Skype Room System-Konto von Skype for Business-Diensten in einem Skype for Business Server-Pool deaktivieren müssen, verwenden Sie den folgenden Befehl, um das Konto zu deaktivieren: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Optional: Erstellen einer Skype Room System-Administratorgruppe in Active Directory

Jeder Skype Room System-Client, der der Domäne beitritt, kann von einem Domänenbenutzer mit lokalen Administratorrechten auf dem Skype Room System-Appliance-PC vollständig verwaltet werden. Aus diesem Grund können Sie eine dedizierte Administratorgruppe in Active Directory erstellen und dieser Gruppe während der Einrichtung des neuen Skype Room System-Computers Administratorrechte geben.
