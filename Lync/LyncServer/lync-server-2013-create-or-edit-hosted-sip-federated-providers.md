---
title: 'Lync Server 2013: Erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7704074db1b210ca341b05df9fbd02afabbc70a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507492"
---
# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="d0a19-102">Erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0a19-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0a19-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d0a19-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d0a19-104">Hosted Provider Instant Messaging (im)-Konnektivität ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chat, um mit Benutzern von Chat Diensten zu kommunizieren, die von gehosteten Anbietern bereitgestellt werden, einschließlich Microsoft 365 und lync online.</span><span class="sxs-lookup"><span data-stu-id="d0a19-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including Microsoft 365 and Lync Online.</span></span>

<span data-ttu-id="d0a19-105">Jeder gehostete Anbieter ist mit dem vollqualifizierten Domänennamen des Edgeservers des Anbieters sowie der Standardüberprüfungsstufe **Benutzern nur die Kommunikation mit den Personen in ihren Kontaktlisten erlauben, die diesen Anbieter verwenden** konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d0a19-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="d0a19-106">Verwenden Sie zum Erstellen oder Bearbeiten von gehosteten Anbietern das folgende Verfahren:</span><span class="sxs-lookup"><span data-stu-id="d0a19-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="d0a19-107">So erstellen oder bearbeiten Sie gehostete Anbieter</span><span class="sxs-lookup"><span data-stu-id="d0a19-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="d0a19-108">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d0a19-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0a19-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d0a19-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d0a19-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d0a19-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d0a19-111">Klicken Sie in der linken Navigationsleiste auf \*\*Partnerverbund und externer Zugriff \*\* und dann auf **SIP-Partnerverbundanbieter**.</span><span class="sxs-lookup"><span data-stu-id="d0a19-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="d0a19-112">Wenn Sie einen neuen gehosteten Anbieter erstellen müssen, klicken Sie auf **Neu** und anschließend auf **Gehosteter Anbieter**.</span><span class="sxs-lookup"><span data-stu-id="d0a19-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="d0a19-113">Wenn Sie in der Liste der gehosteten Anbieter einen Eintrag bearbeiten müssen, wählen Sie einen gehosteten Anbieter aus, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d0a19-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="d0a19-114">Auf der Seite **SIP-Partnerverbundanbieter bearbeiten** können Sie folgende Einstellungen eingeben oder bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="d0a19-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="d0a19-115">**Aktivieren der Kommunikation mit diesem Anbieter**     Wenn Sie diese Einstellung auswählen, wird die Kommunikation mit den Benutzern dieses Anbieters aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d0a19-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="d0a19-116">**Anbietername:**     Eine erforderliche Eigenschaft, geben Sie den Namen des Anbieters ein, der in der Liste der SIP-Verbund Anbieter wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d0a19-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="d0a19-117">**Zugriffs-Edgedienst (FQDN):**     Eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Zugriffs-Edgedienst des gehosteten Anbieters ein, den Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d0a19-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="d0a19-118">Diese Informationen sollten vom gehosteten Anbieter bereitgestellt und nur dann geändert werden, wenn der gehostete Anbieter eine Änderung am FQDN des Zugriffs-Edgediensts beim gehosteten Anbieter vornimmt.</span><span class="sxs-lookup"><span data-stu-id="d0a19-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="d0a19-119">**Standard Überprüfungsebene:**     Die Standardeinstellung **ermöglicht Benutzern die Kommunikation mit Personen in Ihrer Kontaktliste, die diesen Anbieter verwenden** , beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.</span><span class="sxs-lookup"><span data-stu-id="d0a19-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="d0a19-p103">Die Auswahl der Option **Benutzern die Kommunikation mit jedem erlauben, der diesen Anbieter verwendet** entfernt die Einschränkung, dass Sie eine Kontaktanfrage erhalten und angenommen haben müssen. Diese Einstellung hat keine Auswirkungen darauf, wer Sie aus dem Netzwerk des gehosteten Anbieters kontaktieren kann.</span><span class="sxs-lookup"><span data-stu-id="d0a19-p103">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="d0a19-122">Wenn Sie die Einstellungen konfiguriert haben, klicken Sie auf **Commit**, um zu speichern oder auf **Abbrechen**, um die Änderungen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="d0a19-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0a19-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0a19-123">See Also</span></span>


[<span data-ttu-id="d0a19-124">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0a19-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="d0a19-125">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0a19-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

