---
title: Konfigurieren der Integration in Exchange Storage für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die Integration in den Exchange-Speicher in Skype for Business Server konfigurieren.'
ms.openlocfilehash: b58aa090e4e6c51beb1f99ba5dc9020e029c8c39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286425"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="41a5a-103">Konfigurieren der Integration in Exchange Storage für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="41a5a-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="41a5a-104">**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Integration in den Exchange-Speicher in Skype for Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="41a5a-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="41a5a-105">Wenn Sie die Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie die Skype for Business Server-Archivierungsrichtlinien für Ihre Benutzer nicht konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="41a5a-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="41a5a-106">Stattdessen konfigurieren Sie Exchange-in-situ-Speicherrichtlinien, um die Archivierung für Benutzer zu unterstützen, die sich in Exchange befinden, wobei ihre Postfächer in-situ gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="41a5a-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="41a5a-107">Bevor Sie die Integration in Exchange-Speicher konfigurieren, lesen Sie [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="41a5a-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="41a5a-108">Ausführliche Informationen zu den Exchange-in-situ-Speicherrichtlinien finden Sie in der Exchange-Produktdokumentation.</span><span class="sxs-lookup"><span data-stu-id="41a5a-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="41a5a-109">Konfigurieren der Integration in den Microsoft Exchange-Speicher</span><span class="sxs-lookup"><span data-stu-id="41a5a-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="41a5a-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="41a5a-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="41a5a-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="41a5a-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="41a5a-112">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="41a5a-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="41a5a-113">Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und auf **Details anzeigen** und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="41a5a-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="41a5a-114">Wenn Sie die Integration in Exchange-Speicher aktivieren möchten, aktivieren Sie das Kontrollkästchen **Microsoft Exchange-Integration** .</span><span class="sxs-lookup"><span data-stu-id="41a5a-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="41a5a-115">Deaktivieren Sie das Kontrollkästchen **Microsoft Exchange-Integration** , um die Integration in Exchange-Speicher zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="41a5a-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="41a5a-116">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="41a5a-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="41a5a-117">Wenn Skype for Business Server und Microsoft Exchange in verschiedenen Gesamtstrukturen bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="41a5a-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="41a5a-118">Wenn Sie die Microsoft Exchange-Integration verwenden und Microsoft Exchange Server nicht in derselben Gesamtstruktur wie Skype for Business Server bereitgestellt wird, müssen Sie sicherstellen, dass die folgenden Exchange Active Directory-Attribute mit der Gesamtstruktur synchronisiert werden, in der Skype für Business Server wird bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="41a5a-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="41a5a-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="41a5a-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="41a5a-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="41a5a-120">proxyAddresses</span></span>
    
<span data-ttu-id="41a5a-p102">Dies ist ein mehrwertiges Attribut. Bei der Synchronisierung dieses Attributs müssen Sie die Werte zusammenführen und nicht ersetzen, um sicherzustellen, dass die vorhandenen Werte nicht verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="41a5a-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

