---
title: SBA-Einstellungen der Registrierungsstelle – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie bearbeiten die Einstellungen für die Widerstandsfähigkeit und konfigurieren die folgenden Eigenschaften:'
ms.openlocfilehash: 4297f70acfbf695d8dcfdcdb58a09d8f608add71
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701640"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="64dd5-103">SBA-Einstellungen der Registrierungsstelle – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="64dd5-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="64dd5-104">Sie bearbeiten die Einstellungen für die **Widerstandsfähigkeit** und konfigurieren die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="64dd5-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="64dd5-105">Wählen Sie in der Liste **zugeordneter Benutzer Dienst und sicherungsregistrierungspool** aus.</span><span class="sxs-lookup"><span data-stu-id="64dd5-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="64dd5-106">Aktivieren Sie optional das Kontrollkästchen **Automatisches Failover und Failback für VoIP** .</span><span class="sxs-lookup"><span data-stu-id="64dd5-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="64dd5-107">Konfigurieren Sie das **Erkennungsintervall für Sprachfehler (SEK)** und das **sprach-Failback-Intervall (SEK)**.</span><span class="sxs-lookup"><span data-stu-id="64dd5-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="64dd5-108">Standardmäßig sind die Intervalle 120 Sekunden für die Sprachfehler Erkennung und 240 Sekunden für sprach-Failback.</span><span class="sxs-lookup"><span data-stu-id="64dd5-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="64dd5-109">Die Anzahl der Sekunden, die Sie für die Failover-und Failback-Intervalle definieren, sollten sorgfältig getestet werden, um sicherzustellen, dass die Widerstandsfähigkeit wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="64dd5-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="64dd5-110">Wenn Sie das Intervall auf "gering" (also weniger als 120 Sekunden) oder das Failover und die Failback-Einstellung zu eng festlegen, kann dies zu einem tatsächlichen Failover und Failback führen, die nicht erwartungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="64dd5-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="64dd5-111">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="64dd5-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="64dd5-112">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="64dd5-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="64dd5-113">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="64dd5-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="64dd5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64dd5-114">See also</span></span>

[<span data-ttu-id="64dd5-115">Planung für Enterprise-VoIP-Resilienz</span><span class="sxs-lookup"><span data-stu-id="64dd5-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
