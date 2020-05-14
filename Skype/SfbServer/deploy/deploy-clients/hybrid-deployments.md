---
title: Hybridbereitstellungen für Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lesen Sie dieses Thema, um zu erfahren, wie Skype Room System in einer Hybridumgebung bereitgestellt wird.
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219675"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="994e8-103">Hybridbereitstellungen für Skype Room System</span><span class="sxs-lookup"><span data-stu-id="994e8-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="994e8-104">Lesen Sie dieses Thema, um zu erfahren, wie Skype Room System in einer Hybridumgebung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="994e8-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="994e8-105">Hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="994e8-105">Hybrid deployments</span></span>

<span data-ttu-id="994e8-106">Führen Sie die folgenden Schritte aus, wenn Ihre Topologie über Skype for Business Server und Exchange Online verfügt und Sie das Skype Room System-Ressourcenpostfach auf Exchange Online hosten möchten.</span><span class="sxs-lookup"><span data-stu-id="994e8-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="994e8-107">In diesem Abschnitt wird außerdem ein Hybrid Szenario behandelt, in dem Sie sowohl Exchange Online als auch Exchange Server bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="994e8-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="994e8-108">Zur Veranschaulichung wird LyncSample.com für die lokale Domäne und LyncSample.ccstp.net für die Online Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="994e8-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="994e8-109">Erstellen Sie ein Ressourcenpostfach in der Exchange-Verwaltungskonsole (LyncSample.ccsctp.net), indem Sie eine Verbindung mit der Exchange Online-Verwaltungsshell herstellen, wie in Exchange Online-vorsehen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="994e8-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="994e8-110">Sie können die OWA-Konnektivität mithilfe von lrstest5@LyncSample.ccsctp.NET überprüfen, um sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="994e8-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="994e8-111">Fügen Sie in der Microsoft 365-oder Office 365 Exchange-Verwaltungskonsole eine e-Mail-Adresse lrstest5@LyncSample.com (on-Prem Domain) hinzu, und legen Sie Sie als Antwortadresse fest.</span><span class="sxs-lookup"><span data-stu-id="994e8-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="994e8-112">Erstellen Sie eine Active Directory Benutzer lrstest5@LyncSample.com, legen Sie die e-Mail-Adresse auf lrstest5@LyncSample.com, und legen Sie die Zieladresse auf lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="994e8-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="994e8-113">Rufen Sie die Verzeichnissynchronisierung ab, und überprüfen Sie nach Abschluss der Synchronisierung, ob die Benutzer in Aad zusammengeführt werden und ob die Eigenschaften in den Ressourcen des Empfängers in der Microsoft 365-oder Office 365 Exchange-Verwaltungskonsole geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="994e8-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="994e8-114">Überprüfen der OWA-Konnektivität mithilfe von lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="994e8-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="994e8-115">(Zuvor haben Sie die OWA-Konnektivität über die Online Domäne überprüft.)</span><span class="sxs-lookup"><span data-stu-id="994e8-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="994e8-116">Nachdem Sie das Postfach erstellt haben, können Sie mithilfe von "CalendarProcessing" in der Exchange Online-Verwaltungsshell das Postfach konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="994e8-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="994e8-117">Weitere Informationen finden Sie in den Schritten 3 bis 6 unter einzelne Gesamtstruktur-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="994e8-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="994e8-118">Wenn Sie über eine Hybridumgebung mit Exchange Server und Exchange Online verfügen, wechseln Sie zum Exchange-Verwaltungsshell und enable-Remote Mailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.Mail.ccsctp.net-Room.</span><span class="sxs-lookup"><span data-stu-id="994e8-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="994e8-119">Anschließend wird die Verzeichnissynchronisierung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="994e8-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="994e8-120">Wenn Sie das Skype Room System-Postfach in Exchange Online hosten möchten, sind diese Exchange-Verwaltungsshell Schritte nicht erforderlich, und Sie können mit Schritt 6 fortfahren.</span><span class="sxs-lookup"><span data-stu-id="994e8-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="994e8-121">Aktivieren Sie das Skype Room System-Konto für Skype for Business, indem Sie das folgende Cmdlet für Skype for Business-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="994e8-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="994e8-122">Wenn Sie Skype for Business Online anstelle von Skype for Business Server im obigen Szenario haben, stellen Sie nach dem Bereitstellen des Exchange-Ressourcenpostfachs ein Skype for Business-Konto bereit, wie unter Skype for Business Online-Bereitstellung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="994e8-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

