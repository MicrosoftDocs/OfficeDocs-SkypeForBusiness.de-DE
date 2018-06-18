---
title: Verwalten von Skype Room System-Konten
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie Skype Room System-Konten verwalten.
ms.openlocfilehash: 4d3535c9583481273f7a511143244b511cdb5819
ms.sourcegitcommit: 0f089f0c1bc641793c61928fb1c8fa62b2dfabee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2018
ms.locfileid: "19927788"
---
# <a name="manage-skype-room-system-accounts"></a>Verwalten von Skype Room System-Konten
 
Lesen Sie dieses Thema und erfahren Sie, wie Sie Skype Room System-Konten verwalten. 

> [!NOTE]
> Skype-Chatroom-Systemen v2 ist ein anderes Produkt mit verschiedenen Abhängigkeiten und Bereitstellungsverfahren. Informationen zu Skype Raum Systemen v2 finden Sie unter Skype Raum Systemen v2 [(Übersicht)](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Das Systemkonto von Skype Platz zwischen Pools verschieben

Wenn Sie das Skype Raum Systemkonto (beispielsweise während des Upgrades) aus einem Skype für Business Server-Pool in einen anderen verschieben möchten, verwenden Sie den folgenden Befehl Skype Raum System Konto Pool zu verschieben: 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Deaktivieren Sie das Systemkonto von Skype Raum für Skype für Unternehmensdienste

Wenn Sie eine vorhandene Skype Raum Systemkonto von Skype für BusinessServices auf einen Skype für Business Server-Pool deaktivieren müssen, verwenden Sie den folgenden Befehl, um das Konto zu deaktivieren: 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Optional: Erstellen einer Administratorgruppe Skype Raum System in Active Directory

Jeder Skype Raum System-Client, der die Domäne hinzugefügt kann von einem Domänenbenutzer mit lokalen Administratorrechten auf dem Gerät Skype Raum System PC vollständig verwaltet werden. Aus diesem Grund können Sie Erstellen einer dedizierten Administratoren Gruppe in Active Directory und geben dieser Gruppe Administratorrechte während Set up des neuen Skype Raum System Computers.
  

