---
title: Konfigurieren von Trunks in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Im Rahmen der Bereitstellung von Enterprise-VoIP können Sie einen Trunk zwischen einem Vermittlungsserver und eines oder mehrerer Peers zum öffentlichen Telefonnetz (PSTN) Netzwerkkonnektivität für Enterprise-VoIP-Clients und Geräte in Ihrer Organisation bereitstellen konfigurieren.
ms.openlocfilehash: 293685436997833c21dbd7b0d98521202e1beb99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896264"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="5adec-103">Konfigurieren von Trunks in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="5adec-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="5adec-104">Im Rahmen der Bereitstellung von Enterprise-VoIP können Sie einen Trunk zwischen einem Vermittlungsserver und mindestens eine der folgenden Peers zum öffentlichen Telefonnetz (PSTN) Netzwerkkonnektivität für Enterprise-VoIP-Clients und Geräte in Ihrer Organisation bereitstellen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="5adec-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="5adec-105">SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten</span><span class="sxs-lookup"><span data-stu-id="5adec-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="5adec-106">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="5adec-106">PSTN gateway</span></span>
- <span data-ttu-id="5adec-107">Nebenstellenanlage (Private Branch Exchange, PBX)</span><span class="sxs-lookup"><span data-stu-id="5adec-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="5adec-108">Weitere Informationen hierzu finden Sie unter [Planen der PSTN-Konnektivität in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="5adec-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5adec-109">Vor Beginn des trunkkonfiguration stellen Sie sicher, dass die Topologie erstellt wurde und dem Vermittlungsserver und seinen Peer konfiguriert und miteinander verknüpft wurden.</span><span class="sxs-lookup"><span data-stu-id="5adec-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="5adec-110">Weitere Informationen hierzu finden Sie unter [Definieren eines Gateways im Topologie-Generator in Skype für Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="5adec-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5adec-111">Als Bestandteil der trunkkonfiguration können Sie die Skype für Business Server Media Bypass-Feature ermöglicht Medien, für die Umgehung des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="5adec-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="5adec-112">Trunks mit oder ohne medienumgehung konfiguriert werden können, aber es wird dringend empfohlen, dass Sie ihn aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5adec-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="5adec-113">Weitere Informationen hierzu finden Sie unter [Plan für Medien in Skype für Unternehmen zu umgehen](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="5adec-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
