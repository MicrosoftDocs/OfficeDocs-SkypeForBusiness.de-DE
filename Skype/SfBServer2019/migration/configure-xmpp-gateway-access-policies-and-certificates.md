---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Die XMPP-Föderation definiert eine externe Bereitstellung, die auf dem Extensible Messaging and Presence Protocol (XMPP) basiert. Eine XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:'
ms.openlocfilehash: 01adcbe06718068e84844f704858e04198b197b2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239291"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="01a50-104">Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways</span><span class="sxs-lookup"><span data-stu-id="01a50-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="01a50-105">Die XMPP-Föderation definiert eine externe Bereitstellung, die auf dem Extensible Messaging and Presence Protocol (XMPP) basiert.</span><span class="sxs-lookup"><span data-stu-id="01a50-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="01a50-106">Eine XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:</span><span class="sxs-lookup"><span data-stu-id="01a50-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="01a50-107">Chat und Anwesenheit – nur für Personen</span><span class="sxs-lookup"><span data-stu-id="01a50-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="01a50-108">Erstellen von XMPP-verbundkontakten im Skype for Business-Client</span><span class="sxs-lookup"><span data-stu-id="01a50-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="01a50-109">Wenn Sie Richtlinien für die Unterstützung von XMPP-Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, nicht aber für Benutzer von SIP-Chat Diensten (Session Initiation Protocol) oder SIP-Verbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="01a50-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="01a50-110">Sie konfigurieren einen XMPP-Verbundpartner für jede XMPP-Verbunddomäne, die es Ihren Benutzern ermöglichen soll, Kontakte hinzuzufügen und mit Ihnen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="01a50-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="01a50-111">Sobald die Richtlinien vorhanden sind, müssen Sie die XMPP-Gateway-Zertifikate konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="01a50-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="01a50-112">Die XMPP-Funktionalität ist in Skype for Business Server 2019 veraltet, kann aber auf einem Legacy Server in Koexistenz mit Skype for Business Server 2019 fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="01a50-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="01a50-113">Stellen Sie sicher, dass Sie bereits den Legacy Server (Skype for Business Server 2015/lync Server 2013) XMPP-Gateway bereitgestellt haben und die Zugriffsrichtlinien so konfiguriert haben, dass Benutzer für Legacy-XMPP-Gateways aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="01a50-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="01a50-114">Ausführliche Informationen finden Sie unter [Migrieren von XMPP](migrating-xmpp-federation.md)-Föderationen.</span><span class="sxs-lookup"><span data-stu-id="01a50-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="01a50-115">Konfigurieren einer Richtlinie für den externen Zugriff zum Aktivieren von Benutzern für Legacy-XMPP-Gateways</span><span class="sxs-lookup"><span data-stu-id="01a50-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="01a50-116">Öffnen Sie das Legacy-Control Panel für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="01a50-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="01a50-117">Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="01a50-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="01a50-118">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="01a50-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="01a50-119">Geben Sie einen Namen für die Benutzerrichtlinie für den externen Zugriff ein.</span><span class="sxs-lookup"><span data-stu-id="01a50-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="01a50-120">Geben Sie eine Beschreibung für die Benutzerrichtlinie für den externen Zugriff an.</span><span class="sxs-lookup"><span data-stu-id="01a50-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="01a50-121">Wählen Sie **Kommunikation mit Verbundbenutzern aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="01a50-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="01a50-122">Wählen Sie **Kommunikation mit XMPP-Verbundbenutzern aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="01a50-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="01a50-123">Klicken Sie auf **Commit** , um Ihre Änderungen an der Website-oder Benutzerrichtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="01a50-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

