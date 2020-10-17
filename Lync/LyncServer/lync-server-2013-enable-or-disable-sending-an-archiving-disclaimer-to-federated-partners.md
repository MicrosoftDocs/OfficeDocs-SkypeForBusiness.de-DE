---
title: Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner
description: Aktivieren oder Deaktivieren des Sendens eines Archivierungs Disclaimers an Verbundpartner.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1523a19bc2758e170c044a306398bef45ec33f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563511"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a><span data-ttu-id="4972f-103">Aktivieren oder Deaktivieren des Sendens von Archivierungs Haftungsausschlüssen an Verbundpartner in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4972f-103">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4972f-104">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4972f-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4972f-105">Zu dem Zeitpunkt, zu dem Sie die Edgeserver und den aktivierten Partnerverbund für Ihre Organisation bereitgestellt haben, sollten Sie angegeben haben, ob der Haftungsausschluss für die Archivierung automatisch an Verbundpartner gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4972f-105">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="4972f-106">Wenn Sie die externe Kommunikation archivieren, sollten Sie das Senden eines Haftungsausschlusses für die Archivierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4972f-106">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="4972f-107">Verwenden Sie das Verfahren in diesem Thema, um diese Konfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4972f-107">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4972f-108">Im folgenden Verfahren wird vorausgesetzt, dass Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="4972f-108">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="4972f-109">Ausführliche Informationen zum Aktivieren des Verbund finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4972f-109">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="4972f-110">So aktivieren oder deaktivieren Sie das Senden eines Archivierungs Disclaimers an Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="4972f-110">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="4972f-111">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4972f-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4972f-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4972f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4972f-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4972f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4972f-114">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.</span><span class="sxs-lookup"><span data-stu-id="4972f-114">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="4972f-115">Klicken Sie auf der Registerkarte **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4972f-115">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4972f-116">Aktivieren oder deaktivieren Sie im Abschnitt **Bearbeiten der Zugriffs-Edge-Konfiguration**unter **Kommunikation mit Verbundbenutzern aktivieren**das Kontrollkästchen **Archivierungs Haftungsausschluss an Verbundpartner senden** , um das automatische Senden des Haftungsausschlusses für die Archivierung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4972f-116">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="4972f-117">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4972f-117">Click **Commit**.</span></span>

<span data-ttu-id="4972f-118">Damit Verbundbenutzer mit Benutzern in ihrer lync Server 2013-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff für die Unterstützung des Zugriffs durch Verbundbenutzer konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="4972f-118">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="4972f-119">Ausführliche Informationen finden Sie unter [Manage XMPP Federated Partners in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4972f-119">For details, see [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="4972f-120">Ausführliche Informationen zum Steuern des Zugriffs auf bestimmte Verbunddomänen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4972f-120">For details about controlling access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4972f-121">Aktivieren oder Deaktivieren des Archivierungs Disclaimers mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="4972f-121">Enabling or Disabling the Archiving Disclaimer by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4972f-122">Die Verwendung des Disclaimers für die Archivierung kann mithilfe von Windows PowerShell und dem Set-CsAccessEdgeConfiguration-Cmdlet verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4972f-122">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="4972f-123">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4972f-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4972f-124">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="4972f-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="4972f-125">So aktivieren Sie den Haftungsausschluss für Archivierung</span><span class="sxs-lookup"><span data-stu-id="4972f-125">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="4972f-126">Um den Haftungsausschluss für die Archivierung zu aktivieren, legen Sie den Wert der **EnableArchivingDisclaimer** -Eigenschaft auf true ($true) fest:</span><span class="sxs-lookup"><span data-stu-id="4972f-126">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="4972f-127">So deaktivieren Sie den Haftungsausschluss für Archivierung</span><span class="sxs-lookup"><span data-stu-id="4972f-127">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="4972f-128">Wenn Sie den Haftungsausschluss für die Archivierung deaktivieren möchten, legen Sie den Wert der **EnableArchivingDisclaimer** -Eigenschaft auf false ($false) fest:</span><span class="sxs-lookup"><span data-stu-id="4972f-128">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

