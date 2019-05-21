---
title: Konfigurieren einer SNMP-Anwendung in Skype for Business Server
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Konfigurieren einer SNMP-Anwendung für die Arbeit mit E9-1-1 in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 575c982dae20ed085e49690edfbb141786390516
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303418"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="8bbbf-103">Konfigurieren einer SNMP-Anwendung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8bbbf-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="8bbbf-104">Konfigurieren einer SNMP-Anwendung für die Arbeit mit E9-1-1 in Skype for Business Server Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="8bbbf-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="8bbbf-105">Skype for Business Server enthält eine standardmäßige Webdienstschnittstelle, mit der Sie den standortinformationsdienst mit SNMP-Anwendungen (Simple Network Management Protocol) verbinden können, die Mac-Adressen mit Port-und Switch-Informationen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="8bbbf-106">Wenn eine SNMP-Anwendung installiert ist und der standortinformationsdienst keine Übereinstimmung in der Standortdatenbank findet, fragt der standortinformationsdienst die Anwendung automatisch mit der vom Client angegebenen MAC-Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="8bbbf-107">Der standortinformationsdienst verwendet dann die von der SNMP-Anwendung zurückgegebenen Port-und Switch-Informationen, um die Standortdatenbank erneut abzufragen.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8bbbf-108">Mac-Adressen stehen auf Computern unter Windows 8 nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="8bbbf-109">So konfigurieren Sie die URL für die SNMP-Anwendung</span><span class="sxs-lookup"><span data-stu-id="8bbbf-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="8bbbf-110">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8bbbf-111">Führen Sie das folgende Cmdlet aus, um die URL für die SNMP-Anwendung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="8bbbf-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bbbf-112">See also</span></span>

[<span data-ttu-id="8bbbf-113">Satz-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="8bbbf-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

