---
title: 'Lync Server 2013: Aktivieren der Lync-Skype-Konnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794d2a71c07e742a3ab5597d4bd2aff77157d675
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="59e7a-102">Aktivieren der Lync-Skype-Konnektivität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59e7a-102">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59e7a-103">_**Letztes Änderungsdatum des Themas:** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="59e7a-103">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="59e7a-104">Nachdem Sie die Bereitstellungsanforderung übermittelt haben, können Sie sich auf die lync Server-Umgebung und die administrativen Aufgaben konzentrieren, die zum Konfigurieren der lync-Skype-Konnektivität erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="59e7a-104">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="59e7a-105">In diesem Abschnitt wird davon ausgegangen, dass der lync Server-Administrator lync Server bereitgestellt und den externen Zugriff konfiguriert hat.</span><span class="sxs-lookup"><span data-stu-id="59e7a-105">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="59e7a-106">Weitere Informationen zum Konfigurieren von externem Zugriff für lync Server finden Sie unter [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) und [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="59e7a-106">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="59e7a-107">Um die lync Server-Umgebung für lync-Skype-Konnektivität vorzubereiten, muss der lync Server-Administrator die folgenden drei Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="59e7a-107">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="59e7a-108">1 \.</span><span class="sxs-lookup"><span data-stu-id="59e7a-108">1\.</span></span> <span data-ttu-id="59e7a-109">Konfigurieren des Partnerverbunds und der PIC</span><span class="sxs-lookup"><span data-stu-id="59e7a-109">Configure Federation and PIC</span></span>

<span data-ttu-id="59e7a-110">Föderation ist erforderlich, um Skype-Benutzern die Kommunikation mit lync-Benutzern in Ihrer Organisation zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="59e7a-110">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="59e7a-111">PIC (Public Instant Messaging Connectivity) ist eine Klasse des Verbandes und muss so konfiguriert sein, dass Ihre lync-Nutzer mit Skype-Nutzern kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="59e7a-111">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="59e7a-112">Föderation und PIC werden mithilfe der lync Server-Systemsteuerung konfiguriert (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="59e7a-112">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="59e7a-113">![PIC wird angezeigt] (images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "PIC wird angezeigt")</span><span class="sxs-lookup"><span data-stu-id="59e7a-113">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59e7a-114">Der PIC-Partnerverbund wird von Live Communication Server 2005 SP1 oder Office Communications Server 2007 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="59e7a-114">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="59e7a-115">Zu den unterstützten Plattformen für die PIC-Föderation gehören lync Server 2013, lync Server 2010 und Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59e7a-115">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="59e7a-116">2 \.</span><span class="sxs-lookup"><span data-stu-id="59e7a-116">2\.</span></span> <span data-ttu-id="59e7a-117">Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Benutzerzugriffs im Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="59e7a-117">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="59e7a-118">Mithilfe der lync Server-Systemsteuerung muss ein Administrator mindestens eine Richtlinie für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Skype-Benutzer mit internen lync Server-Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="59e7a-118">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="59e7a-119">![Richtlinien] (images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Richtlinien")</span><span class="sxs-lookup"><span data-stu-id="59e7a-119">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="59e7a-120">3 \.</span><span class="sxs-lookup"><span data-stu-id="59e7a-120">3\.</span></span> <span data-ttu-id="59e7a-121">Konfigurieren der Skype PIC-Anbieter Einstellung für lync</span><span class="sxs-lookup"><span data-stu-id="59e7a-121">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="59e7a-122">Mithilfe der lync Server-Verwaltungsshell muss ein Administrator die lync-Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="59e7a-122">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59e7a-123">Benutzer der Dienstanbieter für öffentliche Instant Messaging-Konnektivität (PIC) können nicht an Chat-oder Audio-oder Videokonferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) konfiguriert haben, um die Konnektivität öffentlicher Chats zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="59e7a-123">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="59e7a-124">Informationen zum Konfigurieren von Verbund und PIC finden Sie unter "aktivieren oder Deaktivieren von [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)Verbund-und öffentlichen Chat Verbindungen" unter.</span><span class="sxs-lookup"><span data-stu-id="59e7a-124">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="59e7a-125">Informationen zum Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs von Verbundbenutzern finden Sie unter "Konfigurieren von Richt [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)Linien zum Steuern des Zugriffs öffentlicher Benutzer" unter.</span><span class="sxs-lookup"><span data-stu-id="59e7a-125">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="59e7a-126">**So bearbeiten Sie einen vorhandenen Messenger oder Skype PIC-Anbieter und konfigurieren ihn für Skype**</span><span class="sxs-lookup"><span data-stu-id="59e7a-126">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="59e7a-127">Öffnen Sie auf einem lync Server-Front-End-Server die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="59e7a-127">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="59e7a-128">Führen Sie die folgenden beiden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="59e7a-128">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59e7a-129">Wenn Sie nicht bereits über einen PIC-Anbieter in Ihrer Umgebung verfügen und einen neuen PIC-Anbieter erstellen, müssen Sie das Cmdlet <STRONG>Remove-CsPublicProvider</STRONG> nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="59e7a-129">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59e7a-130">In lync Server 2013 CU5 &amp; lync-Desktop Client in Office 2013 SP1 wurden die NameDecorationRoutingDomain und NameDecorationExcludedDomainList verbessert, wenn lync-Benutzer Skype-Kontakte hinzufügen, die erforderlich sind, um nicht-Microsoft-Domänen zu "verzieren" identifizieren und leiten Sie Sie an Skype weiter (das Format: User (contoso. com) @MSN. com).</span><span class="sxs-lookup"><span data-stu-id="59e7a-130">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="59e7a-131">Diese neuen Einstellungen ermöglichen die automatische Formatierung der im Dialogfeld „Skype-Kontakt hinzufügen“ eingegebenen Benutzeradresse mit dem Parameter „NameDecorationRoutingDomain“ (der auf „msn.com“ festgelegt sein sollte), wenn die Domänen nicht im Parameter „NameDecorationExcludedDomainList“ enthalten sind (zurzeit werden „msn.com“, „live.com“, „Hotmail.com“ und „outlook.com“ unterstützt).</span><span class="sxs-lookup"><span data-stu-id="59e7a-131">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="59e7a-132">Von einem lync-Client aus können Sie nun Skype als PIC-Anbieter auswählen und einen Skype-Client hinzufügen, indem Sie sein Microsoft-Konto angeben.</span><span class="sxs-lookup"><span data-stu-id="59e7a-132">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="59e7a-133">Darüber hinaus kann ein Skype-Nutzer, der sich mit seinem Microsoft-Konto zusammengeführt und angemeldet hat, Kontaktanfragen an lync-Nutzer senden.</span><span class="sxs-lookup"><span data-stu-id="59e7a-133">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="59e7a-134">Weitere Informationen zu Microsoft-Konten finden Sie unter [Was ist ein Microsoft-Konto?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="59e7a-134">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="59e7a-135">Weitere Informationen zum Hinzufügen von Clients zu lync finden Sie unter [Verwenden der lync-Skype-Konnektivität in lync Server 2013 als Endbenutzer](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="59e7a-135">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="59e7a-136">![Skype-Kontakt hinzufügen] (images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype-Kontakt hinzufügen")</span><span class="sxs-lookup"><span data-stu-id="59e7a-136">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="59e7a-137">Detaillierte Informationen zum Ändern von gehosteten Anbietern finden Sie unter "erstellen oder Bearbeiten von gehosteten SIP [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)-Verbund Anbietern" unter.</span><span class="sxs-lookup"><span data-stu-id="59e7a-137">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="59e7a-138">Damit sind die Verwaltungsaufgaben abgeschlossen, die auf dem Server durchgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="59e7a-138">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="59e7a-139">Sie sind jetzt für die lync-Skype-Konnektivität eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="59e7a-139">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

