---
title: Fallstudie "Teams voice Contoso"
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
description: Sprachfallstudie zu Teams für multinationale Unternehmen
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097491"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso-Fallstudie: Übersicht über die Sprachmigration von Teams

In diesem Artikel wird eine Fallstudie dazu eingeführt, wie ein fiktives multinationales Unternehmen, Contoso, eine Teams-Sprachlösung für ihre Organisation implementiert hat.

Contoso hat Microsoft 365 Enterprise bereitgestellt und wichtige Entwurfsentscheidungen und Implementierungsdetails für folgendes adressiert: Netzwerk, Identität, Windows 10 Enterprise, Office 365 ProPlus, Verwaltung mobiler Geräte, Informationsschutz, Sicherheit, Upgrade von Skype for Business auf Teams, Telefonsystem und Audiokonferenzen.  

Dieser Artikel befasst sich mit der Migration der lokalen Benutzer durch Contoso zu Teams für einheitliche Kommunikation, Zusammenarbeit und Sprachsteuerung. Hintergrundinformationen dazu, wie Contoso die digitale Transformation mithilfe der Clouddienste von Microsoft beschleunigt hat, finden Sie in allen Kernartikeln, die mit der Übersicht über [die Contoso-Fallstudie beginnen.](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

In den wichtigsten Artikeln finden Sie Informationen zu den folgenden Themen:  

- Anforderungen an die IT-Infrastruktur von Contoso
- Netzwerk
- Identität 
- Windows 10 Enterprise
- Office 365 Pro Plus
- Verwaltung mobiler Geräte
- Informationsschutz
- Zusammenfassung der Microsoft 365 Enterprise-Sicherheit
- Team für ein geheimes Projekt
- SharePoint Online-Website für hochgradig vertrauliche digitale Ressourcen

Informationen zum Planen eines Upgrades finden Sie unter Erste Schritte mit [Ihrem Microsoft Teams-Upgrade.](upgrade-start-here.md)

## <a name="contoso-business-goals-for-teams"></a>Contoso-Geschäftsziele für Teams

Um ihre lokalen Benutzer zu Teams zu migrieren, um einheitliche Kommunikation, Zusammenarbeit und Sprachsteuerung zu ermöglichen, hat Contoso sich für die folgenden Geschäftsziele entschieden:

- Aktivieren von Teams 

  Das einheitliche Kommunikations- und Zusammenarbeitsteam von Contoso hat Teams mit den richtigen Richtlinien zum Steuern und Ermöglichen einer sicheren internen und externen Zusammenarbeit ermöglicht. 

- Upgrade von Skype for Business auf Microsoft Teams 

  Skype for Business wurde in Contoso weit verbreitet bereitgestellt. Mit der Notwendigkeit, ältere Systeme zu verschieben, hat Contoso beschlossen, seine Skype for Business-Benutzer auf Teams zu aktualisieren. Weitere Informationen finden Sie unter [Contoso-Fallstudie: Upgradeplan für Teams.](voice-case-study-migration-plan.md)

- Telefonsystem  

  Skype for Business mit Unternehmensstimme wurde in Contoso weit verbreitet. Mit der Notwendigkeit, ältere Systeme zu verschieben, die der nächste Hop für ihre Vermittlungsserver waren, migrierte Contoso seine Skype for Business -Sprachbenutzer zu Telefonsystem. Contoso-Websites verwendeten Microsoft-Anrufplan, Telefonsystem-Direct-Routing oder eine Kombination aus beiden. Weitere Informationen finden Sie unter [Contoso-Fallstudie: Telefonsystem](voice-case-study-phone-system.md).

- Standortbasiertes Routing 

  Mit Bürostandorten in ländern mit Telefonieaufsicht musste Contoso das Location-Based Routing neu erstellen, das in Skype for Business bei der Bereitstellung des Telefonsystems vorhanden war. Weitere Informationen finden Sie unter [Contoso-Fallstudie: Location-Based Routing](voice-case-study-location-based-routing.md).

- Notrufe 

  Dort, wo Direct Routing implementiert wurde, hat Contoso Notrufe bei genehmigten Dritten eingerichtet. Weitere Informationen finden Sie unter [Contoso-Fallstudie: Notrufe](voice-case-study-emergency-calling.md).

- Audiokonferenzen 

  Contoso richtete Audiokonferenzdienstnummern ein, die auf ihrem SIP-Trunk bei ihrem PSTN-Anbieter gehostet wurden. Weitere Informationen finden Sie unter [Contoso-Fallstudie: Audiokonferenzen](voice-case-study-audio-conferencing.md). 

- Optimierung lokaler Medien 

  Contoso nutzte die Optimierung lokaler Medien an Standorten, an denen es einen direkten Route-Trunk zu Microsoft Phone System gab, der von Remotewebsites genutzt wurde. Weitere Informationen finden Sie unter [Planen der Optimierung](direct-routing-media-optimization.md) lokaler Medien und Konfigurieren der Optimierung lokaler [Medien.](direct-routing-media-optimization-configure.md)

- Automatische Telefonwarteschlangen und Anrufwarteschlangen

  Als Ergebnis von Covid-19 wollte Contoso Unterstützung beim Empfang bereitstellen, während die Mitarbeiter remote arbeiteten. Contoso verwendet automatische Telefonwarteschlangen und Anrufwarteschlangen, um eingehende Anrufe an die Telefonnummer des Empfangers zu verwalten. Weitere Informationen finden Sie unter [Contoso-Fallstudie: Automatische Telefonwarteschlangen und Anrufwarteschlangen.](voice-case-study-call-queues.md)