---
title: Planen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: In diesem Thema erfahren, wie für freigegebene Zeile Darstellung (SLA) in Skype Business Server 2015 November 2015 geplant kumulative Update.
ms.openlocfilehash: b65d637426b0a8533089b21021bce566373ca9f1
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884508"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="7703d-103">Planen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7703d-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7703d-104">In diesem Thema erfahren, wie für freigegebene Zeile Darstellung (SLA) in Skype Business Server 2015 November 2015 geplant kumulative Update.</span><span class="sxs-lookup"><span data-stu-id="7703d-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="7703d-105">Darstellung einer freigegebenen Linie ist ein Feature in Skype für Unternehmen für die Verarbeitung mehrerer Anrufe an eine bestimmte Anzahl freigegebenen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7703d-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="7703d-106">SLA konfigurieren kann Enterprise Voice aktiviert Skype für Geschäftsbenutzer als freigegebene Zahl mit mehrere Zeilen auf mehrere Aufrufe reagieren.</span><span class="sxs-lookup"><span data-stu-id="7703d-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="7703d-107">Die Anrufe werden nicht auf die freigegebenen Anzahl tatsächlich empfangen, sie werden stattdessen an Benutzer, die eine Stellvertretung für die freigegebenen Anzahl übernehmen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="7703d-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="7703d-108">Keines der Stellvertretungen kann Anruf auswählen, während Sie der Rest der Delegaten erhalten eine Benachrichtigung über ein Telefon zu, die den Anruf entnommen und welcher Zeile dementsprechend ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="7703d-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="7703d-109">Sowohl die Anzahl der Zeilen und an die Stellvertretungen können für eine freigegebene Zahl in SLA konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7703d-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="7703d-110">Darüber hinaus erweiterte Optionen an, wie BusyOption (was in einer Situation geschieht, wenn alle Zeilen beschäftigt sind) und MissedCallOption (die Groß-/Kleinschreibung in welche die Stellvertretungen auswählen einen Aufruf keines), kann auch für eine freigegebene Anzahl konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7703d-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="7703d-111">SLA wird nur unter den folgenden Telefone unterstützt (es ist nicht für Skype für Business-Clients auf Computern, Mobiltelefone oder andere Geräte unterstützt):</span><span class="sxs-lookup"><span data-stu-id="7703d-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="7703d-112">Polycom VVX300 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="7703d-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="7703d-113">Polycom VVX400 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="7703d-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="7703d-114">Polycom VVX500 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="7703d-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="7703d-115">Polycom VVX600 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="7703d-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="7703d-116">Vereinbarung zum SERVICELEVEL ist ein neues Feature in Skype für Business Server 2015 November Kumulatives Update.</span><span class="sxs-lookup"><span data-stu-id="7703d-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="7703d-117">Informationen zum Bereitstellen von SLA finden Sie unter [Shared Zeile Darstellung in Skype für Business Server 2015 bereitstellen](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="7703d-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="7703d-118">Liste der Funktionen</span><span class="sxs-lookup"><span data-stu-id="7703d-118">Feature List</span></span>

<span data-ttu-id="7703d-119">Das Einrichten einer SLA-Gruppe macht Folgendes möglich:</span><span class="sxs-lookup"><span data-stu-id="7703d-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="7703d-p102">Alle Stellvertretungen in der Gruppe können eingehende Anrufe für dieselbe gemeinsam genutzte Nummer annehmen. Diese Anrufe können Festnetz- oder SIP-Anrufe sein.</span><span class="sxs-lookup"><span data-stu-id="7703d-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="7703d-122">Stellvertretungen können Anrufe halten und annehmen.</span><span class="sxs-lookup"><span data-stu-id="7703d-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="7703d-123">Stellvertretungen können Anrufe an eine Nummer außerhalb der SLA-Gruppe weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="7703d-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="7703d-124">Stellvertretungen bekommen angezeigt, wie viele Anrufe es aktuell für die gemeinsam genutzte Nummer gibt, und sie können den Status jedes einzelnen Anrufs einsehen.</span><span class="sxs-lookup"><span data-stu-id="7703d-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="7703d-p103">Sie können eine maximale Anzahl gleichzeitiger Anrufe für die gemeinsam genutzte Nummer konfigurieren. Sie können auch einstellen, wie zusätzliche Anrufe behandelt werden sollen, wenn die maximale Anzahl erreicht worden ist. Zusätzliche Anrufe können mit einem Besetztzeichen abgewiesen, an eine alternative Nummer oder an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7703d-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="7703d-p104">Sie können konfigurieren, wie entgangene Anrufe (solche, die nach einer festgelegten Zeit nicht angenommen worden sind) behandelt werden sollen. Wenn Sie Voicemail für die Gruppenidentität aktivieren, gehen entgangene Anrufe automatisch an die Voicemail. Wenn Voicemail für die Gruppenidentität (gemeinsam genutzte Nummer) nicht aktiviert ist, können Sie wählen, ob entgangene Anrufe mit einem Besetztzeichen abgewiesen, an eine alternative Nummer weitergeleitet oder getrennt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7703d-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

