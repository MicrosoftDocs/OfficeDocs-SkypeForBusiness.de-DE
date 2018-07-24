---
title: Front-End Mediation Service Einstellungen – Erweiterung für Lync Server 2010
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
ms.openlocfilehash: fa3038e8480fb11430388c95914750ab1d9ca68c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971988"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Front-End Mediation Service Einstellungen – Erweiterung für Lync Server 2010
 
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
  

