---
title: Verwalten vertrauenswürdiger Anwendungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK basiert, das von Skype for Business Server als vertrauenswürdig eingestuft wird.
ms.openlocfilehash: b2a257ad197d573beccb187ef49e41b3864c1a58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817076"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="b944b-103">Verwalten von vertrauenswürdigen Anwendungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b944b-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="b944b-104">Bei einer *vertrauenswürdigen Anwendung* handelt es sich um eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK basiert, das von Skype for Business Server als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="b944b-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="b944b-105">Ausführliche Informationen zu UCMA-Anwendungen finden Sie unter "Unified Communications Managed API 3,0 Core SDK Documentation http://go.microsoft.com/fwlink/p/?linkId=210320" unter.</span><span class="sxs-lookup"><span data-stu-id="b944b-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="b944b-106">Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist.</span><span class="sxs-lookup"><span data-stu-id="b944b-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="b944b-107">In diesem Artikel erfahren Sie, wie Sie einen neuen vertrauenswürdigen Anwendungsserver konfigurieren, eine Liste der vertrauenswürdigen Anwendungen anzeigen und vertrauenswürdige Anwendungsinformationen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="b944b-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="b944b-108">Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers</span><span class="sxs-lookup"><span data-stu-id="b944b-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="b944b-109">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="b944b-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b944b-110">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="b944b-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="b944b-111">Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b944b-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="b944b-112">Klicken Sie im Dialogfeld **Topologie speichern** unter auf die Topologie-Generator-Datei, die Sie verwenden möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b944b-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="b944b-113">Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver**, und klicken Sie dann auf **neuer vertrauenswürdiger Anwendungs Pool**.</span><span class="sxs-lookup"><span data-stu-id="b944b-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="b944b-114">Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, wählen Sie aus, ob es sich um einen Einzelserver-oder mehrere Server handelt, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b944b-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="b944b-115">Wählen Sie auf der Seite **Nächster Hop auswählen** in der Liste den Skype for Business Server-Front-End-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="b944b-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="b944b-116">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b944b-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="b944b-117">Wählen Sie den obersten Knoten **für Skype for Business Server**aus, und klicken Sie dann im Menü **Aktionen** auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="b944b-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="b944b-118">Der **Vertrauenswürdige Anwendungspool** sollte erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="b944b-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="b944b-119">Anzeigen einer Liste vertrauenswürdiger Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b944b-119">View a list of trusted applications</span></span>

<span data-ttu-id="b944b-120">Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine Liste der vertrauenswürdigen Anwendungen anzuzeigen, die Sie in Ihrer Skype for Business Server-Umgebung bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="b944b-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="b944b-121">Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK basiert, das von Skype for Business Server als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="b944b-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="b944b-122">Diese Vertrauensstellung wird in der folgenden Liste zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="b944b-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="b944b-123">Vertrauenswürdige Anwendungen werden von Skype for Business Server nicht für die Authentifizierung in Frage gestellt.</span><span class="sxs-lookup"><span data-stu-id="b944b-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="b944b-124">Vertrauenswürdige Anwendungen werden nicht von Skype for Business Server für SIP-Transaktionen, Verbindungen oder ausgehende VoIP-Anrufe (Voice over Internet Protocol) gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="b944b-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="b944b-125">Vertrauenswürdige Anwendungen können sich als alle Benutzer erweisen und können an Konferenzen teilnehmen, ohne dass Sie in Dienstplänen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b944b-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="b944b-126">Vertrauenswürdige Anwendungen sind hochgradig verfügbar und widerstandsfähig.</span><span class="sxs-lookup"><span data-stu-id="b944b-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="b944b-127">In der Skype for Business Server-Systemsteuerung können Sie den Namen der Anwendungen, den Pool, in dem Sie ausgeführt werden, und den verwendeten Port sehen.</span><span class="sxs-lookup"><span data-stu-id="b944b-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="b944b-128">So zeigen Sie eine Liste vertrauenswürdiger Anwendungen an</span><span class="sxs-lookup"><span data-stu-id="b944b-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="b944b-129">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsServerAdministrator“, „CsAdministrator“, „CsHelpDesk“ oder „CsViewOnlyAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="b944b-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="b944b-130">Details zu den vordefinierten Administratorrollen, die in Skype for Business Server zur Verfügung stehen, finden Sie unter [rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="b944b-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="b944b-131">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b944b-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="b944b-132">Klicken Sie in der linken Navigationsleiste auf **Topologie**, und klicken Sie dann auf **vertrauenswürdige Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="b944b-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="b944b-133">Klicken Sie auf der Seite **vertrauenswürdige Anwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="b944b-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="b944b-134">Anzeigen von Informationen zu vertrauenswürdigen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b944b-134">View trusted application information</span></span>

<span data-ttu-id="b944b-135">Sie können Informationen zu vertrauenswürdigen Anwendungen mithilfe von Windows PowerShell und dem Cmdlet **Get-CsTrustedApplication** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b944b-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="b944b-136">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b944b-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="b944b-137">So zeigen Sie vertrauenswürdige Anwendungen an</span><span class="sxs-lookup"><span data-stu-id="b944b-137">To view trusted applications</span></span>

<span data-ttu-id="b944b-138">Wenn Sie alle vertrauenswürdigen Anwendungen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="b944b-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="b944b-139">Dieser Befehl gibt für jede vertrauenswürdige Anwendung Informationen zurück, die der folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="b944b-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="b944b-140">Ausführliche Informationen finden Sie unter [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="b944b-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
