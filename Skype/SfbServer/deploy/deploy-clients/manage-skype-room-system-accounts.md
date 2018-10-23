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
  

