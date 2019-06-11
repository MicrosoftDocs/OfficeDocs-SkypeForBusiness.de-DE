---
title: Ändern der Standardaktion für nicht explizit unterstützte oder eingeschränkte Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b364253a87f1cbff1ef60322c65780b6497880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="1b715-102">Ändern der Standardaktion für Clients, die in lync Server 2013 nicht explizit unterstützt oder eingeschränkt werden</span><span class="sxs-lookup"><span data-stu-id="1b715-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b715-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1b715-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1b715-104">Sie können nicht nur die Version der Clients angeben, die Sie in ihrer lync Server 2013-Umgebung unterstützen möchten, sondern auch eine Standardaktion für Clients angeben, für die noch keine Versionsrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1b715-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="1b715-105">Auf diese Weise können Sie einschränken, welche Clientversionen in ihrer lync Server-Umgebung verwendet werden, was Ihnen helfen kann, die Kosten zu kontrollieren, die mit der Unterstützung mehrerer Clientversionen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="1b715-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="1b715-106">So ändern Sie die Standardaktion für nicht explizit unterstützte oder eingeschränkte Clients</span><span class="sxs-lookup"><span data-stu-id="1b715-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="1b715-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="1b715-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1b715-108">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1b715-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1b715-109">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1b715-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1b715-110">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **Client Versions Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1b715-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="1b715-111">Doppelklicken Sie auf der Seite **Client Versions Konfiguration** auf die **globale** Konfiguration in der Liste.</span><span class="sxs-lookup"><span data-stu-id="1b715-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="1b715-112">Überprüfen Sie im Dialogfeld **Client-Versions Konfiguration bearbeiten** , ob das Kontrollkästchen **Versionskontrolle aktivieren** aktiviert ist, und wählen Sie dann unter **Standardaktion**eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="1b715-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="1b715-113">**Zulassen**   ermöglicht es dem Client, sich anzumelden, wenn die Client Version nicht mit einem Filter in der Liste der **clientversionsrichtlinien** übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="1b715-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="1b715-114">**Blockieren**   verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste der **clientversionsrichtlinien** entspricht.</span><span class="sxs-lookup"><span data-stu-id="1b715-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="1b715-115">**Blockieren mit URL**   verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste der **clientversionsrichtlinien** entspricht und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b715-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="1b715-116">**Allow with URL**   ermöglicht es dem Client, sich anzumelden, wenn die Client Version keinem Filter in der Liste der **clientversionsrichtlinien** entspricht und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b715-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="1b715-117">Wenn Sie **Block with URL**ausgewählt haben, geben Sie die Client Download-URL ein, die in die Fehlermeldung im Feld **URL** eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b715-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="1b715-118">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1b715-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="1b715-119">So deaktivieren Sie die Client Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="1b715-119">To disable client version control</span></span>

  - <span data-ttu-id="1b715-120">Wenn Sie die Versionskontrolle deaktivieren möchten, damit sich alle Clients unabhängig von der Client Version anmelden können, deaktivieren Sie das Kontrollkästchen **Versionskontrolle aktivieren** , und klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1b715-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1b715-121">Ändern der Standardaktion mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1b715-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1b715-122">Die Standardaktion, die ausgeführt werden soll, wenn Benutzer versuchen, sich mithilfe von Clients anzuschließen, die nicht explizit unterstützt werden oder durch eine clientversionsrichtlinie eingeschränkt sind, können mithilfe der Windows PowerShell-Befehlszeilenschnittstelle und des Cmdlets " **CsClientVersionPolicy** " verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1b715-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="1b715-123">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1b715-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1b715-124">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="1b715-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="1b715-125">So konfigurieren Sie die Standardaktion zum Blockieren des Zugriffs</span><span class="sxs-lookup"><span data-stu-id="1b715-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="1b715-126">Mit dem folgenden Befehl wird die Standardaktion für den Redmond-Website Block festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1b715-126">The following command sets the default action for the Redmond site Block.</span></span> <span data-ttu-id="1b715-127">Dadurch wird die Registrierung für jeden Client blockiert, für den keine Client-Versions Konfigurationsregel vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1b715-127">This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="1b715-128">So konfigurieren Sie die Standardaktion zum Zulassen des Zugriffs</span><span class="sxs-lookup"><span data-stu-id="1b715-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="1b715-129">In diesem Beispiel ist die Standardaktion für die Website "Redmond" auf "zulassen" eingestellt.</span><span class="sxs-lookup"><span data-stu-id="1b715-129">In this example, the default action for the Redmond site is set to Allow.</span></span> <span data-ttu-id="1b715-130">Dies ermöglicht die Registrierung für jeden Client, für den keine Client-Versions Konfigurationsregel vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1b715-130">This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="1b715-131">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) ".</span><span class="sxs-lookup"><span data-stu-id="1b715-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1b715-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b715-132">See Also</span></span>


[<span data-ttu-id="1b715-133">Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b715-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

