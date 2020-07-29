---
title: Empfohlene Methoden und Best Practices zum Erstellen von Kursteams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: lakuan
description: Erfahren Sie mehr über die empfohlenen Methoden und Best Practices zum Erstellen von Kursteams für Ihre Schule.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e85ef79247bdf35c3c116504af23728a0d268ca5
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429327"
---
# <a name="recommended-methods-and-best-practices-for-creating-class-teams"></a>Empfohlene Methoden und Best Practices zum Erstellen von Kursteams

Microsoft Teams Education bietet  [spezifische Teamtypen](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)  für die Nutzung in Bildungseinrichtungen. Der Teamtyp [Klasse](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) wurde für die Nutzung im Unterricht konzipiert und bietet spezifische Funktionen, die den Unterricht unterstützen, einschließlich:  

- Aufgaben
- Noten
- OneNote-Kursnotizbuch  
- [Ordner für Kursmaterialien](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)  zum Sichern von schreibgeschützten Inhalten für Schüler/Studenten
- [Früher Lehrer-Zugang](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) zum Einrichten des Kurses, bevor Schüler hinzugefügt werden 
- Die Fähigkeit, störende Schüler stummzuschalten und andere Sonderberechtigungen   

Es gibt eine Reihe von Möglichkeiten, wie Kursteams erstellt werden können, und Teams für Bildungseinrichtungen verfügt über eine eigene Gruppe von Bereitstellungstools, um es so einfach wie möglich zu machen. Wir werden mehrere Optionen durchgehen, um Ihnen bei der Auswahl des richtigen Bereitstellungspfads zu helfen, der Ihren Anforderungen am besten entspricht.  

## <a name="automatic-team-creation-using-sds"></a>Automatische Teamerstellung mit SDS

**Diese Feature wird bald verfügbar sein, spätestens Ende Juli 2020.**

Die Automatisierung der Teamerstellung spart den IT-Administratoren und Lehrkräften Zeit. Dadurch wird sichergestellt, dass Lehrkräfte alle ihre Kursteams erstellt haben und bereit zum Einrichten bei der Anmelden sind. [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) ist ein kostenloses Office 365 Education-Tool, das die Daten aus dem Datenerfassungssystem einer Bildungseinrichtung liest, z. B. eines Schülerinformationssystems (SIS) oder Learning Management Systems (LMS). SDS verwendet die Daten, um das Office 365-Setup auf viele verschiedene Arten zu erweitern, darunter das Erstellen von Kursteams in großen Mengen und die Synchronisierung mit Ihrem Informationssystem, um die Mitgliedschaft Ihres Kursleiters und Ihrer Schüler zu aktualisieren, wenn sich die Registrierung ändert. SDS kann Daten aus jedem beliebigen System importieren. Es verfügt über integrierte Konnektoren für viele der [SIS-Anbieter](https://docs.microsoft.com/schooldatasync/what-sis-and-mis-vendors-does-school-data-sync-support). Es wird dringend empfohlen, SDS zu verwenden, da es die folgenden Vorteile bietet.  

### <a name="benefits"></a>Vorteile

- Automatisches Erstellen und Verwalten von Kursteams – Kursleiter können sich bei Teams anmelden und sofort mit dem Lehren beginnen.
- Mitgliedschaftssynchronisierung mit SIS/LMS zum Verwalten von Änderungen der Kursteilnehmer-Mitgliedschaft.
- EDU Customer Success-Team steht zur kostenlosen Bereitstellungsunterstützung zur Verfügung.
- [Früher Lehrer-Zugang](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): Pädagogen haben Zeit, um ihr Team vorzubereiten, bevor sie Studenten aufnehmen.  
- Erstellt optional Benutzer und wendet Office 365-Lizenzen an.
- Erstellt Sicherheitsgruppen für die Verwendung in Office 365, einschließlich der Team Richtlinie.
- Erstellt administrative Einheiten für umfangreich administrative Delegierung und [Lehrer Passwort zurücksetzen](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset). 
- Integrierte Fehler- und Wiederholungsbehandlung, Drosselung des Backoffs und Session-Stabilität für die Verarbeitung in großem Maßstab, um die Arbeit der Administratoren zu reduzieren.  
- Integrierte Bereinigungsfunktionen zum Umbenennen und Archivieren von Gruppen und Teams, sobald diese veraltet sind.
- [Noten-Synchronisierung](https://docs.microsoft.com/schooldatasync/grade-sync): Kursleiter können alle ihre Benotungen in Teams durchführen und die Noten automatisch von Teams zurück in das SIS-Notenbuch übertragen. 
- [Datenschutz für Schüler/Studenten](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): Verhindern Sie, dass Kursteilnehmer nicht-Microsoft-Apps verwenden, und verfolgen und verwalten Sie die Zustimmung der Eltern. 
- Importierte Daten werden verwendet, um Bildungseinblicke mit Benutzerrollen, Organisationen (Schulen) und anderen wichtigen Daten anzureichern.  

### <a name="considerations"></a>Erwägungen

SDS erstellt Teams in zwei Schritten. Im ersten Schritt wird eine Microsoft 365-Gruppe in Azure Active Directory (Azure AD) erstellt, und im zweiten Schritt wird diese Gruppe automatisch in ein Team umgewandelt. Der zweite Schritt beim Erstellen von Teams ist in SDS optional. Ein Administrator möchte möglicherweise, je nach Bereitstellungszeit und der Anzahl nicht verwendeter Teams, die daraus resultieren können, Teams nicht automatisch erstellen. Wir empfehlen Institutionen mit 500.000 Teams oder mehr, die automatische Teamerstellung in SDS zu deaktivieren und die [von Dozenten geleitete Teamerstellungsmethode](#educator-led-team-creation-from-office-365-class-groups) zu verwenden.  

### <a name="get-started"></a>Erste Schritte

Um zu beginnen, wechseln Sie zu [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) und kontaktieren Sie die [https://aka.ms/sdssupport](https://aka.ms/sdssupport) Bereitstellungshilfe.  

## <a name="educator-led-team-creation-from-office-365-class-groups"></a>Von Dozenten geleitete Teamerstellung aus Office 365-Kursgruppen

**Diese Feature wird bald verfügbar sein, spätestens Mitte August 2020.**

Die von Dozenten geleitete Teamerstellung ist eine großartige Bereitstellungsoption, wenn Sie den Lehrkräften die schnelle Erstellung der benötigten Kurse erleichtern möchten. Außerdem empfehlen wir Einrichtungen mit mehr als 500.000 Teams diese Methode verwenden, um die Anzahl der von außen kreierten Teams zu minimieren.  

Bei diesem hybriden Ansatz können Sie entweder SDS zum Erstellen von Gruppen für jeden Kurs (empfohlen) verwenden oder [Graph-API](https://docs.microsoft.com/graph/api/educationroot-post-classes) verwenden, um sie selbst zu erstellen. Nach der Vorbereitung von Kursgruppen können Lehrkräfte deren Gruppen in Teams konvertieren, indem Sie das Symbol **Vorgeschlagene Kurse** verwenden.

:::image type="content" source="media/class-teams-edu-suggested-classes.png" alt-text="Screenshot mit dem Symbol Vorgeschlagene Kurse":::

### <a name="benefits"></a>Vorteile

- [Früher Lehrer-Zugang](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): Pädagogen haben Zeit, um ihr Team vorzubereiten, bevor sie Studenten aufnehmen.  
- Reduziert die Anzahl der nicht genutzten und nicht mehr benötigten Teams. Die Kurse werden vorbereitet und vorgeschlagen, aber nicht erstellt, es sei denn, der Lehrer beabsichtigt, sie zu verwenden. Diese Option wird für große Institute, die über mehr als 500.000 Teams verfügen, zur Wahrung der Übersichtlichkeit empfohlen.
- SDS
    - Mitgliedschaftssynchronisierung mit SIS/LMS zum Verwalten von Änderungen der Kursteilnehmer-Mitgliedschaft.
    - EDU Customer Success-Team steht zur kostenlosen Bereitstellungsunterstützung zur Verfügung.
    - Erstellt optional Benutzer und wendet Office 365-Lizenzen an.
    - Erstellt Sicherheitsgruppen für die Verwendung in Office 365, einschließlich der Team Richtlinie.
    - Erstellt administrative Einheiten für umfangreich administrative Delegierung und [Lehrer Passwort zurücksetzen](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset).
    - Integrierte Fehler- und Wiederholungsbehandlung, Drosselung des Backoffs und Session-Stabilität für die Verarbeitung in großem Maßstab, um die Arbeit der Administratoren zu reduzieren. 
    - Integrierte Bereinigungsfunktionen zum Umbenennen und Archivieren von Gruppen und Teams, sobald diese veraltet sind. 
    - [Noten-Synchronisierung](https://docs.microsoft.com/schooldatasync/grade-sync): Kursleiter können alle ihre Benotungen in Teams durchführen und die Noten automatisch von Teams zurück in das SIS-Notenbuch übertragen. 
    - [Datenschutz für Schüler/Studenten](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): Verhindern Sie, dass Kursteilnehmer nicht-Microsoft-Apps verwenden, und verfolgen und verwalten Sie die Zustimmung der Eltern. 
    - Importierte Daten werden verwendet, um Bildungseinblicke mit Benutzerrollen, Organisationen (Schulen) und anderen wichtigen Daten anzureichern.
- Graph-API
    - Zusätzliche Flexibilität und Kontrolle.
    - Erfordert keine Integration in SDS.

### <a name="considerations"></a>Erwägungen

- Nicht vollständig automatisiert und erfordert die Handlung eines Lehrers.
- Lehrer, die nicht zum Erstellen von Teams berechtigt sind, können weiterhin Teams aus bestehenden Gruppen erstellen, wie [hier](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)gezeigt wird.
- Die Graph-API erfordert ein hohes Maß an technischem Know-how und Zeit zum Erstellen und Ausführen des Skripts sowie zum Beheben von Problemen beim Erstellen von Kursgruppen.

### <a name="get-started"></a>Erste Schritte

Wenn Sie mit der SDS-Methode beginnen möchten, wechseln Sie zu [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) und kontaktieren Sie die [https://aka.ms/sdssupport](https://aka.ms/sdssupport) Bereitstellungshilfe. 

Wenn Sie die Graph-API-Methode verwenden möchten, lesen Sie [Graph-API](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-1.0&tabs=http) und [Erstellen eines Klassenteams](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http).  

> [!NOTE]
> Um diese Methode mit SDS verwenden zu können, müssen Sie die Option zur automatischen Teamerstellung in Ihrem SDS-Profil deaktivieren. Sie können auch eine Kombination aus automatischer und von Dozenten geleiteter Teamerstellung für erforderliche und optionale Kursteams verwenden, mithilfe von zwei SDS-Profilen.

## <a name="powershell-script-using-graph-apis"></a>PowerShell-Skript mit Graph-APIs

Mit PowerShell können Sie ein Skript schreiben, um Teams zu erstellen und Einstellungen automatisch zu konfigurieren. Es ist erforderlich, dass der Administrator zuerst die Gruppe erstellt, Lehrer und Schüler hinzufügt und dann das Team wie [hier](https://docs.microsoft.com/graph/teams-create-group-and-team)beschrieben erstellt. Sie können auch die Microsoft Graph-API zum Erstellen, Konfigurieren, Duplizieren und Archivieren von Teams verwenden. Weitere Informationen hierzu finden Sie unter [Microsoft Graph-API verwenden, um mit Microsoft Teams zu arbeiten](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview), [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams) und [Erstellen eines Kursteams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-6-create-a-team-with-a-non-standard-base-template-type). Die Verwendung von Graph-APIs bietet eine hervorragende Möglichkeit, um mehr Kontrolle und Flexibilität zu haben, doch erfordert es ein hohes Maß an technischem Wissen und braucht anfänglichen mehr Zeit zum Einrichten.  

### <a name="benefits"></a>Vorteile

- Zusätzliche Flexibilität und Kontrolle.
- Option zum Erstellen von Lehrer-Frühzugang-Teams oder sofortiger Schüler-Zugang zu Teams.  
- Wenn Sie [Teams aus Gruppen](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-4-create-a-team-from-group)erstellen, haben Lehrkräfte frühzeitigen Zugriff und Änderungen an der Kursteilnehmer-Mitgliedschaft in der Azure AD-Gruppe werden synchronisiert.

### <a name="considerations"></a>Erwägungen

- Erfordert ein hohes Maß an technischem Know-how und Zeit zum Erstellen und Ausführen des Skripts, sowie zum Beheben von Problemen beim Erstellen von Kursgruppen.
- Keine integrierte Fehlerbehandlung oder Wiederholungsversuche.
- Änderungen an der Mitgliedschaft werden nicht mit SIS synchronisiert. 

> [!NOTE]
> Kursteams benötigen eine versteckte Gruppenmitgliedschaft, sodass nur Lehrer und Schüler innerhalb des Kurses die Mitglieder dieses Kurses sehen können. Informationen zum Erstellen einer Office 365-Kursgruppe finden Sie unter [Erstellen eines Kursteams](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http), um die gleichen Datenschutzanforderungen zu erfüllen.

## <a name="manual-team-creation"></a>Manuelle Teamerstellung

Schüler/Studenten und Lehrkräfte können Teams optimal nutzen, wenn Hindernisse minimiert werden und die Flexibilität bereitgestellt wird, es auf ihre Bedürfnisse zuzuschneiden. Eine Möglichkeit, wie Benutzer ihre Teams-Erfahrung maßschneidern können, ist das Erstellen von Teams. Lehrkräfte erstellen ein eigenes Kursteam und laden Schüler wie [hier](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch) gezeigt wird ein. Lehrkräfte können Schüler einladen, indem sie [Schüler dem Team](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954)hinzufügen, [einen Teilnahmecode](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)teilen, oder [einen Link zum Team freigeben](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Wenn möglich, ist es am besten, wenn Lehrkräfte ihre Schüler/Studenten in das Team aufnehmen, um sicherzustellen, dass diese Zugriff erhalten und darüber informiert werden, dass sie zu einem Team hinzugefügt wurden.

### <a name="benefits"></a>Vorteile

- Zusätzliche Flexibilität für Lehrkräfte.
- Sofortige Teamerstellung und Zugriff.  

### <a name="considerations"></a>Erwägungen

- Erfordert Handlung eines Lehrer und Zeit.
- Die Schüler-Mitgliedschaft wird nicht mit SIS synchronisiert und erfordert eine manuelle Verwaltung.
- Bietet Lehrern keinen frühen Zugriff auf ihre Teams. Schüler und Studenten erhalten sofortigen Zugriff.

## <a name="recommended-best-practices"></a>Empfohlene bewährte Methoden

- Frühzeitiges bereitstellen! Stellen Sie frühzeitig bereit, um sicherzustellen, dass alles zuverlässig funktioniert und für den ersten Schultag bereit ist. Wenn Sie SDS verwenden, benötigen Sie keine volle Studenten-Mitgliedschaft, um die SDS-Bereitstellung starten zu können. Die Kursteilnehmer werden synchronisiert, wenn diese Informationen in Ihrem SIS verfügbar sind.
- Wenn Sie über mehr als 500.000 Teams verfügen, empfehlen wir die [von Dozenten geleitete Teamerstellungsmethode](#educator-led-team-creation-from-office-365-class-groups). Es reduziert nicht verwendete Teams und Unübersichtlichkeit, da nur Kursteams erstellt werden, die relevant und erforderlich sind.  
- Wenn bei der automatischen SDS-Teamerstellung Probleme auftreten (z. B. fehlende Klassen) und die Lehrer diese sofort benötigen, können Sie die [von Dozenten geleitete Teamerstellungsmethode](#educator-led-team-creation-from-office-365-class-groups) verwenden, um den Vorgang wiederholen. Die [Manuelle Teamerstellung](#manual-team-creation) ist eine weitere Lösung, die jedoch Ihre Teammitgliedschaft nicht auf dem neuesten Stand hält.  
- Das Mandanten-Team-Limit ist 500.000 Teams. Daher sollten Administratoren proaktiv versuchen, die Anzahl nicht verwendeter Teams zu reduzieren, um zu vermeiden, dass diese Grenzwerte überschritten und die Einrichtungszeit verlängert wird. Weitere Informationen zu den Grenzwerten finden Sie unter [Limits und Spezifikationen für Microsoft Teams](limits-specifications-teams.md).  
