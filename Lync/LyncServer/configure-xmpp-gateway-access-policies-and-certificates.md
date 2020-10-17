---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
description: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e958100501ad9ca87d1ab970162f4be8c7692a99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549711"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="09d54-103">Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways</span><span class="sxs-lookup"><span data-stu-id="09d54-103">Configure XMPP gateway access policies and certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09d54-104">_**Letztes Änderungsstand des Themas:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="09d54-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="09d54-p101">Der XMPP-Partnerverbund definiert eine externe Bereitstellung basierend auf dem XMPP-Protokoll (eXtensible Messaging and Presence Protocol). Die XMPP-Konfiguration erlaubt Lync-Benutzern wie folgt den Zugriff auf XMPP-Domänenbenutzer:</span><span class="sxs-lookup"><span data-stu-id="09d54-p101">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="09d54-107">Chat und Anwesenheit – nur zwischen Benutzern</span><span class="sxs-lookup"><span data-stu-id="09d54-107">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="09d54-108">Erstellung von XMPP-Verbundkontakten im Lync-Client</span><span class="sxs-lookup"><span data-stu-id="09d54-108">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="09d54-p102">Beim Konfigurieren von Richtlinien für die Unterstützung von XMPP-Verbundpartnern (extensible Messaging and Presence Protocol) gelten die Richtlinien für Benutzer von XMPP-Partnerverbunddomänen, aber nicht für Benutzer von SIP (Session Initiation Protocol)-Chatdienstanbietern (z. B. Windows Live) oder von SIP-Partnerverbunddomänen. Sie konfigurieren einen XMPP-Verbundpartner für jede XMPP-Partnerverbunddomäne, der Ihre Benutzer Kontakte hinzufügen und mit der sie kommunizieren sollen können. Wenn die Richtlinien vorhanden sind, müssen Sie die XMPP-Gatewayzertifikate konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="09d54-p102">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09d54-112">Um mit der XMPP-Gateway-Migration zu beginnen, müssen Sie das lync Server 2013 XMPP-Gateway bereitstellen und Zugriffsrichtlinien konfigurieren, um Benutzer für lync Server 2013 XMPP-Gateway zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="09d54-112">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="09d54-113">Alle Benutzer müssen in die lync Server 2013-Bereitstellung verschoben werden, bevor Sie diese Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="09d54-113">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="09d54-114">Ausführliche Informationen finden Sie unter <A href="configure-xmpp-gateway-on-lync-server-2013.md">configure XMPP Gateway on lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="09d54-114">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="09d54-115">Konfigurieren einer externen Zugriffsrichtlinie, um Benutzer für Lync Server 2013 XMPP Gateway zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="09d54-115">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="09d54-116">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="09d54-116">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="09d54-117">Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff**, und klicken Sie dann auf **Externe Zugriffsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="09d54-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="09d54-118">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="09d54-118">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="09d54-119">Geben Sie einen Namen für die externe Benutzerzugriffsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="09d54-119">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="09d54-120">Geben Sie eine Beschreibung für die externe Benutzerzugriffsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="09d54-120">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="09d54-121">Wählen Sie **Kommunikation mit Partnerbenutzern aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="09d54-121">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="09d54-122">Wählen Sie **Kommunikation mit XMPP-Partnerverbundbenutzern aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="09d54-122">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="09d54-123">Klicken Sie auf **Commit ausführen**, um Ihre Änderungen am Standort oder an der Benutzerrichtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="09d54-123">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

