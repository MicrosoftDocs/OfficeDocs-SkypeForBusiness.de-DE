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
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Ausfallsicherheit bietet hohe Verfügbarkeit und Notfallwiederherstellung für den registrierungsstellenpool. Durch Bereitstellung einer Sicherungsregistrierung für den Fall eines Ausfalls der primären Registrierung kann die Sicherungsregistrierung die Aufgabe der ausgefallenen Registrierung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann, je nachdem, welche Systeme mit der primären Registrierung ausgefallen sind, die Funktionalität möglicherweise eingeschränkt sein.
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217156"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="708c0-105">Registrierungseinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="708c0-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="708c0-106">Ausfallsicherheit bietet hohe Verfügbarkeit und Notfallwiederherstellung für den registrierungsstellenpool.</span><span class="sxs-lookup"><span data-stu-id="708c0-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="708c0-107">Durch Bereitstellung einer Sicherungsregistrierung für den Fall eines Ausfalls der primären Registrierung kann die Sicherungsregistrierung die Aufgabe der ausgefallenen Registrierung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="708c0-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="708c0-108">Bei Benutzern kann, je nachdem, welche Systeme mit der primären Registrierung ausgefallen sind, die Funktionalität möglicherweise eingeschränkt sein.</span><span class="sxs-lookup"><span data-stu-id="708c0-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="708c0-109">Im Abschnitt **Ausfallsicherheit** des Dialogfelds **Eigenschaften bearbeiten** Ihrer Survivable Branch Appliance oder Ihres Survivable Branch Servers können Sie die folgenden Einstellungen ändern:</span><span class="sxs-lookup"><span data-stu-id="708c0-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="708c0-110">**Zugeordneter Benutzer Dienst und sicherungsregistrierungspool** Wählen Sie in der Dropdownliste die Enterprise Edition-Front-End-Pool oder Standard Edition Front-End-Server aus, die als Sicherungs Registrierungsstelle für die Survivable Branch Appliance oder Survivable Branch Server fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="708c0-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="708c0-111">**Aktivieren von Failover und Failback** Wählen Sie diese Einstellung, um die automatische Erkennung einer fehlgeschlagenen Registrierungsstelle und die automatische Ermittlung zu ermöglichen, dass die primäre Registrierungsstelle gesichert ist und bereit ist, den Registrierungsprozess fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="708c0-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="708c0-112">**Fehler Erkennungsintervall (Sek.)** Geben Sie die Anzahl der Sekunden ein, die verstreichen sollen, bevor festgestellt wird, dass die primäre Registrierungsstelle fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="708c0-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="708c0-113">Der Standardwert ist 120 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="708c0-113">The default value is 120 seconds.</span></span> <span data-ttu-id="708c0-114">Dieses Feld ist erforderlich, wenn Sie **Failover und Fallback aktivieren** auswählen.</span><span class="sxs-lookup"><span data-stu-id="708c0-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="708c0-115">**Rückfall Erkennungsintervall (Sek.)** Geben Sie die Anzahl der Sekunden ein, die verstreichen sollen, bevor festgestellt wird, dass die primäre Registrierungsstelle gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="708c0-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="708c0-116">Der Standardwert ist 240 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="708c0-116">The default value is 240 seconds.</span></span> <span data-ttu-id="708c0-117">Dieses Feld ist erforderlich, wenn Sie **Failover und Fallback aktivieren** auswählen.</span><span class="sxs-lookup"><span data-stu-id="708c0-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="708c0-p105">Wenn Sie das Ausfall- und Fallbackerkennungsintervall festlegen, sollten Sie kein Intervall eingeben, das für das Auslösen eines Failovers oder Fallbacks sorgt, wenn die Registrierung kurzfristig nicht reagiert. Je nach Auslastung des Pools oder der Server ist es möglich, dass die primäre Registrierung ggf. kurzfristig nicht reagiert.</span><span class="sxs-lookup"><span data-stu-id="708c0-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

