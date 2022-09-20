---
title: Übersicht über die Fallstudie "Teams Voice Contoso"
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Teams Voice Case Study für multinationale Unternehmen: Übersicht über die VoIP-Migration'
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae0d123841e57987346fae304e34bde28e4ffe84
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808626"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso-Fallstudie: Übersicht über die Sprachmigration in Teams

In diesem Artikel wird eine Fallstudie vorgestellt, in der erläutert wird, wie ein fiktives multinationales Unternehmen, Contoso, eine Teams-VoIP-Lösung für ihre Organisation implementiert hat.

Contoso hat Microsoft 365 Enterprise bereitgestellt und wichtige Designentscheidungen und Implementierungsdetails für Folgendes adressiert: Netzwerk, Identität, Windows 10 Enterprise, Office 365 ProPlus, Verwaltung mobiler Geräte, Informationsschutz, Sicherheit, Upgrade von Skype for Business zu Teams, Telefonsystem und Audiokonferenzen.  

In diesem Artikel wird erläutert, wie Contoso seine lokalen Benutzer zu Teams migriert hat, um einheitliche Kommunikation, Zusammenarbeit und VoIP zu ermöglichen. Hintergrundinformationen dazu, wie Contoso die digitale Transformation mithilfe der Clouddienste von Microsoft beschleunigt hat, finden Sie in allen Kernartikeln, beginnend mit der [Contoso-Fallstudieübersicht](/microsoft-365/enterprise/contoso-case-study).

[https://learn.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

In den Kernartikeln finden Sie Informationen zu folgenden Themen:  

- It-Infrastrukturanforderungen von Contoso
- Networking
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- Verwaltung mobiler Geräte
- Informationsschutz
- Zusammenfassung der Microsoft 365 Enterprise Sicherheit
- Team für ein streng geheimes Projekt
- SharePoint Online-Website für streng vertrauliche digitale Objekte

Für Informationen zum Planen eines Upgrades sollten Sie mit den [ersten Schritten mit Ihrem Microsoft Teams-Upgrade](upgrade-start-here.md) beginnen.

## <a name="contoso-business-goals-for-teams"></a>Contoso-Geschäftsziele für Teams

Um ihre lokalen Benutzer für einheitliche Kommunikation, Zusammenarbeit und Spracherkennung zu Teams zu migrieren, entschied sich Contoso für die folgenden Geschäftsziele:

- Teams-Aktivierung 

  Das einheitliche Kommunikations- und Zusammenarbeitsteam von Contoso ermöglichte Teams mit den richtigen Richtlinien, um die sichere interne und externe Zusammenarbeit zu steuern und zu ermöglichen. 

- Upgrade von Skype for Business auf Microsoft Teams 

  Skype for Business wurde in Contoso weit verbreitet. Angesichts der Notwendigkeit, ältere Systeme zu wechseln, hat Contoso beschlossen, seine Skype for Business-Benutzer auf Teams zu aktualisieren. Weitere Informationen finden Sie unter [Contoso-Fallstudie: Teams-Upgradeplan](voice-case-study-migration-plan.md).

- Telefonsystem  

  Skype for Business mit Enterprise-VoIP wurde in Contoso weit verbreitet. Aufgrund der Notwendigkeit, ältere Systeme zu verlassen, die der nächste Hop für ihre Vermittlungsserver waren, hat Contoso seine Skype for Business Enterprise-VoIP-Benutzer zum Telefonsystem migriert. Contoso-Websites verwendeten Microsoft-Anrufplan, Direct Routing für Telefonsysteme oder eine Kombination aus beidem. Weitere Informationen finden Sie unter [Contoso-Fallstudie: Telefonsystem](voice-case-study-phone-system.md).

- Standortbasiertes Routing 

  Mit Bürostandorten in Ländern, in denen telefoniereglementiert wurde, musste Contoso das Location-Based Routing neu erstellen, das in Skype for Business in der Bereitstellung des Telefonsystems vorhanden war. Weitere Informationen finden Sie in [der Contoso-Fallstudie Location-Based Routing](voice-case-study-location-based-routing.md).

- Notrufe 

  Wo Direct Routing implementiert wurde, richtete Contoso Notrufe mit genehmigten Dritten ein. Weitere Informationen finden Sie unter [Contoso-Fallstudie: Notrufe](voice-case-study-emergency-calling.md).

- Audiokonferenzen 

  Contoso richtete Audiokonferenzdienstnummern, die auf ihrem SIP-Trunk gehostet wurden, bei ihrem PSTN-Anbieter ein. Weitere Informationen finden Sie unter [Contoso-Fallstudie: Audiokonferenzen](voice-case-study-audio-conferencing.md). 

- Lokale Medienoptimierung 

  Contoso nutzte die lokale Medienoptimierung an Standorten, an denen sie einen direkten Routingtrunk zu Microsoft Phone System hatten, der von Remotestandorten genutzt wurde. Weitere Informationen finden Sie unter [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).

- Automatische Telefonzentralen und Anrufwarteschleifen

  Aufgrund von Covid-19 wollte Contoso Empfangsmitarbeiter unterstützen, während ihre Mitarbeiter remote arbeiteten. Contoso verwendete automatische Telefonzentralen und Anrufwarteschleifen, um eingehende Anrufe an die Telefonnummer des Empfangsmitarbeiters zu verwalten. Weitere Informationen finden Sie unter [Contoso-Fallstudie: Automatische Telefonzentralen und Anrufwarteschleifen](voice-case-study-call-queues.md).
