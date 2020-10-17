---
title: Ändern der Standardaktion für Clients, die nicht explizit unterstützt oder eingeschränkt sind
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213e42a7477202cf40a0b06c79edde49976f0bbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515272"
---
# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="1067a-102">Ändern Sie die Standardaktion für Clients, die nicht explizit unterstützt oder in lync Server 2013 eingeschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="1067a-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1067a-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1067a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1067a-104">Zusätzlich zur Angabe der Version der Clients, die Sie in ihrer lync Server 2013 Umgebung unterstützen möchten, können Sie auch eine Standardaktion für Clients angeben, für die noch keine Versionsrichtlinie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1067a-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="1067a-105">Auf diese Weise können Sie einschränken, welche Clientversionen in ihrer lync Server Umgebung verwendet werden, was Ihnen helfen kann, die mit der Unterstützung mehrerer Clientversionen verbundenen Kosten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="1067a-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="1067a-106">So ändern Sie die Standardaktion für Clients, die nicht explizit unterstützt oder eingeschränkt werden</span><span class="sxs-lookup"><span data-stu-id="1067a-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="1067a-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="1067a-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1067a-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1067a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1067a-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1067a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1067a-110">Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Clientversionskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1067a-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="1067a-111">Doppelklicken Sie auf der Seite **Clientversionskonfiguration** auf die Konfiguration **Global** in der Liste.</span><span class="sxs-lookup"><span data-stu-id="1067a-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="1067a-112">Stellen Sie im Dialogfeld **Clientversionskonfiguration bearbeiten** sicher, dass das Kontrollkästchen **Versionskontrolle aktivieren** aktiviert ist, und wählen Sie anschließend unter **Standardaktion** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="1067a-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="1067a-113">**Zulassen**     Ermöglicht dem Client die Anmeldung, wenn die Client Version keinem Filter in der Liste mit den **clientversionsrichtlinien** entspricht.</span><span class="sxs-lookup"><span data-stu-id="1067a-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="1067a-114">**Block**     Verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste mit den **clientversionsrichtlinien** entspricht.</span><span class="sxs-lookup"><span data-stu-id="1067a-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="1067a-115">**Blockieren mit URL**     Verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste mit den **clientversionsrichtlinien** entspricht, und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1067a-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="1067a-116">**Zulassen mit URL**     Ermöglicht dem Client die Anmeldung, wenn die Client Version keinem Filter in der Liste mit den **clientversionsrichtlinien** entspricht, und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1067a-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="1067a-117">Wenn Sie die Option **Blockieren mit URL** auswählen, geben Sie im Feld **URL** die URL für den Clientdownload ein, die in der Fehlermeldung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1067a-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="1067a-118">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1067a-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="1067a-119">So deaktivieren Sie die Clientversionskontrolle</span><span class="sxs-lookup"><span data-stu-id="1067a-119">To disable client version control</span></span>

  - <span data-ttu-id="1067a-120">Um die Versionskontrolle zu deaktivieren und allen Clients unabhängig von der Clientversion die Anmeldung zu ermöglichen, deaktivieren Sie das Kontrollkästchen **Versionskontrolle aktivieren**, und klicken Sie anschließend auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1067a-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1067a-121">Ändern der Standardaktion mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1067a-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1067a-122">Die Standardaktion, die ausgeführt werden soll, wenn Benutzer versuchen, sich mit Clients zu anmelden, die nicht explizit unterstützt oder durch eine clientversionsrichtlinie eingeschränkt sind, können über Windows PowerShell Befehlszeilenschnittstelle und das Cmdlet " **CsClientVersionPolicy** " verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1067a-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="1067a-123">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1067a-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1067a-124">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="1067a-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="1067a-125">So konfigurieren Sie die Standardaktion zum Blockieren des Zugriffs</span><span class="sxs-lookup"><span data-stu-id="1067a-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="1067a-p104">Mit dem folgenden Befehl wird die Standardaktion zum Blockieren des Standorts "Redmond" festgelegt. Dadurch wird die Registrierung für alle Clients blockiert, für die keine Konfigurationsregel bezüglich der Clientversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1067a-p104">The following command sets the default action for the Redmond site Block. This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="1067a-128">So konfigurieren Sie die Standardaktion zum Zulassen des Zugriffs</span><span class="sxs-lookup"><span data-stu-id="1067a-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="1067a-p105">In diesem Beispiel ist die Standardaktion für den Standort "Redmond" auf "Zulassen" festgelegt. Dadurch wird die Registrierung für alle Clients zugelassen, für die keine Konfigurationsregel bezüglich der Clientversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1067a-p105">In this example, the default action for the Redmond site is set to Allow. This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="1067a-131">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) ".</span><span class="sxs-lookup"><span data-stu-id="1067a-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1067a-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1067a-132">See Also</span></span>


[<span data-ttu-id="1067a-133">Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1067a-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

