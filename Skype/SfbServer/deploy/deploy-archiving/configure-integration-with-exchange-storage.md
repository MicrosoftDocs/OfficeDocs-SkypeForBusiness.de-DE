---
title: Konfigurieren der Integration mit Exchange-Speicher für Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie die Integration mit Exchange-Speicher in Skype für Business Server konfigurieren.'
ms.openlocfilehash: 35ef648a1076283f63752221a807da21bf4208ca
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370620"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="5ce4a-103">Konfigurieren der Integration mit Exchange-Speicher für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="5ce4a-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="5ce4a-104">**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie die Integration mit Exchange-Speicher in Skype für Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="5ce4a-105">Wenn Sie Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie keine Skype für Business Server Archivierungsrichtlinien für Ihre Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="5ce4a-106">Stattdessen konfigurieren Sie Exchange In-Place Hold Richtlinien zur Unterstützung der Archivierung für Benutzer in Exchange, mit ihren Postfächern Compliance-Archiv platzieren verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="5ce4a-107">Lesen Sie vor dem Konfigurieren von Integration mit Exchange-Speicher [für die Archivierung in Skype für Business Server planen](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="5ce4a-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="5ce4a-108">Ausführliche Informationen zu Exchange Compliance-Archiv Richtlinien finden Sie in der Produktdokumentation zu Exchange.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="5ce4a-109">Konfigurieren der Integration mit Microsoft Exchange-Speicher</span><span class="sxs-lookup"><span data-stu-id="5ce4a-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="5ce4a-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5ce4a-111">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5ce4a-112">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="5ce4a-113">Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und auf **Details anzeigen** und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5ce4a-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="5ce4a-114">Aktivieren Sie das Kontrollkästchen **Microsoft Exchange-Integration** , zum Aktivieren der Integration mit Exchange-Speicher.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="5ce4a-115">Deaktivieren Sie das Kontrollkästchen **Microsoft Exchange-Integration** , um die Integration von Exchange-Speicher zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="5ce4a-116">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="5ce4a-117">Wenn Skype für Business Server und Microsoft Exchange in unterschiedlichen Gesamtstrukturen bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="5ce4a-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="5ce4a-118">Wenn Sie Microsoft Exchange-Integration verwenden, und Microsoft Exchange Server ist nicht in derselben Gesamtstruktur wie Skype für Business Server bereitgestellt, Sie müssen sicherstellen, dass die folgenden Exchange Active Directory-Attribute mit der Gesamtstruktur synchronisiert sind, in dem Skype für Business-Server bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="5ce4a-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="5ce4a-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5ce4a-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="5ce4a-120">Proxyadressen</span><span class="sxs-lookup"><span data-stu-id="5ce4a-120">proxyAddresses</span></span>
    
<span data-ttu-id="5ce4a-p102">Dies ist ein mehrwertiges Attribut. Bei der Synchronisierung dieses Attributs müssen Sie die Werte zusammenführen und nicht ersetzen, um sicherzustellen, dass die vorhandenen Werte nicht verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

