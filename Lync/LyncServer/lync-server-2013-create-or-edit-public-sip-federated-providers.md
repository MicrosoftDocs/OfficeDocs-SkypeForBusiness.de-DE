---
title: 'Lync Server 2013: Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 795950427023a193eff3ab0012687e381e3d3eff
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="8edc8-102">Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8edc8-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8edc8-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8edc8-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8edc8-104">Die Verbindung mit öffentlichen Instant Messaging-Verbindungen ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chat, um mit Benutzern von Chat Diensten zu kommunizieren, die von öffentlichen Sofortnachrichten-Dienstanbietern bereit\!gestellt werden, einschließlich Windows Live Messenger, Yahoo und AOL.</span><span class="sxs-lookup"><span data-stu-id="8edc8-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="8edc8-105">Lync Server 2013 hat öffentliche Anbieter Konfigurationen für America Online, Windows Live und Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="8edc8-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="8edc8-106">und AOL.</span><span class="sxs-lookup"><span data-stu-id="8edc8-106">instant messaging.</span></span> <span data-ttu-id="8edc8-107">Jeder öffentliche Anbieter ist mit dem vollqualifizierten Domänennamen des Edgeservers für den jeweiligen Anbieter sowie mit der Standardüberprüfungsstufe **Benutzer können nur mit Personen in ihrer Liste 'Kontakte' kommunizieren, die diesen Anbieter verwenden** konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8edc8-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="8edc8-108">In der Standardeinstellung ist kein öffentlicher Anbieter aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8edc8-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="8edc8-109">Bevor Sie die öffentlichen Anbieter aktivieren, sollten Sie zunächst die Lizenzvereinbarung und die Bereitstellungsmaßnahmen abschließen.</span><span class="sxs-lookup"><span data-stu-id="8edc8-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="8edc8-110">Es ist möglich, die Anbieter vor Abschluss der Lizenzvereinbarung und der Bereitstellungsmaßnahmen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8edc8-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="8edc8-111">Benutzer können jedoch nicht mit Kontakten dieser Anbieter kommunizieren, bevor die Vorbereitungsmaßnahmen nicht abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="8edc8-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="8edc8-112">Ausführliche Informationen zur Lizenzierung und Bereitstellung öffentlicher Anbieter finden Sie unter [configure Policies to Control Public User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8edc8-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="8edc8-113">Mit den folgenden Verfahren können Sie öffentliche Anbieter erstellen oder bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="8edc8-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="8edc8-114">So erstellen oder bearbeiten Sie öffentliche Anbieter</span><span class="sxs-lookup"><span data-stu-id="8edc8-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="8edc8-115">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="8edc8-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8edc8-116">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8edc8-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8edc8-117">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8edc8-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8edc8-118">Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **SIP-Partneranbieter**.</span><span class="sxs-lookup"><span data-stu-id="8edc8-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="8edc8-119">Wenn Sie einen öffentlichen Anbieter erstellen möchten, klicken Sie auf **Neu** und dann auf **Öffentlicher Anbieter**.</span><span class="sxs-lookup"><span data-stu-id="8edc8-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="8edc8-120">Um einen Eintrag aus der Liste der öffentlichen Anbieter zu bearbeiten, wählen Sie einen öffentlichen Anbieter aus, klicken auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="8edc8-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="8edc8-121">Auf der Seite **SIP-Partneranbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder ändern:</span><span class="sxs-lookup"><span data-stu-id="8edc8-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="8edc8-122">**Kommunikation mit diesem Anbieter**   aktivieren beim Auswählen dieser Einstellung wird Chat mit den Benutzern dieses Anbieters aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8edc8-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="8edc8-123">**Anbietername:**   eine erforderliche Eigenschaft geben Sie den Namen des Anbieters ein, der in der Liste der SIP-Verbund Anbieter wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8edc8-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="8edc8-124">**Zugriffs-Edgedienst (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Zugriffs-Edgedienst des Anbieters ein, den Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8edc8-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="8edc8-125">Diese Informationen werden als Standardelement bereitgestellt und sollten nur geändert werden, wenn der öffentliche Anbieter eine Änderung am FQDN des Zugriffs-Edgedienst beim öffentlichen Anbieter vornimmt.</span><span class="sxs-lookup"><span data-stu-id="8edc8-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="8edc8-126">**Standard Überprüfungsebene:**   die Standardeinstellung **ermöglicht Benutzern die Kommunikation mit Personen in Ihrer Kontaktliste, die diesen Anbieter verwenden** , beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.</span><span class="sxs-lookup"><span data-stu-id="8edc8-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="8edc8-p105">Durch Auswählen von **Benutzer können mit allen Benutzern mit diesem Anbieter kommunizieren** wird die Einschränkung entfernt, dass eine Kontakteinladung empfangen und angenommen worden sein muss. Diese Einschränkung hat keine Auswirkungen darauf, welche Benutzer aus dem Netzwerk des öffentlichen Anbieters mit Ihnen Kontakt aufnehmen können.</span><span class="sxs-lookup"><span data-stu-id="8edc8-p105">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="8edc8-129">Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken Sie auf **Commit**, um die Änderungen zu speichern, oder auf **Abbrechen**, um die Änderungen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="8edc8-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8edc8-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8edc8-130">See Also</span></span>


[<span data-ttu-id="8edc8-131">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8edc8-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="8edc8-132">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8edc8-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

