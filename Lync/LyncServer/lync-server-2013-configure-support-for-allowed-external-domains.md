---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für zulässige externe Domänen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfab1a41f39d975d2920bdf97ea601618277f35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="2f48a-102">Konfigurieren der Unterstützung für zulässige externe Domänen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f48a-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f48a-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2f48a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2f48a-104">Wenn Sie die Unterstützung für Federated-Partner konfiguriert haben, können Sie verwalten, welche bestimmten Domänen mit Ihrer Organisation verbunden werden können.</span><span class="sxs-lookup"><span data-stu-id="2f48a-104">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="2f48a-105">Sie konfigurieren eine oder mehrere bestimmte externe Domänen als zugelassene Verbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="2f48a-105">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="2f48a-106">Fügen Sie dazu jede Domäne zur Liste der zulässigen Domänen hinzu.</span><span class="sxs-lookup"><span data-stu-id="2f48a-106">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="2f48a-107">Auch wenn die Partner Ermittlung für Ihre Organisation aktiviert ist, gehen Sie wie folgt vor, wenn es sich bei der Domäne um einen Verbundpartner handelt, der möglicherweise mit mehr als 1.000 ihrer Benutzer kommunizieren muss, oder wenn Sie möglicherweise mehr als 20 Nachrichten pro Sekunde senden müssen.</span><span class="sxs-lookup"><span data-stu-id="2f48a-107">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="2f48a-108">Wenn die Partner Ermittlung für Ihre Organisation nicht aktiviert ist, können nur Benutzer externer Domänen, die Sie der Liste zugelassene Domänen hinzufügen, an Chats und Konferenzen mit Benutzern in Ihrer Organisation teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="2f48a-108">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="2f48a-109">Wenn Sie den Zugriff auf eine Verbunddomäne auf einen bestimmten Server einschränken möchten, auf dem der Access-Edgedienst des Verbundpartners ausgeführt wird, können Sie den Domänennamen des Servers angeben, auf dem der Access Edge-Dienst für jede Domäne in der Liste der zulässigen Domänen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2f48a-109">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f48a-110">In diesem Verfahren wird beschrieben, wie Sie die Unterstützung für bestimmte Domänen konfigurieren, aber die Implementierung der Unterstützung für verbundene Benutzer erfordert auch, dass Sie die Unterstützung für verbundene Benutzer für Ihre Organisation aktivieren und Richtlinien konfigurieren und anwenden, um zu steuern, welche Benutzer Zusammenarbeit mit Verbundbenutzern.</span><span class="sxs-lookup"><span data-stu-id="2f48a-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="2f48a-111">Details zum Aktivieren der Unterstützung für Verbundbenutzer finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2f48a-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="2f48a-112">Details zum Konfigurieren von Richtlinien für die Steuerung der Föderation finden Sie unter <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2f48a-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="2f48a-113">So fügen Sie eine externe Domäne zur Liste der zulässigen Domänen hinzu</span><span class="sxs-lookup"><span data-stu-id="2f48a-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="2f48a-114">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="2f48a-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2f48a-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2f48a-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2f48a-116">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2f48a-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2f48a-117">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Föderationsdomänen**.</span><span class="sxs-lookup"><span data-stu-id="2f48a-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="2f48a-118">Klicken Sie auf der Seite **Federated Domains** auf **neu**und dann auf **zugelassene Domäne**.</span><span class="sxs-lookup"><span data-stu-id="2f48a-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="2f48a-119">Führen Sie in **neuen Föderationsdomänen**die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="2f48a-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="2f48a-120">Geben Sie in **Domänenname (oder FQDN)** den Namen der Föderationspartner-Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="2f48a-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2f48a-121">Dieser Name muss eindeutig sein und kann nicht bereits als zulässige Domäne für diesen Server mit dem Access Edge-Dienst vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="2f48a-121">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="2f48a-122">Der Name darf nicht mehr als 256 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="2f48a-122">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="2f48a-123">Bei der Suche nach dem Domänennamen des Partner Partners wird eine Übereinstimmung mit dem Suffix ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2f48a-123">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="2f48a-124">Wenn Sie beispielsweise <STRONG>contoso.com</STRONG>eingeben, gibt die Suche auch die Domäne <STRONG>IT.contoso.com</STRONG>zurück.</span><span class="sxs-lookup"><span data-stu-id="2f48a-124">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="2f48a-125">Eine Föderationspartner-Domäne kann nicht gleichzeitig blockiert und zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="2f48a-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="2f48a-126">Lync Server 2013 verhindert, dass dies geschieht, damit Sie Ihre Listen nicht synchronisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="2f48a-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="2f48a-127">Wenn Sie den Zugriff auf Diese Verbunddomäne auf Benutzer eines bestimmten Servers einschränken möchten, auf dem der Access Edge-Dienst ausgeführt wird, geben Sie in **Access Edge Service (FQDN)** den FQDN des Servers der Verbunddomäne ein, auf dem der Access Edge-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2f48a-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="2f48a-128">Wenn Sie zusätzliche Informationen angeben möchten, geben Sie in **Kommentar**Informationen ein, die Sie für andere Systemadministratoren über diese Konfiguration freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="2f48a-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="2f48a-129">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2f48a-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="2f48a-130">Wiederholen Sie die Schritte 4 bis 6 für jede Federated-Partner-Domäne, die Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="2f48a-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="2f48a-131">Zum Aktivieren des Zugriffs auf den Verbundbenutzer müssen Sie auch die Unterstützung für den Verbundbenutzer Zugriff in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2f48a-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="2f48a-132">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2f48a-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="2f48a-133">Darüber hinaus müssen Sie die Richtlinie für Benutzer konfigurieren und anwenden, die in der Lage sein sollen, mit Verbundbenutzern zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2f48a-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="2f48a-134">Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2f48a-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

