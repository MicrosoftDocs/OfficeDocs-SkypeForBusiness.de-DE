---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'XMPP-Verbund definiert eine externe Bereitstellung auf Grundlage von eXtensible Messaging and Presence Protocol (XMPP). XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzern anhand folgender Kriterien:'
ms.openlocfilehash: 65ef8904660eaa75ddd10238a6561ea91b9f7278
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889973"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="b56d7-104">Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways</span><span class="sxs-lookup"><span data-stu-id="b56d7-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="b56d7-105">XMPP-Verbund definiert eine externe Bereitstellung auf Grundlage von eXtensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="b56d7-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="b56d7-106">XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzern anhand folgender Kriterien:</span><span class="sxs-lookup"><span data-stu-id="b56d7-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="b56d7-107">Sofortnachrichten und Anwesenheit – nur zwischen Personen</span><span class="sxs-lookup"><span data-stu-id="b56d7-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="b56d7-108">Erstellung von XMPP-Verbundkontakten auf die Skype für Business-client</span><span class="sxs-lookup"><span data-stu-id="b56d7-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="b56d7-109">Beim Konfigurieren von Richtlinien für die Unterstützung von XMPP-Verbundpartner, die Richtlinien gelten für Benutzer von XMPP federated Domänen, aber nicht für Benutzer von Session Initiation-Protokoll (SIP) instant messaging (IM) Service Provider oder SIP verbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="b56d7-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="b56d7-110">Konfigurieren Sie eine XMPP-Verbundpartner für jede federated XMPP-Domäne, die Sie Ihre Benutzer die Kontakte hinzufügen und die Kommunikation mit zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="b56d7-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="b56d7-111">Nachdem die Richtlinien vorhanden sind, müssen Sie die Zertifikate XMPP-Gateway zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b56d7-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b56d7-112">XMPP-Funktionen ist in Skype für Business Server 2019 veraltet, sondern in einen Legacyserver zusammen mit Skype für Business Server 2019 fortgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b56d7-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="b56d7-113">Stellen Sie sicher, dass den Server der Vorversionen bereits bereitgestellt haben (Skype für Business Server 2015 / Lync Server 2013) XMPP-Gateway und Richtlinien für den Zugriff zum Aktivieren von Benutzern für legacy XMPP-Gateway konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b56d7-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="b56d7-114">Weitere Informationen hierzu finden Sie unter [Migrieren von XMPP-Verbund](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="b56d7-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="b56d7-115">Konfigurieren einer Richtlinie für externen Zugriff zum Aktivieren von Benutzern für legacy-XMPP-Gateway</span><span class="sxs-lookup"><span data-stu-id="b56d7-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="b56d7-116">Öffnen Sie die Vorversion Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="b56d7-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b56d7-117">Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff**und klicken Sie dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="b56d7-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="b56d7-118">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="b56d7-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="b56d7-119">Geben Sie einen Namen für die externe benutzerzugriffsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="b56d7-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="b56d7-120">Geben Sie eine Beschreibung für die externe benutzerzugriffsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="b56d7-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="b56d7-121">Wählen Sie **Kommunikation mit Partnerbenutzern aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="b56d7-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="b56d7-122">Wählen Sie **Kommunikation mit XMPP partnerverbundbenutzern aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="b56d7-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="b56d7-123">Klicken Sie auf **Commit** , um Ihre Änderungen an der Standort- oder Benutzerrichtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b56d7-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

