---
title: Erste Schritte mit Microsoft Teams für Fernunterricht
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith, lakuan
description: Startup-Anleitung für Fernunterricht für Microsoft Teams für Bildungseinrichtungen.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 231007549102b8cddc02a0d2a5d29266662b4b2f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466023"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Erste Schritte mit Microsoft Teams für Fernunterricht

In diesem Artikel werden die Schritte zur IT-Verwaltung behandelt, um Ihre Bildungseinrichtung für remote Learning mit Microsoft Teams einzurichten.

In Teams können **Lehrkräfte Folgendes** :

- Sprechen Sie schnell mit schülern.
- Freigeben von Dateien und Websites.
- Erstellen Sie OneNote-Kursnotizbücher.
  - Organisieren Sie interaktive Lektionen.
  - Geben Sie effektives und zeitnahes Feedback.
- Verteilen und Benoten von Aufgaben.
- Teilen Sie Unterrichtsmaterialien in Professional Learning Communities.

**Education-Administratoren und -Mitarbeiter** können:

- Bleiben Sie über Ereignisse auf dem Laufenden.
- Zusammenarbeiten mithilfe von Mitarbeiterteams für Ankündigungen und aktuelle Unterhaltungen.

# <a name="accounts--licenses"></a>[Konten & Lizenzen](#tab/accounts)

## <a name="user-accounts-licenses-and-identity-security"></a>Sicherheit von Benutzerkonten, Lizenzen und Identität

Teams verwendet Microsoft 365, um Benutzer zu authentifizieren und Dienste bereitzustellen. Alle Benutzer sollten Microsoft 365-Identitäten eingerichtet haben, um die Zusammenarbeit zu erleichtern.

Wenn noch keine Benutzeridentitäten vorhanden sind, führen Sie diesen Prozess aus, um sie einzurichten:

1. [Erstellen Sie Benutzer mit School Data Sync](/microsoft-365/education/deploy/school-data-sync).
2. [Weisen Sie Benutzern Lizenzen zu](teams-edu-licensing.md).
3. [Erstellen Sie Microsoft 365-Gruppen](Office-365-groups.md).
4. [Einrichten von Exchange](Exchange-Teams-interact.md).
5. [Richten Sie SharePoint und OneDrive ein](SharePoint-OneDrive-interact.md).
6. [Richten Sie Benutzer ein, die über Google-E-Mails verfügen](/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

Microsoft Teams ist in allen Microsoft 365-Plänen enthalten, einschließlich des kostenlosen A1-Education-Plans.

Anleitungen zur Bereitstellung von Microsoft 365 und zum Einrichten von Teams finden Sie unter ["Erstellen Ihres Microsoft 365-Mandanten](/microsoft-365/education/deploy/create-your-office-365-tenant)".

# <a name="set-up-teams"></a>[Einrichten von Teams](#tab/setup)

## <a name="easily-set-up-teams"></a>Müheloses Einrichten von Teams

Hier sind die beiden Dinge, die Sie tun müssen, um mit Teams in Betrieb zu gehen:

### <a name="1-allow-users-to-create-teams"></a>1. Benutzern das Erstellen von Teams erlauben

**Standardmäßig kann jeder Microsoft 365-Gruppen und Teams erstellen**, aber diese Möglichkeit ist möglicherweise nicht immer angemessen.

Einige Schulen möchten z. B. verhindern, dass Schüler Teams ohne Aufsicht erstellen. Die Erstellung von Microsoft 365-Gruppen und -Teams kann [auf bestimmte Sicherheitsgruppen beschränkt](/microsoft-365/admin/create-groups/manage-creation-of-groups) werden.

Für Hochschulen empfehlen wir, dass jeder, einschließlich der Studenten, Teams für Kurse, Forschung, Gruppenprojekte und Studiengruppen erstellen kann.

Eine exemplarische Anleitung zum Erstellen von Teams finden [Sie unter Erstellen eines Kursteams in Microsoft Teams](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).

### <a name="2-configure-user-experiences-using-policies"></a>2. Benutzeroberflächen mithilfe von Richtlinien konfigurieren

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Schauen Sie sich [an, wie Sie Kursteilnehmer in Teams für den Fernunterricht schützen](https://support.office.com/article/f00fa399-0473-4d31-ab72-644c137e11c8).
>
> Wenn Sie unsere Edu-Richtlinienempfehlungen anzeigen möchten, lesen Sie [die Teams-Richtlinien und Richtlinienpakete für Bildungseinrichtungen](policy-packages-edu.md).

Teams-Richtlinien steuern die Für bestimmte Benutzer oder Gruppen verfügbaren Funktionen. Richtlinien können definieren, wer privaten Chat, private Anrufe, Besprechungsplanung, Inhaltstypen, die freigegeben werden können, und vieles mehr verwenden darf.

**Hochschulmitarbeiter, Lehrkräfte und Schüler können die standardmäßigen** (globalen) Richtlinien verwenden. Sie können Richtlinien anpassen, um Teams weitere Funktionen hinzuzufügen, einschließlich [Übersetzungsfunktionen](messaging-policies-in-teams.md#messaging-policy-settings) und [automatischer Besprechungstranskription](meetings-policies-recording-and-transcription.md#transcription).

**Schüler der Primarstufe** benötigen möglicherweise eingeschränkte Funktionen. Es wird empfohlen, Änderungen an der Richtlinie "Global (organisationsweiter Standard)" vorzunehmen.

**Mitarbeitern und Lehrkräften der Grundschule** sollten Richtlinien zugewiesen werden, die wichtige Funktionen gewähren, z. B. das Zulassen von privatem Chat und die Planung von Besprechungen. [Weisen Sie Mitarbeitern und Pädagogen diese Richtlinien in großen Mengen zu](batch-group-policy-assignment-edu.md).

> [!IMPORTANT]
> Für Besprechungsrichtlinien, die allen Benutzern zugewiesen sind, empfehlen wir, die Einstellung " **Personen automatisch zulassen** " für **"Jeder in Ihrer Organisation**" festzulegen. Dadurch wird sichergestellt, dass nicht authentifizierte Benutzer aus dem Wartebereich zugelassen werden müssen, bevor sie an Teams-Besprechungen teilnehmen können.
>
> Weitere Informationen finden Sie unter [Besprechungsrichtlinien in Teams verwalten](meeting-policies-participants-and-guests.md#automatically-admit-people).

# <a name="class-teams"></a>[Kursteams](#tab/class-teams)

## <a name="create-class-teams-for-secure-classroom-use"></a>Erstellen von Kursteams für sichere Nutzung im Unterricht

Microsoft Teams für Bildungseinrichtungen bietet [spezielle Teamtypen](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) für die Nutzung in der Ausbildung. Der Teamtyp [Klasse](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) wurde für die Nutzung im Unterricht konzipiert und bietet spezifische Funktionen, die den Unterricht unterstützen, einschließlich:

- Zuordnungen.
- Klasse.
- OneNote-Kursnotizbuch.
- [Ordner "Kursmaterialien](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)  " zum Sichern schreibgeschützter Inhalte für Kursteilnehmer.
- [Insights](./class-insights.md), um Echtzeit-Daten bezüglich des Engagements von Schülern/Studenten, Aufgaben und des Wohlbefindens aller Klassenzimmer zu liefern.
- [Early educator access](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) to set up the class before students are added.
- Die Möglichkeit, störende Schüler und andere spezielle Berechtigungen stummzuschalten.

Kursteams können erstellt werden über:

- [School Data Sync (SDS)](#automatic-team-creation-using-sds).
- [Von Lehrkräften geleitete Erstellung mit Microsoft 365-Klassengruppen](#educator-led-team-creation-from-microsoft-365-class-groups).
- [PowerShell-Skripts mit Graph-APIs](#powershell-script-using-graph-apis).
- [Manuelle Teamerstellung](#manual-team-creation).

Wir werden mehrere Optionen durchgehen, um Ihnen bei der Auswahl des richtigen Bereitstellungspfads zu helfen, der Ihren Anforderungen am besten entspricht.

### <a name="automatic-team-creation-using-sds"></a>Automatische Teamerstellung mit SDS

[School Data Sync (SDS)](/SchoolDataSync) liest die Daten aus dem Datensatzsystem einer Bildungseinrichtung, z. B. einem Student Information System (SIS) oder Learning Management System (LMS).

SDS kann Daten aus jedem Datensatzsystem importieren und verfügt über integrierte Connectors für viele [SIS-Anbieter](/schooldatasync/frequently-asked-questions#what-sismis-vendors-does-school-data-sync-support).  

#### <a name="benefits-of-sds"></a>Vorteile von SDS

- Erstellt automatisch Benutzer und wendet Lizenzen an.
- Erstellt und verwaltet automatisch Kursteams.
- Wird mit SIS/LMS synchronisiert, um Änderungen der Schülermitgliedschaft aufrechtzuerhalten.
- [Ermöglicht Lehrkräften die Vorbereitung von Kursen vor dem Hinzufügen von Kursteilnehmern](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).
- Sicherheitsgruppen können automatisch erstellt werden.
- Erstellt administrative Einheiten für die bereichsbezogene administrative Delegierung.
- [Ermöglicht die Kennwortzurücksetzung für Lehrkräfte](/schooldatasync/how-to-enable-teacher-password-reset).
- Verfügt über integrierte Bereinigungsfunktionen zum Umbenennen und Archivieren von Gruppen und Teams.
- [Synchronisiert Noten von Teams mit SIS](/schooldatasync/grade-sync).
- [Schützt personenbezogene Daten von Kursteilnehmern](/schooldatasync/protecting-student-personal-data).
- Verfolgt und verwaltet die Zustimmung des Erziehungsberechtigten.
- Bietet bessere Education Insights Daten.

#### <a name="considerations-for-sds"></a>Überlegungen zu SDS

SDS erstellt Teams in zwei Schritten:

1. SDS erstellt eine Microsoft 365-Gruppe in Azure Active Directory (Azure AD).
2. SDS wandelt diese Gruppe automatisch in ein Team um.

Der zweite Schritt beim Erstellen von Teams ist in SDS optional. Ein Administrator möchte möglicherweise, je nach Bereitstellungszeit und der Anzahl nicht verwendeter Teams, die daraus resultieren können, Teams nicht automatisch erstellen. Sehen Sie sich stattdessen die [Von Dozenten geleitete Teamerstellungsmethode an](#educator-led-team-creation-from-microsoft-365-class-groups).  

#### <a name="get-started-with-sds"></a>Erste Schritte mit SDS

To get started, go to [School Data Sync (SDS)](/SchoolDataSync) and contact [https://aka.ms/sdssupport](https://aka.ms/sdssupport) for free deployment assistance.  

### <a name="educator-led-team-creation-from-microsoft-365-class-groups"></a>Von Lehrkräften geleitete Teamerstellung aus Microsoft 365-Klassengruppen

Die von Lehrkräften geleitete Teamerstellung erleichtert Lehrkräften das Erstellen der benötigten Kurse.  

Bei diesem Ansatz können Sie entweder SDS verwenden, um Gruppen für jede Klasse zu erstellen (empfohlen) oder [Graph-API](/graph/api/educationroot-post-classes) verwenden, um sie selbst zu erstellen.

Nachdem Kursgruppen vorbereitet wurden, können Lehrkräfte ihre Gruppen in Teams konvertieren:

1. Wählen Sie die Registerkarte "Teams" in Teams aus.
2. Wählen Sie oben im Client das Symbol " **Vorgeschlagene Klassen** " aus.

#### <a name="benefits-of-educator-led-team-creation"></a>Vorteile der Von Lehrkräften geleiteten Teamerstellung

- Kurse werden vorbereitet und vorgeschlagen, aber nicht erstellt, es sei denn, der Dozent beabsichtigt, sie zu verwenden.
- Für Institutionen mit mehr als 500.000 Teams reduziert diese Methode die Anzahl unnötiger Teams.
- [SDS-Vorteile](#benefits-of-sds).
- Graph-API Vorteile.
  - Gibt Lehrkräften die Kontrolle, welche Klassen erstellt werden.
  - Erfordert keine Integration in SDS.

#### <a name="considerations-for-educator-led-team-creation"></a>Überlegungen zur Erstellung von von Lehrkräften geleiteten Teams

- Nicht vollständig automatisiert und erfordert Handlung einer Lehrkraft.
- Lehrkräfte, die nicht über die Berechtigung zum Erstellen von Teams verfügen, können weiterhin [Teams aus vorhandenen Gruppen erstellen](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).
- Graph-API erfordert ein hohes Maß an technischem Know-how, Zeit zum Erstellen und Ausführen des Skripts und Zeit zum Beheben von Problemen.

#### <a name="get-started-with-educator-led-team-creation"></a>Erste Schritte mit der Erstellung von von Lehrkräften geleiteten Teams

Um mit der SDS-Methode zu beginnen, wechseln Sie zu [School Data Sync (SDS),](/SchoolDataSync) und wenden Sie sich an die [https://aka.ms/sdssupport](https://aka.ms/sdssupport) kostenlose Bereitstellungsunterstützung.

- Sie müssen die automatische Teamerstellung in Ihrem SDS-Profil deaktivieren.
- Sie können eine Kombination aus automatischer und von Lehrkräften geleiteter Teamerstellung für Kursteams verwenden, indem Sie zwei SDS-Profile verwenden.

Wenn Sie die Graph-API-Methode verwenden möchten, lesen Sie [Graph-API](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-1.0&preserve-view=true) und [Erstellen eines Klassenteams](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true).  

### <a name="powershell-script-using-graph-apis"></a>PowerShell-Skript mit Graph-APIs

Mit PowerShell können Sie ein Skript schreiben, um Teams und Kanäle zu erstellen und Einstellungen automatisch zu konfigurieren.

Bei dieser Methode muss der Administrator [zuerst die Gruppe erstellen, Lehrkräfte und Schüler hinzufügen und dann das Team erstellen](/graph/teams-create-group-and-team).

Sie können die [Microsoft Graph-API auch verwenden, um Teams zu erstellen, zu konfigurieren, zu klonen und zu archivieren](/graph/api/resources/teams-api-overview).

#### <a name="benefits-of-powershell-scripts"></a>Vorteile von PowerShell-Skripts

- Gibt IT-Administratoren die Kontrolle über die Erstellung von Kursen.
- Option zum Erstellen von frühzeitigem Zugriff für Lehrkräfte auf Teams oder von sofortigem Zugriff für Schüler/Studenten auf Teams.
- [Synchronisiert Änderungen der Schülermitgliedschaft mit der Azure AD-Gruppe](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

#### <a name="considerations-for-powershell-scripts"></a>Überlegungen zu PowerShell-Skripts

- Erfordert ein hohes Maß an technischem Know-how und Zeit zum Erstellen und Ausführen des Skripts, sowie zum Beheben von Problemen beim Erstellen von Kursgruppen.
- Keine integrierte Fehlerbehandlung oder Wiederholungsversuche.
- Mitgliedschaftsänderungen werden nicht mit SIS synchronisiert.

> [!NOTE]
> Kursteams benötigen eine versteckte Gruppenmitgliedschaft, sodass nur Lehrkräfte und Schüler/Studenten innerhalb des Kurses dessen Mitglieder sehen können. Informationen zum Erstellen einer Microsoft 365-Klassengruppe finden [Sie unter Erstellen eines Kursteams](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) , um die Datenschutzanforderungen zu erfüllen.

### <a name="manual-team-creation"></a>Manuelle Teamerstellung

Benutzer können ihre Teams-Erfahrung anpassen, indem sie die Möglichkeit haben, eigene Teams zu erstellen.

Abhängig von den Berechtigungen eines Benutzers kann er:

- [Richten Sie ihre eigenen Teams ein, und laden Sie Benutzer ein, einschließlich Der Kursteilnehmer](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch).
- [Fügen Sie dem Team manuell Benutzer hinzu](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954).
- [Freigeben eines Joincodes](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).
- [Geben Sie einen Link für das Team frei](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

Am besten fügen Lehrkräfte ihre Kursteilnehmer zum Team hinzu, um sicherzustellen, dass die Kursteilnehmer Zugriff erhalten und benachrichtigt werden, dass sie hinzugefügt wurden.

#### <a name="benefits-of-manual-team-creation"></a>Vorteile der manuellen Teamerstellung

- Gibt Lehrkräften die volle Kontrolle über die Erstellung von Kursen.
- Kursteams werden sofort erstellt.

#### <a name="considerations-for-manual-team-creation"></a>Überlegungen zur manuellen Teamerstellung

- Erfordert Handlung und Zeit einer Lehrkraft.
- Die Mitgliedschaft von Kursteilnehmern wird nicht mit SIS synchronisiert und erfordert eine manuelle Verwaltung.
- Die Kursteilnehmer erhalten sofortigen Zugriff auf Kursteams.

### <a name="recommended-best-practices"></a>Empfohlene bewährte Methoden

- Stellen Sie frühzeitig bereit, um sicherzustellen, dass alles zuverlässig funktioniert und für den ersten Schultag bereit ist.

- Bei Problemen mit der automatischen SDS-Teamerstellung können Lehrkräfte die [von Lehrkräften geleitete Teamerstellungsmethode](#educator-led-team-creation-from-microsoft-365-class-groups) verwenden, um den Vorgang erneut zu versuchen. [Die manuelle Teamerstellung](#manual-team-creation) ist eine weitere Lösung, aber Klassen werden nicht mit SIS synchronisiert.

- Das Mandanten-Team-Limit ist 500.000 Teams. Daher sollten Administratoren die Anzahl nicht verwendeter Teams reduzieren, um zu vermeiden, dass diese Grenzwerte erreicht werden. Weitere Informationen finden Sie unter [Grenzwerte und Spezifikationen für Microsoft Teams](limits-specifications-teams.md).  

# <a name="educator-early-access"></a>[Frühzeitiger Zugriff für Lehrkräfte](#tab/early-access)

## <a name="early-access-to-class-teams"></a>Frühzeitiger Zugriff auf Kursteams

Early Access Class Teams ermöglicht Lehrkräften den Zugriff auf ihre Kursteams, bevor die Kursteilnehmer sie anzeigen können. Lehrkräfte haben Zeit zum Einrichten, Hinzufügen von Dateien und Organisieren, bevor sie ihren Kursteilnehmern Zugriff gewähren.

Wenn die Kursteilnehmer auf das Team zugreifen können, können sie [ihren Kurs aktivieren](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).

### <a name="how-do-i-create-class-teams-that-allow-educators-early-access-to-set-up-a-team-before-admitting-students"></a>Wie erstelle ich Kursteams, die Lehrkräften frühzeitigen Zugriff zum Einrichten eines Teams ermöglichen, bevor ich Schüler/Studenten zulasse?

Teams, die aus Gruppen erstellt wurden (über SDS, von Dozenten geleitet oder mithilfe der Graph-API), erstellen standardmäßig automatisch Teams für frühzeitigen Zugriff.

Wenn Sie Ihre eigenen Teams für frühzeitigen Zugriff mithilfe der Graph-API erstellen möchten, müssen Sie zuerst [einen Kurs erstellen](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) und dann [das Team aus einer Gruppe erstellen](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

### <a name="how-do-i-check-if-a-class-is-activated"></a>Wie kann ich überprüfen, ob ein Kurs aktiviert wurde?

Zeigen Sie im [Teamressourcentyp](/graph/api/resources/team?view=graph-rest-beta&preserve-view=true) die Eigenschaft ["MembershipLimitedToOwners](/graph/api/resources/team?view=graph-rest-beta#properties&preserve-view=true)" an, um festzustellen, ob eine Klasse aktiviert ist.

Verwenden Sie die [Get Team API](/graph/api/team-get?tabs=http&view=graph-rest-beta&preserve-view=true) (API zum Abrufen des Teams), um die Eigenschaft ```isMembershipLimitedToOwners``` für einen bestimmten Kurs abzufragen. Wenn das Team aktiviert wurde, wird der Wert „false“ zurückgegeben. Wenn das Team nicht aktiviert wurde, wird der Wert "true" zurückgegeben.

### <a name="how-do-i-activate-a-class-for-an-educator"></a>Wie aktiviere ich einen Kurs für eine Lehrkraft?

Verwenden Sie die [Update Team-API](/graph/api/team-update?tabs=http&view=graph-rest-beta&preserve-view=true), und legen Sie die ```isMembershipLimitedToOwners``` Eigenschaft auf "false" fest, um das Team im Namen Ihrer Lehrkraft zu aktivieren. Nachdem ein Team aktiviert wurde, kann es nicht mehr rückgängig gemacht werden.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Erstellen von Mitarbeiterteams für die Kommunikation und Zusammenarbeit von Mitarbeitern

[Mitarbeiterteams](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) sind für Education-Administratoren und -Mitarbeiter vorgesehen, um Informationen auszutauschen und an institutsweiten Initiativen zusammenzuarbeiten.

Education-Administratoren können dem Team Mithilfe des Assistenten zum Erstellen von Teams Mitarbeiter hinzufügen, [indem sie Mitglieder hinzufügen, nachdem das Team erstellt wurde](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9), oder indem [sie einen Teilnahmecode oder einen Link zum Team freigeben](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

# <a name="meeting-scenarios"></a>[Besprechungsszenarien](#tab/scenarios)

## <a name="teams-meeting-scenarios"></a>Teams-Besprechungsszenarien

### <a name="collaborative-meetings-for-virtual-classes"></a>Gemeinsame Besprechungen für virtuelle Klassen

[Microsoft Teams-Besprechungen ](./tutorial-meetings-in-teams.yml) unterstützen bis zu 250 gleichzeitige Teilnehmer, und bieten die Möglichkeit zur Verwendung von Audio, Video, [Inhaltsfreigaben](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), Whiteboards und freigegebenen Notizen.

Besprechungen können sein:

- [Innerhalb des Teams-Clients geplant](./tutorial-meetings-in-teams.yml).
- Aufgezeichnet und gespeichert, damit die Teilnehmer dies später überprüfen können.
- [Transkribiert, um Inhalte leicht zu finden](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308).
- Zugriff über eine Laptop- oder Mobiltelefon-Webcam, ein Mikrofon und einen Lautsprecher.
- [Optimiert für bestimmte Geräte](https://products.office.com/microsoft-teams/across-devices/devices).
- Für alle Teilnehmer beendet, um sicherzustellen, dass die Kursteilnehmer nicht unbeaufsichtigt an einer Besprechung teilnehmen.

### <a name="districtuniversity-events-or-updates"></a>Schulbezirk-/Universitätsereignisse oder -aktualisierungen

Einige Besprechungen haben ein großes Publikum und zusätzliche Produktionsanforderungen. Diese Besprechungen haben häufig definierte Referenten, Produzenten und moderierte F&A.

Teams unterstützt diese Sitzungen mit [Microsoft Teams-Liveereignissen](teams-live-events/what-are-teams-live-events.md).

Liveereignisse können für Szenarien verwendet werden, z. B.:

- Bezirks- oder universitätsweite Updates.
- Führungsadressen.
- Anweisungen für große Kurse oder Schülergruppen.
- Erweiterung auf Ihre Community.

Erfahren Sie mehr über die Durchführung von Live-Sitzungen unter:

- [Planen und planen Sie ein Liveereignis](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).
- [Produzieren sie ein Liveereignis](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb).
- [Nehmen Sie an einem Liveereignis teil](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac).
- [Moderieren eines F-&A](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

# <a name="resources"></a>[Ressourcen](#tab/resources)

## <a name="support-resources"></a>Supportressourcen

Eine allgemeine Übersicht über den Umstieg auf Remote Learning [, beginnen Sie hier](https://www.microsoft.com/education/remote-learning)

Wenn Sie EIN IT-Administrator, Dozent, Schüler oder Erziehungsberechtigter sind, können Ihnen diese Ressourcen bei der Verwendung von Teams helfen:

- **IT-Admins**
  - [Teams-Features nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).
  - [Laden Sie Teams-Clients herunter, und verteilen Sie sie](get-clients.md).
  - [Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams).
  - [Teams für virtualisierte Desktopinfrastruktur](./teams-for-vdi.md).
  - [Überwachen und Verwalten der Anrufqualität](monitor-call-quality-qos.md).
  - [Überprüfen sie den Dienststatus für Teams](service-health.md).
  - [Optimieren des Microsoft 365-Datenverkehrs für Remotemitarbeiter](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571).
  - [Supportkontakte für Teams](/microsoft-365/admin/contact-support-for-business-products).
  - [Teams für Education Webinare](https://aka.ms/TeamsEDUWebinars).

- **Dozenten**
  - [Hilfecenter für Lehrkräfte](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).
  - [Hilfe zum Fernlernen](https://aka.ms/RemoteLearningHelp).
  - [Laden Sie Teams herunter](get-clients.md).
  - [Teams für Education Webinare](https://aka.ms/TeamsEDUWebinars).
  - [Onlinekurs für Lehrkräfte, die Teams verwenden](https://education.microsoft.com/course/9c9f5c11/overview).
  - [Onlinekurs zum Erstellen von Collaborative Learning-Umgebungen mit Teams](https://education.microsoft.com/course/b1e15cfc/overview).
  - [Legen Sie ein Supportticket ab](https://www.microsoft.com/microsoft-teams/download-app).

- **Studenten**
  - [Hilfecenter für Kursteilnehmer](https://support.office.com/article/student-help-center-395ab230-55bf-44c6-b265-e832d729b694).
  - [Hilfe zum Fernlernen](https://aka.ms/RemoteLearningHelp).
  - [Laden Sie Teams herunter](https://www.microsoft.com/microsoft-teams/download-app).

- **Wächter**
  - [Hilfe zum Fernlernen](https://aka.ms/RemoteLearningHelp).
  - [Laden Sie Teams herunter](https://www.microsoft.com/microsoft-teams/download-app).

---
