---
title: Anzeigen von trunk-Konfigurationsinformationen in Skype for Business Server
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
description: SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter.
ms.openlocfilehash: 0ccbf86891d6265298411ad2f90988123529b614
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816904"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="a7cc8-103">Anzeigen von trunk-Konfigurationsinformationen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a7cc8-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="a7cc8-104">SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="a7cc8-105">Ob Medienumgehung für die Trunks aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="a7cc8-106">Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="a7cc8-107">Ob die SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden trunk erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="a7cc8-108">Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-Trunk-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="a7cc8-109">Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).</span><span class="sxs-lookup"><span data-stu-id="a7cc8-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="a7cc8-110">**So zeigen Sie SIP-Trunk-Konfigurationsinformationen mithilfe der Skype for Business Server-Systemsteuerung an**</span><span class="sxs-lookup"><span data-stu-id="a7cc8-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="a7cc8-111">Klicken Sie im Skype for Business Server-Control Panel auf **VoIP-Routing**und dann auf trunk- **Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="a7cc8-112">Auf dem Reiter " **trunk Configuration** " sehen Sie eine Liste aller ihrer trunk Configuration Settings-Sammlungen. für jede Sammlung werden Werte für die Eigenschaften **Name**, **Scope**, **State**und **Media Bypass** sowie die Anzahl der **PSTN-Nutzungen**, **Regeln**für die Rufnummernanzeige und **benannte Nummern Regeln** für die Sammlung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="a7cc8-113">Wenn Sie weitere Details zu einer Sammlung von trunk-Konfigurationseinstellungen anzeigen möchten, klicken Sie auf die Sammlung von Interesse, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="a7cc8-114">Beachten Sie, dass Sie detaillierte Informationen nur für eine Sammlung von trunk-Konfigurationseinstellungen gleichzeitig anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a7cc8-115">Anzeigen von SIP-Trunk-Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a7cc8-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a7cc8-116">Die SIP-Trunk-Konfigurationseinstellungen können mithilfe von Skype for Business Server PowerShell und dem Cmdlet Get-CsTrunkConfiguration angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="a7cc8-117">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Windows PowerShell-Remotesitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="a7cc8-118">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von http://go.microsoft.com/fwlink/p/?linkId=255876Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="a7cc8-119">diesen Link ersetzen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="a7cc8-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="a7cc8-120">**So zeigen Sie die SIP-Trunk-Konfigurationsinformationen an**</span><span class="sxs-lookup"><span data-stu-id="a7cc8-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="a7cc8-121">Wenn Sie Informationen zu allen Ihren SIP-Trunk-Konfigurationseinstellungen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="a7cc8-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="a7cc8-122">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="a7cc8-122">That will return information similar to this:</span></span>

```console
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
<span data-ttu-id="a7cc8-123">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="a7cc8-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



