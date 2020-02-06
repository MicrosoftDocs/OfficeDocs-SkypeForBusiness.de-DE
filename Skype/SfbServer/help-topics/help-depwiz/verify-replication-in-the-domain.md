---
title: Überprüfen der Replikation in der Domäne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Um die Replikation der Domänenvorbereitung zu überprüfen, die in Schritt 1: Vorbereiten eines Schemas durchgeführt wurde, muss ein Cmdlet aus der lync Server-Verwaltungsshell der Skype for Business Server-Verwaltungsshell ausgeführt werden. Wenn Sie das Windows PowerShell-Cmdlet ausführen möchten, melden Sie sich bei einem Computer an, der Mitglied der von Ihnen vorbereiteten Domäne und als Mitglied der Gruppe der Domänenadministratoren ist. Gehen Sie wie folgt vor:'
ms.openlocfilehash: da61941bacd1d5463c11cf044d9ce8a6442ef9d4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823289"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="8cf67-105">Überprüfen der Replikation in der Domäne</span><span class="sxs-lookup"><span data-stu-id="8cf67-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="8cf67-106">Um die Replikation der Domänenvorbereitung zu überprüfen, die in **Schritt 1: Vorbereiten eines Schemas**durchgeführt wurde, muss ein Cmdlet aus der lync Server-Verwaltungsshell der Skype for Business Server-Verwaltungsshell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8cf67-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="8cf67-107">Wenn Sie das Windows PowerShell-Cmdlet ausführen möchten, melden Sie sich bei einem Computer an, der Mitglied der von Ihnen vorbereiteten Domäne und als Mitglied der Gruppe der Domänenadministratoren ist.</span><span class="sxs-lookup"><span data-stu-id="8cf67-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="8cf67-108">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="8cf67-108">Do the following:</span></span>
  
1. <span data-ttu-id="8cf67-109">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="8cf67-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8cf67-110">Geben Sie in Windows PowerShell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8cf67-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="8cf67-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8cf67-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="8cf67-112">Über den Parameter „GlobalSettingsDomainController“ können Sie den Speicherort der globalen Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="8cf67-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="8cf67-113">Wenn Ihre Einstellungen im System Container gespeichert sind (typisch für Upgrade-Bereitstellungen, bei denen die globale Einstellung nicht zum Konfigurationscontainer migriert wurde), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Active Directory-Domänendienste-Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="8cf67-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="8cf67-114">Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="8cf67-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="8cf67-115">Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänencontroller in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8cf67-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="8cf67-116">Wenn Sie den Parameter „Domain“ nicht angeben, wird die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="8cf67-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="8cf67-117">Bei erfolgreicher Domänenvorbereitung gibt dieses Cmdlet den Wert **LC_DOMAIN_SETTINGS_STATE_READY** zurück.</span><span class="sxs-lookup"><span data-stu-id="8cf67-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

