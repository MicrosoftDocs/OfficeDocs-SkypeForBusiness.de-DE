---
title: Lokale Bereitstellungen mit mehreren Gesamtstrukturen im Skype Room System
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
ms.openlocfilehash: d215ce13059c414d6c6142d7cd1e93ea9011c97b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093529"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Lokale Bereitstellungen mit mehreren Gesamtstrukturen im Skype Room System
 
In diesem Thema erfahren Sie, wie Sie Skype Room System in einer lokalen Umgebung mit mehreren Gesamtstrukturen bereitstellen.
  
> [!NOTE]
> Für die Bereitstellung in mehreren Gesamtstrukturen erfordert Skype Room System Exchange Server 2013 CU6, veröffentlicht am 26. August 2014. Vermeiden Sie die erneute Verwendung eines vorhandenen Postfachs für Skype Room System. Verwenden Sie ein neues Ressourcenpostfach (altes Postfach löschen und neu erstellen) für Skype Room System. Informationen zum Wiederherstellen der Besprechungen, die durch Löschen des Postfachs verloren gehen, finden Sie unter [Verbinden oder Wiederherstellen eines gelöschten Postfachs.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
Nach dem Erstellen des Postfachs können Sie Set-CalendarProcessing zum Konfigurieren des Postfachs verwenden. Weitere Informationen finden Sie in den Schritten 3 bis 6 unter Lokale Bereitstellungen mit einer einzelnen Gesamtstruktur. Aktivieren Sie nach dem Erstellen eines Exchange-Ressourcenpostfachs für Skype Room System das Konto für Skype for Business, indem Sie die Schritte unter Aktivieren von Skype Room System Accounts for Skype for Business unter Lokale Bereitstellungen mit einer einzelnen Gesamtstruktur ausführen.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Option 1: Erstellen eines neuen Ressourcenpostfachs

So stellen Sie Skype Room System in einer Umgebung mit mehreren Gesamtstrukturen zur Verfügung:
  
1. Erstellen eines verknüpften Benutzers (LinkedRoomTest) in Active Directory (Authentifizierungsstruktur).
    
2. Führen Sie die folgenden Befehle in Exchange Server Verwaltungsshell aus:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Option 2: Ändern eines vorhandenen Raumpostfachs in Skype Room System (verknüpftes) Ressourcenpostfach

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```