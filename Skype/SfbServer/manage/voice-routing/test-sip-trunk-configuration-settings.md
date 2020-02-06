---
title: Testen der SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. '
ms.openlocfilehash: 911947b33f0e609b4dd532ec5cc2c3d56a08618c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816935"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c74f5-103">Testen der SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c74f5-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="c74f5-104">SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="c74f5-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="c74f5-105">Diese Einstellungen geben unter anderem Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="c74f5-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="c74f5-106">Ob Medienumgehung für die Trunks aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c74f5-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="c74f5-107">Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c74f5-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="c74f5-108">Ob die SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden trunk erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c74f5-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="c74f5-109">Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-Trunk-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="c74f5-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="c74f5-110">Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).</span><span class="sxs-lookup"><span data-stu-id="c74f5-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="c74f5-111">Administratoren können auch das Cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) verwenden, um zu überprüfen, ob ein trunk eine von einem Benutzer gewählte Nummer in eine Zahl umwandeln kann, die vom Gateway verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c74f5-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="c74f5-112">Trunk-Konfigurationseinstellungen können nur mit Windows PowerShell und dem Test-CsTrunkConfiguration-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c74f5-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="c74f5-113">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c74f5-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="c74f5-114">**Testen von Konfigurationseinstellungen für SIP-Trunks**</span><span class="sxs-lookup"><span data-stu-id="c74f5-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="c74f5-115">Mit dem folgenden Befehl wird überprüft, ob mit den Trunk-Konfigurationseinstellungen für den Standort Redmond die gewählte Rufnummer 4255551212 ordnungsgemäß konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c74f5-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
