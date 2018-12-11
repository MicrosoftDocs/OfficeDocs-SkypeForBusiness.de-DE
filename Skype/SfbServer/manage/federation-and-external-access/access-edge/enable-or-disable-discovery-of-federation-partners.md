---
title: Aktivieren oder Deaktivieren der Suche von Verbundpartnern
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Der Zeitpunkt Edgeserver bereitgestellt und aktiviert den Verbund für Ihr Unternehmen, Sie sollten haben angegeben, ob die automatische Ermittlung aus verbundpartnerdomänen unterstützen.
ms.openlocfilehash: afa022ae1a52124c3dabaf788de8308ba9834227
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222849"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="5842a-103">Aktivieren Sie oder deaktivieren Sie der Ermittlung von Verbundpartnern in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="5842a-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="5842a-104">Der Zeitpunkt Edgeserver bereitgestellt und aktiviert den Verbund für Ihr Unternehmen, Sie sollten haben angegeben, ob die automatische Ermittlung aus verbundpartnerdomänen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5842a-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="5842a-105">Verwenden Sie das Verfahren in diesem Thema, um die Konfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5842a-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="5842a-106">Das folgende Verfahren wird davon ausgegangen, dass Sie den Verbund für Ihre Organisation bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="5842a-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="5842a-107">Ausführliche Informationen zur Aktivierung des Verbunds finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5842a-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="5842a-108">So aktivieren oder Deaktivieren der automatischen Suche von Partnerdomänen für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="5842a-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="5842a-109">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="5842a-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5842a-110">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5842a-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="5842a-111">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**, und dann auf **Konfiguration für Zugriffsedge**.</span><span class="sxs-lookup"><span data-stu-id="5842a-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="5842a-112">Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5842a-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5842a-113">Klicken Sie in **Konfiguration für Zugriffsedge bearbeiten**, unter der **Kommunikation mit Partnerbenutzern aktivieren**aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Partner Domäne Discovery aktivieren** , zum Aktivieren oder Deaktivieren der automatischen Suche von Partnerdomänen.</span><span class="sxs-lookup"><span data-stu-id="5842a-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="5842a-114">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5842a-114">Click **Commit**.</span></span>

<span data-ttu-id="5842a-115">Um Verbundbenutzer Zusammenarbeit mit Benutzern in Ihrer Skype für Business Server-Bereitstellung zu aktivieren, müssen Sie auch mindestens eine externe Zugriffsrichtlinie zur Unterstützung der partnerbenutzerzugriff konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="5842a-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="5842a-116">Weitere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des partnerverbunds und öffentlichen Instant Messaging-Diensten](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="5842a-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="5842a-117">Ausführliche Informationen zum Steuern des Zugriffs für spezifische Partnerdomänen an finden Sie unter [Verwalten von SIP-verbunddomänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md) und [Verwalten von SIP-partnerverbundanbieter](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="5842a-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5842a-118">Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="5842a-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5842a-119">Ermittlung von Verbundpartnern kann mithilfe von Windows PowerShell und das Set-CsAccessEdgeConfiguration-Cmdlet verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="5842a-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="5842a-120">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5842a-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="5842a-121">So aktivieren Sie die Suche von Verbundpartnern</span><span class="sxs-lookup"><span data-stu-id="5842a-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="5842a-122">Legen Sie den Wert der Eigenschaft **EnablePartnerDiscovery** auf "true" ($True), um die Suche von Verbundpartnern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5842a-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="5842a-123">Beachten Sie, dass DNS-SRV-routing, um den Eigenschaftswert ändern aktiviert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5842a-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="5842a-124">So deaktivieren Sie die Suche von Verbundpartnern</span><span class="sxs-lookup"><span data-stu-id="5842a-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="5842a-125">Um die Suche von Verbundpartnern zu deaktivieren, legen Sie den Wert der Eigenschaft **EnablePartnerDiscovery** auf "false" ($False):</span><span class="sxs-lookup"><span data-stu-id="5842a-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

