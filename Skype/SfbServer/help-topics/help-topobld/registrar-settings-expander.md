---
title: Registrierungseinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Die Widerstandsfähigkeit bietet eine höhere Verfügbarkeit und Disaster Recovery für den Registrar-Pool. Durch die Bereitstellung einer Sicherungs Registrierungsstelle bei einem Ausfall der primären Registrierungsstelle kann die Sicherungs Registrierungsstelle die fehlerhafte Registrierungsstelle übernehmen, sodass sich die Benutzer anmelden und kommunizieren können. Benutzer können möglicherweise eine reduzierte Funktionalität erfahren, je nachdem, welche Systeme mit der primären Registrierungsstelle fehlgeschlagen sind.
ms.openlocfilehash: bac382486b45acbb2e25d3be26d23ea67f1aa15b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696730"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="33887-105">Registrierungseinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="33887-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="33887-106">Die Widerstandsfähigkeit bietet eine höhere Verfügbarkeit und Disaster Recovery für den Registrar-Pool.</span><span class="sxs-lookup"><span data-stu-id="33887-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="33887-107">Durch die Bereitstellung einer Sicherungs Registrierungsstelle bei einem Ausfall der primären Registrierungsstelle kann die Sicherungs Registrierungsstelle die fehlerhafte Registrierungsstelle übernehmen, sodass sich die Benutzer anmelden und kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="33887-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="33887-108">Benutzer können möglicherweise eine reduzierte Funktionalität erfahren, je nachdem, welche Systeme mit der primären Registrierungsstelle fehlgeschlagen sind.</span><span class="sxs-lookup"><span data-stu-id="33887-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="33887-109">Im Abschnitt " **Widerstandsfähigkeit** " des Dialogfelds " **Eigenschaften bearbeiten** " für die überlebensfähige Branch-Appliance oder den Überlebenden Branch-Server können Sie die folgenden Einstellungen ändern:</span><span class="sxs-lookup"><span data-stu-id="33887-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="33887-110">**Zugehöriger Benutzer Dienst und sicherungsregistrierungspool** Wählen Sie in der Dropdownliste den Enterprise Edition-Front-End-Pool oder den Standard Edition-Front-End-Server aus, der als Sicherungs Registrierungsstelle für die Survivable Branch Appliance oder den Survivable Branch-Server fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="33887-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="33887-111">**Aktivieren von Failover und Failback** Wählen Sie diese Einstellung aus, um die automatische Erkennung einer fehlgeschlagenen Registrierungsstelle und die automatische Ermittlung zu ermöglichen, dass die primäre Registrierungsstelle gesichert ist und den Registrierungsprozess fortsetzen kann.</span><span class="sxs-lookup"><span data-stu-id="33887-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="33887-112">**Fehler Erkennungsintervall (Sek.)** Geben Sie die Anzahl der Sekunden ein, die verstreichen sollen, bevor festgestellt wird, dass die primäre Registrierungsstelle fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="33887-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="33887-113">Der Standardwert ist 120 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="33887-113">The default value is 120 seconds.</span></span> <span data-ttu-id="33887-114">Dieses Feld ist erforderlich, wenn Sie **Failover und Failback aktivieren**auswählen.</span><span class="sxs-lookup"><span data-stu-id="33887-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="33887-115">**Fall Back Erkennungsintervall (Sek.)** Geben Sie die Anzahl der Sekunden ein, die verstreichen sollen, bevor festgestellt wird, dass die primäre Registrierungsstelle gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="33887-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="33887-116">Der Standardwert ist 240 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="33887-116">The default value is 240 seconds.</span></span> <span data-ttu-id="33887-117">Dieses Feld ist erforderlich, wenn Sie **Failover und Fallback aktivieren**auswählen.</span><span class="sxs-lookup"><span data-stu-id="33887-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="33887-118">Achten Sie beim Definieren des Fehler Erkennungs Intervalls und des Fall Back Erkennungs Intervalls darauf, dass kein Intervall eingegeben wird, das das Failover und das Fallback verursacht, wenn die Registrierungsstelle für einen kurzen Zeitraum nicht antwortet.</span><span class="sxs-lookup"><span data-stu-id="33887-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="33887-119">Es ist möglich, dass die primäre Registrierungsstelle aufgrund des Ladens des Pools oder der Server für kurze Zeiträume nicht reagiert.</span><span class="sxs-lookup"><span data-stu-id="33887-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

