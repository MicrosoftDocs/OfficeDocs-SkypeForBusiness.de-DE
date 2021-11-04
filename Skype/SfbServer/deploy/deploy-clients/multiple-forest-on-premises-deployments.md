---
title: Skype Lokale Bereitstellungen mit mehreren Gesamtstrukturen für Das Raumsystem
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: In diesem Thema erfahren Sie, wie Sie Skype Raumsystem in einer lokalen Umgebung mit mehreren Gesamtstrukturen bereitstellen.
ms.openlocfilehash: 49885d1e64c40f161eb0fc07ec79187b5ea3bdb1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761583"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype Lokale Bereitstellungen mit mehreren Gesamtstrukturen für Das Raumsystem
 
In diesem Thema erfahren Sie, wie Sie Skype Raumsystem in einer lokalen Umgebung mit mehreren Gesamtstrukturen bereitstellen.
  
> [!NOTE]
> Zur Bereitstellung in mehreren Gesamtstrukturen erfordert Skype Room System Exchange Server 2013 CU6, das am 26. August 2014 veröffentlicht wurde. Vermeiden Sie die erneute Verwendung eines vorhandenen Postfachs für Skype Raumsystem. Verwenden Sie ein neues Ressourcenpostfach (altes Postfach löschen und neu erstellen) für Skype Raumsystem. Informationen zum Wiederherstellen der verlorenen Besprechungen durch Löschen des Postfachs finden Sie [unter Verbinden oder Wiederherstellen eines gelöschten Postfachs.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
Nach dem Erstellen des Postfachs können Sie Set-CalendarProcessing verwenden, um das Postfach zu konfigurieren. Weitere Informationen finden Sie in den Schritten 3 bis 6 unter lokale Bereitstellungen mit einzelner Gesamtstruktur. Nachdem Sie ein Exchange Ressourcenpostfach für Skype Raumsystem erstellt haben, aktivieren Sie das Konto für Skype for Business, indem Sie die Schritte unter Aktivieren Skype Raumsystemkonten für Skype for Business unter lokalen Bereitstellungen mit einzelner Gesamtstruktur ausführen.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Option 1: Erstellen eines neuen Ressourcenpostfachs

So stellen Sie Skype Raumsystem in einer Umgebung mit mehreren Gesamtstrukturen bereit:
  
1. Erstellen Sie einen verknüpften Benutzer (LinkedRoomTest) in Active Directory (Authentifizierungsgesamtstruktur).
    
2. Führen Sie die folgenden Befehle in der Exchange Server-Verwaltungsshell aus:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Option 2: Ändern eines vorhandenen Raumpostfachs in Skype Raumsystem-Ressourcenpostfach (verknüpft)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```