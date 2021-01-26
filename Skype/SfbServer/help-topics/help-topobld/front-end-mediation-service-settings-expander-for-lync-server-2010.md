---
title: Einstellungen für den Front-End-Vermittlungsdienst für Lync Server 2010 – Erweiterung
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
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Einstellungen unter PSTN-Gateway für Vermittlungsserver. Sie können die folgenden Einstellungen definieren:'
ms.openlocfilehash: ad6aab0ce528db01621b1d43a62624d96649e66a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807055"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Einstellungen für den Front-End-Vermittlungsdienst für Lync Server 2010 – Erweiterung
 
In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Einstellungen unter **PSTN-Gateway für Vermittlungsserver**. Sie können die folgenden Einstellungen definieren:
  
- Wählen Sie **den aktivierten Vermittlungsserver** aus, wenn Sie den Vermittlungsserver mit diesem Front-End-Server oder front-End-Pool verbinden möchten.
    
- **Abhörports:** Definieren Sie die Ports, die der Vermittlungsserver abhört. Sie können einen Port für **TLS** (Transport Layer Security) oder **TCP** (Transport Control Protocol) definieren. Damit der Porteintrag für TCP verfügbar ist, müssen Sie das Kontrollkästchen **TCP-Port aktivieren** aktivieren. 
    
    > [!IMPORTANT]
    > Ermitteln Sie anhand der Dokumentation und Konfigurationseinstellungen für das PSTN-Gateway (Public Switched Telephone Network), ob Sie Portwerte für TLS, TCP oder beides aktivieren und definieren müssen. TLS ist ein sichereres Protokoll, das Zertifikate verwendet, um den Datenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway zu verschlüsseln. Nicht alle PSTN-Gateways unterstützen TLS. 
  
- Auflistung des momentan zugeordneten und vorhandenen **Trunks** (Session Initiation Protocol-Trunks (SIP)), **Gateways** (PSTN-Gateway oder IP-PBX) und **Standorts** (für Trunk und Gateway konfigurierter Standort).
    
- Wählen Sie einen Trunk, ein Gateway und einen Standort aus, und klicken Sie auf **Als Standardeinstellung festlegen**, um die Auswahl als Standardeinstellung für diesen Vermittlungsdienst festzulegen. Um die Auswahl als Standardeinstellung aufzuheben, wählen Sie die aktuelle Standardeinstellung aus und klicken auf **Festlegung als Standardeinstellung aufheben**. Wählen Sie anschließend eine neue Standardeinstellung aus, und klicken Sie auf **Als Standardeinstellung festlegen**.
    
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

