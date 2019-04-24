---
title: Skype Room System – Hybridbereitstellungen
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lesen Sie in diesem Thema erfahren, wie Skype Raum System in einer hybridumgebung bereitstellen.
ms.openlocfilehash: 40cbcd7cd95b6a5dc7542f913fe7599bedc7eb85
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219451"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="cbbf4-103">Skype Room System – Hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="cbbf4-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="cbbf4-104">Lesen Sie in diesem Thema erfahren, wie Skype Raum System in einer hybridumgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="cbbf4-105">Hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="cbbf4-105">Hybrid deployments</span></span>

<span data-ttu-id="cbbf4-106">Gehen Sie folgendermaßen vor, wenn Ihre Topologie Skype für Business Server und Exchange Online, und Sie das Ressourcenpostfach Skype Raum System auf Exchange Online hosten möchten.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="cbbf4-107">Dieser Abschnitt behandelt auch ein Hybridszenario, in dessen Rahmen sowohl Exchange Online als auch Exchange Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="cbbf4-108">Zur Veranschaulichung verwenden wir für die lokale Domäne und LyncSample.ccstp.net LyncSample.com für die online-Domäne.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="cbbf4-109">Erstellen Sie ein Ressourcenpostfach im Exchange Administrationscenter (LyncSample.ccsctp.net) durch Verbinden mit der Exchange Online-Verwaltungsshell wie in Exchange Online-Bereitstellung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="cbbf4-110">OWA-Konnektivität mit lrstest5@LyncSample.ccsctp.net anmelden kann überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="cbbf4-111">Fügen Sie einer e-Mail-Adresse lrstest5@LyncSample.com (auf Prem Domäne hinzu), und legen Sie es als Antwortadresse, in der Office 365-Exchange-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="cbbf4-112">Erstellen einer auf Prem Active Directory-Benutzer lrstest5@LyncSample.com, legen Sie die E-mail-Adresse auf lrstest5@LyncSample.com und die Zieladresse auf lrstest5@LyncSample.com festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="cbbf4-113">Auslösen Directory-Synchronisierung und, nachdem Synchronisierung abgeschlossen ist, stellen Sie sicher, dass Benutzer in AAD zusammenführen und Sie nicht zum Ändern der Eigenschaften des Empfängers Ressourcen im Office365 Exchange Administrationscenter können.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="cbbf4-114">Überprüfen der OWA-Konnektivität mit lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="cbbf4-115">(Zu einem früheren Zeitpunkt haben Sie OWA-Konnektivität mithilfe der Onlinedomäne überprüft.)</span><span class="sxs-lookup"><span data-stu-id="cbbf4-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="cbbf4-p103">Nachdem das Postfach erstellt worden ist, können Sie Set-CalendarProcessing in der Exchange-Online-Verwaltungsshell verwenden, um das Postfach zu konfigurieren. Mehr dazu erfahren Sie in den Schritten 3–6 unter „Lokale Bereitstellungen mit einzelner Gesamtstruktur“.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="cbbf4-118">Wenn Sie eine hybridumgebung mit Exchange Server und Exchange Online haben, fahren Sie mit der Exchange-Verwaltungsshell und Enable-RemoteMailbox lrstest5@LyncSample.com - RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Chatroom.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="cbbf4-119">Lösen Sie anschließend die Verzeichnissynchronisierung aus.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="cbbf4-120">Wenn Sie das Postfach Skype Raum im Exchange Online hosten möchten, diese Schritte für die Exchange-Verwaltungsshell sind nicht erforderlich, und können Sie mit Schritt 6 fortfahren.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="cbbf4-121">Aktivieren Sie das Systemkonto von Skype Raum für Skype für Unternehmen durch Ausführen des folgenden Cmdlets auf Skype für Business-Verwaltungsshell:</span><span class="sxs-lookup"><span data-stu-id="cbbf4-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="cbbf4-122">Wenn Sie Skype für Business Online anstelle von Skype für Business Server im obigen Szenario haben, klicken Sie dann nach dem das Ressourcenpostfach Exchange-Bereitstellung Bereitstellen einer Skype für Business Konto wie in Skype für die Bereitstellung von Business Online beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cbbf4-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

