---
title: Endgültige Checkliste für Anrufsteuerungen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Endgültige Checkliste für die Bereitstellung der Anrufannahme Steuerung in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: fab6472d931d0475a3e3b0a0f413fce7775d7a15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281592"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Bereitstellung der Anrufsteuerung: endgültige Checkliste für Skype for Business Server
 
Endgültige Checkliste für die Bereitstellung der Anrufannahme Steuerung in Skype for Business Server Enterprise-VoIP 
  
Überprüfen Sie anhand der folgenden Liste, ob Sie alle erforderlichen Konfigurationsaufgaben für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) abgeschlossen haben.
  
- Wenn ein oder mehrere Edgeserver bereitgestellt werden, muss jede externe Schnittstellen-IP-Adresse der Subnetliste in den Netzwerkkonfigurationseinstellungen mit einer Bitmaske von 32 hinzugefügt werden. Sie sollten dieses Subnetz (IP-Adresse) außerdem der Netzwerkstandort-ID für den geografischen Standort zuordnen, an dem der A/V-Edgedienst bereitgestellt wurde.
    
    > [!NOTE]
    > Edgeserver müssen keine CAC-Implementierung implementieren. 
  
- Stellen Sie sicher, dass die CAC-Funktion aktiviert ist, wie unter [Aktivieren der Anrufsteuerung in Skype for Business Server](enable-call-admission-control.md)angegeben.
    
- Stellen Sie sicher, dass die Anrufsteuerung an allen zentralen Standorten aktiviert ist. Dies kann über den Topologie-Generator erfolgen. Wenn beim Veröffentlichen eine Warnung generiert wird, ignorieren Sie Sie *nicht* .
    
- Stellen Sie sicher, dass alle im Unternehmensnetzwerk verwalteten Subnetze in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Darüber hinaus ist es wichtig, dass jedes Subnetz einer Netzwerk Website zugeordnet ist, wie unter [Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in Skype for Business](deploy-network.md)erläutert wird.
    
- Stellen Sie sicher, dass die Subnetz- oder IP-Adressen aller Front-End-Server, Survivable Branch Appliances (SBAs), A/V-Konferenzserver (sofern in einem separaten Pool bereitgestellt) und Vermittlungsserver in den Netzwerkkonfigurationseinstellungen konfiguriert sind.
    

