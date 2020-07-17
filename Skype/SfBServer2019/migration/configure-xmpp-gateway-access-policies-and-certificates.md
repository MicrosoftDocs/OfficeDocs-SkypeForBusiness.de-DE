---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Der XMPP-Partnerverbund definiert eine externe Bereitstellung basierend auf dem XMPP-Protokoll (eXtensible Messaging and Presence Protocol). Eine XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753935"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="31b87-104">Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways</span><span class="sxs-lookup"><span data-stu-id="31b87-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="31b87-105">Der XMPP-Partnerverbund definiert eine externe Bereitstellung basierend auf dem XMPP-Protokoll (eXtensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="31b87-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="31b87-106">Eine XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:</span><span class="sxs-lookup"><span data-stu-id="31b87-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="31b87-107">Chat und Anwesenheit – nur Person zu Person</span><span class="sxs-lookup"><span data-stu-id="31b87-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="31b87-108">Erstellen von XMPP-verbundkontakten im Skype for Business-Client</span><span class="sxs-lookup"><span data-stu-id="31b87-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="31b87-109">Wenn Sie Richtlinien für die Unterstützung von XMPP-Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, jedoch nicht für Benutzer von SIP-Chat (Session Initiation Protocol)-Dienstanbietern oder SIP-Verbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="31b87-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="31b87-110">Sie konfigurieren einen XMPP-Verbundpartner für jede XMPP-Verbunddomäne, die Sie Ihren Benutzern erlauben möchten, Kontakte hinzuzufügen und mit Ihnen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="31b87-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="31b87-111">Wenn die Richtlinien vorhanden sind, müssen Sie die XMPP-Gatewayzertifikate konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="31b87-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="31b87-112">Die XMPP-Funktionalität ist in Skype for Business Server 2019 veraltet, kann aber in einem Legacy Server in Koexistenz mit Skype for Business Server 2019 fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="31b87-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="31b87-113">Stellen Sie sicher, dass Sie das XMPP-Gateway für Legacy Server (Skype for Business Server 2015/lync Server 2013) bereits bereitgestellt haben, und konfigurieren Sie die Zugriffsrichtlinien, um Benutzer für das Vorgänger-XMPP-Gateway zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="31b87-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="31b87-114">Ausführliche Informationen finden Sie unter [Migrating XMPP Federation](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="31b87-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="31b87-115">Konfigurieren einer Richtlinie für den externen Zugriff zur Aktivierung von Benutzern für das Vorgänger-XMPP-Gateway</span><span class="sxs-lookup"><span data-stu-id="31b87-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="31b87-116">Öffnen Sie die Legacy Skype for Business Server Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="31b87-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="31b87-117">Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff**, und klicken Sie dann auf **Externe Zugriffsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="31b87-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="31b87-118">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="31b87-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="31b87-119">Geben Sie einen Namen für die externe Benutzerzugriffsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="31b87-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="31b87-120">Geben Sie eine Beschreibung für die externe Benutzerzugriffsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="31b87-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="31b87-121">Wählen Sie **Kommunikation mit Partnerbenutzern aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="31b87-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="31b87-122">Wählen Sie **Kommunikation mit XMPP-Partnerverbundbenutzern aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="31b87-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="31b87-123">Klicken Sie auf **Commit ausführen**, um Ihre Änderungen am Standort oder an der Benutzerrichtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="31b87-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

