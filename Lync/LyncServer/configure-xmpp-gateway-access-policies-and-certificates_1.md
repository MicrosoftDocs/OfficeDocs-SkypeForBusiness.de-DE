---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49733819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f93134da1f61f4036a468a6aeeffb3867c2cce89
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="d82ab-102">Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways</span><span class="sxs-lookup"><span data-stu-id="d82ab-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d82ab-103">_**Letztes Änderungsdatum des Themas:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="d82ab-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="d82ab-104">Die XMPP-Föderation definiert eine externe Bereitstellung, die auf dem Extensible Messaging and Presence Protocol (XMPP) basiert.</span><span class="sxs-lookup"><span data-stu-id="d82ab-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="d82ab-105">Eine XMPP-Konfiguration ermöglicht lync-Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:</span><span class="sxs-lookup"><span data-stu-id="d82ab-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="d82ab-106">Chat und Anwesenheit – nur Person zu Person</span><span class="sxs-lookup"><span data-stu-id="d82ab-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="d82ab-107">Erstellen von XMPP-verbundkontakten im lync-Client</span><span class="sxs-lookup"><span data-stu-id="d82ab-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="d82ab-108">Wenn Sie Richtlinien für die Unterstützung von Verbundpartnern des Extensible Messaging and Presence Protocol (XMPP) konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, nicht aber für Benutzer von SIP-Chat Diensten (im). (beispielsweise Windows Live) oder SIP-Verbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="d82ab-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="d82ab-109">Sie konfigurieren einen XMPP-Verbund Partner für jede XMPP-Verbunddomäne, die es Ihren Benutzern ermöglichen soll, Kontakte hinzuzufügen und mit Ihnen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="d82ab-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="d82ab-110">Sobald die Richtlinien vorhanden sind, müssen Sie die XMPP-Gateway-Zertifikate konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d82ab-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d82ab-111">Um mit der XMPP-Gateway-Migration zu beginnen, müssen Sie das lync Server 2013 XMPP-Gateway bereitstellen und Zugriffsrichtlinien konfigurieren, um Benutzer für lync Server 2013 XMPP-Gateway zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d82ab-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="d82ab-112">Bevor Sie diese Schritte ausführen, müssen alle Benutzer in die lync Server 2013-Bereitstellung verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="d82ab-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="d82ab-113">Ausführliche Informationen finden Sie unter <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Konfigurieren des XMPP-Gateways unter lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d82ab-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="d82ab-114">Konfigurieren einer Richtlinie für den externen Zugriff zum Aktivieren von Benutzern für lync Server 2013 XMPP-Gateway</span><span class="sxs-lookup"><span data-stu-id="d82ab-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="d82ab-115">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d82ab-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="d82ab-116">Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="d82ab-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="d82ab-117">Klicken Sie auf **neu** , und klicken Sie dann auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="d82ab-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="d82ab-118">Geben Sie einen Namen für die Benutzerrichtlinie für den externen Zugriff ein.</span><span class="sxs-lookup"><span data-stu-id="d82ab-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="d82ab-119">Geben Sie eine Beschreibung für die Benutzerrichtlinie für den externen Zugriff an.</span><span class="sxs-lookup"><span data-stu-id="d82ab-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="d82ab-120">Wählen Sie **Kommunikation mit Verbundbenutzern aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="d82ab-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="d82ab-121">Wählen Sie **Kommunikation mit XMPP-Verbundbenutzern aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="d82ab-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="d82ab-122">Klicken Sie auf **Commit** , um Ihre Änderungen an der Website-oder Benutzerrichtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d82ab-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

