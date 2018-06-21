---
title: Allgemeine Einstellungen für Filialanwendungen – Erweiterung
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Zum Bearbeiten der Einstellungen für eine vorhandene Survivable Branch Appliance oder einen Survivable Branch Server werden in den folgenden Abschnitten bearbeitet:'
ms.openlocfilehash: eb82254746ea74e06dcd51231712d4694fa8aa9c
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19991600"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Allgemeine Einstellungen für Filialanwendungen – Erweiterung
 
Zum Bearbeiten der Einstellungen für eine vorhandene Survivable Branch Appliance oder einen Survivable Branch Server werden in den folgenden Abschnitten bearbeitet:
  
- Allgemeine Einstellungen
    
- Flexibilitätseinstellungen
    
- Vermittlungsservereinstellungen
    
## 

Für eine Survivable Branch Appliance oder einen Survivable Branch Server werden Sie durch Folgendes angezeigt:
  
### <a name="general-settings"></a>Allgemeine Einstellungen

Der vollqualifizierte Domänenname (FQDN) des Survivable Branch Appliance oder einen Survivable Branch Server. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.
  
Sie können die Option **Alle konfigurierten IP-Adressen verwenden** oder **Dienstnutzung auf ausgewählte IP-Adressen beschränken** wählen. Wenn Sie die Option **Dienst auf definierte IP-Adressen beschränken** wählen, definieren Sie die primäre IP-Adresse, die der Server für die gesamte Kommunikation verwendet (mit Ausnahme der PSTN-Kommunikation). Für die Verwendung mit dem Telefonfestnetz wird eine gesonderte IP-Adresse bestimmt.
  
In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:
  
- Archivierungsserver zuordnen ermöglicht Ihnen die Auswahl der Survivable Branch Appliance oder einen Survivable Branch Server einen Archivierungsserver zuordnen. Sie können wählen Sie aus einem bereits definierten Archivierungsserver, indem Sie den Server aus der Dropdownliste auswählen, oder klicken Sie auf **neu** , um einen neuen Archivierungsserver angeben.
    
    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein. 
  
- Zuordnen von Monitoring Server ermöglicht Ihnen die Auswahl der Survivable Branch Appliance oder einen Survivable Branch Server einen Monitoring Server zuordnen. Sie können wählen Sie aus einer bereits definierten Monitoring Server, indem Sie den Server aus der Dropdownliste auswählen, oder klicken Sie auf **neu** , um einen neuen Monitoring Server angeben.
    
- Ordnen Sie die Edge-Pool Ihnen die bietet Auswahl der Survivable Branch Appliance oder Survivable Branch Server ein Edge-Server oder Pool zuzuordnen. Sie können in der Dropdownliste einen bereits definierten Edgeserver oder -pool auswählen oder auf **Neu** klicken, um einen neuen Edgeserver oder -pool anzugeben.
    
### <a name="resiliency"></a>Flexibilität

Dank der Flexibilität (Ausfallsicherheit) ist die hohe Verfügbarkeit des Registrierungspools gewährleistet. Durch Bereitstellung einer Sicherungsregistrierungsstelle für den Fall eines Ausfalls der primären Registrierungsstelle kann die Sicherungsregistrierungsstelle die Aufgabe der ausgefallenen Registrierung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann es, je nachdem, welche Systeme mit der primären Registrierung ausgefallen sind, möglicherweise zu einer eingeschränkten Funktionalität kommen.
  
Wählen Sie aus der Dropdownliste den Enterprise Edition-Front-End-Pool oder Standard Edition-Front-End-Server, der als sicherungsregistrierung für die Survivable Branch Appliance oder einen Survivable Branch Server fungiert. Sie können außerdem Zeitintervalle für Failover und Fallback auswählen. Die (in Sekunden angegebenen) Zeiteinstellungen für Failover und Fallback ermöglichen die automatische Erkennung einer ausgefallenen Registrierung und eines Zeitpuffers zur automatischen Bestimmung, dass die primäre Registrierung wieder betriebsbereit ist und den Registrierungsprozess übernehmen kann.
  
> [!IMPORTANT]
> Bei der Erkennung von Fehlern und das fallback Intervall definieren, werden Sie nicht, die ein Intervall angeben, der bewirkt das Failover und fallback eintritt, wenn die Registrierung nicht für ein kurzer Zeit reagiert. Es ist möglich, dass die primäre Registrierungsstelle für kurze Zeit, basierend auf das Laden des Pools oder Servern nicht reagieren kann. Die Standardwerte für eine Survivable Branch Appliance oder einen Survivable Branch Server in einer Website in einen Pool oder Standard Edition-Front-End-Server ist für Failover und 240 Sekunden für Fallback 120 Sekunden. 
  
### <a name="mediation-server"></a>Vermittlungsserver

Für **Vermittlungsserver** können Sie Folgendes angeben:
  
Das Kontrollkästchen **verbundener Vermittlungsserver aktiviert** ist nicht auf einem Survivable Branch Appliance oder einen Survivable Branch Server verfügbar, da der Vermittlungsserver verbunden ist.
  
Sie definieren den Überwachungsport auf den Pool-Servern für Transport Layer Security (TLS). Standardmäßig ist dieser Port 5067. Wenn Sie **Aktivieren TCP-Port**auswählen, müssen Sie einen TCP-Port für den verbundenen Vermittlungsserver definieren. Dies ist eine optionale Einstellung, und verweisen Sie auf die Anforderungen Ihres Gateways oder PSTN-Anforderungen zu ermitteln, ob dies notwendig ist. Standardmäßig ist der Wert des TCP-Ports 5068.
  
Definieren Sie PSTN-Gateways, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn Sie bereits Gateways definiert haben, werden sie zur Verfügung, die der Vermittlungsserver zugeordnet. Falls noch keine Gateways definiert wurden, jedoch zur Definition zur Verfügung stehen, können Sie **Neu** auswählen. Sie können auch Gateways entfernen, die bereits für diesen Vermittlungsserver konfiguriert sind. Wählen Sie das Gateway aus, und klicken Sie dann auf **Entfernen**.
  
Wenn Sie mehr als ein Gateway einen Vermittlungsserver zugeordnet haben, wird das erste Gateway verknüpften Standardgateway sein. Wenn Sie ein anderes Gateway als Standardgateway auswählen müssen, wählen Sie das gewünschte Gateway aus, und klicken Sie auf **Als Standard**.
  
### 

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Survivable Branch Appliance oder einen Survivable Branch Server finden Sie unter [Branch-Site Resiliency Solutions](http://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).
  

