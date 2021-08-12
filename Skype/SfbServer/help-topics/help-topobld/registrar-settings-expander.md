---
title: Einstellungen der Registrierungsstelle – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Resilienz bietet hohe Verfügbarkeit und Notfallwiederherstellung für den Registrierungsstellenpool. Durch Bereitstellung einer Sicherungsregistrierung für den Fall eines Ausfalls der primären Registrierung kann die Sicherungsregistrierung die Aufgabe der ausgefallenen Registrierung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann, je nachdem, welche Systeme mit der primären Registrierung ausgefallen sind, die Funktionalität möglicherweise eingeschränkt sein.
ms.openlocfilehash: 75184413222c2de6d580b1ae088b4d65bc7e9851fd10aaaba6b303daa1a53e5e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329639"
---
# <a name="registrar-settings-expander"></a>Einstellungen der Registrierungsstelle – Erweiterung
 
Resilienz bietet hohe Verfügbarkeit und Notfallwiederherstellung für den Registrierungsstellenpool. Durch Bereitstellung einer Sicherungsregistrierung für den Fall eines Ausfalls der primären Registrierung kann die Sicherungsregistrierung die Aufgabe der ausgefallenen Registrierung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann, je nachdem, welche Systeme mit der primären Registrierung ausgefallen sind, die Funktionalität möglicherweise eingeschränkt sein.
  
Im Abschnitt **Ausfallsicherheit** des Dialogfelds **Eigenschaften bearbeiten** Ihrer Survivable Branch Appliance oder Ihres Survivable Branch Servers können Sie die folgenden Einstellungen ändern:
  
- **Zugeordneter Benutzerdienst und Sicherungsregistrierungsstellenpool** Wählen Sie in der Dropdownliste den Enterprise Edition Front-End-Pool oder Standard Edition Front-End-Server aus, der als Sicherungsregistrierungsstelle für die Survivable Branch Appliance oder den Survivable Branch Server fungieren soll.
    
- **Aktivieren von Failover und Failback** Wählen Sie diese Einstellung aus, um die automatische Erkennung einer fehlgeschlagenen Registrierungsstelle und die automatische Bestimmung zu ermöglichen, dass die primäre Registrierungsstelle gesichert ist und bereit ist, den Registrierungsstellenprozess fortzusetzen.
    
- **Fehlererkennungsintervall (s)** Geben Sie die Anzahl der Sekunden ein, die verstrichen sein sollten, bevor festgestellt wird, dass die primäre Registrierungsstelle fehlgeschlagen ist. Der Standardwert ist 120 Sekunden. Dieses Feld ist erforderlich, wenn Sie **Failover und Fallback aktivieren** auswählen.
    
- **Fallbackerkennungsintervall (s)** Geben Sie die Anzahl der Sekunden ein, die verstrichen sein sollten, bevor festgestellt wird, dass die primäre Registrierungsstelle gesichert ist. Der Standardwert ist 240 Sekunden. Dieses Feld ist erforderlich, wenn Sie **Failover und Fallback aktivieren** auswählen.
    
> [!IMPORTANT]
> Wenn Sie das Ausfall- und Fallbackerkennungsintervall festlegen, sollten Sie kein Intervall eingeben, das für das Auslösen eines Failovers oder Fallbacks sorgt, wenn die Registrierung kurzfristig nicht reagiert. Je nach Auslastung des Pools oder der Server ist es möglich, dass die primäre Registrierung ggf. kurzfristig nicht reagiert. 
  

