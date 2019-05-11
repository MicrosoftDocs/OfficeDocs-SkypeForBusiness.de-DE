---
title: Konfigurieren einer sekundären standortinformationsdienst in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Konfigurieren einer sekundären Standortdatenbank Quelle (SLS) für E9-1-1 in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 047fd1a7dca0c4c2b76d01fd0c5d67230246441e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892293"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="66dcd-103">Konfigurieren einer sekundären standortinformationsdienst in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="66dcd-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="66dcd-104">Konfigurieren einer sekundären Standortdatenbank Quelle (SLS) für E9-1-1 in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="66dcd-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="66dcd-105">Skype für Business Server bietet eine Webdienstschnittstelle, die Sie verwenden können, um den standortinformationsdienst mit einer sekundären Standort Quelle (SLS)-Datenbank zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="66dcd-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="66dcd-106">Web-Service-Schnittstelle, die mit der SLS-Datenbank verbindet muss Standortinformationen Service-WSDL-Datei entsprechen.</span><span class="sxs-lookup"><span data-stu-id="66dcd-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="66dcd-107">Wenn eine Standortdatenbank und die sekundäre Standortdatenbank konfiguriert sind, der standortinformationsdienst zuerst fragt die Standortdatenbank und keine Übereinstimmung gefunden wird, sendet die Anforderung vom Client an der SLS-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="66dcd-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="66dcd-108">Wenn Sie der Speicherort der SLS vorhanden ist, sendet der Standortinformationen-Dienst klicken Sie dann den Speicherort an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="66dcd-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="66dcd-109">So konfigurieren Sie eine sekundäre Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="66dcd-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="66dcd-110">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="66dcd-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="66dcd-111">Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="66dcd-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="66dcd-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66dcd-112">See also</span></span>

[<span data-ttu-id="66dcd-113">"Set-cswebserviceconfiguration"</span><span class="sxs-lookup"><span data-stu-id="66dcd-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

