---
title: 'Lync Server 2013: aktivieren Lync-Skype Konnektivität'
description: 'Lync Server 2013: aktivieren Lync-Skype Konnektivität.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f31856299b05af7d6b8e934d6e9784d1571b7e29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558491"
---
# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="63fe2-103">Aktivieren Lync-Skype Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63fe2-103">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63fe2-104">_**Letztes Änderungsstand des Themas:** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="63fe2-104">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="63fe2-105">Nachdem Sie die Bereitstellung angefordert haben, können Sie sich auf die lync Server Umgebung und die administrativen Aufgaben konzentrieren, die zum Konfigurieren Lync-Skype Konnektivität erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="63fe2-105">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="63fe2-106">In diesem Abschnitt wird davon ausgegangen, dass der lync Server Administrator lync Server bereitgestellt und den externen Zugriff konfiguriert hat.</span><span class="sxs-lookup"><span data-stu-id="63fe2-106">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="63fe2-107">Weitere Informationen zum Konfigurieren des externen Zugriffs für lync Server finden Sie unter [Planen des Zugriffs durch externe Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) und [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="63fe2-107">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="63fe2-108">Um die lync Server Umgebung für Lync-Skype Konnektivität vorzubereiten, muss der lync Server Administrator die folgenden drei Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="63fe2-108">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="63fe2-109">1\.</span><span class="sxs-lookup"><span data-stu-id="63fe2-109">1\.</span></span> <span data-ttu-id="63fe2-110">Konfigurieren von Partnerverbund und PIC</span><span class="sxs-lookup"><span data-stu-id="63fe2-110">Configure Federation and PIC</span></span>

<span data-ttu-id="63fe2-111">Partnerverbund ist erforderlich, damit Skype-Benutzer mit lync-Benutzern in Ihrer Organisation kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="63fe2-111">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="63fe2-112">Die öffentliche Instant Messaging-Konnektivität (PIC) ist eine Klasse des Verbunds und muss so konfiguriert sein, dass Ihre lync-Benutzer mit Skype-Benutzern kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="63fe2-112">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="63fe2-113">Partnerverbund und PIC werden mithilfe der lync Server-Systemsteuerung, unten dargestellt, konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="63fe2-113">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="63fe2-114">![Anzeigen von PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Anzeigen von PIC")</span><span class="sxs-lookup"><span data-stu-id="63fe2-114">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63fe2-115">PIC Federation wird von Live Communication Server 2005 SP1 oder Office Communications Server 2007 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63fe2-115">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="63fe2-116">Die unterstützten Plattformen für den PIC-Verbund umfassen lync Server 2013, lync Server 2010 und Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="63fe2-116">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="63fe2-117">2\.</span><span class="sxs-lookup"><span data-stu-id="63fe2-117">2\.</span></span> <span data-ttu-id="63fe2-118">Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer</span><span class="sxs-lookup"><span data-stu-id="63fe2-118">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="63fe2-119">Mit dem lync Server-Systemsteuerung muss ein Administrator eine oder mehrere Richtlinien für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Skype-Benutzer mit internen lync Server-Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="63fe2-119">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="63fe2-120">![Richtlinien](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Richtlinien")</span><span class="sxs-lookup"><span data-stu-id="63fe2-120">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="63fe2-121">3\.</span><span class="sxs-lookup"><span data-stu-id="63fe2-121">3\.</span></span> <span data-ttu-id="63fe2-122">Konfigurieren der Skype PIC-Anbieter Einstellung für lync</span><span class="sxs-lookup"><span data-stu-id="63fe2-122">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="63fe2-123">Mit dem lync Server-Verwaltungsshell muss ein Administrator die lync-Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="63fe2-123">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63fe2-124">Benutzer von PIC-Dienstanbietern (Public Instant Messaging Connectivity) können nicht an Chat-oder Audio-oder Videokonferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) für die Unterstützung von Verbindungen mit öffentlichen Chat Diensten konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="63fe2-124">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="63fe2-125">Informationen zum Konfigurieren von Partnerverbund und PIC finden Sie unter "aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen" unter [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063) .</span><span class="sxs-lookup"><span data-stu-id="63fe2-125">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="63fe2-126">Informationen zum Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer finden Sie unter "configure Policies to Control Public User Access" unter [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064) .</span><span class="sxs-lookup"><span data-stu-id="63fe2-126">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="63fe2-127">**So bearbeiten Sie einen vorhandenen Messenger-oder Skype PIC-Anbieter und konfigurieren ihn für Skype**</span><span class="sxs-lookup"><span data-stu-id="63fe2-127">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="63fe2-128">Öffnen Sie in einer lync Server Front-End-Server die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="63fe2-128">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="63fe2-129">Führen Sie die folgenden zwei Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="63fe2-129">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63fe2-130">Wenn in Ihrer Umgebung noch kein PIC-Anbieter vorhanden ist und Sie einen neuen PIC-Anbieter erstellen, müssen Sie das Cmdlet <STRONG>Remove-CsPublicProvider</STRONG> nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="63fe2-130">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63fe2-131">In lync Server 2013 CU5 &amp; lync-Desktop-Client in Office 2013 SP1 hinzugefügt, verbessern NameDecorationRoutingDomain und NameDecorationExcludedDomainList die Situation, in der lync-Benutzer Skype-Kontakte hinzufügen, um nicht-Microsoft-Domänen zu "dekorieren", um diese zu identifizieren und an Skype weiterzuleiten (das Format: User (contoso. com) @MSN. com).</span><span class="sxs-lookup"><span data-stu-id="63fe2-131">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="63fe2-132">Diese neuen Einstellungen ermöglichen die automatische Formatierung der Adresse des Benutzers eingeben im Dialogfeld "Skype-Kontakt hinzufügen" mit dem NameDecorationRoutingDomain (die auf MSN.com festgelegt werden sollte), wenn Sie nicht die Domänen im NameDecorationExcludedDomainList enthält (wir können derzeit MSN.com, Live.com, hotmail.com, Outlook.com) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="63fe2-132">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="63fe2-133">Von einem lync-Client aus können Sie nun Skype als PIC-Anbieter auswählen und einen Skype-Client hinzufügen, indem Sie Ihr Microsoft-Konto angeben.</span><span class="sxs-lookup"><span data-stu-id="63fe2-133">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="63fe2-134">Darüber hinaus kann ein Skype-Benutzer, der sich mit seinem Microsoft-Konto zusammengeführt und angemeldet hat, Kontaktanfragen an lync-Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="63fe2-134">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="63fe2-135">Weitere Informationen zu Microsoft-Konten finden Sie unter [Was ist ein Microsoft-Konto?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="63fe2-135">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="63fe2-136">Weitere Informationen zum Hinzufügen von Clients zu lync finden Sie unter [using Lync-Skype Connectivity in lync Server 2013 as a End User](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="63fe2-136">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="63fe2-137">![Skype-Kontakt hinzufügen](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype-Kontakt hinzufügen")</span><span class="sxs-lookup"><span data-stu-id="63fe2-137">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="63fe2-138">Ausführliche Informationen zum Ändern gehosteter Anbieter finden Sie unter "erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern" unter [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .</span><span class="sxs-lookup"><span data-stu-id="63fe2-138">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="63fe2-139">Dadurch werden die administrativen Aufgaben abgeschlossen, die auf dem Server ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="63fe2-139">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="63fe2-140">Sie sind nun für Lync-Skype Konnektivität eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="63fe2-140">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

