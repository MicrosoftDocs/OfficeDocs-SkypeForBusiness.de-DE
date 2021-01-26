---
title: Lokale Bereitstellungen von Skype Room System mit mehreren Gesamtstrukturen
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
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: In diesem Thema erfahren Sie, wie Sie Skype Room System in einer lokalen Umgebung mit mehreren Gesamtstrukturen bereitstellen.
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805745"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Lokale Bereitstellungen von Skype Room System mit mehreren Gesamtstrukturen
 
In diesem Thema erfahren Sie, wie Sie Skype Room System in einer lokalen Umgebung mit mehreren Gesamtstrukturen bereitstellen.
  
> [!NOTE]
> Für die Bereitstellung in mehreren Gesamtstrukturen erfordert Skype Room System Exchange Server 2013 CU6, das am 26. August 2014 veröffentlicht wurde. Vermeiden Sie die erneute Verwendung eines vorhandenen Postfachs für Skype Room System. Verwenden Sie ein neues Ressourcenpostfach für Skype Room System (altes Postfach löschen und neu erstellen). Informationen zum Wiederherstellen der durch das Löschen des Postfachs verlorenen Besprechungen finden Sie unter [Verbinden oder Wiederherstellen eines gelöschten Postfachs.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx) 
  
Nach dem Erstellen des Postfachs können Sie Set-CalendarProcessing zum Konfigurieren des Postfachs verwenden. Weitere Informationen finden Sie in den Schritten 3 bis 6 unter lokalen Bereitstellungen mit einer einzelnen Gesamtstruktur. Aktivieren Sie nach dem Erstellen eines Exchange-Ressourcenpostfachs für Skype Room System das Konto für Skype for Business, indem Sie die Schritte unter "Aktivieren von Skype Room System Accounts for Skype for Business unter lokalen Bereitstellungen mit einer einzelnen Gesamtstruktur" ausführen.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Option 1: Erstellen eines neuen Ressourcenpostfachs

So stellen Sie Skype Room System in einer Umgebung mit mehreren Gesamtstrukturen zur Verfügung:
  
1. Erstellen eines verknüpften Benutzers (LinkedRoomTest) in Active Directory (Authentifizierungsstruktur).
    
2. Führen Sie die folgenden Befehle in der Exchange Server aus:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Option 2: Ändern eines vorhandenen Raumpostfachs in ein (verknüpftes) Ressourcenpostfach für Skype Room System

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


