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
ms.openlocfilehash: 416a211ec9954dd2c2a8c856a67c72226209f3e7dd6114536574e63c5520b841
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279463"
---
# <a name="manage-skype-room-system-accounts"></a>Verwalten von Skype Room Systems-Konten
 
In diesem Thema erfahren Sie, wie Sie Skype Room System-Konten verwalten. 

> [!NOTE]
> Microsoft Teams-Räume ist ein anderes Produkt mit unterschiedlichen Abhängigkeiten und Bereitstellungsverfahren. Informationen zu Microsoft Teams-Räume finden Sie in der Übersicht über die [Microsoft Teams-Räume-Verwaltung.](/microsoftteams/rooms/rooms-manage)
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Verschieben des Skype Raumsystemkontos zwischen Pools

Wenn Sie das Skype Room System-Konto von einem Skype for Business Server-Pool in einen anderen verschieben müssen (z. B. während Upgrades), verwenden Sie den folgenden Befehl, um den Skype Raumsystem-Kontopool zu verschieben: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Deaktivieren des Skype Raumsystemkontos für Skype for Business Dienste

Wenn Sie ein vorhandenes Skype Room System-Konto aus Skype for Business Diensten in einem Skype for Business Server-Pool deaktivieren müssen, verwenden Sie den folgenden Befehl, um das Konto zu deaktivieren: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Optional: Erstellen einer Skype Raumsystemadministratorgruppe in Active Directory

Jeder Skype Raumsystemclient, der der Domäne beitritt, kann vollständig von einem Domänenbenutzer mit lokalen Administratorrechten auf dem Skype Raumsystemanwendungs-PC verwaltet werden. Daher können Sie eine dedizierte Administratorgruppe in Active Directory erstellen und dieser Gruppe während der Einrichtung des neuen Skype Raumsystemcomputers Administratorrechte erteilen.
