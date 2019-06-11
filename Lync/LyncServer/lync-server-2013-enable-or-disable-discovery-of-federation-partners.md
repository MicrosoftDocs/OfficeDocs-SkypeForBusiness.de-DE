---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren der Suche von Verbundpartnern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e83f261fe6fa3ece259518b7730239adf20944c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="cc396-102">Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc396-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc396-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cc396-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cc396-104">Zu dem Zeitpunkt, zu dem Sie Ihre Edgeserver und den aktivierten Verbund für Ihre Organisation bereitgestellt haben, sollten Sie angeben, ob die automatische Ermittlung von Verbundpartner Domänen unterstützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cc396-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="cc396-105">Verwenden Sie das in diesem Thema beschriebene Verfahren, um diese Konfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cc396-105">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc396-106">Im folgenden Verfahren wird davon ausgegangen, dass Sie die Föderation für Ihre Organisation bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="cc396-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="cc396-107">Details zum Aktivieren von Föderation finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cc396-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="cc396-108">So aktivieren oder deaktivieren Sie die automatische Ermittlung von Verbunddomänen für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="cc396-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="cc396-109">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="cc396-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cc396-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cc396-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cc396-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cc396-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cc396-112">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie auf **Access-Edge-Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="cc396-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="cc396-113">Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="cc396-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cc396-114">Aktivieren oder deaktivieren Sie in der **Konfiguration der Access-Edge-Konfiguration**unter **Kommunikation mit Verbundbenutzern aktivieren**das Kontrollkästchen **Ermittlung der Partnerdomäne aktivieren** , um die automatische Ermittlung von Partnerdomänen zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="cc396-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="cc396-115">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cc396-115">Click **Commit**.</span></span>

<span data-ttu-id="cc396-116">Damit Verbundbenutzer mit Benutzern in ihrer lync Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfiguriert haben, um den Verbundbenutzer Zugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cc396-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="cc396-117">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cc396-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="cc396-118">Details zum Steuern des Zugriffs für bestimmte Verbunddomänen finden Sie unter [Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) und [Verwalten von xmpp. Federated-Partner in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cc396-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cc396-119">Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cc396-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cc396-120">Die Ermittlung von Verbundpartnern kann mithilfe von Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="cc396-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="cc396-121">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cc396-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cc396-122">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="cc396-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="cc396-123">So aktivieren Sie die Suche nach Verbundpartnern</span><span class="sxs-lookup"><span data-stu-id="cc396-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="cc396-124">Um die Suche nach Verbundpartnern zu aktivieren, setzen Sie den Wert der **EnablePartnerDiscovery** -Eigenschaft auf true ($true).</span><span class="sxs-lookup"><span data-stu-id="cc396-124">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="cc396-125">Beachten Sie, dass Sie das DNS-SRV-Routing aktivieren müssen, um diesen Eigenschaftswert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cc396-125">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="cc396-126">So deaktivieren Sie die Ermittlung von Verbundpartnern</span><span class="sxs-lookup"><span data-stu-id="cc396-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="cc396-127">Um die Ermittlung von Verbundpartnern zu deaktivieren, setzen Sie den Wert der **EnablePartnerDiscovery** -Eigenschaft auf false ($false):</span><span class="sxs-lookup"><span data-stu-id="cc396-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

