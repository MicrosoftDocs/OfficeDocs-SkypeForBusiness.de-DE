---
title: Einrichten des Telefonsystems in Ihrer Organisation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: Schrittweise Anleitung, die erläutert, wie Sie Teams Telefonsystem für Ihre Organisation in einem Microsoft 365.
ms.openlocfilehash: 3a5c275c7d7d881ff770e6e84a3d4fa935d2827f
ms.sourcegitcommit: 71edff2670367082312de59c4e21775682871418
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2022
ms.locfileid: "63043343"
---
# <a name="set-up-phone-system-in-your-organization"></a>Einrichten des Telefonsystems in Ihrer Organisation

Dieser Artikel enthält eine Roadmap zu Inhalten für die Einrichtung von Telefonsystem-Technologie von Microsoft zum Aktivieren von Anrufsteuerung und PBX-Funktionen (Private Branch Exchange) in der Microsoft 365 Cloud. Links zu ausführlicheren Informationen finden Sie am Ende jedes Schritts. 

Bevor Sie diesen Artikel lesen, vergewissern Sie sich, dass Sie [gelesen](what-is-phone-system-in-office-365.md) haben, was Telefonsystem und was sie mit ihren [Telefonsystem](here-s-what-you-get-with-phone-system.md). In den letzten beiden Artikeln werden die Telefonsystem und Features beschrieben.    

In diesem Artikel werden die folgenden Schritte beschrieben: 

- [Schritt 1: Kaufen und Zuweisen einer Telefonsystem Lizenz](#step-1-buy-and-assign-a-phone-system-license)  
- [Schritt 2: Auswählen einer PSTN-Verbindungsoption](#step-2-choose-a-pstn-connectivity-option) 
- [Schritt 3: Abrufen von Telefonnummern für Ihre Benutzer](#step-3-get-phone-numbers-for-your-users)
- [Schritt 4: Erhalten von Telefonnummern für Dienste](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [Schritt 5: Einrichten einer Anrufwarteschleife](#step-5-if-you-want-to-set-up-a-call-queue) 
- [Schritt 6: Wenn Sie eine automatische Attendant einrichten möchten](#step-6-if-you-want-to-set-up-an-auto-attendant) 
- [Schritt 7: Einrichten von Guthaben für Kommunikationen für gebührenfreie Nummern](#step-7-set-up-communications-credits-for-toll-free-numbers)
 

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>Schritt 1: Kaufen und Zuweisen einer Telefonsystem Lizenz

Wenn Sie einem Telefonsystem Benutzer eine Lizenz zuweisen, sind die Schritte identisch mit dem Zuweisen einer Microsoft 365 Lizenz. Sie können auch mehreren Benutzern Gleichzeitig Lizenzen zuweisen. Weitere Informationen zu verfügbaren Telefonsystem-Lizenzen und zum Erwerben und Zuweisen von Lizenzen finden Sie unter  [Add-On Teams](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) lizenzen und Zuweisen von [Microsot Teams-Add-On-Lizenzen](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>Schritt 2: Auswählen einer PSTN-Verbindungsoption 
 
Damit Ihre Benutzer externe Anrufe verwenden und empfangen können, müssen Sie Telefonsystem Mit dem öffentlichen Telefonnetz (PSTN) verbinden. Microsoft bietet mehrere Optionen für die Verbindung mit dem PSTN, darunter: 

- Anrufplan. Eine All-in-the-Cloud-Lösung mit Microsoft als Ihrem PSTN-Anbieter. 

- Operatoren Verbinden. Wenn Ihr bestehender Netzbetreiber am Microsoft Operator Verbinden-Programm teil nimmt, können diese PSTN-Anrufe und Session Border Controller (SBCs) für Sie verwalten. 

- Direktes Routing. Verwenden Sie Ihren eigenen PstN-Netzbetreiber, indem Sie Ihre SBCs mit Telefonsystem. 

Weitere Informationen zu allen Konnektivitätsoptionen finden Sie unter [PstN-Konnektivitätsoptionen](pstn-connectivity.md).   

## <a name="step-3-get-phone-numbers-for-your-users"></a>Schritt 3: Abrufen von Telefonnummern für Ihre Benutzer

Bevor Sie in Ihrer Organisation Benutzer für das Tätigen und Empfangen von Anrufen einrichten können, müssen Sie Telefonnummern für diese anfordern.

Informationen zum Verwalten von Telefonnummern für Ihre Benutzer finden Sie in den folgenden Artikeln. Wie Sie Nummern für einen Benutzer verwalten, hängt von der von Ihnen verwendeten PSTN-Konnektivitätsoption ab.   

- [Verwalten von Telefonnummern für](manage-phone-numbers-landing-page.md) Ihre Organisation – Bietet eine Übersicht über Telefonnummerntypen mit Links zu bestimmten Artikeln zum Abrufen und Verwalten von Nummern je nach Ihrer PSTN-Verbindungsoption. Beschreibt die beiden Arten [von Benutzertelefonnummern](manage-phone-numbers-landing-page.md#user-telephone-numbers). 
 
- [Zuweisen, Ändern oder Entfernen](assign-change-or-remove-a-phone-number-for-a-user.md) einer Telefonnummer für einen Benutzer – Beschreibt, wie Sie die erworbenen Telefonnummern zuweisen und verwalten. 
 
- [Wie viele Telefonnummern erhalten](how-many-phone-numbers-can-you-get.md) Sie? – Beschreibt, wie viele Telefonnummern Sie erhalten können, je nachdem, welche Arten von Telefonnummern Sie gekauft und zugewiesen haben. 


## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>Schritt 4: Erhalten von Telefonnummern für Dienste (Anrufwarteschleifen, automatische Telefonkonferenzen)

Sie können nicht nur Telefonnummern für Ihre Benutzer erhalten, sondern auch gebührenpflichtige oder gebührenfreie Telefonnummern für Dienste wie automatische Telefonkonferenzen und Anrufwarteschleifen erwerben. Eine Servicenummer kann Hunderte von Anrufen gleichzeitig verarbeiten, während die Telefonnummer eines Benutzers nur einige wenige Anrufe gleichzeitig verarbeiten kann.   

Sie können Servicenummern von Microsoft erhalten, die in Ihrer Lizenzierung enthalten sind. Wenn Sie pstN-Konnektivität über Operator Verbinden Direct Routing haben, können Sie die von Ihrem eigenen Netzbetreiber oder Netzbetreiber bereitgestellten Leistungsnummern verwenden. 

Weitere Informationen finden Sie unter:

- [Verwalten von Telefonnummern für](manage-phone-numbers-landing-page.md) Ihre Organisation – Bietet eine Übersicht über Telefonnummerntypen mit Links zu bestimmten Artikeln zum Abrufen und Verwalten von Nummern je nach Ihrer PSTN-Verbindungsoption.  
Beschreibt [service phone numbers](manage-phone-numbers-landing-page.md#service-telephone-numbers) available from Microsoft that are included in your licensing. Wenn Sie Informationen zu den von der Netzbetreiber-Verbinden Direct Routing bereitgestellten Leistungsnummern erhalten, wenden Sie sich an Ihren Anbieter. 

- [Wie viele Telefonnummern erhalten](how-many-phone-numbers-can-you-get.md) Sie? – Beschreibt, wie viele Telefonnummern Sie erhalten können, je nachdem, welche Arten von Telefonnummern Sie gekauft und zugewiesen haben. 

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>Schritt 5: Einrichten einer Anrufwarteschleife

Anrufwarteschleifen umfassen Begrüßungen, die verwendet werden, wenn jemand eine Telefonnummer für Ihre Organisation anruft, die Möglichkeit, die Anrufe automatisch zu halten, und die Möglichkeit, nach dem nächsten verfügbaren Telefonmitarbeiter zu suchen, um den Anruf zu verarbeiten. Sie können eine einzige Anrufwarteschleife oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen. 

Weitere Informationen zu Anrufwarteschleifen finden Sie unter [Erstellen einer Anrufwarteschleife](create-a-phone-system-call-queue.md).

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>Schritt 6: Wenn Sie eine automatische Attendant einrichten möchten

Mit automatischen Telefonkonferenzen können Personen, die sich in Ihre Organisation ein- und ausliefern, in einem Menüsystem navigieren, um sie an die richtige Abteilung, an die richtige Anrufwarteschleife, an eine Person oder einen Operator zu senden.  

Informationen zum Einrichten automatischer Attendants finden Sie unter  [Einrichten einer automatischen Attendant](create-a-phone-system-auto-attendant.md).

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>Schritt 7: Einrichten von Guthaben für Kommunikationen für gebührenfreie Telefonnummern

Wenn Sie mit Ihrem Konto gebührenfreie Telefonnummern Microsoft Teams möchten, müssen Sie Guthaben für Kommunikationen einrichten. Gebührenfreie Anrufe werden nach Minuten abgerechnet und erfordern einen positiven Guthabensaldo für Kommunikationen. 

Guthaben für Kommunikationen ist eine bequeme Möglichkeit, gebührenfreie Telefonnummern hinzuzufügen, die sie wie folgt verwenden: 

- Mit Servicenummern für Sprach-Apps, z. B. automatischen Telefonkonferenzen oder Anrufwarteschleifen. 

- So wählen Sie eine beliebige internationale Telefonnummer, wenn Sie Abonnements für einen Plan für Inlandanrufe haben oder die in einem Abonnement für einen Plan für Inlands- und Auslandsanrufe enthalten sind. 

- So wählen Sie eine Nummer aus und bezahlen pro Minute, sobald die monatliche Minuten-Zuteilung aufgebraucht ist. 

Weitere Informationen finden Sie unter  [Was ist Guthaben für Kommunikationen?](what-are-communications-credits.md) und [Einrichten von Guthaben für Kommunikationen für Ihre Organisation](set-up-communications-credits-for-your-organization.md).
  

## <a name="related-topics"></a>Verwandte Themen

- [Was ist das Telefonsystem?](what-is-phone-system-in-office-365.md)

- [Das Telefonsystem bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

- [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-landing-page.md)


    
  
 
