---
title: Einstellungen für den Front-End-Vermittlungsdienst für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Sie können die Eigenschaften der Mediation Server PSTN-gatewayeinstellungen in diesem Dialogfeld bearbeiten. Definieren Sie die folgenden Einstellungen:'
ms.openlocfilehash: 1a189481eebafc18e925df391c55fa5ced656d91
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889273"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Einstellungen für den Front-End-Vermittlungsdienst für Lync Server 2010 – Erweiterung
 
Sie können die Eigenschaften der **Mediation Server PSTN-Gateway** Einstellungen in diesem Dialogfeld bearbeiten. Definieren Sie die folgenden Einstellungen:
  
- Wählen Sie die **verbundener Vermittlungsserver aktiviert** , wenn Sie den Vermittlungsserver mit diesem Front-End-Server oder Front-End-Pools zu verbinden möchten.
    
- **Überwachungsports**: Definieren Sie die Ports, die der Vermittlungsserver überwacht wird. Sie können einen Port für **TLS** oder Transport Layer Security oder **TCP**, definieren oder transport Control-Protokoll. Für den Porteintrag für TCP verfügbar sein soll müssen Sie das Kontrollkästchen für **Aktivieren TCP-Port**auswählen. 
    
    > [!IMPORTANT]
    > Finden Sie in der Dokumentation und Konfiguration Einstellungen für Ihre Gateway public switched Telephone Network, (PSTN) zu ermitteln, wenn Sie bei aktivierter definieren müssen Port TLS, TCP oder beide Werte. TLS ist eine sicherere Protokoll, Verwendung von Zertifikaten zur Verschlüsselung des Datenverkehrs zwischen dem Vermittlungsserver und PSTN-Gateway. Nicht alle PSTN-Gateways unterstützt TLS. 
  
- Auflistung des momentan zugeordneten und vorhandenen **Trunks** (Session Initiation Protocol-Trunk (SIP)), **Gateways** (PSTN-Gateway oder IP-PBX) und **Standorts** (für Trunk und Gateway konfigurierter Standort).
    
- Wählen Sie einen Trunk, ein Gateway und einen Standort aus, und klicken Sie auf **Als Standardeinstellung festlegen**, um die Auswahl als Standardeinstellung für diesen Vermittlungsdienst festzulegen. Um die Auswahl als Standardeinstellung aufzuheben, wählen Sie die aktuelle Standardeinstellung aus und klicken Sie auf **Festlegung als Standardeinstellung aufheben**. Wählen Sie anschließend eine neue Standardeinstellung aus und klicken Sie auf **Als Standardeinstellung festlegen**.
    
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

