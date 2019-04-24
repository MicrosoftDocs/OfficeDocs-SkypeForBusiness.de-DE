---
title: Lokale Bereitstellungen von Skype Room System mit mehreren Gesamtstrukturen
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit mehrfacher Gesamtstruktur bereitgestellt wird.
ms.openlocfilehash: 507040a1d8274817e7a4a0780135ee8f6642c77c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219416"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="79745-103">Lokale Bereitstellungen von Skype Room System mit mehreren Gesamtstrukturen</span><span class="sxs-lookup"><span data-stu-id="79745-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="79745-104">Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit mehrfacher Gesamtstruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="79745-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79745-105">Um die Bereitstellung in mehreren Gesamtstrukturen erfordert Skype Raum System Exchange Server 2013 CU6 auf 26 August 2014 veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="79745-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="79745-106">Vermeiden Sie ein vorhandenes Postfach für Skype Raum System wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="79745-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="79745-107">Verwenden Sie ein neues (alte Postfach löschen und Neuerstellen) Ressourcenpostfach für Skype Raum System.</span><span class="sxs-lookup"><span data-stu-id="79745-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="79745-108">Informationen zum Wiederherstellen von Besprechungen verloren durch Löschen des Postfachs finden Sie unter [Connect- oder Wiederherstellen eines gelöschten Postfachs](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="79745-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="79745-109">Nachdem das Postfach erstellt wurde, können Sie Set-CalendarProcessing für die Postfachkonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="79745-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="79745-110">Mehr dazu erfahren Sie in den Schritten 3–6 unter „Lokale Bereitstellungen mit einzelner Gesamtstruktur“.</span><span class="sxs-lookup"><span data-stu-id="79745-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="79745-111">Aktivieren Sie nach dem Erstellen einer Exchange-Ressourcenpostfach für Skype Raum System, das Konto für Skype für Unternehmen mithilfe des Verfahrens in Skype Raum Systemkonten aktivieren für Skype für Unternehmen unter Gesamtstruktur lokale Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="79745-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="79745-112">Option 1: Erstellen eines neuen Ressourcenpostfachs</span><span class="sxs-lookup"><span data-stu-id="79745-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="79745-113">Skype-Chatroom-System in einer Umgebung mit mehreren Gesamtstrukturen bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="79745-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="79745-114">Erstellen Sie einen verknüpften Nutzer (LinkedRoomTest) in Active Directory (Authentifizierungs-Gesamtstruktur).</span><span class="sxs-lookup"><span data-stu-id="79745-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="79745-115">Führen Sie die folgenden Befehle in der Exchange Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="79745-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="79745-116">Option 2: Ändern einer vorhandenen Raumpostfach Skype Raum Systempostfach (verknüpfte) Ressource</span><span class="sxs-lookup"><span data-stu-id="79745-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


