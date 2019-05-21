---
title: Registrierungseinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Die Widerstandsfähigkeit bietet eine höhere Verfügbarkeit und Disaster Recovery für den Registrar-Pool. Durch die Bereitstellung einer Sicherungs Registrierungsstelle bei einem Ausfall der primären Registrierungsstelle kann die Sicherungs Registrierungsstelle die fehlerhafte Registrierungsstelle übernehmen, sodass sich die Benutzer anmelden und kommunizieren können. Benutzer können möglicherweise eine reduzierte Funktionalität erfahren, je nachdem, welche Systeme mit der primären Registrierungsstelle fehlgeschlagen sind.
ms.openlocfilehash: d23258e0573136843b4efab19f92ff0a3190c405
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297652"
---
# <a name="registrar-settings-expander"></a>Registrierungseinstellungen – Erweiterung
 
Die Widerstandsfähigkeit bietet eine höhere Verfügbarkeit und Disaster Recovery für den Registrar-Pool. Durch die Bereitstellung einer Sicherungs Registrierungsstelle bei einem Ausfall der primären Registrierungsstelle kann die Sicherungs Registrierungsstelle die fehlerhafte Registrierungsstelle übernehmen, sodass sich die Benutzer anmelden und kommunizieren können. Benutzer können möglicherweise eine reduzierte Funktionalität erfahren, je nachdem, welche Systeme mit der primären Registrierungsstelle fehlgeschlagen sind.
  
Im Abschnitt " **Widerstandsfähigkeit** " des Dialogfelds " **Eigenschaften bearbeiten** " für die überlebensfähige Branch-Appliance oder den Überlebenden Branch-Server können Sie die folgenden Einstellungen ändern:
  
- **Zugehöriger Benutzer Dienst und sicherungsregistrierungspool** Wählen Sie in der Dropdownliste den Enterprise Edition-Front-End-Pool oder den Standard Edition-Front-End-Server aus, der als Sicherungs Registrierungsstelle für die Survivable Branch Appliance oder den Survivable Branch-Server fungieren soll.
    
- **Aktivieren von Failover und Failback** Wählen Sie diese Einstellung aus, um die automatische Erkennung einer fehlgeschlagenen Registrierungsstelle und die automatische Ermittlung zu ermöglichen, dass die primäre Registrierungsstelle gesichert ist und den Registrierungsprozess fortsetzen kann.
    
- **Fehler Erkennungsintervall (Sek.)** Geben Sie die Anzahl der Sekunden ein, die verstreichen sollen, bevor festgestellt wird, dass die primäre Registrierungsstelle fehlgeschlagen ist. Der Standardwert ist 120 Sekunden. Dieses Feld ist erforderlich, wenn Sie **Failover und Failback aktivieren**auswählen.
    
- **Fall Back Erkennungsintervall (Sek.)** Geben Sie die Anzahl der Sekunden ein, die verstreichen sollen, bevor festgestellt wird, dass die primäre Registrierungsstelle gesichert wird. Der Standardwert ist 240 Sekunden. Dieses Feld ist erforderlich, wenn Sie **Failover und Fallback aktivieren**auswählen.
    
> [!IMPORTANT]
> Achten Sie beim Definieren des Fehler Erkennungs Intervalls und des Fall Back Erkennungs Intervalls darauf, dass kein Intervall eingegeben wird, das das Failover und das Fallback verursacht, wenn die Registrierungsstelle für einen kurzen Zeitraum nicht antwortet. Es ist möglich, dass die primäre Registrierungsstelle aufgrund des Ladens des Pools oder der Server für kurze Zeiträume nicht reagiert. 
  

