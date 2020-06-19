---
title: Teams Voice Contoso-Fallstudie
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams Voice Case Study für Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786007"
---
# <a name="contoso-case-study-location-based-routing"></a>Contoso-Fallstudie: standortbasiertes Routing

Location-Based Routing (LBR) ist ein Feature, das die Gebühren Umgehung auf der Grundlage der Richtlinien und des physischen Standorts des Benutzers zum Zeitpunkt des Einleitens oder Empfangens eines Anrufs beschränkt.  

## <a name="overview"></a>Übersicht

Contoso hat zwei Niederlassungen in einem Land, in dem es illegal ist, den PSTN-Anbieter (Public Switched Telephone Network) zu umgehen, um die Kosten für Ferngespräche zu verringern. Das Hauptbüro verfügt über eine Internet Verbindung, die vom Hauptbüro und vom zweiten Office verwendet wird. Jede Niederlassung verfügt über einen eigenen Session Border Controller (SBC), der mit einem PSTN-Netzbetreiber verbunden ist.  
 
In diesem Land hatte Contoso LBR für die Bereitstellung von Skype for Business konfiguriert. Wenn Sie feststellen möchten, wie Sie LBR für Teams konfigurieren, lesen Sie den [Plan standortbasiertes Routing für das direkte Routing](location-based-routing-plan.md). Contoso hat festgestellt, dass Teams und Skype for Business denselben Szenarien folgen, wenn ein Anruf getätigt werden kann, wenn er empfangen werden kann, wenn ein PSTN-Anruf an einen Teams-Benutzer übertragen werden kann, und wenn Sie einen anderen Teams-Benutzer in den PSTN-Anruf übertragen können.  

Für Skype for Business wurde LBR mit dem SBC-SIP-Trunk (Session Border Controller) konfiguriert, der eine Verbindung mit dem PSTN-Netzbetreiber herstellt. Für diesen SBC hat Contoso die [Liste der zertifizierten SBCS](direct-routing-border-controllers.md) überprüft und festgestellt, dass die bereitgestellte SBC für das direkte Routing zertifiziert ist, aber nicht für die medienumgehung zertifiziert ist. Zur Unterstützung von LBR muss das direkte Routing auf den SBC vor Ort konfiguriert sein, es muss ein lokales Internet-Ausstieg vorhanden sein, und der SBC muss für die medienumgehung konfiguriert sein. Auf der Grundlage dieser Informationen beschloss Contoso Folgendes:

- So verzögern Sie die Aktivierung von Teams LBR, bis der vorhandene SBC für die medienumgehung zertifiziert ist.   

- Contoso hat entschieden, den Hauptstandort SBC für die direkte Route zu Office 365 zu verwenden.  Der Hauptstandort SBC ist der Proxy-SBC für die Remotewebsite.  

- Contoso hat einen Drittanbieter-Berater in Indien verwendet, um die Zertifizierung der LBR-Konfiguration mit dem Telefonieunternehmen in Land zu unterstützen.  

- Zur Unterstützung von Benutzern, die von außerhalb des Büros arbeiten, um PSTN-Anrufe zu tätigen, wurde das Unternehmen, das das Mobiltelefon ausgestellt hat, seinen Mitarbeitern bereitgestellt. 

Die folgenden Diagramme zeigen die vor-und nach-Bereitstellungen für ein Land mit Telefonie-Regelungen, die standortbasiertes Routing erfordern:

**Ursprüngliche Bereitstellung**

![Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-5.png)

**Bereitstellung mit direktem Routing**

![Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-6.png)


## <a name="configuration"></a>Konfiguration 

Zum Konfigurieren der Netzwerkkomponenten in Microsoft Teams befolgte Contoso die Anweisungen unter [Verwalten Ihrer Netzwerktopologie für Cloud-Sprachfeatures](manage-your-network-topology.md). Contoso hat die folgenden Schritte zum Konfigurieren des standortbasierten Routings ausgeführt: 

- Definieren von netzwerkregionen – es wurde eine netzwerkregion definiert. 

- Definieren von Netzwerk Websites – es wurden zwei Netzwerk Websites definiert. Eine Website für jeden Office-Standort in der Region.

- Netzwerk-Subnetze definieren – jede Etage innerhalb eines Office-Standorts verfügt über ein eigenes Subnetz für das kabelgebundene und drahtlose Netzwerk. Diese Konfiguration führte zu 20 Subnetzen für contoso. 

- Vertrauenswürdige IP-Adressen definieren – die externen IP-Adressen für den SBC wurden der vertrauenswürdigen IP-Adresse hinzugefügt.  

