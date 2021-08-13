---
title: 'Teams Contoso-Fallstudie: Standortbasiertes Routing'
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
description: 'Teams Sprachfallstudie für multinationale Unternehmen: Standortbasiertes Routing'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 974053f3e438ecaee3f9eb876eb99e2cf6e40d151be802acb31183620eabc583
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319638"
---
# <a name="contoso-case-study-location-based-routing"></a>Contoso-Fallstudie: Location-Based Routing

Location-Based Routing (LBR) ist ein Feature, das die gebührenpflichtige Umgehung basierend auf der Richtlinie und dem physischen Standort des Benutzers zum Zeitpunkt des Anrufs bzw. zum Empfang eines Anrufs einschränkt.  

## <a name="overview"></a>Übersicht

Contoso verfügt über zwei Niederlassungen in einem Land, in dem es ungesetzlich ist, den Anbieter des öffentlichen Telefonnetzwerks (PSTN) zu umgehen, um die Kosten für Anrufe im Ferngespräch zu senken. Die Hauptverwaltung verfügt über eine Internetverbindung, die von der Hauptverwaltung und von der zweiten Internetverbindung verwendet wird. Jedes Büro verfügt über einen eigenen Session Border Controller (SBC), der mit einem PSTN-Netzbetreiber verbunden ist.  
 
In diesem Land hatte Contoso LBR für die Bereitstellung Skype for Business konfiguriert. Informationen zum Konfigurieren von LBR für Teams Contoso unter [Plan Location-Based Routing für Direct-Routing.](location-based-routing-plan.md) Contoso hat festgestellt, dass Teams und Skype for Business die gleichen Szenarien für mögliche Anrufe, empfangene Anrufe, PstN-Anrufe an einen Teams-Benutzer und wann Sie einen anderen Teams-Benutzer zum PSTN-Anruf übertragen können.  

Für Skype for Business wurde LBR mit dem Session Border Controller (SBC) SIP Trunk konfiguriert, der eine Verbindung mit dem PSTN-Netzbetreiber herstellen kann. Für diesen SBC hat Contoso die Liste der zertifizierten [SBCs](direct-routing-border-controllers.md) überprüft und festgestellt, dass der bereitgestellte SBC für Direct-Routing zertifiziert, aber nicht für die Medienumgehung zertifiziert ist. Zur Unterstützung von LBR muss Direct-Routing für den lokalen SBC-Server konfiguriert werden, es muss ein lokaler Internet-Egress vorhanden sein, und der SBC muss für die Medienumgehung konfiguriert werden. Auf der Grundlage dieser Informationen hat Contoso die folgenden Punkte entschieden:

- Um die Aktivierung von Teams LBR zu verzögern, bis der vorhandene SBC für die Medienumgehung zertifiziert ist.   

- Contoso hat beschlossen, den Hauptwebsite-SBC für "Direct Route to Office 365" zu Office 365.  Der Hauptwebsite-SBC ist der Proxy-SBC für die Remotewebsite.  

- Contoso hat einen Drittanbieter-Berater mit Sitz in Indien verwendet, um die Zertifizierung der LBR-Konfiguration bei der Telefoniegesellschaft im Land zu unterstützen.  

- Zur Unterstützung von Benutzern, die von außerhalb des Büros arbeiten, um PSTN-Anrufe zu erhalten, wurde den Mitarbeitern vom Unternehmen ein Mobiltelefon zur Verfügung gestellt. 

Die folgenden Diagramme zeigen die Vorher-Nach-Bereitstellungen für ein Land mit Telefoniebestimmungen, die Location-Based erfordern:

**Ursprüngliche Bereitstellung**

![Diagramm, das vor dem Zustand angezeigt wird.](media/voice-case-study-5.png)

**Bereitstellung mit Direct Routing**

![Diagramm 2 mit dem Status "Vor"](media/voice-case-study-6.png)


## <a name="configuration"></a>Konfiguration: 

Zum Konfigurieren der Netzwerkkomponenten in Teams Contoso den Anweisungen unter Verwalten der [Netzwerktopologie für Cloud-Sprachfeatures folgen.](manage-your-network-topology.md) Contoso hat die folgenden Schritte zum Konfigurieren des Routings Location-Based abgeschlossen: 

- Definieren von Netzwerkregionen – Eine Netzwerkregion wurde definiert. 

- Definieren von Netzwerkwebsites – Es wurden zwei Netzwerkwebsites definiert. Eine Website für jeden Bürostandort in der Region.

- Definieren von Netzwerk-Subnetzen – Jede Etage innerhalb eines Bürostandorts verfügt über ein eigenes Subnetz für das verkabelte und das Funknetzwerk. Diese Konfiguration hat 20 Subnetze für Contoso ergeben. 

- Definieren vertrauenswürdiger IP-Adressen – Die nach außen gerichteten IP-Adressen für den SBC wurden der vertrauenswürdigen IP-Adresse hinzugefügt.  

