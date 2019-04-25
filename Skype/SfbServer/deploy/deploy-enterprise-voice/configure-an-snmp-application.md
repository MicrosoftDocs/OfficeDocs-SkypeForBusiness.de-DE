---
title: Konfigurieren einer SNMP-Anwendung in Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Konfigurieren Sie eine SNMP-Anwendung zur Arbeit mit E9-1-1 in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: f45666708b2f5bb3065631bbb4ab38ee88082517
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223690"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="62847-103">Konfigurieren einer SNMP-Anwendung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="62847-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="62847-104">Konfigurieren Sie eine SNMP-Anwendung zur Arbeit mit E9-1-1 in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="62847-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="62847-105">Skype für Business Server umfasst eine standardmäßige webdienstschnittselle, die Sie mit dem Dienst Standortinformationen für Simple Network Management Protocol (SNMP) Clientanwendungen zu hergestellt, die Abgleich von MAC-Adressen mit Port- und Switchinformationen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="62847-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="62847-106">Wenn eine SNMP-Anwendung installiert ist und der Standortinformationen Dienst nicht in der Standortdatenbank Übereinstimmung gefunden, fragt der standortinformationsdienst die Anwendung automatisch mithilfe der MAC-Adresse vom Client.</span><span class="sxs-lookup"><span data-stu-id="62847-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="62847-107">Der Standortinformationen-Dienst verwendet klicken Sie dann die Port- und Switch-Informationen von der SNMP-Anwendung zurückgegeben, um der Standortdatenbank erneut abzufragen.</span><span class="sxs-lookup"><span data-stu-id="62847-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62847-108">MAC-Adressen sind nicht auf Computern unter Windows 8 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="62847-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="62847-109">So konfigurieren Sie die URL für die SNMP-Anwendung</span><span class="sxs-lookup"><span data-stu-id="62847-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="62847-110">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="62847-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="62847-111">Führen Sie das folgende Cmdlet aus, um die URL für die SNMP-Anwendung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="62847-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="62847-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62847-112">See also</span></span>

[<span data-ttu-id="62847-113">"Set-cswebserviceconfiguration"</span><span class="sxs-lookup"><span data-stu-id="62847-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

