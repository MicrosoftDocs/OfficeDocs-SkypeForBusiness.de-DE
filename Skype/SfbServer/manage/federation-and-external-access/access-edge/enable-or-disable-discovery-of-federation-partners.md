---
title: Aktivieren oder Deaktivieren der Suche von Verbundpartnern
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Zu dem Zeitpunkt, zu dem Sie Ihre Edgeserver und den aktivierten Verbund für Ihre Organisation bereitgestellt haben, sollten Sie angeben, ob die automatische Ermittlung von Verbundpartner Domänen unterstützt werden soll.
ms.openlocfilehash: a5569639cf870d2a5da16ef81aa733724a6701b3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280257"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="32ddf-103">Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="32ddf-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="32ddf-104">Zu dem Zeitpunkt, zu dem Sie Ihre Edgeserver und den aktivierten Verbund für Ihre Organisation bereitgestellt haben, sollten Sie angeben, ob die automatische Ermittlung von Verbundpartner Domänen unterstützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="32ddf-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="32ddf-105">Verwenden Sie das in diesem Thema beschriebene Verfahren, um diese Konfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="32ddf-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="32ddf-106">Im folgenden Verfahren wird davon ausgegangen, dass Sie die Föderation für Ihre Organisation bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="32ddf-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="32ddf-107">Details zum Aktivieren von Föderationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="32ddf-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="32ddf-108">So aktivieren oder deaktivieren Sie die automatische Ermittlung von Verbunddomänen für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="32ddf-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="32ddf-109">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="32ddf-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="32ddf-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="32ddf-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="32ddf-111">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie auf **Access-Edge-Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="32ddf-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="32ddf-112">Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="32ddf-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="32ddf-113">Aktivieren oder deaktivieren Sie in der **Konfiguration der Access-Edge-Konfiguration**unter **Kommunikation mit Verbundbenutzern aktivieren**das Kontrollkästchen **Ermittlung der Partnerdomäne aktivieren** , um die automatische Ermittlung von Partnerdomänen zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="32ddf-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="32ddf-114">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="32ddf-114">Click **Commit**.</span></span>

<span data-ttu-id="32ddf-115">Damit Föderationsbenutzer mit Benutzern in Ihrer Skype for Business Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfiguriert haben, um den Verbundbenutzer Zugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="32ddf-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="32ddf-116">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="32ddf-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="32ddf-117">Details zum Steuern des Zugriffs für bestimmte Verbunddomänen finden Sie unter [Verwalten von SIP-Verbunddomänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md) und [Verwalten von SIP-Verbund Anbietern](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="32ddf-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="32ddf-118">Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="32ddf-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="32ddf-119">Die Ermittlung von Verbundpartnern kann mithilfe von Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="32ddf-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="32ddf-120">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="32ddf-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="32ddf-121">So aktivieren Sie die Suche nach Verbundpartnern</span><span class="sxs-lookup"><span data-stu-id="32ddf-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="32ddf-122">Um die Suche nach Verbundpartnern zu aktivieren, setzen Sie den Wert der **EnablePartnerDiscovery** -Eigenschaft auf true ($true).</span><span class="sxs-lookup"><span data-stu-id="32ddf-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="32ddf-123">Beachten Sie, dass Sie das DNS-SRV-Routing aktivieren müssen, um diesen Eigenschaftswert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="32ddf-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="32ddf-124">So deaktivieren Sie die Ermittlung von Verbundpartnern</span><span class="sxs-lookup"><span data-stu-id="32ddf-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="32ddf-125">Um die Ermittlung von Verbundpartnern zu deaktivieren, setzen Sie den Wert der **EnablePartnerDiscovery** -Eigenschaft auf false ($false):</span><span class="sxs-lookup"><span data-stu-id="32ddf-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

