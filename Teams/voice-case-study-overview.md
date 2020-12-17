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
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams Voice Case Study für Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701223"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso-Fallstudie: Übersicht über die VoIP-Migration von Teams

In diesem Artikel wird eine Fallstudie vorgestellt, die zeigt, wie eine fiktive Multi-National Corporation, Contoso, eine Teams-Sprachlösung für Ihre Organisation implementiert hat.

Contoso hat Microsoft 365 Enterprise bereitgestellt und wichtige Entwurfsentscheidungen und Implementierungsdetails für folgende Themen behandelt: Netzwerk, Identität, Windows 10 Enterprise, Office 365 ProPlus, Verwaltung mobiler Geräte, Informationsschutz, Sicherheit, Upgrade von Skype for Business auf Teams, Telefon System und Audiokonferenzen.  

In diesem Artikel wird erläutert, wie Contoso ihre lokalen Benutzer in Teams für einheitliche Kommunikation, Zusammenarbeit und Sprache migriert hat. Hintergrundinformationen dazu, wie Contoso Ihre digitale Transformation mithilfe der Microsoft-Cloud-Dienste beschleunigt hat, finden Sie in den wichtigsten Artikeln, die mit der [Übersicht über die Contoso-Fallstudie](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)beginnen.

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

In den wichtigsten Artikeln finden Sie Informationen zu den folgenden Themen:  

- Anforderungen der IT-Infrastruktur von Contoso
- Netzwerk
- Identität 
- Windows 10 Enterprise
- Office 365 pro Plus
- Verwaltung mobiler Geräte
- Informationsschutz
- Zusammenfassung der Microsoft 365 Enterprise-Sicherheit
- Team für ein Top-Secret-Projekt
- SharePoint Online-Website für hoch vertrauliche digitale Ressourcen

Informationen zum Planen eines Upgrades finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](upgrade-start-here.md).

## <a name="contoso-business-goals-for-teams"></a>Contoso-Geschäftsziele für Teams

Um Ihre lokalen Benutzer zu Teams für Unified Communication, Collaboration und Voice zu migrieren, hat Contoso die folgenden Unternehmensziele beschlossen:

- Teams-Aktivierung 

  Das Unified Communication-und Zusammenarbeits Team von Contoso hat Teams mit den richtigen Richtlinien für die Steuerung und die sichere interne und externe Zusammenarbeit aktiviert. 

- Upgrade von Skype for Business auf Microsoft Teams 

  Skype for Business wurde in contoso umfassend bereitgestellt. Mit der Notwendigkeit, Legacy-Systeme zu entfernen, beschloss contoso, Ihre Skype for Business-Benutzer auf Teams zu aktualisieren. Weitere Informationen finden Sie unter [contoso-Fallstudie: Upgradeplan für Teams](voice-case-study-migration-plan.md).

- Telefonsystem  

  Skype for Business mit Enterprise-VoIP wurde in contoso umfassend bereitgestellt. Mit der Notwendigkeit, Legacy-Systeme zu entfernen, die den nächsten Hop für Ihre Vermittlungsserver waren, migrierte Contoso Ihre Skype for Business Enterprise-VoIP-Benutzer in das Telefon System. Contoso-Websites haben Microsoft-Anrufplan, direktes Telefon System-Routing oder eine Kombination aus beidem verwendet. Weitere Informationen finden Sie unter [contoso-Fallstudie: Telefon System](voice-case-study-phone-system.md).

- Standortbasiertes Routing 

  Mit Office-Standorten in Telefon regulierten Ländern musste Contoso das Location-Based-Routing, das in Skype for Business vorhanden war, in der Bereitstellung Ihres Telefonsystems neu erstellen. Weitere Informationen finden Sie unter [contoso-Fallstudie: Location-Based-Routing](voice-case-study-location-based-routing.md).

- Notrufe 

  Bei der Implementierung von Direct Routing richtete Contoso Notrufe mit genehmigten Drittanbietern ein. Weitere Informationen finden Sie unter [contoso-Fallstudie: Notrufe](voice-case-study-emergency-calling.md).

- Audiokonferenzen 

  Contoso richtete Audiokonferenz-Dienstnummern ein, die im SIP-Stamm Ihres PSTN-Anbieters gehostet wurden. Weitere Informationen finden Sie unter [contoso-Fallstudie: Audiokonferenzen](voice-case-study-audio-conferencing.md). 

- Lokale Medienoptimierung 

  Contoso nutzte die lokale Medienoptimierung an Orten, an denen Sie über einen direkten Routen trunk zu einem Microsoft Phone-System verfügten, das von Remotestandorten genutzt wurde. Weitere Informationen finden Sie unter [Planen der lokalen Medienoptimierung](direct-routing-media-optimization.md) und [Konfigurieren der lokalen Medienoptimierung](direct-routing-media-optimization-configure.md).

- Automatische Telefonzentralen und Anrufwarteschlangen

  Als Ergebnis von Covid-19 wollte Contoso die Unterstützung der Rezeption zur Verfügung stellen, während die Mitarbeiter Remote arbeiten. Contoso hat automatische Telefonzentralen und Anrufwarteschlangen verwendet, um eingehende Anrufe an die Telefonnummer Ihres Rezeptionisten zu verwalten. Weitere Informationen finden Sie unter [contoso-Fallstudie: automatische Telefonzentralen und Anrufwarteschlangen](voice-case-study-call-queues.md).  


