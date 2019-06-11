---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a8edd8d6736d181b59579db29cc1e7244b0a750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="0666d-102">Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0666d-102">Enable or disable remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0666d-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0666d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0666d-104">Bei Remote Benutzern handelt es sich um Benutzer in Ihrer Organisation, die eine persistente Active Directory-Identität innerhalb der Organisation aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0666d-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="0666d-105">Remote Benutzer können sich häufig über ein virtuelles privates Netzwerk (VPN) bei lync Server von außerhalb Ihres Netzwerks anmelden, wenn diese nicht mit dem Netzwerk Ihrer Organisation verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="0666d-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="0666d-106">Zu den Remotebenutzern gehören Mitarbeiter, die zu Hause oder unterwegs arbeiten, und andere Remotemitarbeiter, beispielsweise vertrauenswürdige Anbieter, denen Enterprise-Anmeldeinformationen gewährt wurden.</span><span class="sxs-lookup"><span data-stu-id="0666d-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="0666d-107">Wenn Sie den Remotebenutzerzugriff für Remotebenutzer aktivieren, werden die unterstützten Remotebenutzer über das Internet verbunden und müssen nicht über ein VPN eine Verbindung herstellen, um mit internen Benutzern mit lync Server zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0666d-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="0666d-108">Wenn Sie den Zugriff durch Remotebenutzer unterstützen möchten, müssen Sie den Zugriff durch Remotebenutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0666d-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="0666d-109">Wenn Sie den Remotebenutzerzugriff aktivieren, aktivieren Sie ihn für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="0666d-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="0666d-110">Wenn Sie später den Remotebenutzerzugriff vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0666d-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="0666d-111">Verwenden Sie das Verfahren in diesem Abschnitt, um den Remotebenutzerzugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0666d-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0666d-112">Das Aktivieren des Remotebenutzerzugriffs gibt nur an, dass Ihre Server, auf denen der Access Edge-Dienst ausgeführt wird, die Kommunikation mit Remotebenutzern unterstützen, aber Remotebenutzer nicht an Instant Messaging (im) oder Konferenzen in Ihrer Organisation teilnehmen können, bis Sie auch die Konfiguration unter mindestens eine Richtlinie zum Verwalten der Verwendung von Remotebenutzerzugriff.</span><span class="sxs-lookup"><span data-stu-id="0666d-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="0666d-113">Lync Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0666d-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="0666d-114">Die Priorität der lync Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss).</span><span class="sxs-lookup"><span data-stu-id="0666d-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="0666d-115">Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="0666d-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="0666d-116">Details zum Konfigurieren von Richtlinien für die Verwendung des Remotebenutzerzugriffs finden Sie unter <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0666d-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="0666d-117">So aktivieren oder deaktivieren Sie den Remotebenutzerzugriff für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="0666d-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="0666d-118">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="0666d-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0666d-119">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0666d-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0666d-120">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0666d-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0666d-121">Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **Zugriffs-Edgekonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="0666d-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="0666d-122">Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="0666d-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0666d-123">Führen Sie in " **Access-Edge-Konfiguration bearbeiten**" eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="0666d-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="0666d-124">Aktivieren Sie das Kontrollkästchen **Remotebenutzerzugriff aktivieren** , um den Remotebenutzerzugriff für Ihre Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0666d-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="0666d-125">Deaktivieren Sie das Kontrollkästchen **Remotebenutzerzugriff aktivieren** , um den Remotebenutzerzugriff für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0666d-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="0666d-126">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0666d-126">Click **Commit**.</span></span>

<span data-ttu-id="0666d-127">Damit Remotebenutzer sich bei ihren Servern mit lync Server anmelden können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Zugriff durch Remotebenutzer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0666d-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="0666d-128">Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0666d-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0666d-129">Aktivieren oder Deaktivieren des Remote Benutzerzugriffs mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0666d-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0666d-130">Der Remote Benutzer Zugriff kann mithilfe von Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="0666d-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="0666d-131">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0666d-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0666d-132">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="0666d-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="0666d-133">So aktivieren Sie den Remotebenutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="0666d-133">To enable remote user access</span></span>

  - <span data-ttu-id="0666d-134">Um den Remotebenutzerzugriff zu aktivieren, legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf true ($true) fest:</span><span class="sxs-lookup"><span data-stu-id="0666d-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="0666d-135">So deaktivieren Sie den Remotebenutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="0666d-135">To disable remote user access</span></span>

  - <span data-ttu-id="0666d-136">Um den Remotebenutzerzugriff zu deaktivieren, legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf false ($false) fest:</span><span class="sxs-lookup"><span data-stu-id="0666d-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

