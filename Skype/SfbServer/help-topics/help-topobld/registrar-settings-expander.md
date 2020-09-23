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
# <a name="registrar-settings-expander"></a>Registrierungseinstellungen – Erweiterung
 
Ausfallsicherheit bietet hohe Verfügbarkeit und Notfallwiederherstellung für den registrierungsstellenpool. Durch Bereitstellung einer Sicherungsregistrierung für den Fall eines Ausfalls der primären Registrierung kann die Sicherungsregistrierung die Aufgabe der ausgefallenen Registrierung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann, je nachdem, welche Systeme mit der primären Registrierung ausgefallen sind, die Funktionalität möglicherweise eingeschränkt sein.
  
Im Abschnitt **Ausfallsicherheit** des Dialogfelds **Eigenschaften bearbeiten** Ihrer Survivable Branch Appliance oder Ihres Survivable Branch Servers können Sie die folgenden Einstellungen ändern:
  
- **Zugeordneter Benutzer Dienst und sicherungsregistrierungspool** Wählen Sie in der Dropdownliste die Enterprise Edition-Front-End-Pool oder Standard Edition Front-End-Server aus, die als Sicherungs Registrierungsstelle für die Survivable Branch Appliance oder Survivable Branch Server fungieren soll.
    
- **Aktivieren von Failover und Failback** Wählen Sie diese Einstellung, um die automatische Erkennung einer fehlgeschlagenen Registrierungsstelle und die automatische Ermittlung zu ermöglichen, dass die primäre Registrierungsstelle gesichert ist und bereit ist, den Registrierungsprozess fortzusetzen.
    
- **Fehler Erkennungsintervall (Sek.)** Geben Sie die Anzahl der Sekunden ein, die verstreichen sollen, bevor festgestellt wird, dass die primäre Registrierungsstelle fehlgeschlagen ist. Der Standardwert ist 120 Sekunden. Dieses Feld ist erforderlich, wenn Sie **Failover und Fallback aktivieren** auswählen.
    
- **Rückfall Erkennungsintervall (Sek.)** Geben Sie die Anzahl der Sekunden ein, die verstreichen sollen, bevor festgestellt wird, dass die primäre Registrierungsstelle gesichert wird. Der Standardwert ist 240 Sekunden. Dieses Feld ist erforderlich, wenn Sie **Failover und Fallback aktivieren** auswählen.
    
> [!IMPORTANT]
> Wenn Sie das Ausfall- und Fallbackerkennungsintervall festlegen, sollten Sie kein Intervall eingeben, das für das Auslösen eines Failovers oder Fallbacks sorgt, wenn die Registrierung kurzfristig nicht reagiert. Je nach Auslastung des Pools oder der Server ist es möglich, dass die primäre Registrierung ggf. kurzfristig nicht reagiert. 
  

