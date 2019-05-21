---
title: Planen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: In diesem Thema erfahren Sie, wie Sie in Skype for Business Server 2015, dem kumulativen Update vom November 2015, die gemeinsame Leitungsdarstellung (SLA) planen.
ms.openlocfilehash: 966c9f32a27ba936e880bdb51690bcefed4ffbe4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276447"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="38844-103">Planen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="38844-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="38844-104">In diesem Thema erfahren Sie, wie Sie in Skype for Business Server 2015, dem kumulativen Update vom November 2015, die gemeinsame Leitungsdarstellung (SLA) planen.</span><span class="sxs-lookup"><span data-stu-id="38844-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="38844-105">Die Darstellung der freigegebenen Zeile ist eine Funktion in Skype for Business für die Behandlung mehrerer Anrufe an eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="38844-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="38844-106">SLA kann alle Enterprise-VoIP-aktivierten Skype for Business-Benutzer als freigegebene Nummer mit mehreren Zeilen konfigurieren, um auf mehrere Anrufe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="38844-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="38844-107">Die Anrufe werden für die freigegebene Nummer nicht tatsächlich empfangen, sondern an Benutzer weitergeleitet, die als Stellvertretungen für die freigegebene Nummer fungieren.</span><span class="sxs-lookup"><span data-stu-id="38844-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="38844-108">Jeder Delegierte kann den Anruf annehmen, während die restlichen Teilnehmer eine Benachrichtigung auf dem Telefon erhalten, wer den Anruf aufgenommen hat und welche Zeile damit ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="38844-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="38844-109">Die Anzahl der Zeilen und die Stellvertretungen können für eine freigegebene Nummer in SLA konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="38844-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="38844-110">Darüber hinaus können erweiterte Optionen wie BusyOption (was in einer Situation geschieht, wenn alle Zeilen ausgelastet sind) und MissedCallOption (der Fall, in dem keiner der Stellvertretungen einen Anruf annimmt) auch für eine freigegebene Nummer konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="38844-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="38844-111">SLA wird nur auf den folgenden Telefongeräten unterstützt (es wird nicht für Skype for Business-Clients auf Computern, Mobiltelefonen oder anderen Geräten unterstützt):</span><span class="sxs-lookup"><span data-stu-id="38844-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="38844-112">Polycom VVX300 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="38844-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="38844-113">Polycom VVX400 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="38844-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="38844-114">Polycom VVX500 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="38844-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="38844-115">Polycom VVX600 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="38844-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="38844-116">SLA ist ein neues Feature in Skype for Business Server, 2015, Kumulatives Update vom November.</span><span class="sxs-lookup"><span data-stu-id="38844-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="38844-117">Informationen zum Bereitstellen von SLA finden Sie unter [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="38844-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="38844-118">Liste der Funktionen</span><span class="sxs-lookup"><span data-stu-id="38844-118">Feature List</span></span>

<span data-ttu-id="38844-119">Das Einrichten einer SLA-Gruppe macht Folgendes möglich:</span><span class="sxs-lookup"><span data-stu-id="38844-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="38844-p102">Alle Stellvertretungen in der Gruppe können eingehende Anrufe für dieselbe gemeinsam genutzte Nummer annehmen. Diese Anrufe können Festnetz- oder SIP-Anrufe sein.</span><span class="sxs-lookup"><span data-stu-id="38844-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="38844-122">Stellvertretungen können Anrufe halten und annehmen.</span><span class="sxs-lookup"><span data-stu-id="38844-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="38844-123">Stellvertretungen können Anrufe an eine Nummer außerhalb der SLA-Gruppe weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="38844-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="38844-124">Stellvertretungen bekommen angezeigt, wie viele Anrufe es aktuell für die gemeinsam genutzte Nummer gibt, und sie können den Status jedes einzelnen Anrufs einsehen.</span><span class="sxs-lookup"><span data-stu-id="38844-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="38844-p103">Sie können eine maximale Anzahl gleichzeitiger Anrufe für die gemeinsam genutzte Nummer konfigurieren. Sie können auch einstellen, wie zusätzliche Anrufe behandelt werden sollen, wenn die maximale Anzahl erreicht worden ist. Zusätzliche Anrufe können mit einem Besetztzeichen abgewiesen, an eine alternative Nummer oder an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="38844-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="38844-p104">Sie können konfigurieren, wie entgangene Anrufe (solche, die nach einer festgelegten Zeit nicht angenommen worden sind) behandelt werden sollen. Wenn Sie Voicemail für die Gruppenidentität aktivieren, gehen entgangene Anrufe automatisch an die Voicemail. Wenn Voicemail für die Gruppenidentität (gemeinsam genutzte Nummer) nicht aktiviert ist, können Sie wählen, ob entgangene Anrufe mit einem Besetztzeichen abgewiesen, an eine alternative Nummer weitergeleitet oder getrennt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="38844-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

