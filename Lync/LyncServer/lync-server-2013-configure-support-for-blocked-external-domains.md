---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für blockierte externe Domänen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fe73985687e7a1d6fcd2bbf615127c0757a5307
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="8a283-102">Konfigurieren der Unterstützung für blockierte externe Domänen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a283-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a283-103">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8a283-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8a283-104">Wenn Sie die Unterstützung für Federated-Partner konfiguriert haben, können Sie verwalten, welche Domänen von der Föderation mit Ihrer Organisation blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="8a283-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="8a283-105">Die Liste der blockierten Domänen fungiert als Sperrliste (Auflistung expliziter Einträge, die nicht zulässig sind) und wird in der Föderationsdomänen Erkennung angewendet, wenn diese Option aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8a283-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="8a283-106">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern in lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span><span class="sxs-lookup"><span data-stu-id="8a283-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="8a283-107">Blockieren Sie eine oder mehrere externe Domänen, um eine Verbindung mit Ihrer Organisation herzustellen.</span><span class="sxs-lookup"><span data-stu-id="8a283-107">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="8a283-108">Fügen Sie dazu die Domäne zur Liste der blockierten Domänen hinzu.</span><span class="sxs-lookup"><span data-stu-id="8a283-108">To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="8a283-109">So fügen Sie eine externe Domäne zur Liste der blockierten Domänen hinzu</span><span class="sxs-lookup"><span data-stu-id="8a283-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="8a283-110">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="8a283-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8a283-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8a283-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8a283-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8a283-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8a283-113">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="8a283-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="8a283-114">Klicken Sie auf **Verbunddomänen**, dann auf **neu**und dann auf **Blockierte Domäne**.</span><span class="sxs-lookup"><span data-stu-id="8a283-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="8a283-115">Führen Sie in **neuen Föderationsdomänen**die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="8a283-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="8a283-116">Geben Sie in **Domänenname (oder FQDN)** den Namen der Partnerdomäne ein, die Sie blockieren möchten.</span><span class="sxs-lookup"><span data-stu-id="8a283-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8a283-117">Der Name darf nicht mehr als 256 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="8a283-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="8a283-118">Bei der Suche nach dem Domänennamen des Partner Partners wird eine Übereinstimmung mit dem Suffix ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8a283-118">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="8a283-119">Wenn Sie beispielsweise <STRONG>contoso.com</STRONG>eingeben, gibt die Suche auch die Domäne <STRONG>IT.contoso.com</STRONG>zurück.</span><span class="sxs-lookup"><span data-stu-id="8a283-119">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="8a283-120">Eine Föderationspartner-Domäne kann nicht gleichzeitig blockiert und zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="8a283-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="8a283-121">Lync Server 2013 verhindert, dass dies geschieht, damit Sie Ihre Listen nicht synchronisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="8a283-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="8a283-122">Optional Geben Sie in **Kommentar**Informationen ein, die Sie für andere Systemadministratoren über diese Konfiguration freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="8a283-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="8a283-123">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8a283-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="8a283-124">Wiederholen Sie die Schritte 4 bis 6 für jeden Föderationspartner, den Sie blockieren möchten.</span><span class="sxs-lookup"><span data-stu-id="8a283-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="8a283-125">Zum Aktivieren des Zugriffs auf den Verbundbenutzer müssen Sie auch die Unterstützung für den Verbundbenutzer Zugriff in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8a283-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="8a283-126">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8a283-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="8a283-127">Darüber hinaus müssen Sie die Richtlinie für Benutzer konfigurieren und anwenden, die in der Lage sein sollen, mit Verbundbenutzern zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8a283-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="8a283-128">Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8a283-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

