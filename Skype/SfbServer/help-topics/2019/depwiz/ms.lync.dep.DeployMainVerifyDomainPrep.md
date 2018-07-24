---
title: Überprüfen der Replikation in der Domäne
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Zum Überprüfen der Replikation der Vorbereitung der Domäne erreicht in Schritt 1: Schema vorbereiten, es ist erforderlich, um ein Cmdlet aus der Skype für Business Server Management Shell Lync Server-Verwaltungsshell ausführen. Um das Windows PowerShell-Cmdlet ausführen, melden Sie sich an einem Computer, der Mitglied der Domäne, die Sie vorbereitet haben, und als Mitglied der Gruppe Domänen-Admins ist. Gehen Sie wie folgt vor:'
ms.openlocfilehash: 5f4e4344d6f14647216265f2615eb0c3fd3f9e82
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992766"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="8c018-105">Überprüfen der Replikation in der Domäne</span><span class="sxs-lookup"><span data-stu-id="8c018-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="8c018-106">Zum Überprüfen der Replikation der Vorbereitung der Domäne erreicht **Schritt 1: Schema vorbereiten**, es ist erforderlich, um ein Cmdlet aus der Skype für Business Server Management Shell Lync Server-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="8c018-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="8c018-107">Um das Windows PowerShell-Cmdlet ausführen, melden Sie sich an einem Computer, der Mitglied der Domäne, die Sie vorbereitet haben, und als Mitglied der Gruppe Domänen-Admins ist.</span><span class="sxs-lookup"><span data-stu-id="8c018-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="8c018-108">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="8c018-108">Do the following:</span></span>
  
1. <span data-ttu-id="8c018-109">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Unternehmen**und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="8c018-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8c018-110">Geben Sie in Windows PowerShell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8c018-110">In Windows PowerShell, type the following:</span></span>
    
  ```
  Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
  ```

    <span data-ttu-id="8c018-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8c018-111">For example:</span></span>
    
  ```
  Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
  ```

    > [!NOTE]
    > <span data-ttu-id="8c018-112">Über den Parameter „GlobalSettingsDomainController“ können Sie den Speicherort der globalen Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="8c018-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="8c018-113">Wenn die Einstellungen im Systemcontainer gespeichert werden (die typische mit Upgrade-Bereitstellungen, die nicht bereits erfolgt sind die globale in den Konfigurationscontainer migrierten Einstellung ist), definieren Sie einen Domänencontroller im Stamm der Gesamtstruktur Active Directory-Domänendienste.</span><span class="sxs-lookup"><span data-stu-id="8c018-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="8c018-114">Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="8c018-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="8c018-115">Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänencontroller in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8c018-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="8c018-116">Wenn Sie den Parameter „Domain“ nicht angeben, wird die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c018-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="8c018-117">Dieses Cmdlet gibt den Wert **LC_DOMAIN_SETTINGS_STATE_READY** zurück, wenn die domänenvorbereitung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="8c018-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

