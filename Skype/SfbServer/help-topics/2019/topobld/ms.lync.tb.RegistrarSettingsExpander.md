---
title: Einstellungen der Registrierungsstelle – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: Ausfallsicherheit bietet hohe Verfügbarkeit und Notfallwiederherstellung für den Registrierungsstellenpool. Durch Bereitstellung einer Sicherungsregistrierung für den Fall eines Ausfalls der primären Registrierung kann die Sicherungsregistrierung die Aufgabe der ausgefallenen Registrierung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann, je nachdem, welche Systeme mit der primären Registrierung ausgefallen sind, die Funktionalität möglicherweise eingeschränkt sein.
ms.openlocfilehash: cb7a5204b3b282c73f9440e61267b723b112b735
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822115"
---
# <a name="registrar-settings-expander"></a>Einstellungen der Registrierungsstelle – Erweiterung
 
Ausfallsicherheit bietet hohe Verfügbarkeit und Notfallwiederherstellung für den Registrierungsstellenpool. Durch Bereitstellung einer Sicherungsregistrierung für den Fall eines Ausfalls der primären Registrierung kann die Sicherungsregistrierung die Aufgabe der ausgefallenen Registrierung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann, je nachdem, welche Systeme mit der primären Registrierung ausgefallen sind, die Funktionalität möglicherweise eingeschränkt sein.
  
Im Abschnitt **Ausfallsicherheit** des Dialogfelds **Eigenschaften bearbeiten** Ihrer Survivable Branch Appliance oder Ihres Survivable Branch Servers können Sie die folgenden Einstellungen ändern:
  
- **Zugeordneter Benutzerdienst und Sicherungsregistrierungspool** Wählen Sie in der Dropdownliste den Front-End-Pool der Enterprise Edition oder den Standard Edition-Front-End-Server aus, der als Sicherungsregistrierungsstelle für die Survivable Branch Appliance oder den Survivable Branch Server fungieren soll.
    
- **Aktivieren von Failover und Failback** Wählen Sie diese Einstellung aus, um die automatische Erkennung einer ausgefallenen Registrierung und die automatische Bestimmung zu ermöglichen, dass die primäre Registrierung wieder betriebsbereit ist und den Registrierungsprozess fortsetzen kann.
    
- **Fehlererkennungsintervall (s)** Geben Sie die Anzahl der Sekunden ein, die verstreichen sollen, bevor festgestellt wird, dass die primäre Registrierung fehlgeschlagen ist. Der Standardwert ist 120 Sekunden. Dieses Feld ist erforderlich, wenn Sie **Failover und Fallback aktivieren** auswählen.
    
- **Fallbackerkennungsintervall (Sek.)** Geben Sie die Anzahl der Sekunden ein, die verstreichen sollen, bevor festgestellt wird, dass die primäre Registrierung gesichert wird. Der Standardwert ist 240 Sekunden. Dieses Feld ist erforderlich, wenn Sie **Failover und Fallback aktivieren** auswählen.
    
> [!IMPORTANT]
> Wenn Sie das Ausfall- und Fallbackerkennungsintervall festlegen, sollten Sie kein Intervall eingeben, das für das Auslösen eines Failovers oder Fallbacks sorgt, wenn die Registrierung kurzfristig nicht reagiert. Je nach Auslastung des Pools oder der Server ist es möglich, dass die primäre Registrierung ggf. kurzfristig nicht reagiert. 
  

