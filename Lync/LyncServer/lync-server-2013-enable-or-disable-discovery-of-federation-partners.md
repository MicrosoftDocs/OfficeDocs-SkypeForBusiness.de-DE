---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e6fd924d4aef6a9a6657829fa225da9595f52fe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="2a560-102">Aktivieren oder Deaktivieren der Ermittlung von Partnerverbund Partnern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a560-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a560-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2a560-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2a560-p101">Nachdem Sie Ihre Edgeserver bereitgestellt und den Partnerverbund für Ihre Organisation aktiviert haben, sollten Sie festlegen, ob die automatische Suche von Verbundpartnerdomänen unterstützt werden soll. Verwenden Sie das Verfahren in diesem Thema, um diese Konfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2a560-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a560-106">Im folgenden Verfahren wird vorausgesetzt, dass Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="2a560-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="2a560-107">Ausführliche Informationen zum Aktivieren des Verbund finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2a560-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="2a560-108">So aktivieren oder deaktivieren Sie die automatische Suche von Partnerdomänen für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="2a560-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="2a560-109">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="2a560-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2a560-110">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2a560-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2a560-111">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2a560-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2a560-112">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.</span><span class="sxs-lookup"><span data-stu-id="2a560-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="2a560-113">Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2a560-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2a560-114">Aktivieren oder deaktivieren Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** unter **Kommunikation mit Partnerbenutzern aktivieren** das Kontrollkästchen **Suche von Partnerdomänen aktivieren**, um die automatische Suche von Partnerdomänen zu aktivieren bzw. zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2a560-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="2a560-115">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="2a560-115">Click **Commit**.</span></span>

<span data-ttu-id="2a560-116">Damit Verbundbenutzer mit Benutzern in ihrer lync Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff für die Unterstützung des Zugriffs durch Verbundbenutzer konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="2a560-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="2a560-117">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen im-Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2a560-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="2a560-118">Ausführliche Informationen zum Steuern des Zugriffs auf bestimmte Verbunddomänen finden Sie unter [Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) und [Verwalten von XMPP-Verbundpartnern in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2a560-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2a560-119">Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2a560-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2a560-120">Die Ermittlung von Partnerverbund Partnern kann mit Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="2a560-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="2a560-121">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2a560-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2a560-122">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="2a560-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="2a560-123">So aktivieren Sie die Ermittlung von Verbundpartnern</span><span class="sxs-lookup"><span data-stu-id="2a560-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="2a560-p106">Legen Sie zur Aktivierung der Ermittlung von Verbundpartnern den Wert der Eigenschaft **EnablePartnerDiscovery** auf "True" ($True) fest. Beachten Sie, dass Sie DNS-SRV-Routing aktivieren müssen, um diesen Eigenschaftswert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2a560-p106">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True). Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="2a560-126">So deaktivieren Sie die Ermittlung von Verbundpartnern</span><span class="sxs-lookup"><span data-stu-id="2a560-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="2a560-127">Legen Sie zur Deaktivierung der Ermittlung von Verbundpartnern den Wert der Eigenschaft **EnablePartnerDiscovery** auf "False" ($False) fest:</span><span class="sxs-lookup"><span data-stu-id="2a560-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

