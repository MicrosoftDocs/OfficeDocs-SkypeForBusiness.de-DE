---
title: Verwalten von Skype Room System-Konten
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie Skype Room System-Konten verwalten.
ms.openlocfilehash: 5276bd1f2b74000e681efadd8961b9c048351c3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293333"
---
# <a name="manage-skype-room-system-accounts"></a>Verwalten von Skype Room System-Konten
 
Lesen Sie dieses Thema und erfahren Sie, wie Sie Skype Room System-Konten verwalten. 

> [!NOTE]
> Microsoft Teams Rooms ist ein anderes Produkt mit unterschiedlichen Abhängigkeiten und Bereitstellungsverfahren. Informationen zu Microsoft Teams-Räumen finden Sie in der Übersicht zur Microsoft Teams rooms- [Verwaltung](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Verschieben des Skype Room-System Kontos zwischen Pools

Wenn Sie das Skype Room-Systemkonto von einem Skype for Business Server-Pool in einen anderen verschieben möchten (beispielsweise bei Upgrades), verwenden Sie den folgenden Befehl, um den Pool des Skype Room-Systemkontos zu verschieben: 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Deaktivieren des Skype Room-System Kontos für Skype for Business-Dienste

Wenn Sie ein vorhandenes Skype Room-System Konto über Skype for Business-Dienste in einem Skype for Business Server-Pool deaktivieren möchten, verwenden Sie den folgenden Befehl, um das Konto zu deaktivieren: 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Optional: Erstellen einer Skype Room-System Administratorgruppe in Active Directory

Jeder Skype Room-System Client, der der Domäne Beitritt, kann von einem Domänenbenutzer mit lokalen Administratorrechten auf dem Skype Room System Appliance-PC vollständig verwaltet werden. Aus diesem Grund können Sie eine dedizierte Administratorengruppe in Active Directory erstellen und dieser Gruppe während der Einrichtung des neuen Skype Room-System Computers Administratorrechte erteilen.
  

