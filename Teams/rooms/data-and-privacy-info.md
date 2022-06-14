---
title: Daten- und Datenschutzinformationen
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 06/01/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Daten- und Datenschutzinformationen
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: 3fa24a1009c5480c308dfc35306286d470178820
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057085"
---
# <a name="approach"></a>Ansatz

Kunden, die Microsoft Teams-Räume Managed Services verwenden, vertrauen Microsoft ihre wertvollsten Ressourcen an – Daten. Sie vertrauen darauf, dass ihre Privatsphäre geschützt wird und dass sie nur in einer Weise verwendet wird, die ihren Erwartungen entspricht.

Die Technologie folgt Datenschutzprozessen, um sicherzustellen, dass sie bei der Erfassung und Verwendung von Daten, die den Dienst effektiv ausführen, den Kundenversprechen entspricht.
## <a name="data-collection-and-privacy"></a>Datensammlung und Datenschutz

 Microsoft Teams-Räume Managed Services überwacht Geräte, sammelt Kundeninhaltsdaten und greift remote auf die Geräte zu und verwaltet sie als Administrator. Die gesammelten Daten sind auf Informationen beschränkt, die erforderlich sind, um die Integrität, die Ursache und die Minderung von Problemen zu überwachen, die in den registrierten Räumen identifiziert wurden. Bestimmte gesammelte Daten sind spezifisch für ein Raumkonto, nicht für einzelne Benutzer.

> [!Note]
> Beiläufige Verweise auf einen einzelnen Benutzer können während der Nutzung des Geräts im Aktivitätsprotokoll vorhanden sein.

## <a name="who-can-access-data"></a>Wer auf Daten zugreifen können

Managed Services ergreift strenge Maßnahmen, um Kundendaten vor unangemessenem Zugriff oder der Verwendung durch unbefugte Personen zu schützen. Diese Maßnahmen umfassen die Einschränkung des Zugriffs durch Microsoft-Mitarbeiter und -Subunternehmer.

## <a name="zero-standing-access-data-storage"></a>Zero Standing Access-Datenspeicher

Verwaltete Dienste mindern Risiken, die mit Konten mit privilegiertem Zugriff von böswilligen Akteuren innerhalb und außerhalb einer Organisation verbunden sind, durch das Prinzip von Zero Standing Access. Mit diesem Prinzip können verwaltete Dienste standardmäßig ohne berechtigungen ausgeführt werden, die jedem Benutzer zur Verfügung stehen. In Kombination mit den Prinzipien von Just-In-Time und Just-Enough-Access bietet es ein robustes Framework, um standardmäßig sicher und konform zu sein. Diagnosedaten stehen dem Microsoft-Dienstbetriebsteam über ein internes Portal zur Verfügung.

## <a name="data-handling"></a>Datenverarbeitung

Microsoft unterliegt strengen Standards für die Datenübertragung, Speicherung, Verwendung und Aufbewahrung. Microsoft verfügt über Standardrichtlinien für die Datenverarbeitung, die regeln, wie Daten basierend auf der Datenklassifizierung behandelt werden sollen.



## <a name="technology-description"></a>Technologiebeschreibung

Verwaltete Dienste senden Daten an Microsoft, um Probleme in der Bereitstellung zu überwachen, zu diagnostizieren und zu beheben. Beispiele hierfür sind:

- Sicherstellen, dass das Gerät auf dem neuesten Stand ist (einschließlich App, Betriebssystem, Treiber, F/W)
- Sicherstellen, dass das Gerät einsatzbereit ist (angemeldet, alle Peripheriegeräte, die einen fehlerfreien Zustand melden usw.)
- Sicherstellen, dass die Umgebung bereit ist (bereitgestellte Konten, Netzwerkgeschwindigkeiten sind schnell genug usw.)
- Ermitteln, ob Hardware- oder Installationsprobleme auftreten können (z. B. lose Verkabelung)
- Heuristik zur Ermittlung von Problemen (übermäßige Neustarts usw.)

Verwaltete Dienste verwalten das Gerät mit den folgenden Aktionen:

- Software aktualisieren
- Beheben von Problemen durch Neustarts, Zurücksetzen von USB-Verbindungen & Zuständen
- Sammeln sie bestimmte Protokolle, um Probleme zu diagnostizieren

Managed Services überwacht oder zeichnet keine Audio-, Video-, Medien- oder Besprechungsinhalte aus Lösungskits auf.

### <a name="service-collected-data-categories"></a>Vom Dienst erfasste Datenkategorien
 
|Kategorie|Details|Grund für die Abfrage|
| :- | :- | :- |
|Fortlaufende Datenerfassung und -verwaltung|IP-Adresse, Identität des Raumkontos (Exchange, Skype for Business und/oder Teams), Standortkoordinaten, E-Mails und Kommunikation innerhalb des Portals mit Microsoft oder Software|Identifizieren und Herstellen einer Verbindung mit dem System unter Verwaltung; Fehler zu identifizieren, zu diagnostizieren und zu mindern; Nutzung, Analysen und Einblicke nachverfolgen; Abfrage- und Reparaturverbindungsstatus|
|Ad-hoc-Datenerfassung und -verwaltung|Ereignisprotokollinformationen, Benutzeraktivität/Identität des angemeldeten Raumbenutzers sowie Diagnoseinformationen, Windows Systemabfragen (Beispiele: Liste der USB-Geräte, Energiezustand usw.)|Identifizieren, Diagnostizieren und Minimieren von Fehlern und für Nutzung, Analyse und Einblicke|

Bestimmte vertrauliche Daten im Geräteaktivitätsprotokoll werden lokal gelöscht (nicht von verwalteten Diensten erfasst):

- Betreff und Textkörper der Besprechung
- Visitenkarteninformationen für Besprechungsteilnehmer (z. B. Titel, Telefonnummer usw.)
- Inhalt der Besprechungsnachricht

> [!NOTE]
> Wenn Microsoft verwaltete Dienste weiterentwickelt, können sich die spezifischen Daten ändern.

### <a name="enrollment"></a>Registrierung

Managed Services ist im Onlineportal für automatisierte Überwachungs- und Supportdienste registriert, einschließlich Diagnose und Berichterstellung. Die Registrierung erfolgt über eine Netzwerkkommunikation, die mit dem auf dem Gerät basierenden öffentlichen Schlüssel (Trusted Platform Module, TPM) verschlüsselt wird.

### <a name="unenrollment"></a>Aufhebung der Registrierung

Die Registrierung des Geräts kann aufgehoben werden, indem verwaltete Dienste deinstalliert werden. Microsoft entfernt das Gerät auch während der Außerbetriebnahme aus der Back-End-Überwachung und kann gesammelte Daten auf Anfrage löschen.
## <a name="compliance"></a>Compliance

Alle Techniker, die an dem Produkt arbeiten, müssen sich einer Schulung zur Sicherheits- und Datenschutzsensibilisierung unterziehen. Microsoft stellt außerdem sicher, dass alle Mitarbeiter die Annahme von Verantwortlichkeiten für Datenschutzanforderungen bestätigen.

Managed Services bietet regionale Datenaufbewahrungsunterstützung über die Rechenzentren in Europa (EU), Asien-Pazifik (APAC) und den USA (USA). Die Dienstkunden werden Daten im Zusammenhang mit der Organisation im Rechenzentrum ihrer ausgewählten Region gespeichert haben.

## <a name="more-resources"></a>Weitere Ressourcen

Microsoft Teams-Räume Sicherheit:/microsoftteams/rooms/security Microsoft Datenschutzbestimmungen: https://aka.ms/privacy Datenverwaltung bei Microsoft: https://www.microsoft.com/trust-center/privacy/data-management Dienstbeschreibung für verwaltete Dienste: [Microsoft Teams verwalteten Chatroomdienst](microsoft-teams-rooms-premium.md)
