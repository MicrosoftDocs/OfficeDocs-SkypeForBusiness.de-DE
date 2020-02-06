---
title: Konfigurieren von Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Im Rahmen der Bereitstellung von Enterprise-VoIP können Sie einen trunk zwischen einem Vermittlungs Server und einem oder mehreren Peers konfigurieren, um die PSTN-Konnektivität (Public Switched Telephone Network) für Enterprise-VoIP-Clients und-Geräte in Ihrer Organisation bereitzustellen.
ms.openlocfilehash: 41e92f994606ea2153359546d408335d13a21f88
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817015"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="8856e-103">Konfigurieren von Trunks in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8856e-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="8856e-104">Im Rahmen der Enterprise-VoIP-Bereitstellung können Sie einen trunk zwischen einem Vermittlungs Server und einem oder mehreren der folgenden Peers konfigurieren, um die PSTN-Konnektivität (Public Switched Telephone Network) für Enterprise-VoIP-Clients und-Geräte in Ihrer Organisation bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="8856e-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="8856e-105">SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten</span><span class="sxs-lookup"><span data-stu-id="8856e-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="8856e-106">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="8856e-106">PSTN gateway</span></span>
- <span data-ttu-id="8856e-107">Nebenstellenanlage (Private Branch Exchange, PBX)</span><span class="sxs-lookup"><span data-stu-id="8856e-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="8856e-108">Ausführliche Informationen finden Sie unter [Planen der PSTN-Konnektivität in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="8856e-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8856e-109">Bevor Sie die trunk-Konfiguration beginnen, stellen Sie sicher, dass die Topologie erstellt wurde und dass der Vermittlungs Server und sein Peer konfiguriert und miteinander verknüpft wurden.</span><span class="sxs-lookup"><span data-stu-id="8856e-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="8856e-110">Ausführliche Informationen finden Sie unter [Definieren eines Gateways im Topologie-Generator in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="8856e-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8856e-111">Als Teil der trunk-Konfiguration können Sie die Medien Umgehungsfunktion von Skype for Business Server aktivieren, mit der Medien den Vermittlungsserver umgehen können.</span><span class="sxs-lookup"><span data-stu-id="8856e-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="8856e-112">Trunks kann entweder mit oder ohne aktivierte medienumgehung konfiguriert werden, wir empfehlen jedoch dringend, diese zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8856e-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="8856e-113">Ausführliche Informationen finden Sie unter [Planen der medienumgehung in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="8856e-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
