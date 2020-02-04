---
title: Einstellungen für den Front-End-Vermittlungsdienst für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'In diesem Dialogfeld können Sie die Eigenschaften der Einstellungen für den Vermittlungs Server-PSTN-Gateway bearbeiten. Sie definieren die folgenden Einstellungen:'
ms.openlocfilehash: bd24c24d14e24ed7e4ce53bc30d01b2e955be6cf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697280"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Einstellungen für den Front-End-Vermittlungsdienst für Lync Server 2010 – Erweiterung
 
In diesem Dialogfeld können Sie die Eigenschaften der Einstellungen für den **Vermittlungs Server-PSTN-Gateway** bearbeiten. Sie definieren die folgenden Einstellungen:
  
- Wählen Sie den beiliegenden **Vermittlungsserver** aus, wenn Sie den Vermittlungsserver mit diesem Front-End-Server oder Front-End-Pools collocate möchten.
    
- **Abhör Anschlüsse**: definieren Sie die Ports, die vom Vermittlungs Server überwacht werden. Sie können einen Port für **TLS** oder Transport Layer Security oder **TCP**oder Transport Control Protocol definieren. Damit der Port Eintrag für TCP verfügbar ist, müssen Sie das Kontrollkästchen für TCP- **Port aktivieren**aktivieren. 
    
    > [!IMPORTANT]
    > Informationen dazu finden Sie in den Dokumentations-und Konfigurationseinstellungen für das PSTN-Gateway (Public Switched Telephone Network), um festzustellen, ob Portwerte TLS, TCP oder beides aktiviert und definiert werden müssen. TLS ist ein sichereres Protokoll, in dem der Datenverkehr zwischen dem Vermittlungs Server und dem PSTN-Gateway mithilfe von Zertifikaten verschlüsselt wird. Nicht alle PSTN-Gateways unterstützen TLS. 
  
- Auflistung des momentan zugeordneten und vorhandenen **Trunks** (Session Initiation Protocol-Trunk (SIP)), **Gateways** (PSTN-Gateway oder IP-PBX) und **Standorts** (für Trunk und Gateway konfigurierter Standort).
    
- Wählen Sie einen Trunk, ein Gateway und einen Standort aus, und klicken Sie auf **Als Standardeinstellung festlegen**, um die Auswahl als Standardeinstellung für diesen Vermittlungsdienst festzulegen. Um die Auswahl als Standardeinstellung aufzuheben, wählen Sie die aktuelle Standardeinstellung aus und klicken Sie auf **Festlegung als Standardeinstellung aufheben**. Wählen Sie anschließend eine neue Standardeinstellung aus und klicken Sie auf **Als Standardeinstellung festlegen**.
    
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

