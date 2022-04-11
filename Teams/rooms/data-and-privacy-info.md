---
title: Daten- und Datenschutzinformationen
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
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
ms.openlocfilehash: 0aea2402705eb817c7f075cf003245c0ad3258fd
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2022
ms.locfileid: "64757116"
---
# <a name="approach"></a>Ansatz

Kunden, die verwaltete Dienste nutzen, vertrauen Microsoft ihre wertvollsten Ressourcen an – Daten. Sie vertrauen darauf, dass ihre Privatsphäre geschützt wird und dass sie nur in einer Weise verwendet wird, die ihren Erwartungen entspricht.

Die Technologie folgt Datenschutzprozessen, um sicherzustellen, dass sie bei der Erfassung und Verwendung von Daten, die den Dienst ausführen, den Kundenversprechen entspricht.

## <a name="data-collection"></a>Datensammlung

Die von der Technologie gesammelten Daten sind auf Informationen beschränkt, die erforderlich sind, um die Integrität, die Ursache und die Minderung von Problemen zu überwachen, die in den registrierten Räumen identifiziert wurden.

Die Technologie überwacht Geräte, sammelt Telemetriedaten und ermöglicht Es Microsoft, als Administrator remote auf die Geräte zuzugreifen und diese zu verwalten.

Die erfassten Telemetriedaten sind spezifisch für ein Raumkonto, nicht für einen einzelnen Benutzer. Beiläufige Verweise auf einen einzelnen Benutzer können während der Nutzung des Geräts im Aktivitätsprotokoll vorhanden sein.

### <a name="who-can-access-your-data"></a>Wer auf Ihre Daten zugreifen kann

Der Technologiedienst ergreift strenge Maßnahmen, um Kundendaten vor unangemessenem Zugriff oder unbefugter Nutzung zu schützen. Dies schließt das Einschränken des Zugriffs durch Microsoft-Mitarbeiter und -Subunternehmer ein.

### <a name="zero-standing-access-data-storage"></a>Zero Standing Access Data Storage

Die Technologie entschärft Risiken im Zusammenhang mit Konten mit privilegiertem Zugriff – von böswilligen Akteuren innerhalb und außerhalb einer Organisation – durch das Prinzip des Zero Standing Access. Auf diese Weise kann der Dienst standardmäßig ohne berechtigungen ausgeführt werden, die jedem Benutzer zur Verfügung stehen. In Kombination mit den Prinzipien von Just-In-Time und Just-Enough-Access bietet es ein robustes Framework, um standardmäßig sicher und konform zu sein. Diagnosedaten stehen unserem Service operations-Team über ein internes Portal zur Verfügung.

## <a name="data-handling"></a>Datenverarbeitung

Microsoft unterliegt strengen Standards für die Datenübertragung, Speicherung, Nutzung und Aufbewahrung. Microsoft verfügt über Datenverarbeitungsstandardrichtlinien, die festlegen, wie Daten basierend auf der Datenklassifizierung behandelt werden sollen.

Microsoft erweitert die Datenschutzrechte der Datenschutz-Grundverordnung (DSGVO) auf alle Kunden weltweit, nicht nur in Europa.

## <a name="data-classification"></a>Datenklassifizierung

Die Datenklassifizierung kann verwendet werden, um die Sicherheits-, Compliance- und Datenschutzanforderungen und -prozesse für das Sammeln, Speichern und Verwenden von persönlichen Benutzerinformationen einzuhalten.


|Klassifizierung|Beschreibung|Beispiel|
| :- | :- | :- |
|Kundeninhalte|Inhalte, die von Administratoren und Benutzern direkt bereitgestellt/erstellt werden.|<p>- Vom Kunden generierte BLOB- oder strukturierte Speicherdaten</p><p>- Kundeneigene/bereitgestellte Geheimschlüssel (Kennwörter, Zertifikate, Verschlüsselungsschlüssel, Speicherschlüssel)</p>|
|Identifizierbare Informationen für Endbenutzer (EUII)|Daten, die den Benutzer eines Microsoft-Diensts identifizieren oder verwenden können. EUII enthält keine Kundeninhalte.|<p>- Benutzername oder Anzeigename (DOMÄNE\Benutzername)</p><p>- Benutzerprinzipalname (name@company.com)</p><p>– Benutzerspezifische IP-Adresse</p>|
|Kontodaten|<p>Kundenabrechnungsinformationen und Zahlungsinstrumentinformationen, einschließlich Administratorkontaktinformationen, z. B. Mandant</p><p>Name, Adresse oder Adresse des Administrators</p><p>Telefonnummer.</p>|<p>– Kontaktinformationen des Mandantenadministrators (z. B.</p><p>Name, Adresse, E-Mail-Adresse, Telefonnummer des Mandantenadministrators)</p><p>– Bereitstellung des Kunden</p><p>Informationen</p>|
|Pseudonyme Bezeichner für Endbenutzer (EUPI)|<p>Ein von Microsoft erstellter Bezeichner, der an den Benutzer eines Microsoft-Diensts gebunden ist. Wenn EUPI mit anderen Informationen kombiniert wird, z. B. einer Zuordnungstabelle, wird der Endbenutzer identifiziert. EUPI enthält keine vom Kunden hochgeladenen oder erstellten Informationen.</p><p>(Kundeninhalte oder EUII)</p>|<p>– Benutzer-GUIDs, PUIDs oder SIDs</p><p>- Sitzungs-IDs</p>|
|Organisationsidentifizierbare Informationen (OII)|Daten, die verwendet werden können, um einen Mandanten zu identifizieren, in der Regel Konfigurations- oder Nutzungsdaten. Diese Daten können nicht mit einem Benutzer verknüpft werden und enthalten keine Kundeninhalte.|<p>- Mandanten-ID (nicht-GUID)</p><p>- Domänenname in E-Mail-Adresse (xxx@contoso.com) oder einer anderen mandantenspezifischen Domäne</p><p>Informationen</p>|
|Systemmetadaten|Beim Ausführen des Diensts oder Programms generierte Daten, die nicht mit einem Benutzer oder Mandanten verknüpft werden können.|<p>- Ereignisprotokolle</p><p>- Nutzungsdaten</p><p>- Konfigurationsdaten</p>|

Technologiebeschreibung

Die Technologie sendet Daten an Microsoft, um Probleme bei der Bereitstellung zu überwachen, zu diagnostizieren und zu mindern. Beispiele hierfür sind:

1. Sicherstellen, dass das Gerät auf dem neuesten Stand ist (einschließlich App, Betriebssystem, Treiber, F/W)
1. Sicherstellen, dass das Gerät einsatzbereit ist (angemeldet, alle Peripheriegeräte, die einen fehlerfreien Zustand melden usw.)
1. Sicherstellen, dass die Umgebung bereit ist (bereitgestellte Konten, Netzwerkgeschwindigkeiten sind schnell genug usw.)
1. Ermitteln, ob Hardware- oder Installationsprobleme auftreten können (z. B. lose Verkabelung)
1. Heuristik zur Ermittlung von Problemen (übermäßige Neustarts usw.) 

Die Technologie verwaltet das Gerät mit Aktionen wie

1. Software aktualisieren
1. Beheben von Problemen durch Neustarts, Zurücksetzen von USB-Verbindungen & Zuständen
1. Sammeln sie bestimmte Protokolle, um Probleme zu diagnostizieren

Die Technologie überwacht oder zeichnet keine Audio-, Video-, Medien- oder Besprechungsinhalte aus Solution Kits auf. 

### <a name="service-collected-data-categories"></a>Vom Dienst erfasste Datenkategorien
 
|Kategorie|Details|Grund für die Abfrage|
| :- | :- | :- |
|Laufende Datensammlung & Management|IP-Adresse, Identität des Raumkontos (Exchange, Skype for Business und/oder Teams), Standortkoordinaten, E-Mails und Kommunikation innerhalb des Portals mit Microsoft oder Software|Identifizieren und Herstellen einer Verbindung mit dem System unter Verwaltung; Identifizieren, Diagnostizieren und Verringern von Fehlern; Nachverfolgen von Nutzung, Analysen und Erkenntnissen; Abfrage& Verbindungsstatus reparieren|
|Ad hoc Data Collection & Management|<p>Ereignisprotokollinformationen, Benutzeraktivität/Identität des angemeldeten Raumbenutzers zusammen mit Diagnoseinformationen\*, Windows-Systemabfragen (Beispiele: Liste der USB-Geräte,</p><p>Energiezustand usw.)</p>|Identifizieren, Diagnostizieren und Minimieren von Fehlern und für Nutzung, Analysen und Einblicke|
|<p>Testversionsregistrierung und</p><p>Installationsanforderungen</p>|<p>Windows-Systemabfragen</p><p>Beispiele: Liste der USB-Geräte, Energiezustand usw.</p>|<p>Erforderlich für Registrierung, Onboarding, Bestellung und Lieferung,</p><p>und setup for the Trial.</p>|

\* Vertrauliche PII im Geräteaktivitätsprotokoll werden lokal gelöscht (nicht von der Technologie erfasst):

1. Besprechungsthema & Textkörper
1. Visitenkarteninformationen für Besprechungsteilnehmer (z. B. Titel, Telefonnummer usw.)
1. Inhalt der Besprechungsnachricht

>> [!NOTE]
>Wenn Microsoft die Technologie weiterentwickelt, können sich die spezifischen Daten ändern. 

### <a name="agent-data-classification"></a>Agent-Datenklassifizierung

**Detaillierte Beschreibung aller Daten, die der MTRP-Agent während der laufenden Überwachung erfasst**
|Beschreibung der gesammelten Daten|Klassifizierung|
| :- | :- |
|Identität eines freigegebenen Geräts|OII|
|Kunden-ID|OII|
|MMR-Agent-Verzeichnisspeicherort|Systemmetadaten|
|MTR-App protokolliert Verzeichnisspeicherort|Systemmetadaten|
|Seriennummer des Geräts|Systemmetadaten|
|Geräte-BIOS-Informationen|Systemmetadaten|

|Version des MMR-Agents|Systemmetadaten|
| :- | :- |
|Version der MTR-App|Systemmetadaten|
|Version der Teams-App|Systemmetadaten|
|Zeit des nachts ausgeführten Wartungsauftrags für die MTR-App|Systemmetadaten|
|UPDATE-URL des MMR-Agents|Systemmetadaten|
|MMR-Agent-Ring|Systemmetadaten|
|Windows-Betriebssystemversion|Systemmetadaten|
|Aktuell angemeldeter Benutzer|Systemmetadaten|
|GUID der MMR-Agent-Sitzung|Systemmetadaten|
|Domänenname|Systemmetadaten|
|Zeit seit dem letzten Neustart des Betriebssystems|Systemmetadaten|
|Zeit seit dem letzten Start des MMR-Agents|Systemmetadaten|
|MTR-Gerätemodell und -Modell|Systemmetadaten|
|Status des verwendeten Geräts|Systemmetadaten|
|Geräte-Onboarding-Typ|Systemmetadaten|
|Anzahl der angeschlossenen Monitore|Systemmetadaten|
|MTR-Lautsprecherdetails|Systemmetadaten|
|MTR-Mikrofondetails|Systemmetadaten|
|MTR-Standardlautsprecherdetails|Systemmetadaten|
|Einstellung für die automatische Bildschirmfreigabe der MTR-App|Systemmetadaten|
|Bluetooth-Ankündigungseinstellung der MTR-App|Systemmetadaten|
|Datum der letzten Änderung des Kennworts|Systemmetadaten|
|MTR-Kennwortdrehungseinstellung|Systemmetadaten|
|MTR-App Teams/Skype for Business-Einstellung|Systemmetadaten|
|MTR-App-Updatering|Systemmetadaten|
|MTR-App-Inhaltskameraeinstellung|Systemmetadaten|
|Einstellung für MTR-App-Besprechungsnamen|Systemmetadaten|
|MTR-App vor dem Raum zeigt Einstellung an|Systemmetadaten|
|GUID der MTR-App|Systemmetadaten|
|Proxyadresse und Port|Systemmetadaten|
|Integrität des MTR-Geräts|Systemmetadaten|
|Details des MTR-Raumkontos|OII|
|IPV4-Adresse und IPV6-Adresse|OII|
|Längengrad und Breitengrad|OII|
|MTR-Gerätehostname|OII|
|MTR-Gerätezeitzone|Systemmetadaten|
|Status der MTR-App|Systemmetadaten|
|Crestron-Dienstdetails|Systemmetadaten|
|Logitech-Firmwareversion und Logitech-Synchronisierungsversion|Systemmetadaten|
|Cpu-Gesamtprozentsatz in Verwendung|Systemmetadaten|
|Gesamtzahl der verwendeten RAM-Speicher|Systemmetadaten|
|VON MTR Skype oder Teams Apps verwendete CPU|Systemmetadaten|
|MTR-Gerätetemperatur|Systemmetadaten|
|Status interner Datenträgerlaufwerke|Systemmetadaten|
|Details zu MTR-App-Abstürzen|Systemmetadaten|
|Details zu erkannten Speicherlecks, die durch Apps auf dem Gerät verursacht werden|Systemmetadaten|

|<p>Details aller Geräte-Bluescreen-Fehler, die über die</p><p>letzte 24 Stunden</p>|Systemmetadaten|
| :- | :- |
|<p>Details zu allen Fehlern, die die MTR-App während Besprechungen auf</p><p>das Gerät</p>|Systemmetadaten|
|Installierte Softwaredetails|Systemmetadaten|
|Details zu installierten/ausstehenden/fehlenden Hotfixes|Systemmetadaten|
|Erkannte Hardwaredetails|Systemmetadaten|
|Details aller Treiber auf dem Gerät|Systemmetadaten|
|Details zu allen MMR-Gerätekorrekturen|Systemmetadaten|
|Details zur Raumnutzung während der letzten 24 Stunden, Besprechungszeit und Anzahl|Systemmetadaten|
|Details zu automatischen Windows Store-Updates|Systemmetadaten|
|Details zu Windows-Betriebssystemupdates|Systemmetadaten|
|Details zum Zerkleinern von MMR-Agenten|Systemmetadaten|
|MMR-Agent– Verbindungsfehlerdetails|Systemmetadaten|
|Details dazu, ob die TPM-Sicherheit aktiviert ist|Systemmetadaten|
|Details zum MTR-Geräteverbindungsstatus|Systemmetadaten|

**Daten-MTRP-Agent sammelt für Vorfalldiagnose und -behebung**
|Beschreibung der gesammelten Daten|Klassifizierung|
| :- | :- |
|<p>Ereignisprotokolle: System, Anwendung, Skype Raumsystem, Microsoft- Windows-AppXDeploymentServer%4Operational, Microsoft-Windows- PowerShell%4Operational, Microsoft-Windows- AppXDeployment%4Operational,Microsoft-Windows- AppXDeploymentServer%4Operational, Microsoft-Windows- TWinUI%4Operational, Microsoft Managed Rooms, Microsoft-Windows-</p><p>TaskScheduler%4Operational, Sicherheit</p>|Systemmetadaten|
|Bearbeitete MTR-App-Protokolle\*|Systemmetadaten|
|Microsoft Teams-Protokolle|Systemmetadaten|
|MMR-Agent sqlLitedb|Systemmetadaten|
|Details zu Den Energiezustandsinformationen des Geräts|Systemmetadaten|
|Gerätegruppenrichtlinieninformationen|Systemmetadaten|
|Überwachungsablaufverfolgung aller MMR-Agent-Aktionen|Systemmetadaten|
\* Vertrauliche PII im Geräteaktivitätsprotokoll werden lokal gelöscht.

### <a name="enrollment"></a>Registrierung


Diese Technologie wird beim Onlineportal für automatisierte Überwachungs- und Supportdienste, einschließlich Diagnose und Berichterstellung, registriert. Die Registrierung erfolgt über eine Netzwerkkommunikation, die mit dem auf dem Gerät basierenden öffentlichen Schlüssel (Trusted Platform Module, TPM) verschlüsselt wird.

### <a name="un-enrollment"></a>Registrierung aufheben

Die Registrierung des Geräts kann aufgehoben werden, indem die Technologie deinstalliert wird. Microsoft entfernt das Gerät auch während der Außerbetriebnahme aus der Back-End-Überwachung und kann gesammelte Daten auf Anfrage löschen.

### <a name="data-flow"></a>Datenfluss

Die Technologie fügt einen Datenfluss vom Agent zu MTR Managed Services hinzu.

![Datenfluss vom Agent zu MTR Managed Services](../media/data-and-privacy-info-005.png)

Durch das Aktivieren der Integration von Microsoft Defender für Endpunkt wird ein zusätzlicher Datenfluss vom MDE-Agent zur Microsoft Defender-Infrastruktur eingeführt.

![zusätzlicher Datenfluss vom MDE-Agent zu Defender](../media/data-and-privacy-info-006.png)

## <a name="compliance"></a>Compliance

Alle Ingenieure, die an dem Produkt arbeiten, müssen sich einer Schulung zur Sicherheits- und Datenschutzsensibilisierung unterziehen. Microsoft stellt außerdem sicher, dass alle Mitarbeiter die Annahme von Verantwortlichkeiten für Datenschutzanforderungen bestätigen.

Die Technologie bietet regionale Datenaufbewahrungsunterstützung über die Rechenzentren in Europa (EU), Asien-Pazifik (APAC) und den USA (USA). Dies bedeutet, dass die Dienstkunden Daten im Zusammenhang mit der Organisation im Rechenzentrum ihrer ausgewählten Region gespeichert haben.

## <a name="additional-resources"></a>Weitere Ressourcen

Microsoft Teams Rooms Security:/microsoftteams/rooms/security Microsoft Privacy Statement: https://aka.ms/privacy Datenverwaltung bei Microsoft: https://www.microsoft.com/trust-center/privacy/data-management Die Beschreibung des Technologiediensts: [Microsoft Teams vom Verwalteten Raumdienst](microsoft-teams-rooms-premium.md)
