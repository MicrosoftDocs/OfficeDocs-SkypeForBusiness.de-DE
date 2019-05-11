---
title: Testen von SIP-trunkkonfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters. '
ms.openlocfilehash: 1caf96e9979936c8fb9ff61d9b28b613fb09ce7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902264"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="8133b-103">Testen von SIP-trunkkonfigurationseinstellungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8133b-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="8133b-104">SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters.</span><span class="sxs-lookup"><span data-stu-id="8133b-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="8133b-105">Diese Einstellungen geben unter anderem Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="8133b-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="8133b-106">Ob Medienumgehung für die Trunks aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8133b-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="8133b-107">Die Bedingungen, unter denen Pakete Real-Time Transport Control Protocol (RTCP) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="8133b-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="8133b-108">Unabhängig davon, ob die Verschlüsselung secure Real-Time Transport Protocol (SRTP) für jeden Trunk erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8133b-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="8133b-109">Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="8133b-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="8133b-110">Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).</span><span class="sxs-lookup"><span data-stu-id="8133b-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="8133b-111">Administratoren können auch das [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) -Cmdlet verwenden, um sicherzustellen, dass eine Zahl, wie von einem Benutzer eine Nummer gewählt wird, die vom Gateway behandelt werden können ein Trunk konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8133b-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="8133b-112">Trunk-Konfigurationseinstellungen können nur mit Windows PowerShell und dem Test-CsTrunkConfiguration-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8133b-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="8133b-113">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8133b-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="8133b-114">**Testen von Konfigurationseinstellungen für SIP-Trunks**</span><span class="sxs-lookup"><span data-stu-id="8133b-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="8133b-115">Mit dem folgenden Befehl wird überprüft, ob mit den Trunk-Konfigurationseinstellungen für den Standort Redmond die gewählte Rufnummer 4255551212 ordnungsgemäß konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8133b-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
