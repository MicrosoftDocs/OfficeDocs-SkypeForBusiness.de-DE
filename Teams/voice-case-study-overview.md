---
title: Teams Überblick über die Contoso-Fallstudie über Sprachanrufe
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
description: 'Teams Sprachfallstudie für multinationale Unternehmen: Übersicht über die Sprachmigration'
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa9c4e3e8468723d4e0fce7f2fa5a61646213260fe16a3c137b6c8fe7e01a635
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319628"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso-Fallstudie: Übersicht Teams Sprachmigration

In diesem Artikel wird eine Fallstudie dazu eingeführt, wie ein fiktives multinationales Unternehmen Contoso eine Teams-Sprachlösung für ihre Organisation implementiert hat.

Contoso hat Microsoft 365 Enterprise bereitgestellt und wichtige Entwurfsentscheidungen und Implementierungsdetails für folgende Themen getroffen: Netzwerk-, Identitäts-, Windows 10 Enterprise-, Office 365 ProPlus-, Verwaltung mobiler Geräte, Datenschutz, Sicherheit, Upgrade von Skype for Business auf Teams, Telefonsystem und Audiokonferenzen.  

Dieser Artikel befasst sich mit der Migration der lokalen Benutzer von Contoso Teams vereinheitlichte Kommunikation, Zusammenarbeit und Sprachanrufe. Hintergrundinformationen dazu, wie Contoso die digitale Transformation mithilfe der Microsoft-Clouddienste beschleunigt hat, finden Sie in allen Artikeln, die mit der [Übersicht über die Contoso-Fallstudie beginnen.](/microsoft-365/enterprise/contoso-case-study)

[https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

In den wichtigsten Artikeln finden Sie Informationen zu folgenden Themen:  

- Anforderungen an die IT-Infrastruktur von Contoso
- Netzwerk
- Identity
- Windows 10 Enterprise
- Office 365 Pro Pluszeichen
- Verwaltung mobiler Geräte
- Schutz von Informationen
- Zusammenfassung der Microsoft 365 Enterprise Sicherheit
- Team für ein oberstes geheimes Projekt
- SharePoint Onlinewebsite für streng vertrauliche digitale Objekte

Informationen zum Planen eines Upgrades finden Sie unter Erste Schritte mit ihrem Microsoft Teams [Upgrade.](upgrade-start-here.md)

## <a name="contoso-business-goals-for-teams"></a>Contoso-Geschäftsziele für Teams

Zum Migrieren ihrer lokalen Benutzer zu einem Teams einheitlichen Kommunikations-, Zusammenarbeits- und Sprachbefehls hat Contoso die folgenden Geschäftsziele verfolgt:

- Teams aktivieren 

  Das einheitliche Kommunikations- und Zusammenarbeitsteam von Contoso hat Teams Richtlinien zum Steuern und Aktivieren einer sicheren internen und externen Zusammenarbeit aktiviert. 

- Upgrade von Skype for Business auf Microsoft Teams 

  Skype for Business wurde in Contoso weit verbreitet bereitgestellt. Da die alten Systeme ausgeschaltet werden müssen, hat Contoso beschlossen, die Benutzer Skype for Business auf Teams. Weitere Informationen finden Sie in der [Contoso-Fallstudie: Teams Upgradeplan.](voice-case-study-migration-plan.md)

- Telefonsystem  

  Skype for Business mit Enterprise-Sprache wurde in Contoso weit verbreitet bereitgestellt. Da die alten Systeme, bei denen es sich um den nächsten Hop für die Vermittlungsserver war, abschalten müssen, migrierte Contoso die Benutzer Skype for Business Enterprise-Voice zu Telefonsystem. Contoso-Websites verwendeten microsoft Calling Plan, Telefonsystem Direct Routing oder eine Kombination aus beiden. Weitere Informationen finden Sie in [der Contoso-Fallstudie: Telefonsystem.](voice-case-study-phone-system.md)

- Standortbasiertes Routing 

  Mit Bürostandorten in Telefonie-regulierten Ländern musste Contoso das Location-Based-Routing neu erstellen, das in den Skype for Business in der Telefonbereitstellung Telefonsystem war. Weitere Informationen finden Sie in der [Contoso-Fallstudie: Location-Based Routing.](voice-case-study-location-based-routing.md)

- Notrufe 

  Dort, wo Direct Routing implementiert wurde, hat Contoso Notrufe mit genehmigten Dritten eingerichtet. Weitere Informationen finden Sie in der [Contoso-Fallstudie: Notrufe.](voice-case-study-emergency-calling.md)

- Audiokonferenzen 

  Contoso hat die auf dem SIP-Trunk des PSTN-Anbieters gehosteten Audiokonferenz-Servicenummern eingerichtet. Weitere Informationen finden Sie in [der Contoso-Fallstudie: Audio conferencing (Audiokonferenz).](voice-case-study-audio-conferencing.md) 

- Optimierung lokaler Medien 

  Contoso hat die Optimierung lokaler Medien an Standorten genutzt, an denen ein direkter Route-Trunk zum Microsoft-Telefon-System zur Verfügung stand, das von Remotestandorten genutzt wurde. Weitere Informationen finden Sie unter Planen der Optimierung [lokaler Medien und](direct-routing-media-optimization.md) Konfigurieren der Optimierung lokaler [Medien.](direct-routing-media-optimization-configure.md)

- Automatische Telefonkonferenzen und Anrufwarteschleifen

  Als Ergebnis von Covid-19 wollte Contoso Unterstützung beim Empfang bereitstellen, während die Mitarbeiter remote arbeiteten. Contoso hat automatische Telefonkonferenzen und Anrufwarteschleifen verwendet, um eingehende Anrufe an die Telefonnummer des Empfangstelefons zu verwalten. Weitere Informationen finden Sie in der [Contoso-Fallstudie: Automatische Telefonkonferenzen und Anrufwarteschleifen.](voice-case-study-call-queues.md)
