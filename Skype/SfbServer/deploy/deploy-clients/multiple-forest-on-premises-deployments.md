---
title: Lokale Bereitstellungen von Skype Room System mit mehreren Gesamtstrukturen
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit mehrfacher Gesamtstruktur bereitgestellt wird.
ms.openlocfilehash: eb5aa2cbe3bef26602279ffa9d4a5dc38a7e7bc2
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775040"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Lokale Bereitstellungen von Skype Room System mit mehreren Gesamtstrukturen
 
Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit mehrfacher Gesamtstruktur bereitgestellt wird.
  
> [!NOTE]
> Für die Bereitstellung in mehreren Gesamtstrukturen erfordert das Skype Room System Exchange Server 2013 CU6, das am 26. August 2014 veröffentlicht wurde. Vermeiden Sie es, ein vorhandenes Postfach für das Skype Room-System erneut zu verwenden. Verwenden Sie ein neues Ressourcenpostfach für Skype Room System (altes Postfach löschen und neu erstellen). Informationen zum Wiederherstellen der verloren gegangenen Besprechungen durch Löschen des Postfachs finden Sie unter [verbinden oder Wiederherstellen eines gelöschten Postfachs](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Nachdem das Postfach erstellt wurde, können Sie Set-CalendarProcessing für die Postfachkonfiguration verwenden. Mehr dazu erfahren Sie in den Schritten 3–6 unter „Lokale Bereitstellungen mit einzelner Gesamtstruktur“. Nachdem Sie ein Exchange-Ressourcenpostfach für das Skype Room-System erstellt haben, aktivieren Sie das Konto für Skype for Business, indem Sie die Schritte unter Aktivieren von Skype Room-Systemkonten für Skype for Business unter einzelne Gesamtstruktur lokale Bereitstellungen ausführen.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Option 1: Erstellen eines neuen Ressourcenpostfachs

So stellen Sie das Skype Room-System in einer Multi-Forest-Umgebung bereit:
  
1. Erstellen Sie einen verknüpften Nutzer (LinkedRoomTest) in Active Directory (Authentifizierungs-Gesamtstruktur).
    
2. Führen Sie die folgenden Befehle in der Exchange Server-Verwaltungsshell aus:
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Option 2: Ändern eines vorhandenen Raumpostfachs in das Skype Room System (verknüpftes) Ressourcenpostfach

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


