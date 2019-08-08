---
title: Skype Room System – Hybridbereitstellungen
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: In diesem Thema erfahren Sie, wie Sie das Skype Room-System in einer Hybridumgebung bereitstellen.
ms.openlocfilehash: 016a4cf379200dc87b8f94d13a65f10f6c3af25f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234429"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="54abc-103">Skype Room System – Hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="54abc-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="54abc-104">In diesem Thema erfahren Sie, wie Sie das Skype Room-System in einer Hybridumgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="54abc-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="54abc-105">Hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="54abc-105">Hybrid deployments</span></span>

<span data-ttu-id="54abc-106">Führen Sie die folgenden Schritte aus, wenn Ihre Topologie über Skype for Business Server und Exchange Online verfügt und Sie das Skype Room-System Ressourcenpostfach auf Exchange Online hosten möchten.</span><span class="sxs-lookup"><span data-stu-id="54abc-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="54abc-107">Dieser Abschnitt behandelt auch ein Hybridszenario, in dessen Rahmen sowohl Exchange Online als auch Exchange Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="54abc-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="54abc-108">Zu illustrativen Zwecken verwenden wir LyncSample.com für die lokale Domäne und LyncSample.ccstp.net für die Online Domäne.</span><span class="sxs-lookup"><span data-stu-id="54abc-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="54abc-109">Erstellen Sie ein Ressourcenpostfach im Exchange Admin Center (LyncSample.ccsctp.net), indem Sie eine Verbindung zur Exchange Online-Verwaltungsshell herstellen, wie in Exchange Online-Bereitstellung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="54abc-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="54abc-110">Sie können die OWA-Konnektivität mithilfe von lrstest5@LyncSample.ccsctp.NET überprüfen, um sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="54abc-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="54abc-111">Fügen Sie im Office 365 Exchange Admin Center eine e-Mail-Adresse lrstest5@LyncSample.com (auf-Prem-Domäne) hinzu, und stellen Sie Sie als Antwortadresse ein.</span><span class="sxs-lookup"><span data-stu-id="54abc-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="54abc-112">Erstellen Sie eine auf-Prem Active Directory-Benutzer lrstest5@LyncSample.com, legen Sie die e-Mail-Adresse auf lrstest5@LyncSample.com, und legen Sie die Zieladresse auf lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="54abc-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="54abc-113">Führen Sie die Verzeichnissynchronisierung aus, und vergewissern Sie sich nach Abschluss der Synchronisierung, dass Benutzer in Aad zusammengeführt werden und dass Sie die Eigenschaften in den Ressourcen des Empfängers im Office365 Exchange Admin Center nicht ändern können.</span><span class="sxs-lookup"><span data-stu-id="54abc-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="54abc-114">Überprüfen Sie die OWA-Konnektivität mithilfe von lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="54abc-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="54abc-115">(Zu einem früheren Zeitpunkt haben Sie OWA-Konnektivität mithilfe der Onlinedomäne überprüft.)</span><span class="sxs-lookup"><span data-stu-id="54abc-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="54abc-p103">Nachdem das Postfach erstellt worden ist, können Sie Set-CalendarProcessing in der Exchange-Online-Verwaltungsshell verwenden, um das Postfach zu konfigurieren. Mehr dazu erfahren Sie in den Schritten 3–6 unter „Lokale Bereitstellungen mit einzelner Gesamtstruktur“.</span><span class="sxs-lookup"><span data-stu-id="54abc-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="54abc-118">Wenn Sie über eine Hybridumgebung mit Exchange Server und Exchange Online verfügen, wechseln Sie zur Exchange-Verwaltungsshell, und aktivieren Sie RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.Mail.ccsctp.net-Room.</span><span class="sxs-lookup"><span data-stu-id="54abc-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="54abc-119">Lösen Sie anschließend die Verzeichnissynchronisierung aus.</span><span class="sxs-lookup"><span data-stu-id="54abc-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="54abc-120">Wenn Sie das Skype Room-System Postfach in Exchange Online hosten möchten, sind diese Schritte zur Exchange-Verwaltungsshell nicht erforderlich, und Sie können mit Schritt 6 fortfahren.</span><span class="sxs-lookup"><span data-stu-id="54abc-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="54abc-121">Aktivieren Sie das Skype Room-System Konto für Skype for Business, indem Sie auf der Skype for Business-Verwaltungsshell das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="54abc-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="54abc-122">Wenn Sie Skype for Business Online anstelle von Skype for Business Server im obigen Szenario haben, stellen Sie nach der Bereitstellung des Exchange-Ressourcenpostfachs ein Skype for Business-Konto bereit, wie es in der Skype for Business Online-Bereitstellung beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="54abc-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

