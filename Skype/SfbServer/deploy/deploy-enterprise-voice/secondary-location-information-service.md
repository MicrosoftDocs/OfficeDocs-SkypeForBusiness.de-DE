---
title: Konfigurieren eines sekundären Standort Informationsdiensts in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Konfigurieren Sie eine SLS-Datenbank (Secondary Location Source) für E9-1-1 in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 0d637b8b2b61526837be2d56b8654f40bc556064
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288533"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="28e9a-103">Konfigurieren eines sekundären Standort Informationsdiensts in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="28e9a-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="28e9a-104">Konfigurieren Sie eine SLS-Datenbank (Secondary Location Source) für E9-1-1 in Skype for Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="28e9a-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="28e9a-105">Skype for Business Server bietet eine Webdienstschnittstelle, die Sie verwenden können, um den standortinformationsdienst auf eine SLS-Datenbank (Secondary Location Source) zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="28e9a-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="28e9a-106">Die Webdienstschnittstelle, die eine Verbindung mit der SLS-Datenbank herstellt, muss dem Location Information Service-WSDL entsprechen.</span><span class="sxs-lookup"><span data-stu-id="28e9a-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="28e9a-107">Wenn sowohl eine Standortdatenbank als auch eine sekundäre Standortdatenbank konfiguriert sind, fragt der standortinformationsdienst zuerst die Standortdatenbank ab, und wenn keine Übereinstimmung gefunden wird, sendet die standortanforderung vom Client an die SLS-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="28e9a-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="28e9a-108">Wenn der Standort im SLS vorhanden ist, sendet der standortinformationsdienst den Standort dann zurück an den Client.</span><span class="sxs-lookup"><span data-stu-id="28e9a-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="28e9a-109">So konfigurieren Sie eine sekundäre Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="28e9a-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="28e9a-110">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="28e9a-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="28e9a-111">Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="28e9a-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="28e9a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28e9a-112">See also</span></span>

[<span data-ttu-id="28e9a-113">Satz-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="28e9a-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

