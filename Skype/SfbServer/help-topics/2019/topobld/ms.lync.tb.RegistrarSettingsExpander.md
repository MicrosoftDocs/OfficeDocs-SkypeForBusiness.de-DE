---
title: Registrierungseinstellungen – Erweiterung
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Resiliency bietet hohe Verfügbarkeit und Disaster Recovery für den registrierungspool an. Durch die Bereitstellung einer Sicherung Registrierung bei einem Ausfall der primären Registrierung, die Sicherung, die Registrierung für die fehlerhafte Registrierung übernehmen kann, können Benutzer anmelden und kommunizieren. Benutzer können potenziell mit eingeschränkter Funktionalität bemerken, je nachdem, welches Systeme mit die primäre Registrierungsstelle ausgefallen.
ms.openlocfilehash: 9d8460f0a883dfabc55153744ba4f3f886b34898
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="13cda-105">Registrierungseinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="13cda-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="13cda-106">Resiliency bietet hohe Verfügbarkeit und Disaster Recovery für den registrierungspool an.</span><span class="sxs-lookup"><span data-stu-id="13cda-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="13cda-107">Durch die Bereitstellung einer Sicherung Registrierung bei einem Ausfall der primären Registrierung, die Sicherung, die Registrierung für die fehlerhafte Registrierung übernehmen kann, können Benutzer anmelden und kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="13cda-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="13cda-108">Benutzer können potenziell mit eingeschränkter Funktionalität bemerken, je nachdem, welches Systeme mit die primäre Registrierungsstelle ausgefallen.</span><span class="sxs-lookup"><span data-stu-id="13cda-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="13cda-109">Im Abschnitt **Ausfallsicherheit** des Dialogfelds **Eigenschaften bearbeiten** für den Survivable Branch Appliance oder einen Survivable Branch Server können Sie die folgenden Einstellungen ändern:</span><span class="sxs-lookup"><span data-stu-id="13cda-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="13cda-110">**Zugeordneter Benutzerdienst und Sicherungsregistrierungsstellen-pool** Wählen Sie in der Dropdownliste den Enterprise Edition-Front-End-Pool oder Standard Edition-Front-End-Server, der als sicherungsregistrierung für die Survivable Branch Appliance oder einen Survivable Branch Server fungieren.</span><span class="sxs-lookup"><span data-stu-id="13cda-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="13cda-111">**Aktivieren von Failover und Failback** Wählen Sie diese Einstellung, um für die automatische Erkennung von einem fehlgeschlagenen zulassen, Registrierung und die automatische Ermittlung, der die primäre Registrierung sichern und Fortsetzen des Prozesses Registrierung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="13cda-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="13cda-112">**Fehler bei Erkennung Intervall (s)** Geben Sie die Anzahl der Sekunden an, die vergehen soll, bevor er bestimmt wird, dass die primäre Registrierungsstelle ausgefallen ist.</span><span class="sxs-lookup"><span data-stu-id="13cda-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="13cda-113">Der Standardwert ist 120 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="13cda-113">The default value is 120 seconds.</span></span> <span data-ttu-id="13cda-114">Dieses Feld ist erforderlich, wenn Sie **Aktivieren Failover und Failback**auswählen.</span><span class="sxs-lookup"><span data-stu-id="13cda-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="13cda-115">**Fallback Erkennung Intervall (s)** Geben Sie die Anzahl der Sekunden an, die vergehen soll, bevor festgestellt wird, das die primäre Registrierungsstelle gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="13cda-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="13cda-116">Der Standardwert ist 240 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="13cda-116">The default value is 240 seconds.</span></span> <span data-ttu-id="13cda-117">Dieses Feld ist erforderlich, wenn Sie **Failover aktivieren und Fallback**auswählen.</span><span class="sxs-lookup"><span data-stu-id="13cda-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="13cda-118">Wenn Sie das Intervall der Ausfall Erkennung und das Intervall fallback Erkennung definieren, werden Sie nicht, die ein Intervall angeben, der bewirkt das Failover und fallback eintritt, wenn die Registrierung nicht für ein kurzer Zeit reagiert.</span><span class="sxs-lookup"><span data-stu-id="13cda-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="13cda-119">Es ist möglich, dass die primäre Registrierung für einen kurzen Zeitraum basierend auf das Laden des Pools oder Servern nicht reagieren kann.</span><span class="sxs-lookup"><span data-stu-id="13cda-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

