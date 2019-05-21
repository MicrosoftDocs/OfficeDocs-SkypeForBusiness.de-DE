---
title: Bereitstellen und Konfigurieren von Mobility für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: In diesem Artikel werden die Schritte beschrieben, wie Sie eine vorhandene Skype for Business Server-Installation für die Nutzung des mobilitätsdiensts konfigurieren können, damit Ihre mobilen Geräte die Mobilitätsfunktionen von Skype for Business Server nutzen können.
ms.openlocfilehash: 35b9ca6a69dc5add9331aa5399a59a572bdf6906
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303554"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="eec27-103">Bereitstellen und Konfigurieren von Mobility für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eec27-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="eec27-104">In diesem Artikel werden die Schritte beschrieben, wie Sie eine vorhandene Skype for Business Server-Installation für die Nutzung des mobilitätsdiensts konfigurieren können, damit Ihre mobilen Geräte die Mobilitätsfunktionen von Skype for Business Server nutzen können.</span><span class="sxs-lookup"><span data-stu-id="eec27-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="eec27-105">Nachdem Sie den Artikel [Plan für Mobilität für Skype for Business Server](../plan-your-deployment/mobility.md) überprüft haben, sollten Sie mit den folgenden Schritten fortfahren, um die Mobilität in Ihrer Skype for Business Server-Umgebung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="eec27-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="eec27-106">Es handelt sich um folgende Schritte (in dieser Tabelle ist eine Liste der Berechtigungen enthalten):</span><span class="sxs-lookup"><span data-stu-id="eec27-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="eec27-107">**Phase**</span><span class="sxs-lookup"><span data-stu-id="eec27-107">**Phase**</span></span>|<span data-ttu-id="eec27-108">**Berechtigungen**</span><span class="sxs-lookup"><span data-stu-id="eec27-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="eec27-109">Erstellen von DNS-Einträgen</span><span class="sxs-lookup"><span data-stu-id="eec27-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="eec27-110">Domänen-Admins</span><span class="sxs-lookup"><span data-stu-id="eec27-110">Domain Admins</span></span>  <br/> <span data-ttu-id="eec27-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="eec27-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="eec27-112">Ändern von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="eec27-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="eec27-113">Lokaler Administrator</span><span class="sxs-lookup"><span data-stu-id="eec27-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="eec27-114">Konfigurieren des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="eec27-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="eec27-115">Lokaler Administrator</span><span class="sxs-lookup"><span data-stu-id="eec27-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="eec27-116">Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="eec27-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="eec27-117">Domänen-Admins</span><span class="sxs-lookup"><span data-stu-id="eec27-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="eec27-118">Testen der Mobilitätsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="eec27-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="eec27-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eec27-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="eec27-120">Konfigurieren von Pushbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="eec27-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="eec27-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eec27-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="eec27-122">Konfigurieren der Mobilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="eec27-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="eec27-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eec27-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="eec27-p102">Alle folgenden Abschnitte enthalten Schritte, bei denen davon ausgegangen wird, dass Sie das Planungsthema gelesen haben. Wenn Ihnen etwas unklar ist, können Sie dort nachlesen.</span><span class="sxs-lookup"><span data-stu-id="eec27-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="eec27-126">MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eec27-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="eec27-127">Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten.</span><span class="sxs-lookup"><span data-stu-id="eec27-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="eec27-128">Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.</span><span class="sxs-lookup"><span data-stu-id="eec27-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="eec27-129">Erstellen von DNS-Einträgen</span><span class="sxs-lookup"><span data-stu-id="eec27-129">Create DNS records</span></span>
<span data-ttu-id="eec27-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="eec27-130"></span></span>

<span data-ttu-id="eec27-131">Möglicherweise haben Sie diese bereits im Rahmen ihrer Skype for Business Server-Umgebung, aber Sie müssen die folgenden Einträge erstellen, damit AutoDiscovery funktioniert:</span><span class="sxs-lookup"><span data-stu-id="eec27-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="eec27-132">Einen internen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Netzwerk Ihrer Organisation herstellen.</span><span class="sxs-lookup"><span data-stu-id="eec27-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="eec27-133">Einen externen (bzw. öffentlichen) DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung von außerhalb des Netzwerks Ihrer Organisation herstellen.</span><span class="sxs-lookup"><span data-stu-id="eec27-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="eec27-134">Diese Einträge können entweder A(Host)-Namen oder CNAME-Einträge sein (es sind nicht beide erforderlich; hier werden lediglich die Schritte für alle Optionen erläutert).</span><span class="sxs-lookup"><span data-stu-id="eec27-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="eec27-135">Erstellen eines internen DNS-CNAME-Eintrags</span><span class="sxs-lookup"><span data-stu-id="eec27-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="eec27-136">Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **Domänen-Admins** oder der Gruppe **DnsAdmins** ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="eec27-137">Klicken Sie auf **Start**, wählen Sie **Verwaltungstools** (möglicherweise müssen Sie **suchen**, da es sich nicht um eine Startmenüoption handelt), und klicken Sie dann auf **DNS**, um das DNS-Verwaltungs-Snap-In zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="eec27-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="eec27-138">Im linken Bereich des Konsolenfensters müssen Sie zu der Domäne wechseln, die zu den Front-End-Servern Ihres Skype for Business-Servers gehört, und die **Forward-Lookupzonen** dort erweitern.</span><span class="sxs-lookup"><span data-stu-id="eec27-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="eec27-139">Prüfen Sie, welche der folgenden Einträge Sie haben:</span><span class="sxs-lookup"><span data-stu-id="eec27-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="eec27-140">Alle Host A-oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools (s).</span><span class="sxs-lookup"><span data-stu-id="eec27-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="eec27-141">Alle Host a-oder AAAA-Einträge für einen Director-oder Director-Pool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).</span><span class="sxs-lookup"><span data-stu-id="eec27-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="eec27-142">Nachdem Sie dies festgestellt haben, klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen und wählen Sie im Menü **Neuer Alias (CNAME)** aus.</span><span class="sxs-lookup"><span data-stu-id="eec27-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="eec27-143">Geben Sie im Textfeld **Aliasname** als Hostnamen für die URL des internen AutoErmittlungsdiensts „lyncdiscoverinternal“ ein.</span><span class="sxs-lookup"><span data-stu-id="eec27-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="eec27-144">Im **vollqualifizierten Domänennamen (FQDN für Ziel Host**) müssen Sie den internen Webdienst-FQDN für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Director-Pool oder Director) eingeben oder durchsuchen, der in Schritt 4 oben identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="eec27-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="eec27-145">Klicken Sie auf OK, wenn diese eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="eec27-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="eec27-146">Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Nachschlage Zone für jede SIP-Domäne erstellen, die in Ihrer Skype for Business Server-Umgebung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="eec27-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="eec27-147">Erstellen eines externen DNS-CNAME-Eintrags</span><span class="sxs-lookup"><span data-stu-id="eec27-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="eec27-148">Diese Schritte sind allgemein gehalten, da wir nicht wissen, welchen öffentlichen DNS-Anbieter Sie verwenden, Ihnen aber dennoch Hilfestellung leisten möchten. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, über das neue DNS-Einträge vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="eec27-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="eec27-149">Zu diesem Zeitpunkt sollte bereits eine SIP-Domäne für Skype for Business Server vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="eec27-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="eec27-150">Erweitern Sie die **Forward-Nachschlage Zone** für diese SIP-Domäne, oder öffnen Sie Sie auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="eec27-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="eec27-151">Prüfen Sie, welche der folgenden Einträge Sie haben:</span><span class="sxs-lookup"><span data-stu-id="eec27-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="eec27-152">Alle Host A-oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools (s).</span><span class="sxs-lookup"><span data-stu-id="eec27-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="eec27-153">Alle Host a-oder AAAA-Einträge für einen Director-oder Director-Pool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).</span><span class="sxs-lookup"><span data-stu-id="eec27-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="eec27-154">Nachdem Sie diese Information haben, können Sie eine Option für die Erstellung von **Neuer Alias (CNAME)** auswählen.</span><span class="sxs-lookup"><span data-stu-id="eec27-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="eec27-155">Jetzt können Sie einen **Aliasnamen** eingeben. Geben Sie hier „lyndiscover“ für die externe AutoErmittlungsdienst-URL ein.</span><span class="sxs-lookup"><span data-stu-id="eec27-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="eec27-156">Als nächstes sollte ein Bereich vorhanden sein, der in einen **FQDN für den Ziel-Host**eingegeben werden muss, wobei es sich um den FQDN für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Director-Pool oder Director) handeln muss, der in Schritt 3 oben identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="eec27-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="eec27-157">Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche CNAME-Einträge in der Forward-Lookupzone jeder SIP-Domäne in Ihrer Skype for Business Server-Umgebung erstellen müssen, sollten Sie dies tun, aber wenn Sie fertig sind, speichern Sie Ihre Arbeit.</span><span class="sxs-lookup"><span data-stu-id="eec27-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="eec27-158">Erstellen eines internen DNS-A-Eintrags</span><span class="sxs-lookup"><span data-stu-id="eec27-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="eec27-159">Melden Sie sich bei einem DNS-Server in Ihrem Netzwerk an, der entweder Mitglied der Gruppe **Domänen-Admins** oder der Gruppe **DnsAdmins** ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="eec27-160">Klicken Sie auf **Start**, wählen Sie **Verwaltungstools** (möglicherweise müssen Sie **suchen**, da es sich nicht um eine Startmenüoption handelt), und klicken Sie dann auf **DNS**, um das DNS-Verwaltungs-Snap-In zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="eec27-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="eec27-161">Im linken Bereich des Konsolenfensters müssen Sie zu der Domäne wechseln, die zu den Front-End-Servern Ihres Skype for Business-Servers gehört, und die **Forward-Lookupzonen** dort erweitern.</span><span class="sxs-lookup"><span data-stu-id="eec27-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="eec27-162">Prüfen Sie, welche der folgenden Einträge Sie haben:</span><span class="sxs-lookup"><span data-stu-id="eec27-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="eec27-163">Alle Host A-oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools (s).</span><span class="sxs-lookup"><span data-stu-id="eec27-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="eec27-164">Alle Host a-oder AAAA-Einträge für einen Director-oder Director-Pool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).</span><span class="sxs-lookup"><span data-stu-id="eec27-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="eec27-165">Nachdem Sie dies festgestellt haben, klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen und wählen Sie im Menü **Neuer Host (A oder AAAA)** aus.</span><span class="sxs-lookup"><span data-stu-id="eec27-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="eec27-166">Geben Sie im Textfeld **Name** als Hostnamen für die URL des internen AutoErmittlungsdiensts „lyncdiscoverinternal“ ein.</span><span class="sxs-lookup"><span data-stu-id="eec27-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="eec27-167">Geben Sie im Textfeld **IP-Adresse** die interne IP-Adresse des Webdiensts für Ihren Front-End-Pool (oder einen einzelnen Front-End-Server oder Director-Pool oder Director) ein, der in Schritt 4 oben identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="eec27-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="eec27-168">Klicken Sie danach auf **Host hinzufügen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="eec27-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="eec27-169">Sie müssen eine neue Auto Ermittlungs-a-oder AAAA-Einträge in der Forward-Lookupzone für jede SIP-Domäne erstellen, die in Ihrer Skype for Business Server-Umgebung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="eec27-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="eec27-170">Wiederholen Sie hierfür die Schritte 6-8 so oft wie erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eec27-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="eec27-171">Wenn Sie fertig sind, klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="eec27-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="eec27-172">Erstellen eines externen DNS-A-Eintrags</span><span class="sxs-lookup"><span data-stu-id="eec27-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="eec27-173">Diese Schritte sind allgemein gehalten, da wir nicht wissen, welchen öffentlichen DNS-Anbieter Sie verwenden, Ihnen aber dennoch Hilfestellung leisten möchten. Melden Sie sich bei Ihrem öffentlichen DNS-Anbieter mit einem Konto an, über das neue DNS-Einträge vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="eec27-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="eec27-174">Zu diesem Zeitpunkt sollte bereits eine SIP-Domäne für Skype for Business Server vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="eec27-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="eec27-175">Erweitern Sie die **Forward-Nachschlage Zone** für diese SIP-Domäne, oder öffnen Sie Sie auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="eec27-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="eec27-176">Prüfen Sie, welche der folgenden Einträge Sie haben:</span><span class="sxs-lookup"><span data-stu-id="eec27-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="eec27-177">Alle Host A-oder AAAA-Einträge für Ihren Front-End-Server (Standard oder Enterprise) oder Front-End-Pools (s).</span><span class="sxs-lookup"><span data-stu-id="eec27-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="eec27-178">Alle Host a-oder AAAA-Einträge für einen Director-oder Director-Pool (eine optionale Konfiguration, die Sie möglicherweise in Ihrer Bereitstellung haben).</span><span class="sxs-lookup"><span data-stu-id="eec27-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="eec27-179">Nachdem Sie diese Information haben, können Sie eine Option für die Erstellung von **Neuer Host (A oder AAAA)** auswählen.</span><span class="sxs-lookup"><span data-stu-id="eec27-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="eec27-180">Jetzt können Sie einen **Namen** eingeben. Geben Sie hier „lyndiscover“ für die externe AutoErmittlungsdienst-URL ein.</span><span class="sxs-lookup"><span data-stu-id="eec27-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="eec27-181">Als nächstes sollte ein Bereich vorhanden sein, der in eine **IP-Adresse**eingegeben werden muss, wobei es sich um die IP-Adresse Ihres Front-End-Pools (oder eines einzelnen Front-End-Servers oder Director-Pools oder Directors) handeln muss, der in Schritt 3 oben identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="eec27-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="eec27-182">Möglicherweise müssen Sie hier speichern, oder wenn Sie zusätzliche A-oder AAAA-Einträge in der Forward-Lookupzone jeder SIP-Domäne für Ihre Skype for Business Server-Umgebung erstellen müssen, sollten Sie dies tun, aber wenn Sie fertig sind, speichern Sie Ihre Arbeit.</span><span class="sxs-lookup"><span data-stu-id="eec27-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="eec27-183">Ändern von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="eec27-183">Modify certificates</span></span>
<span data-ttu-id="eec27-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="eec27-184"></span></span>

<span data-ttu-id="eec27-185">Wenn Sie Fragen zur Planung rund um Zertifikate haben, haben wir dies im Artikel [Planen der Mobilität für Skype for Business Server](../plan-your-deployment/mobility.md) dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="eec27-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="eec27-186">Nachdem Sie diese gelesen haben, werden Sie durch folgende Schritte geführt:</span><span class="sxs-lookup"><span data-stu-id="eec27-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="eec27-187">Benötige ich neue Zertifikate?</span><span class="sxs-lookup"><span data-stu-id="eec27-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="eec27-188">Anfordern neuer Zertifikate von der Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="eec27-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="eec27-189">Aktualisieren der vorhandenen Zertifikate mit den Ersatzzertifikaten mithilfe der PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eec27-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="eec27-190">Überprüfen der Zertifikate mithilfe des Zertifikat-Snap-Ins in der Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="eec27-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="eec27-191">Benötige ich neue Zertifikate?</span><span class="sxs-lookup"><span data-stu-id="eec27-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="eec27-192">Zunächst müssen Sie möglicherweise überprüfen, welche Zertifikate direkt vorhanden sind und ob Sie über die erforderlichen Einträge verfügen.</span><span class="sxs-lookup"><span data-stu-id="eec27-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="eec27-193">Dazu müssen Sie sich bei Ihrem Skype for Business-Server mit einem Konto anmelden, das ein lokaler Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="eec27-194">Dieses Konto muss möglicherweise auch über Rechte an der ausstellenden Zertifizierungsstelle (Certification Authority, ca) verfügen, für einige dieser Schritte.</span><span class="sxs-lookup"><span data-stu-id="eec27-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="eec27-195">Öffnen Sie die Skype for Business Server-Verwaltungsshell (Sie können die Suche verwenden, um Sie zu finden, wenn Sie Sie nicht an das Startmenü oder die Taskleiste angeheftet haben).</span><span class="sxs-lookup"><span data-stu-id="eec27-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="eec27-p110">Sie müssen unbedingt wissen, welche Zertifikate Ihnen zugewiesen sind, bevor Sie versuchen, ein aktualisiertes Zertifikat hinzuzufügen. Geben Sie daher an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="eec27-p110">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="eec27-p111">Die Informationen aus Schritt 3 sind für Sie eindeutig. Sie können Sie durchgehen, um festzustellen, ob Ihnen ein einzelnes Zertifikat für verschiedene Zwecke zugewiesen wurde, oder ob Sie über mehrere Zertifikate für die einzelnen Komponenten, die sie benötigen, verfügen. Über den Parameter **Verwendung** erfahren Sie, wie ein Zertifikat verwendet wird, und der Parameter **Fingerabdruck** gibt an, ob es sich um das gleiche Zertifikat oder mehrere Zertifikate handelt.</span><span class="sxs-lookup"><span data-stu-id="eec27-p111">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="eec27-p112">Wenn Sie über die in unserem Planungsabschnitt empfohlenen SAN-Einträge verfügen, ist alles in Ordnung. Falls nicht, müssen Sie ein neues Zertifikat bzw. mehrere Zertifikate (abhängig von Ihrer Konfiguration) bei der Zertifizierungsstelle beantragen.</span><span class="sxs-lookup"><span data-stu-id="eec27-p112">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="eec27-203">Anfordern eines neuen Zertifikats oder mehrerer Zertifikate von der Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="eec27-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="eec27-204">Nachdem Sie geprüft haben, über welche SAN-Einträge Sie verfügen, wissen Sie, dass Sie ein **einzelnes Zertifikat** haben (nachdem Sie dies anhand der obigen Schritte geprüft haben), und dass Sie nicht über alle benötigten Einträge verfügen.</span><span class="sxs-lookup"><span data-stu-id="eec27-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="eec27-205">Sie müssen bei Ihrer Zertifizierungsstelle ein neues Zertifikat beantragen.</span><span class="sxs-lookup"><span data-stu-id="eec27-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="eec27-206">Öffnen Sie Ihre Skype for Business Server-PowerShell:</span><span class="sxs-lookup"><span data-stu-id="eec27-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="eec27-207">Für einen fehlenden AutoErmittlungsdienst-SAN (ersetzen Sie den Parameter -Ca durch den Pfad Ihrer Zertifizierungsstelle):</span><span class="sxs-lookup"><span data-stu-id="eec27-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="eec27-208">Wenn Sie nun über mehrere SIP-Domänen verfügen, können Sie den AllSipDomain-Parameter wie im obigen Beispiel nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="eec27-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="eec27-209">Sie müssen stattdessen den Parameter „DomainName“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="eec27-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="eec27-210">Und wenn Sie den Parameter „DomainName“ verwenden, müssen Sie den vollqualifizierten Domänennamen für die Einträge „lyncdiscoverinternal“ und „lyncdiscover“ definieren.</span><span class="sxs-lookup"><span data-stu-id="eec27-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="eec27-211">Ein Beispiel wäre Folgendes (ersetzen Sie den Parameter -Ca mit dem Pfad Ihrer Zertifizierungsstelle):</span><span class="sxs-lookup"><span data-stu-id="eec27-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="eec27-212">Nachdem Sie geprüft haben, über welche SAN-Einträge Sie verfügen, wissen Sie, dass Sie **mehrere Zertifikate** haben und dass Sie nicht über alle benötigten Einträge verfügen.</span><span class="sxs-lookup"><span data-stu-id="eec27-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="eec27-213">Sie müssen bei Ihrer Zertifizierungsstelle ein neues Zertifikat beantragen.</span><span class="sxs-lookup"><span data-stu-id="eec27-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="eec27-214">Öffnen Sie Ihre Skype for Business Server-PowerShell:</span><span class="sxs-lookup"><span data-stu-id="eec27-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="eec27-215">Für einen fehlenden AutoErmittlungsdienst-SAN (ersetzen Sie den Parameter -Ca durch den Pfad Ihrer Zertifizierungsstelle):</span><span class="sxs-lookup"><span data-stu-id="eec27-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="eec27-216">Wenn Sie nun über mehrere SIP-Domänen verfügen, können Sie den AllSipDomain-Parameter wie im obigen Beispiel nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="eec27-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="eec27-217">Sie müssen stattdessen den Parameter „DomainName“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="eec27-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="eec27-218">Und wenn Sie den Parameter „DomainName“ verwenden, müssen Sie den vollqualifizierten Domänennamen für die Einträge „lyncdiscoverinternal“ und „lyncdiscover“ definieren.</span><span class="sxs-lookup"><span data-stu-id="eec27-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="eec27-219">Ein Beispiel wäre Folgendes (ersetzen Sie den Parameter -Ca mit dem Pfad Ihrer Zertifizierungsstelle):</span><span class="sxs-lookup"><span data-stu-id="eec27-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="eec27-220">Nachdem die neuen Zertifikate von der Zertifizierungsstelle generiert wurden, müssen Sie sie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eec27-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="eec27-221">Zuweisen von Zertifikaten mit der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="eec27-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="eec27-222">Abhängig von den Ergebnissen im Abschnitt „Benötige ich neue Zertifikate“ oben müssen Sie **einen** der folgenden Befehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="eec27-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="eec27-223">Wenn Sie ein einzelnes Zertifikat für alles haben (die Fingerabdrücke sind identisch), müssen Sie folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="eec27-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="eec27-224">Wenn Sie verschiedene Zertifikate haben (die Fingerabdrücke sind unterschiedlich), führen Sie stattdessen folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="eec27-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="eec27-225">Anzeigen von Zertifikaten in der Microsoft Management Console (MMC)</span><span class="sxs-lookup"><span data-stu-id="eec27-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="eec27-p117">Es gibt eine Option zum Anzeigen Ihrer Zertifikate mit dem Zertifikat-Snap-In für die MMC. Geben Sie einfach „MMC“ in das Suchfeld ein, und die Anwendungsoption wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eec27-p117">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="eec27-p118">Um das Zertifikat-Snap-In hinzuzufügen, klicken Sie auf **Datei** und dann auf **Snap-In hinzufügen/entfernen...** (auch das Tastaturkürzel **Strg+M** kann verwendet werden). **Zertifikate** ist eine Option im linken Fensterbereich. Wählen Sie sie aus, und wählen Sie dann **Computerkonto** im Popup-Fenster. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="eec27-p118">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="eec27-230">Wenn Sie sich im Popupfenster befinden, ist es wahrscheinlich, dass Sie dies auf dem Computer machen, auf dem sich die Zertifikate befinden, die Sie sich ansehen müssen, daher sollten Sie die Auswahl auf dem **lokalen Computer** beibehalten, wenn das so ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="eec27-231">Wenn Sie an einem Remotecomputer arbeiten, ändern Sie das Optionsfeld auf **einen anderen Computer** , und geben Sie dann entweder den FQDN des Computers ein, oder verwenden Sie die Schaltfläche **Durchsuchen** , um nach diesem Computer über AD zu suchen.</span><span class="sxs-lookup"><span data-stu-id="eec27-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="eec27-232">Nachdem Sie den Computer ausgewählt haben, müssen Sie auf Fertig **stellen** und dann auf **OK** klicken, um das Snap-in zur MMC hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="eec27-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="eec27-233">Erweitern Sie den Abschnitt **Zertifikate** im linken Bereich der MMC.</span><span class="sxs-lookup"><span data-stu-id="eec27-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="eec27-234">Erweitern Sie auch den **persönlichen Ordner**, und wählen Sie dann **Zertifikate** aus.</span><span class="sxs-lookup"><span data-stu-id="eec27-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="eec27-235">Damit können Sie die Zertifikate in diesem Speicher anzeigen.</span><span class="sxs-lookup"><span data-stu-id="eec27-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="eec27-236">Sie müssen die anzuzeigenden Zertifikate suchen, mit der rechten Maustaste darauf klicken und die Option **Öffnen** wählen.</span><span class="sxs-lookup"><span data-stu-id="eec27-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eec27-237">Woher wissen Sie, welches Zertifikat das ist?</span><span class="sxs-lookup"><span data-stu-id="eec27-237">How do you know what certificate this is?</span></span> <span data-ttu-id="eec27-238">Es sollte entweder das einzelne Zertifikat sein, das allen für Ihre Farm zugewiesen ist, oder Sie haben möglicherweise mehrere Zertifikate für verschiedene Dinge, wie standardmäßige, interne Webdienste usw., in diesem Fall müssen Sie möglicherweise mehrere Zertifikate betrachten.</span><span class="sxs-lookup"><span data-stu-id="eec27-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="eec27-239">Mehrere Zertifikate haben denselben Fingerabdruck.</span><span class="sxs-lookup"><span data-stu-id="eec27-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="eec27-p122">Nachdem Sie die **Zertifikat**-Ansicht geöffnet haben, wählen Sie **Details**. Dort sehen Sie den Zertifikatantragstellernamen, wenn Sie **Antragsteller** auswählen, und der zugewiesene Antragstellername und die zugeordneten Eigenschaften werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eec27-p122">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="eec27-p123">Sie müssen auch die Einträge für den **alternativen Antragstellernamen** prüfen. Dort finden Sie einen oder mehrere der folgenden Einträge:</span><span class="sxs-lookup"><span data-stu-id="eec27-p123">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="eec27-244">Der Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt.</span><span class="sxs-lookup"><span data-stu-id="eec27-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="eec27-245">Den Namen des Servers, dem das Zertifikat zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="eec27-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="eec27-246">Einfache URL-Einträge, üblicherweise „meet“ und „dialin“.</span><span class="sxs-lookup"><span data-stu-id="eec27-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="eec27-247">Webdienste interne und Webdienste externe Namen (beispielsweise webpool01.contoso.net, webpool01.contoso.com), basierend auf den Optionen, die im Topologie-Generator und über berittenen Webdiensten ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="eec27-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="eec27-248">Wenn Sie bereits zugewiesen ist, wird die lyncdiscover. \<sipdomain\> und lyncdiscoverinternal. \<sipdomain\> -Datensätze.</span><span class="sxs-lookup"><span data-stu-id="eec27-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="eec27-249">Wenn mehr als ein Zertifikat zugewiesen ist, müssen Sie mehrere Zertifikate prüfen (siehe Hinweis oben).</span><span class="sxs-lookup"><span data-stu-id="eec27-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="eec27-250">Wenn Sie also lyncdiscover finden. \<sipdomain\> und lyncdiscoverinternal. \<sipdomain\> Records, Sie haben diese bereits konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="eec27-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="eec27-251">Sie können die MMC schließen.</span><span class="sxs-lookup"><span data-stu-id="eec27-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="eec27-252">Wenn sie nicht zugewiesen sind, müssen Sie entweder ein neues Zertifikat beantragen stellen (wie oben beschrieben) oder die Zertifikate nach dem Antrag installieren (es wird empfohlen, hierfür wie oben beschrieben PowerShell zu verwenden).</span><span class="sxs-lookup"><span data-stu-id="eec27-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="eec27-253">Konfigurieren des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="eec27-253">Configure the reverse proxy</span></span>
<span data-ttu-id="eec27-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="eec27-254"></span></span>

<span data-ttu-id="eec27-p125">Die folgenden Schritte sind nicht zur exakten Befolgung gedacht. In früheren Produktversionen wurden Sie beispielsweise durch die Konfiguration von Threat Management Gateway (TMG) geführt, und wenn Sie dies nicht verwendeten, mussten Sie von dieser Stelle an Ihre eigene Version erarbeiten.</span><span class="sxs-lookup"><span data-stu-id="eec27-p125">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="eec27-257">TMG wird von Microsoft nicht mehr als Produkt angeboten, und wenn Sie es noch konfigurieren müssen, können Sie sich die 2013-Schritte für [lync Server](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)anschauen.</span><span class="sxs-lookup"><span data-stu-id="eec27-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="eec27-258">Die folgenden Informationen sollten jedoch generell hilfreich sein, auch wenn es keine Möglichkeit gibt, spezielle Exemplarische Vorgehensweisen für jeden Reverse-Proxy bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="eec27-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="eec27-259">Es sind zwei Hauptpunkte zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="eec27-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="eec27-260">Möchten Sie die anfängliche AutoErmittlung-Anforderung über HTTPS stellen (empfohlen)?</span><span class="sxs-lookup"><span data-stu-id="eec27-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="eec27-261">Wenn Sie über eine Webveröffentlichungsregel verfügen, müssen Sie diese ändern.</span><span class="sxs-lookup"><span data-stu-id="eec27-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="eec27-262">Wenn Sie noch nicht über eine Webveröffentlichungsregel verfügen, müssen Sie eine erstellen.</span><span class="sxs-lookup"><span data-stu-id="eec27-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="eec27-263">Wenn Sie die anfängliche AutoErmittlung-Anforderung über HTTP stellen, müssen Sie diese Regel ebenfalls erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="eec27-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="eec27-264">**Wichtig** Ein Proxy-Timeoutwert ist eine Zahl, die von der Bereitstellung bis zur Bereitstellung variieren kann.</span><span class="sxs-lookup"><span data-stu-id="eec27-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="eec27-265">Überwachen Sie Ihre Bereitstellung, und ändern Sie den Wert für die optimale Benutzerfreundlichkeit für Clients.</span><span class="sxs-lookup"><span data-stu-id="eec27-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="eec27-266">Möglicherweise können Sie den Wert so einstellen, dass er so gering wie 200 ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="eec27-267">Wenn Sie lync Mobile-Clients in Ihrer Umgebung unterstützen, sollten Sie den Wert auf 960 setzen, um Timeouts für Push-Benachrichtigungen von Office 365 zu ermöglichen, die einen Timeoutwert von 900 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="eec27-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="eec27-268">Es ist sehr wahrscheinlich, dass Sie den Timeoutwert erhöhen müssen, um zu verhindern, dass der Client die Verbindung trennt, wenn der Wert zu klein ist, oder die Zahl verkleinern, wenn Verbindungen über den Proxy nicht getrennt, aber lange nach dem Trennen des Clients gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="eec27-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="eec27-269">Das überwachen und Baselining, was für Ihre Umgebung üblich ist, ist die einzige genaue Möglichkeit, die entsprechende Einstellung für diesen Wert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="eec27-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="eec27-270">Bearbeiten einer bestehenden Webveröffentlichungsregel für den externen AutoErmittlungsdienst-SAN und die -URL</span><span class="sxs-lookup"><span data-stu-id="eec27-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="eec27-271">Öffnen Sie die Reverse-Proxy-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="eec27-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="eec27-272">Sie müssen die Webveröffentlichungsregel lokalisieren und die Option "Bearbeiten" auswählen (abhängig von der Konfiguration Ihres Reverse-Proxys).</span><span class="sxs-lookup"><span data-stu-id="eec27-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="eec27-273">Es sollte ein Bereich vorhanden sein, in dem angegeben ist, auf was diese Webveröffentlichungsregel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="eec27-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="eec27-274">Sie müssen diese Regel für eingehende Websites oder Anforderungen für Websites ändern.</span><span class="sxs-lookup"><span data-stu-id="eec27-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="eec27-275">Dafür müssen Sie einen neuen Eintrag **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="eec27-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="eec27-276">Geben Sie den Namen der Auto Ermittlungs Website ein (das Beispiel, das wir verwenden werden, ist lyncdiscover.contoso.com), und klicken Sie je nach Format Ihres Reverse-Proxys auf **OK** oder **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eec27-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="eec27-277">Möglicherweise verfügen Sie über ein neues Zertifikat mit dem SAN-Eintrag für AutoErmittlung.</span><span class="sxs-lookup"><span data-stu-id="eec27-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="eec27-278">Dieser muss ebenfalls installiert und für die Verwendung entsprechend den Einstellungen Ihres Reverse-Proxys konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="eec27-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="eec27-279">Vergessen Sie nicht, alles zu speichern, wenn die Konfiguration abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="eec27-280">Wenn Ihr Reverse-Proxy über eine **Test** Funktionalität verfügt, nutzen Sie ihn, um sicherzustellen, dass alles ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="eec27-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="eec27-281">Möglicherweise müssen Sie diese Schritte nun wiederholen, wenn Sie einen Director-oder Director-Pool in Ihrer Umgebung haben (Dies würde bedeuten, dass Sie eine zweite Regel haben).</span><span class="sxs-lookup"><span data-stu-id="eec27-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="eec27-282">Erstellen einer Webveröffentlichungsregel für die externe Auto Ermittlungs-URL</span><span class="sxs-lookup"><span data-stu-id="eec27-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="eec27-283">Öffnen Sie die Reverse-Proxy-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="eec27-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="eec27-284">Sie müssen ermitteln, wo Sie in der Benutzeroberfläche ihre Webveröffentlichungsregeln erstellen, und die Option **neu** oder **Erstellen** auswählen (je nach Konfiguration des Reverse-Proxys kann es sich um ein Menü oder eine Registerkarte handeln).</span><span class="sxs-lookup"><span data-stu-id="eec27-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="eec27-285">Suchen Sie nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.</span><span class="sxs-lookup"><span data-stu-id="eec27-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="eec27-286">In der Regel müssen Sie folgende Informationen eingeben:</span><span class="sxs-lookup"><span data-stu-id="eec27-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="eec27-287">**Name**: der Name Ihrer Regel</span><span class="sxs-lookup"><span data-stu-id="eec27-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="eec27-288">**Regelaktion**: in diesem Fall handelt es sich um eine **Zulassungs** Regel, bei der Sie etwas über Ihren Reverse-Proxy durchlaufen lassen.</span><span class="sxs-lookup"><span data-stu-id="eec27-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="eec27-289">Die Regel oder Option für die **Veröffentlichung**, die Sie auswählen, ist **einzelne Website oder Lastenausgleich**.</span><span class="sxs-lookup"><span data-stu-id="eec27-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="eec27-290">Für externen Zugriff muss es sich um **SSL** handeln; wählen Sie diese Option.</span><span class="sxs-lookup"><span data-stu-id="eec27-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="eec27-291">Sie müssen einen Pfad für die **interne Veröffentlichung**veröffentlichen und den FQDN für die externen Webdienste im Load Balancer des Front-End-Pools eingeben (oder den FQDN des Load Balancer des Director-Pools, wenn Sie einen haben), ein Beispiel wäre sfb_ pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="eec27-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="eec27-292">Sie sollten \* \*\* / \*\*als den zu veröffentlichenden Pfad eingeben, Sie müssen aber auch **den ursprünglichen Hostheader weiterleiten**.</span><span class="sxs-lookup"><span data-stu-id="eec27-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="eec27-p131">Sie finden eine Option für Details oder Informationen zum **öffentlichen oder externen Namen**. Dort können Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="eec27-p131">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="eec27-295">**Anforderungen akzeptieren**, dies sollte aber für den Domänennamen geschehen.</span><span class="sxs-lookup"><span data-stu-id="eec27-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="eec27-296">Geben Sie als **Namen** den Wert **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="eec27-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="eec27-297"><sipdomain>(Dies ist die URL des externen AutoErmittlungsdiensts).</span><span class="sxs-lookup"><span data-stu-id="eec27-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="eec27-298">Wenn Sie nun eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, müssen Sie den FQDN für die externen Webdienste in Ihrem Front-End-Pool eingeben (beispielsweise lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="eec27-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="eec27-299">Es wird eine **path** -Option geben, und Sie müssen \* hier \*\* / \*\*eingeben.</span><span class="sxs-lookup"><span data-stu-id="eec27-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="eec27-300">Wählen Sie mit Ihrem aktuellen öffentlichen Zertifikat einen **SSL-Listener** aus.</span><span class="sxs-lookup"><span data-stu-id="eec27-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="eec27-301">**Authentifizierungsdelegierung** muss auf **Keine Delegierung** festgelegt sein, aber direkte Clientauthentifizierung **muss** zulässig sein.</span><span class="sxs-lookup"><span data-stu-id="eec27-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="eec27-302">Diese Regel muss auf **Alle Benutzer** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="eec27-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="eec27-303">Das dürften alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="eec27-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="eec27-304">Sie müssen sicherstellen, dass der **ursprüngliche Hostheader** weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="eec27-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="eec27-305">Auch die **Webserver**-Ports müssen festgelegt werden. Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="eec27-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="eec27-306">**Leiten Sie Anforderungen an den HTTP-Port weiter**. Die Portnummer muss **8080** lauten.</span><span class="sxs-lookup"><span data-stu-id="eec27-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="eec27-307">**Leiten Sie Anforderungen an den SSL-Port weiter**. Die Portnummer muss **4443** lauten.</span><span class="sxs-lookup"><span data-stu-id="eec27-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="eec27-308">Wenn alles konfiguriert ist, müssen Sie die Optionen speichern oder anwenden und sollten die Regel dann testen.</span><span class="sxs-lookup"><span data-stu-id="eec27-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="eec27-309">Erstellen einer Webveröffentlichungsregel für Port 80 (optional)</span><span class="sxs-lookup"><span data-stu-id="eec27-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="eec27-310">Öffnen Sie die Reverse-Proxy-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="eec27-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="eec27-311">Sie müssen ermitteln, wo Sie in der Benutzeroberfläche ihre Webveröffentlichungsregeln erstellen, und die Option **neu** oder **Erstellen** auswählen (je nach Konfiguration des Reverse-Proxys kann es sich um ein Menü oder eine Registerkarte handeln).</span><span class="sxs-lookup"><span data-stu-id="eec27-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="eec27-312">Suchen Sie nach der Option zum Erstellen einer neuen Webveröffentlichungsregel.</span><span class="sxs-lookup"><span data-stu-id="eec27-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="eec27-313">In der Regel müssen Sie folgende Informationen eingeben:</span><span class="sxs-lookup"><span data-stu-id="eec27-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="eec27-314">**Name**: der Name Ihrer Regel</span><span class="sxs-lookup"><span data-stu-id="eec27-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="eec27-315">**Regelaktion**: in diesem Fall handelt es sich um eine **Zulassungs** Regel, bei der Sie etwas über Ihren Reverse-Proxy durchlaufen lassen.</span><span class="sxs-lookup"><span data-stu-id="eec27-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="eec27-316">Die Regel oder Option für die **Veröffentlichung**, die Sie auswählen, ist **einzelne Website oder Lastenausgleich**.</span><span class="sxs-lookup"><span data-stu-id="eec27-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="eec27-317">Dabei muss es sich um eine **nicht gesicherte Verbindung zur Verbindung mit dem veröffentlichten Webserver bzw. der Farm handeln**.</span><span class="sxs-lookup"><span data-stu-id="eec27-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="eec27-318">Sie müssen einen Pfad für die **interne Veröffentlichung**veröffentlichen, und geben Sie den FQDN für die VIP- **Adresse** des Load Balancer des Front-End-Pools ein, beispielsweise sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="eec27-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="eec27-319">Sie sollten \* \*\* / \*\*als den zu veröffentlichenden Pfad eingeben, Sie müssen aber auch **den ursprünglichen Hostheader weiterleiten**.</span><span class="sxs-lookup"><span data-stu-id="eec27-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="eec27-p134">Sie finden eine Option für Details oder Informationen zum **öffentlichen oder externen Namen**. Dort können Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="eec27-p134">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="eec27-322">**Anforderungen akzeptieren**, dies sollte aber für den Domänennamen geschehen.</span><span class="sxs-lookup"><span data-stu-id="eec27-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="eec27-323">Geben Sie als **Namen** den Wert **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="eec27-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="eec27-324"><sipdomain>(Dies ist die URL des externen AutoErmittlungsdiensts).</span><span class="sxs-lookup"><span data-stu-id="eec27-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="eec27-325">Es wird eine **path** -Option geben, und Sie müssen \* hier \*\* / \*\*eingeben.</span><span class="sxs-lookup"><span data-stu-id="eec27-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="eec27-326">Sie müssen einen Weblistener auswählen oder zulassen, dass der Reverse-Proxy eine für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="eec27-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="eec27-327">**Authentifizierungsdelegierung** muss auf **Keine Delegierung** festgelegt sein, aber direkte Clientauthentifizierung **darf nicht** zulässig sein.</span><span class="sxs-lookup"><span data-stu-id="eec27-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="eec27-328">Diese Regel muss auf **Alle Benutzer** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="eec27-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="eec27-329">Das dürften alle Informationen sein, die Sie zum Erstellen dieser Regel benötigen, damit Sie fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="eec27-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="eec27-330">Die **Webserver**-Ports müssen festgelegt werden. Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="eec27-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="eec27-331">**Leiten Sie Anforderungen an den HTTP-Port weiter**. Die Portnummer muss **8080** lauten.</span><span class="sxs-lookup"><span data-stu-id="eec27-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="eec27-332">**Leiten Sie Anforderungen an den SSL-Port weiter**. Die Portnummer muss **4443** lauten.</span><span class="sxs-lookup"><span data-stu-id="eec27-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="eec27-333">Wenn alles konfiguriert ist, müssen Sie die Optionen speichern oder anwenden und sollten die Regel dann testen.</span><span class="sxs-lookup"><span data-stu-id="eec27-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="eec27-334">Konfigurieren der AutoErmittlung für Mobilität mit Hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="eec27-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="eec27-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="eec27-335"></span></span>

<span data-ttu-id="eec27-336">Hybrid Umgebungen in Skype for Business Server sind Umgebungen, in denen eine lokale und Office 365 Umgebung kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="eec27-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="eec27-337">Wenn Sie Skype for Business Server in einer Hybrid Umgebung verwenden, muss der AutoErmittlungsdienst in der Lage sein, einen Benutzer aus einer dieser Umgebungen zu finden.</span><span class="sxs-lookup"><span data-stu-id="eec27-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="eec27-p137">Damit Mobilclients ermitteln können, wo sich ein Benutzer befindet, muss der AutoErmittlungsdienst mit einem neuen Uniform Resource Locator (URL) konfiguriert sein. Führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="eec27-p137">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="eec27-340">Öffnen Sie die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="eec27-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="eec27-341">Führen Sie die folgenden Schritte aus, um den Wert des Attributs **ProxyFQDN** für Ihre Skype for Business Server-Umgebung zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="eec27-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="eec27-342">Führen Sie dann im Shellfenster folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="eec27-342">Then, still in the shell window, run:</span></span>
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="eec27-343">Hierbei wird [identity] durch den Domänennamen des freigegebenhen SIP-Adressraums ersetzt.</span><span class="sxs-lookup"><span data-stu-id="eec27-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="eec27-344">Testen der Mobilitätsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="eec27-344">Test your Mobility deployment</span></span>
<span data-ttu-id="eec27-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="eec27-345"></span></span>

<span data-ttu-id="eec27-346">Nachdem Sie Skype for Business Server Mobility Service und den AutoErmittlungsdienst für Skype for Business Server bereitgestellt haben, sollten Sie eine Testtransaktion ausführen, um sicherzustellen, dass die Bereitstellung richtig funktioniert.</span><span class="sxs-lookup"><span data-stu-id="eec27-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="eec27-347">Sie können **Test-CsUcwaConference** ausführen, um die Fähigkeit zweier Benutzer zu testen, eine Konferenz zu erstellen, daran teilzunehmen und darin zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="eec27-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="eec27-348">Sie benötigen zwei Benutzer (echte oder Testbenutzer) und deren vollständige Anmeldeinformationen für diesen Test.</span><span class="sxs-lookup"><span data-stu-id="eec27-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="eec27-349">Dieser Befehl funktioniert sowohl für Skype for Business-Clients als auch für lync Server 2013-Clients.</span><span class="sxs-lookup"><span data-stu-id="eec27-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="eec27-350">Für lync Server 2010-Clients in Skype for Business Server 2015 müssen Sie **Test-CsMcxP2PIM** ausführen, um zu testen.</span><span class="sxs-lookup"><span data-stu-id="eec27-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="eec27-351">Ihre lync Server 2010-Benutzer müssen weiterhin tatsächliche Benutzer oder vordefinierte Testbenutzer sein, und Sie benötigen Ihre Kennwort-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="eec27-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="eec27-352">MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eec27-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="eec27-353">Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten.</span><span class="sxs-lookup"><span data-stu-id="eec27-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="eec27-354">Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.</span><span class="sxs-lookup"><span data-stu-id="eec27-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="eec27-355">Testkonferenz für Skype for Business- und Lync 2013-Mobilclients</span><span class="sxs-lookup"><span data-stu-id="eec27-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="eec27-356">Melden Sie sich als Mitglied der **CsAdministrator** -Rolle auf jedem Computer an, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.</span><span class="sxs-lookup"><span data-stu-id="eec27-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="eec27-357">Starten Sie die **Skype for Business Server-Verwaltungsshell** (geben Sie möglicherweise den Namen in suchen ein, oder wechseln Sie zu **Alle Programme** , und wählen Sie ihn aus) aus.</span><span class="sxs-lookup"><span data-stu-id="eec27-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="eec27-358">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="eec27-358">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="eec27-p141">Sie können auch Anmeldeinformationen in einem Skript festlegen und sie an das Test-Cmdlet übergeben. Dafür sehen Sie unten ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="eec27-p141">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="eec27-361">Konferenztest für Lync 2010-Mobilclients</span><span class="sxs-lookup"><span data-stu-id="eec27-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="eec27-362">MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eec27-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="eec27-363">Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten.</span><span class="sxs-lookup"><span data-stu-id="eec27-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="eec27-364">Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.</span><span class="sxs-lookup"><span data-stu-id="eec27-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="eec27-365">Melden Sie sich als Mitglied der **CsAdministrator** -Rolle auf jedem Computer an, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.</span><span class="sxs-lookup"><span data-stu-id="eec27-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="eec27-366">Starten Sie die **Skype for Business Server-Verwaltungsshell** (geben Sie möglicherweise den Namen in suchen ein, oder wechseln Sie zu **Alle Programme** , und wählen Sie ihn aus) aus.</span><span class="sxs-lookup"><span data-stu-id="eec27-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="eec27-367">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="eec27-367">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="eec27-p143">Sie können auch Anmeldeinformationen in einem Skript festlegen und sie an das Test-Cmdlet übergeben. Dafür sehen Sie unten ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="eec27-p143">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="eec27-370">Weitere Informationen zu den Befehlsverfahren finden Sie unter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) und [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="eec27-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="eec27-371">Konfigurieren von Pushbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="eec27-371">Configure for push notifications</span></span>
<span data-ttu-id="eec27-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="eec27-372"></span></span>

<span data-ttu-id="eec27-373">Pushbenachrichtigungen in Form von Badges, Symbolen oder Warnungen können an ein Mobilgerät gesendet werden, selbst wenn die Skype- oder Lync-App inaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="eec27-374">Was sind aber Push-Benachrichtigungen?</span><span class="sxs-lookup"><span data-stu-id="eec27-374">But what are push notifications?</span></span> <span data-ttu-id="eec27-375">Dabei handelt es sich um Ereignisbenachrichtigungen, wie neue oder verpasste Chateinladungen oder eine erhaltene Voicemail.</span><span class="sxs-lookup"><span data-stu-id="eec27-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="eec27-376">Der Skype for Business Server-Mobilitätsdienst sendet diese Benachrichtigungen an den Cloud-basierten Push-Benachrichtigungsdienst von Skype for Business Server, der dann die Benachrichtigungen an den Microsoft Push Notification Service (MSNs) für Windows Phone-Benutzer sendet.</span><span class="sxs-lookup"><span data-stu-id="eec27-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="eec27-377">Diese Funktionalität ist in lync Server 2013 unverändert, doch wenn Sie über einen Skype for Business-Server verfügen, sollten Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="eec27-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="eec27-378">Bei einem Skype for Business Server-Edgeserver fügen Sie einen neuen Hostinganbieter, Microsoft Skype for Business Online, und dann den Anbieter für den Hostinganbieter zwischen Ihrer Organisation und Skype for Business Online ein.</span><span class="sxs-lookup"><span data-stu-id="eec27-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="eec27-p145">Aktivieren Sie Pushbenachrichtigungen, indem Sie das Cmdlet **Set-CsPushNotificationConfiguration** ausführen. Pushbenachrichtigungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="eec27-p145">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="eec27-381">Testen Sie die Partnerverbundkonfiguration und die Pushbenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="eec27-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="eec27-382">Konfigurieren des Skype for Business Edge Server für Pushbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="eec27-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="eec27-383">Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.</span><span class="sxs-lookup"><span data-stu-id="eec27-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="eec27-384">Starten Sie die **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="eec27-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="eec27-385">Fügen Sie einen Skype for Business Server Online-Hostinganbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="eec27-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="eec27-386">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eec27-386">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="eec27-p146">Es kann nur maximal eine Partnerverbundbeziehung mit einem einzelnen Hostinganbieter bestehen. Wenn Sie also bereits einen Hostinganbieter eingerichtet haben, der eine Partnerverbundbeziehung mit „sipfed.online.lync.com“ hat, fügen Sie keinen weiteren Hostinganbieter hinzu, auch wenn die Identität des Hostinganbieters nicht „LyncOnline“ ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-p146">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="eec27-389">Richten Sie den Anbieter Verband für den Hostinganbieter zwischen Ihrer Organisation und dem Push-Benachrichtigungsdienst in Skype for Business Online ein.</span><span class="sxs-lookup"><span data-stu-id="eec27-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="eec27-390">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="eec27-390">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="eec27-391">Aktivieren von Pushbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="eec27-391">Enable push notifications</span></span>

1. <span data-ttu-id="eec27-392">Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.</span><span class="sxs-lookup"><span data-stu-id="eec27-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="eec27-393">Starten Sie die **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="eec27-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="eec27-394">Aktivieren Sie Pushbenachrichtigungen:</span><span class="sxs-lookup"><span data-stu-id="eec27-394">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="eec27-395">Aktivieren Sie den Partnerverbund:</span><span class="sxs-lookup"><span data-stu-id="eec27-395">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="eec27-396">des Partnerverbunds und der Pushbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="eec27-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="eec27-397">Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.</span><span class="sxs-lookup"><span data-stu-id="eec27-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="eec27-398">Starten Sie die **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="eec27-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="eec27-399">Testen Sie die Partnerverbundkonfiguration:</span><span class="sxs-lookup"><span data-stu-id="eec27-399">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="eec27-400">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eec27-400">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="eec27-401">Testen Sie die Pushbenachrichtigungen:</span><span class="sxs-lookup"><span data-stu-id="eec27-401">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="eec27-402">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eec27-402">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="eec27-403">Konfigurieren der Mobilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="eec27-403">Configure Mobility policy</span></span>
<span data-ttu-id="eec27-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="eec27-404"></span></span>

<span data-ttu-id="eec27-405">Sie haben die Möglichkeit, mit Skype for Business Server festzustellen, wer Ihren Mobilitätsdienst nutzen, über Arbeit anrufen, VoIP (Voice over IP) oder Video verwenden oder ob WLAN für VoIP oder Video erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="eec27-406">Mit der Funktion „Geschäftlich anrufen“ kann ein Benutzer Anrufe auf seinem Mobiltelefon unter Verwendung seiner geschäftlichen Telefonnummer anstatt seiner Mobilfunknummer tätigen und entgegennehmen.</span><span class="sxs-lookup"><span data-stu-id="eec27-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="eec27-407">Der Gesprächspartner kann die Mobiltelefonnummer dieses Mobilbenutzers nicht sehen, und der Mobilbenutzer kann damit ausgehende Anrufgebühren vermeiden.</span><span class="sxs-lookup"><span data-stu-id="eec27-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="eec27-408">Wenn VoIP und Video eingerichtet sind, können Benutzer VoIP-Anrufe annehmen und tätigen und Video nutzen.</span><span class="sxs-lookup"><span data-stu-id="eec27-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="eec27-409">Mit den Einstellungen für WLAN-Nutzung wird festgelegt, ob das Mobilgerät eines Benutzers ein WLAN-Netzwerk über ein mobiles Datennetzwerk nutzen muss.</span><span class="sxs-lookup"><span data-stu-id="eec27-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="eec27-410">Mobilität, Anruf über die Arbeit und die VoIP-und Videofunktionen sind standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eec27-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="eec27-411">Die Einstellungen, die WLAN für VoIP und Video erfordern, sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="eec27-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="eec27-412">Administratoren können dies entweder global, nach Standort oder nach Benutzer ändern.</span><span class="sxs-lookup"><span data-stu-id="eec27-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="eec27-413">Um Mobilitätsfunktionen nutzen und über die Arbeit anrufen zu können, müssen die Benutzer:</span><span class="sxs-lookup"><span data-stu-id="eec27-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="eec27-414">Für Skype for Business Server aktiviert</span><span class="sxs-lookup"><span data-stu-id="eec27-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="eec27-415">Aktiviert für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="eec27-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="eec27-416">Eine Mobilitätsrichtlinie zugewiesen, bei der die Option **EnableMobility** auf " **true**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="eec27-417">Damit Benutzer die Funktion „Geschäftlich anrufen“ verwenden können, muss auf sie zudem Folgendes zutreffen:</span><span class="sxs-lookup"><span data-stu-id="eec27-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="eec27-418">Ihnen muss eine VoIP-Richtlinie zugewiesen sein, für die die Option **Gleichzeitiges Klingeln von Telefonen aktivieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="eec27-419">Hat eine Mobilitätsrichtlinie zugewiesen, bei der die **EnableOutsideVoice** auf " **true**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="eec27-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="eec27-p150">Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können mithilfe ihrer Mobilgeräte VoIP-Anrufe zwischen Skype-Benutzern tätigen oder an Konferenzen teilnehmen, indem sie auf ihrem mobilen Gerät den Link „Zum Beitreten klicken“ nutzen. Hierzu müssen die entsprechenden Optionen für die VoIP-Richtlinie, der sie zugeordnet sind, festgelegt sein. Weitere Informationen finden Sie im Planungsthema.</span><span class="sxs-lookup"><span data-stu-id="eec27-p150">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="eec27-422">Ändern der globalen Mobilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="eec27-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="eec27-423">Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.</span><span class="sxs-lookup"><span data-stu-id="eec27-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="eec27-424">Starten Sie die **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="eec27-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="eec27-425">Deaktivieren Sie den Zugriff auf Mobilität, und rufen Sie über Work Global an, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="eec27-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="eec27-426">Sie können den Anruf über die Arbeit ausschalten, ohne den Zugriff auf Mobilität zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="eec27-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="eec27-427">Sie können die Mobilität aber nicht deaktivieren, ohne den Anruf über die Arbeit abzuschalten.</span><span class="sxs-lookup"><span data-stu-id="eec27-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="eec27-428">Weitere Informationen finden Sie unter [Satz-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="eec27-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="eec27-429">Ändern der mobilitätsrichtlinien nach Website</span><span class="sxs-lookup"><span data-stu-id="eec27-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="eec27-430">Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.</span><span class="sxs-lookup"><span data-stu-id="eec27-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="eec27-431">Starten Sie die **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="eec27-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="eec27-p152">Sie können eine Richtlinie auf Standortebene erstellen, den Zugriff auf VoIP und Video deaktivieren und je nach Standort die Einstellungen aktivieren, die WLAN für IP-Audio und -Video erfordern. Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="eec27-p152">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="eec27-434">Weitere Informationen finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="eec27-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="eec27-435">Ändern der mobilitätsrichtlinien nach Benutzer</span><span class="sxs-lookup"><span data-stu-id="eec27-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="eec27-436">Melden Sie sich mit einem Konto an, das ein Mitglied der **CsAdministrator** -Rolle ist, auf einem Computer, auf dem die **Skype for Business Server-Verwaltungsshell** und **OCSCore** installiert sind.</span><span class="sxs-lookup"><span data-stu-id="eec27-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="eec27-437">Starten Sie die **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="eec27-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="eec27-438">Erstellen Sie mobilitätsrichtlinien auf Benutzerebene, deaktivieren Sie Mobilität, und rufen Sie Sie über die Arbeit des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="eec27-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="eec27-439">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="eec27-439">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="eec27-440">Ein weiteres Beispiel mit Beispieldaten:</span><span class="sxs-lookup"><span data-stu-id="eec27-440">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="eec27-441">Sie können den Anruf über die Arbeit ausschalten, ohne den Zugriff auf Mobilität zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="eec27-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="eec27-442">Sie können die Mobilität aber nicht deaktivieren, ohne den Anruf über die Arbeit abzuschalten.</span><span class="sxs-lookup"><span data-stu-id="eec27-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

