---
title: Verwalten von vertrauenswürdigen Anwendungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Eine vertrauenswürdige Anwendung ist eine Anwendung basierend auf Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, der Skype für Business Server vertraut.
ms.openlocfilehash: 0f483cc0a1a3a9e7dad881fc40819a9c27dacdec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911868"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="12405-103">Verwalten von vertrauenswürdigen Anwendungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="12405-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="12405-104">Eine *Vertrauenswürdige Anwendung* ist eine Anwendung basierend auf Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, der Skype für Business Server vertraut.</span><span class="sxs-lookup"><span data-stu-id="12405-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="12405-105">Ausführliche Informationen über UCMA-Anwendungen finden Sie unter "Unified Communications Managed API 3.0 Core SDK-Dokumentation" unter http://go.microsoft.com/fwlink/p/?linkId=210320.</span><span class="sxs-lookup"><span data-stu-id="12405-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="12405-106">Erfolgreich veröffentlichen, aktivieren oder Deaktivieren einer Topologie, die beim Hinzufügen oder Entfernen einer Serverrolle, sollten Sie als ein Benutzer ein Mitglied der Gruppen RTCUniversalServerAdmins und Domänen-Admins angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="12405-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="12405-107">Verwenden Sie diesen Artikel, um Informationen zum Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers, zeigen Sie eine Liste der vertrauenswürdigen Anwendungen und vertrauenswürdige Anwendungsinformationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="12405-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="12405-108">Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers</span><span class="sxs-lookup"><span data-stu-id="12405-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="12405-109">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="12405-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="12405-110">Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="12405-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="12405-111">Wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="12405-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="12405-112">Klicken Sie im Dialogfeld **Topologie speichern unter** klicken Sie auf der Topologie-Generator-Datei, den, die Sie verwenden möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="12405-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="12405-113">Klicken Sie im linken Bereich Maustaste auf **Vertrauenswürdige Anwendungsserver**, und klicken Sie dann auf **Neuer Pool für vertrauenswürdige Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="12405-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="12405-114">Geben Sie den **FQDN des Pools** für den vertrauenswürdigen Anwendungspool auswählen, ob sie einen einzelnen oder mehreren Servern werden, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="12405-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="12405-115">Wählen Sie auf der Seite **Wählen Sie den nächsten Hop** aus der Liste der Skype für Business Server-Front-End-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="12405-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="12405-116">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="12405-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="12405-117">Wählen Sie den obersten Knoten **Skype für Business Server**aus, und klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="12405-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="12405-118">Wurde sollte der **Vertrauenswürdige Anwendungspool** erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="12405-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="12405-119">Anzeigen einer Liste der vertrauenswürdigen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="12405-119">View a list of trusted applications</span></span>

<span data-ttu-id="12405-120">Sie können die Skype Business Server-Systemsteuerung verwenden, zum Anzeigen einer Liste der vertrauenswürdigen Anwendungen, die Sie in Ihre Skype für Business Server-Umgebung bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="12405-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="12405-121">Eine vertrauenswürdige Anwendung ist eine Anwendung basierend auf Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, der Skype für Business Server vertraut.</span><span class="sxs-lookup"><span data-stu-id="12405-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="12405-122">Diese Vertrauensstellung ist in der folgenden Liste zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="12405-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="12405-123">Vertrauenswürdige Anwendungen werden nicht für die Authentifizierung von Skype für Business Server angefordert.</span><span class="sxs-lookup"><span data-stu-id="12405-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="12405-124">Vertrauenswürdige Anwendungen werden nicht von Skype für Business Server für SIP-Transaktionen, Verbindungen oder ausgehende VoIP over Internet Protocol (VoIP) anrufen weder gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="12405-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="12405-125">Vertrauenswürdige Anwendungen können Identität beliebiger Benutzer annehmen und Konferenzen beitreten, ohne in konferenzlisten aufzutauchen.</span><span class="sxs-lookup"><span data-stu-id="12405-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="12405-126">Vertrauenswürdige Anwendungen sind hochverfügbar und ausfallsicher.</span><span class="sxs-lookup"><span data-stu-id="12405-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="12405-127">In der Skype Business Server-Systemsteuerung sehen Sie den Namen der Anwendungen, den Pool für deren Ausführung und den Port, die, den Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="12405-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="12405-128">So zeigen Sie eine Liste der vertrauenswürdigen Anwendungen an</span><span class="sxs-lookup"><span data-stu-id="12405-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="12405-129">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsServerAdministrator“, „CsAdministrator“, „CsHelpDesk“ oder „CsViewOnlyAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="12405-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="12405-130">Ausführliche Informationen zu den vordefinierten Administratorrollen in Skype für Business Server verfügbar sind finden Sie unter [Role-based Access Control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="12405-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="12405-131">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="12405-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="12405-132">Klicken Sie in der linken Navigationsleiste auf **Topologie**, und klicken Sie dann auf **Vertrauenswürdige Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="12405-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="12405-133">Klicken Sie auf der Seite **Vertrauenswürdige Anwendung** auf eine Spaltenüberschrift, um die Anwendungen zu sortieren, bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="12405-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="12405-134">Anzeigen von Informationen für vertrauenswürdige Anwendung</span><span class="sxs-lookup"><span data-stu-id="12405-134">View trusted application information</span></span>

<span data-ttu-id="12405-135">Sie können Informationen zu vertrauenswürdigen Anwendungen mithilfe von Windows PowerShell und das Cmdlet **Get-CsTrustedApplication** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="12405-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="12405-136">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="12405-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="12405-137">So zeigen Sie vertrauenswürdige Anwendungen an</span><span class="sxs-lookup"><span data-stu-id="12405-137">To view trusted applications</span></span>

<span data-ttu-id="12405-138">Um alle vertrauenswürdigen Anwendung anzuzeigen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="12405-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="12405-139">Mit diesem Befehl werden Informationen ähnlich dem folgenden für jede vertrauenswürdige Anwendung zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="12405-139">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   <span data-ttu-id="12405-140">Weitere Informationen hierzu finden Sie unter [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="12405-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
