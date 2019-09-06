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
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="246fd-103">Lokale Bereitstellungen von Skype Room System mit mehreren Gesamtstrukturen</span><span class="sxs-lookup"><span data-stu-id="246fd-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="246fd-104">Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit mehrfacher Gesamtstruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="246fd-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="246fd-105">Für die Bereitstellung in mehreren Gesamtstrukturen erfordert das Skype Room System Exchange Server 2013 CU6, das am 26. August 2014 veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="246fd-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="246fd-106">Vermeiden Sie es, ein vorhandenes Postfach für das Skype Room-System erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="246fd-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="246fd-107">Verwenden Sie ein neues Ressourcenpostfach für Skype Room System (altes Postfach löschen und neu erstellen).</span><span class="sxs-lookup"><span data-stu-id="246fd-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="246fd-108">Informationen zum Wiederherstellen der verloren gegangenen Besprechungen durch Löschen des Postfachs finden Sie unter [verbinden oder Wiederherstellen eines gelöschten Postfachs](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="246fd-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="246fd-109">Nachdem das Postfach erstellt wurde, können Sie Set-CalendarProcessing für die Postfachkonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="246fd-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="246fd-110">Mehr dazu erfahren Sie in den Schritten 3–6 unter „Lokale Bereitstellungen mit einzelner Gesamtstruktur“.</span><span class="sxs-lookup"><span data-stu-id="246fd-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="246fd-111">Nachdem Sie ein Exchange-Ressourcenpostfach für das Skype Room-System erstellt haben, aktivieren Sie das Konto für Skype for Business, indem Sie die Schritte unter Aktivieren von Skype Room-Systemkonten für Skype for Business unter einzelne Gesamtstruktur lokale Bereitstellungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="246fd-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="246fd-112">Option 1: Erstellen eines neuen Ressourcenpostfachs</span><span class="sxs-lookup"><span data-stu-id="246fd-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="246fd-113">So stellen Sie das Skype Room-System in einer Multi-Forest-Umgebung bereit:</span><span class="sxs-lookup"><span data-stu-id="246fd-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="246fd-114">Erstellen Sie einen verknüpften Nutzer (LinkedRoomTest) in Active Directory (Authentifizierungs-Gesamtstruktur).</span><span class="sxs-lookup"><span data-stu-id="246fd-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="246fd-115">Führen Sie die folgenden Befehle in der Exchange Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="246fd-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="246fd-116">Option 2: Ändern eines vorhandenen Raumpostfachs in das Skype Room System (verknüpftes) Ressourcenpostfach</span><span class="sxs-lookup"><span data-stu-id="246fd-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


