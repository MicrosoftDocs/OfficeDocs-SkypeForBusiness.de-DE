---
title: 'Lync Server 2013: Konfigurieren der Besprechungseinladung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bc948f81ddbc9bf4881b2188fc378315b3824ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532332"
---
# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="ae19f-102">Konfigurieren der Besprechungseinladung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae19f-102">Configuring the meeting invitation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae19f-103">_**Letztes Änderungsstand des Themas:** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="ae19f-103">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="ae19f-104">Sie können vom Online-Besprechungs-Add-in gesendete Besprechungseinladungen für lync 2013 anpassen, indem Sie die folgenden optionalen Elemente im Text der Besprechungseinladung einschließen:</span><span class="sxs-lookup"><span data-stu-id="ae19f-104">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="ae19f-105">**Logo Ihrer Organisation** Fügen Sie das Logo Ihrer Organisation zu Besprechungseinladungen hinzu, indem Sie die Option Logo-URL verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae19f-105">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="ae19f-106">Wenn Besprechungseinladungen an Personen außerhalb Ihrer Organisation gesendet werden, sollte sich das Bild in einer öffentlich verfügbaren URL befinden.</span><span class="sxs-lookup"><span data-stu-id="ae19f-106">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="ae19f-107">Die unterstützten Bildformate sind GIF und JPG.</span><span class="sxs-lookup"><span data-stu-id="ae19f-107">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="ae19f-108">Obwohl lync Server 2013 die URL ohne Größenbeschränkungen für das Bild speichert, sollte die maximale Größe des Bilds für optimale Ergebnisse 30 Pixel hoch und 188 Pixel breit sein.</span><span class="sxs-lookup"><span data-stu-id="ae19f-108">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="ae19f-109">**Ein benutzerdefinierter Hilfe-oder Support Link** Fügen Sie eine URL für die Hilfe-oder Support Teamwebsite Ihrer Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae19f-109">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="ae19f-110">Wenn Besprechungseinladungen an Personen außerhalb Ihrer Organisation gesendet werden, sollte die URL öffentlich verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="ae19f-110">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="ae19f-111">Die maximale URL-Länge beträgt 1 KB.</span><span class="sxs-lookup"><span data-stu-id="ae19f-111">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="ae19f-112">**Rechtlicher Haftungsausschluss-Text** Fügen Sie eine URL für juristischen Text oder einen Haftungsausschluss hinzu, der in allen Besprechungseinladungen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ae19f-112">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="ae19f-113">Wenn Besprechungseinladungen an Personen außerhalb Ihrer Organisation gesendet werden, sollte die URL öffentlich verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="ae19f-113">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="ae19f-114">Die maximale URL-Länge beträgt 1 KB.</span><span class="sxs-lookup"><span data-stu-id="ae19f-114">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="ae19f-115">**Benutzerdefinierter Fußzeilentext** Hinzufügen von Text, der in der Einladung als benutzerdefinierte Fußzeile gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="ae19f-115">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="ae19f-116">Die maximale Länge des Texts, der hinzugefügt werden kann, ist 2 KB.</span><span class="sxs-lookup"><span data-stu-id="ae19f-116">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="ae19f-117">Sie können diese Optionen entweder mit lync Server-Systemsteuerung oder lync Server-Verwaltungsshell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ae19f-117">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="ae19f-118">**So passen Sie die Besprechungseinladung mithilfe von lync Server-Systemsteuerung an**</span><span class="sxs-lookup"><span data-stu-id="ae19f-118">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="ae19f-119">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="ae19f-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="ae19f-120">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ae19f-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ae19f-121">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ae19f-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ae19f-122">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ae19f-122">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="ae19f-123">Klicken Sie auf der Seite **besprechungskonfiguration** auf **neu**, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="ae19f-123">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="ae19f-124">Klicken Sie auf **Websitekonfiguration**, um eine Richtlinie auf Standortebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ae19f-124">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="ae19f-125">Geben Sie im Feld **Website Suche auswählen** den vollständigen oder Teil des Namens der Website ein, für die Sie die Einstellungen für den besprechungsbeitritt definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ae19f-125">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="ae19f-126">Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae19f-126">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="ae19f-127">Klicken Sie zum Erstellen einer Richtlinie auf Poolebene auf **Poolkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ae19f-127">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="ae19f-128">Geben Sie im Suchfeld **Dienst auswählen einen** Teil oder den vollständigen Namen des Pool Diensts ein, für den Sie die Einstellungen für den besprechungsbeitritt definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ae19f-128">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="ae19f-129">Klicken Sie in der daraufhin angezeigten Liste mit den Diensten auf den gewünschten Pool, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae19f-129">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="ae19f-130">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ae19f-130">Do any of the following:</span></span>
    
      - <span data-ttu-id="ae19f-131">Geben Sie im Feld **Logo-URL** die URL des Logo Bilds Ihrer Organisation ein.</span><span class="sxs-lookup"><span data-stu-id="ae19f-131">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="ae19f-132">Geben Sie im Feld **Hilfe-URL** die URL zur Hilfe-oder Support Website Ihrer Organisation ein.</span><span class="sxs-lookup"><span data-stu-id="ae19f-132">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="ae19f-133">Geben Sie im Feld **juristischer Text** die URL des rechtlichen Texts oder Haftungsausschlusses ein, den Sie in Besprechungseinladungen einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="ae19f-133">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="ae19f-134">Geben Sie im **Textfeld benutzerdefinierter** Fußzeilentext Fußzeile ein, bis zu 2 KB.</span><span class="sxs-lookup"><span data-stu-id="ae19f-134">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="ae19f-135">**So passen Sie die Besprechungseinladung mithilfe von lync Server-Verwaltungsshell an**</span><span class="sxs-lookup"><span data-stu-id="ae19f-135">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="ae19f-136">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ae19f-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ae19f-137">Führen Sie das Cmdlet **New-CsMeetingConfiguration** oder **CsMeetingConfiguration** aus, um die Optionen für die Besprechungseinladung zu erstellen oder zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ae19f-137">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="ae19f-138">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ae19f-138">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

