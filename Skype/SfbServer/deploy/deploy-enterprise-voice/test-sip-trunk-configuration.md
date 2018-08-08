---
title: Testen von SIP-trunkkonfigurationseinstellungen in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Zusammenfassung: Informationen Sie zum Testen der SIP-trunkkonfigurationseinstellungen mithilfe der Skype für Business Server-Verwaltungsshell.'
ms.openlocfilehash: ea0874eabacfb814c5cc668654c56c86c788beff
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20984071"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="82a22-103">Testen von SIP-trunkkonfigurationseinstellungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="82a22-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="82a22-104">**Zusammenfassung:** Erfahren Sie, wie SIP-Trunk-Konfigurationseinstellungen mithilfe der Skype für Business Server-Verwaltungsshell zu testen.</span><span class="sxs-lookup"><span data-stu-id="82a22-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="82a22-p101">SIP-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network, Festnetz), einer IP-Nebenstellenanlage (Public Branch Exchange, PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="82a22-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="82a22-107">Ob Medienumgehung für die Trunks aktiviert werden soll</span><span class="sxs-lookup"><span data-stu-id="82a22-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="82a22-108">Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="82a22-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="82a22-109">Ob SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden Trunk erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="82a22-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="82a22-110">Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="82a22-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="82a22-111">Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).</span><span class="sxs-lookup"><span data-stu-id="82a22-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="82a22-112">Administratoren können außerdem mit dem Test-CsTrunkConfiguration-Cmdlet überprüfen, ob ein Trunk eine von einem Benutzer gewählte Rufnummer in eine für das Gateway kompatible Rufnummer konvertieren kann.</span><span class="sxs-lookup"><span data-stu-id="82a22-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="82a22-113">Trunkkonfigurationseinstellungen können nur mithilfe von Windows PowerShell und das [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) -Cmdlet getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="82a22-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="82a22-114">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer Remotesitzung von Skype für Business Server-Verwaltungsshell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="82a22-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="82a22-115">Testen von Konfigurationseinstellungen für SIP-Trunks</span><span class="sxs-lookup"><span data-stu-id="82a22-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="82a22-116">Mit dem folgenden Befehl wird überprüft, ob mit den Trunk-Konfigurationseinstellungen für den Standort Redmond die gewählte Rufnummer 4255551212 ordnungsgemäß konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="82a22-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


