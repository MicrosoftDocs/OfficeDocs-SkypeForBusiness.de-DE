---
title: Anzeigen von Trunk-Konfigurationsinformationen in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters.
ms.openlocfilehash: 9d4890cd70256c6f063653a29d5d41f6e5a301cb
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222716"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="1e427-103">Anzeigen von Trunk-Konfigurationsinformationen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="1e427-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="1e427-104">SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters.</span><span class="sxs-lookup"><span data-stu-id="1e427-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="1e427-105">Ob Medienumgehung für die Trunks aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1e427-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="1e427-106">Die Bedingungen, unter denen Pakete Real-Time Transport Control Protocol (RTCP) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e427-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="1e427-107">Unabhängig davon, ob die Verschlüsselung secure Real-Time Transport Protocol (SRTP) für jeden Trunk erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1e427-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="1e427-108">Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="1e427-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="1e427-109">Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).</span><span class="sxs-lookup"><span data-stu-id="1e427-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="1e427-110">**So zeigen Sie SIP-Trunk-Konfigurationsinformationen mithilfe von Skype Business Server-Systemsteuerung an**</span><span class="sxs-lookup"><span data-stu-id="1e427-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="1e427-111">Klicken Sie in der Skype Business Server-Systemsteuerung klicken Sie auf **VoIP-Routing**, und klicken Sie dann auf **Trunkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1e427-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="1e427-112">Klicken Sie auf der Registerkarte **Trunkkonfiguration** sehen Sie eine Liste mit allen Trunk Configuration Settings Sammlungen. für jede Auflistung sehen Sie Werte für die Eigenschaften **Name**, **Bereich**, **Status**und **die medienumgehung** sowie die Anzahl der **PSTN-Verwendungen**, **Aufrufen für Rufnummern**und **genannte Zahl Regeln** verknüpft ist mit der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="1e427-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="1e427-113">Um weitere Details zu einer Auflistung von trunkkonfigurationseinstellungen anzuzeigen, klicken Sie auf die Auflistung von Interesse, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1e427-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="1e427-114">Beachten Sie, dass Sie detaillierte Informationen nur für eine Auflistung von trunkkonfigurationseinstellungen zu einem Zeitpunkt anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="1e427-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1e427-115">Anzeigen von SIP-Trunk-Konfigurationsinformationen mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="1e427-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1e427-116">SIP-Trunk-Konfigurationen, die Einstellungen mithilfe von Skype für Business Server-PowerShell und dem Cmdlet Get-CsTrunkConfiguration angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="1e427-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="1e427-117">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer Windows PowerShell-Remotesitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1e427-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="1e427-118">Ausführliche Informationen zur Verwendung von remote Windows PowerShell für Business Server eine Verbindung mit Skype finden Sie im Lync Server-Windows PowerShell-Blog-Artikel "Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell" unter http://go.microsoft.com/fwlink/p/?linkId=255876.</span><span class="sxs-lookup"><span data-stu-id="1e427-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="1e427-119">ERSETZEN ODER DIESEN LINK ENTFERNEN.</span><span class="sxs-lookup"><span data-stu-id="1e427-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="1e427-120">**So zeigen Sie SIP-Trunk-Konfigurationsinformationen an**</span><span class="sxs-lookup"><span data-stu-id="1e427-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="1e427-121">Anzeigen von Informationen zu allen SIP-Trunk-Konfigurationseinstellungen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="1e427-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="1e427-122">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="1e427-122">That will return information similar to this:</span></span>

```
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
<span data-ttu-id="1e427-123">Weitere Informationen finden Sie im Hilfethema zum [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e427-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



