---
title: Erste Schritte mit Teams für Organisationen im Gesundheitswesen
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-overview
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Erfahren Sie mehr über Gesundheitsfunktionen wie Microsoft Teams Telehealth, EHR-Integration, Integration von Frontline-Worker-System und die Patienten-App.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: a5b8ea7cddba8def74a1f5b839710cf73bafc67e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125768"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Erste Schritte mit Teams für Organisationen im Gesundheitswesen

Microsoft Teams bietet eine Reihe von Telemedicinefunktionen, die für Krankenhaus und andere Organisationen im Gesundheitswesen nützlich sind. Teams-Features werden zur Unterstützung von Senkhilfen in der Entwicklung mit:

- Virtuelle Besuche und Integration des elektronischen Gesundheitswesens (Electronic Healthcare Record, EHR)
- Richtlinienpakete für Teams
- Sicheres Messaging
- Vorlagen für Teams
- Pflegekoordinierung und Zusammenarbeit

Diese Funktionalität ist Teil der Microsoft Cloud für Gesundheitswesen. Erfahren Sie mehr über die Verwendung dieser Lösung, die Funktionen aus Azure, Dynamics 365 und Microsoft 365 bei [Microsoft Cloud for Healthcare vereint.](https://docs.microsoft.com/industry/healthcare)

Schauen Sie sich das folgende Video an, um mehr über die Verwendung der Sammlung im Gesundheitswesen zur Verbesserung der Zusammenarbeit im Gesundheitsteam in Microsoft Teams zu erfahren.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> Im Inhalt dieses Abschnitts wird davon ausgegangen, dass Sie Teams bereits in Ihrer Organisation bereitgestellt haben. Wenn Sie noch kein Rollout von Microsoft Teams durchgeführt haben, lesen Sie zunächst ["Rollout von Microsoft Teams".](../../How-to-roll-out-teams.md)

Die folgenden Szenarien sind für Organisationen im Gesundheitswesen verfügbar:

| Szenario | Beschreibung | Anforderungen |
| -------- | -------- | -------- |
| [Virtuelle Besuche mit Integration des elektronischen Gesundheitswesens (Electronic Healthcare Record, EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Planen, verwalten und durchführen Sie virtuelle Visiten mit Patienten. Dieses Szenario verbindet Microsoft Teams mit der Epischen Plattform, um virtuelle Besuche zu unterstützen. | Aktives Abonnement für Microsoft Cloud im Gesundheitswesen oder Abonnement des eigenständigen Microsoft Teams EHR Connector-Angebots. <br> Benutzer müssen über eine geeignete Microsoft 365- oder Office 365-Lizenz verfügen, die Microsoft #A0 umfasst*. <br> Organisationen müssen über eine epische Version (November 2018 oder höher) verfügen. <br>[Details zu den Anforderungen der EHR](ehr-admin.md#before-you-begin) |
| [Virtuelle Besuche mit Microsoft Bookings und der App Bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Planen, verwalten und durchführen Sie virtuelle Visiten mit Patienten. Dieses Szenario basiert auf Microsoft Bookings zur Unterstützung virtueller Besuche. | Microsoft Bookings muss für die Organisation aktiviert sein. <br> Alle Benutzer der #A0 und alle an Besprechungen teilnehmenden Mitarbeiter müssen über eine Lizenz verfügen, die die Planung von #A1 unterstützt*. <br>[Details zu den Anforderungen für Bookings](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Richtlinienpakete für Teams](#teams-policy-packages)| Stellen Sie sicher, dass klinische Mitarbeiter, Informationsarbeiter und Geräte im Patientenzimmer über den geeigneten Zugriff auf die Funktionen von Teams verfügen.| Benutzer müssen über eine geeignete Lizenz* verfügen. |
| [Sicheres Messaging](#secure-messaging) | Machen Sie sich schneller auf dringende Nachrichten aufmerksam, und vertrauen Sie darauf, dass die Nachricht empfangen und gelesen wurde. | Benutzer müssen über eine geeignete Lizenz* verfügen.  |
| [Vorlagen für Teams](#teams-templates-for-healthcare-organizations) | Erstellen Sie Teams, die eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten Apps für Kommunikation und Zusammenarbeit innerhalb eines Krankenhauses, eines Pods oder einer Abteilung oder zwischen mehreren Sprechstationen, Pods und Abteilungen in einem Krankenhaus enthalten. | Benutzer müssen über eine geeignete Lizenz* verfügen.  |
| [Pflegekoordinierung und Zusammenarbeit](#care-coordination-and-collaboration) | Klinikangestellte und Mitarbeiter können intern an Zeitplänen, Dokumenten, Aufgaben und so weiter zusammenarbeiten.| Benutzer müssen über eine geeignete Lizenz* verfügen. |

*Office 365 A3, A5, E3 und E5 sowie Microsoft 365 Business Standard, A3, A5, E3 und E5 werden unterstützt. Weitere Informationen zur allgemeinen Lizenzierung von Teams finden Sie unter ["Verwalten des Benutzerzugriffs auf Teams".](../../user-access.md)

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Virtuelle Besuche und Integration des elektronischen Gesundheitswesens (Electronic Healthcare Record, EHR)

Verwenden Sie die vollständige Besprechungsplattform in Microsoft Teams, um virtuelle Visiten mit Patienten zu planen, zu verwalten und zu durchführen.

- Wenn Ihre Organisation bereits elektronische Krankenakten oder EHR verwendet, können Sie Microsoft Teams für eine nahtlose Erfahrung integrieren. Microsoft Teams Electronic Health Record (EHR) Connector erleichtert Den Kliniken die Einführung eines virtuellen Patientenbesuchs oder einer Beratung mit einem anderen Anbieter in Teams direkt über das EHR-System. Weitere Informationen finden Sie unter ["Virtuelle Besuche mit Teams – Integration in EHR".](ehr-admin.md)
- Wenn Sie keine unterstützte EHR verwenden, können Sie Microsoft Bookings und die App Bookings in Teams verwenden. Weitere Informationen finden Sie unter ["Bookings-App" und virtuelle Besuche in Microsoft Teams.](../../bookings-app-admin.md)

![Virtuelle Besuche mit Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Richtlinienpakete für Teams

Wenden Sie Richtlinienpakete für Teams an, um zu definieren, welche unterschiedlichen Rollen in Teams zugewiesen werden können. Geben Sie z. B. Richtlinien für:

- Klinische Mitarbeiter, z. B. eingetragene Krankenschwestern, Krankenschwestern, Ärzte und Sozialarbeiter, damit sie vollständigen Zugriff auf Chats, Anrufe, Schichtverwaltung und Besprechungen haben.
- Die Information Workers in Ihrem Gesundheitswesen, z. B. IT-Mitarbeiter, Mitarbeiter, Mitarbeiter der Finanzabteilung und Compliance Officers, können vollständigen Zugriff auf Chats, Anrufe und Besprechungen haben.
- Patientenräume zum Steuern der Einstellungen für Die Geräte des Patientenzimmers.

Weitere Informationen finden Sie in [den Richtlinienpaketen für Teams für das Gesundheitswesen.](../../policy-packages-healthcare.md)

## <a name="secure-messaging"></a>Sicheres Messaging

Secure Messaging unterstützt die Zusammenarbeit innerhalb von Integritätsteams, einschließlich mehrerer neuer Features:

- Ein Absender einer Nachricht kann eine besondere Priorität für seine Nachricht festlegen, sodass der Empfänger so lange benachrichtigt wird, bis er die Nachricht gelesen hat.
- Ein Absender einer Nachricht kann eine Lesebestätigung anfordern, sodass er benachrichtigt wird, wenn eine gesendete Nachricht vom Nachrichtenempfänger gelesen wurde.

Zusammen ermöglichen diese Features eine schnellere Aufmerksamkeit auf dringende Nachrichten und vertrauen darauf, dass die Nachricht empfangen und gelesen wurde. Neue Gesundheitsteams, die diese Features verwenden, können pro Patient erstellt werden. Diese Features sind richtlinienbasierte und können einzelnen Personen oder ganzen Teams zugewiesen werden.

Weitere Informationen finden Sie unter ["Erste Schritte mit Secure Messaging-Richtlinien für Organisationen im Gesundheitswesen".](messaging-policies-hc.md)

Im Zusammenhang mit secure Messaging steht auch die Möglichkeit zur Verfügung, andere Mandanten von Organisationen im Gesundheitswesen zu unterstützen, die eine reichhaltigere Kommunikation zwischen Mandanten ermöglichen. (Siehe [Verwalten des externen Zugriffs (Verbund) in Microsoft Teams).](../../manage-external-access.md)

## <a name="teams-templates-for-healthcare-organizations"></a>Vorlagen für Teams für Organisationen im Gesundheitswesen

Neue Vorlagen für die Erstellung von Teams wurden entwickelt, um die Einstellung "Hospital" zu übernehmen, und weitere werden in Kürze erwartet. Dies erleichtert die Erstellung von Teams, die von Mitarbeitern im Gesundheitswesen verwendet werden, um die Pflege von Patienten in verschiedenen Abteilungen oder Innungen zu koordinieren. Weitere Informationen finden Sie unter ["Erste Schritte mit Teams-Vorlagen für Organisationen im Gesundheitswesen".](healthcare-templates.md) Teams können für interne Abteilungen wie die Ologie oder für Pflegekräfte gestartet werden, und weitere Vorlagen befinden sich in der Entwicklung.

## <a name="care-coordination-and-collaboration"></a>Pflegekoordinierung und Zusammenarbeit

Bringen Sie Ihr Gesundheitsteam zusammen, um die Pflege zu koordinieren und mit Microsoft Teams zusammenzuarbeiten.

![Gesundheitswesen: Zusammenarbeiten mit Ihrem Gesundheitsteam in Teams](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams ermöglicht Ärzten, Klinikikern, Krankenschwesteren und anderen Mitarbeitern die effiziente Zusammenarbeit mit den in Microsoft Teams enthaltenen Funktionen für die Zusammenarbeit, z. B.:

- Richten Sie Teams und Kanäle für Ihre Gesundheitsteams und Information Workers ein. Verwenden Sie Kanäle mit Registerkarten als Möglichkeit, ihre Arbeit zu strukturieren, mit zusätzlicher Hilfe von Registerkarten, an die Sie Informationsquellen anheften können.
- Chatten, Posten von Nachrichten und Kommunizieren. Ihr Team kann beständige Unterhaltungen über verschiedene Patienten führen, die Aufmerksamkeit benötigen.
- Rufen Sie Mitglieder des Gesundheitsteams an, und treffen Sie sie. Richten Sie einzelne Besprechungen ein, oder verwenden Sie Kanalbesprechungen, um tägliche Besprechungen zu verwalten, und das sowohl mit der Leistung von Teams-Audio-, Video-, Bildschirmfreigabe-, Aufzeichnungs- und Transkriptionsfeatures.
- Speichern und teilen Sie Dateien und Dokumente. Ihr Gesundheitsteam ist Teil eines einzelnen virtualisierten Teams, das an den Dokumenten von Office arbeitet und daran zusammenarbeitet.

Darüber hinaus kann Ihr Team Apps in Teams für:

- Freigeben von Listen und Nachverfolgen von Informationen mit der App "Listen"
- Nachverfolgen und Überwachen von Aufgaben mit der App "Aufgaben"
- Optimieren von Genehmigungen mit der App "Genehmigungen"
- Erstellen, Verwalten und Teilen von Zeitplänen mit der App "Schichten"

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Freigeben von Listen und Nachverfolgen von Informationen mit der App "Listen"

> [!NOTE]
> Ab dem 30. Oktober 2020 wurde die App "Patienten" eingestellt und durch die App ["Listen"](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams ersetzt. Mit Listen können Die Pflegeteams in Ihrem Gesundheitswesen Patientenlisten für Szenarien erstellen, von Runden über interkonsistente Teambesprechungen bis hin zur allgemeinen Patientenüberwachung.

Mit der App "Listen" in Teams können Teams Informationen nachverfolgen und Arbeit organisieren. Die App ist für alle Benutzer von Teams vorinstalliert und steht als Registerkarte in jedem Team und Kanal zur Verfügung. Listen können von Grund auf neu, aus vordefinierten Vorlagen oder durch Importieren von Daten in Excel erstellt werden.

Gesundheitsteams können die Vorlage "Patienten" verwenden, um zu beginnen. Sie können Listen erstellen, um die Bedürfnisse und den Status von Patienten nachverfolgt zu können. Vorhandene Patientendaten in Excel-Tabellen können zum Erstellen einer Liste in Teams hinzugefügt werden. Diese Listen können für Szenarien wie Runden und Patientenüberwachung verwendet werden, um die Pflege zu koordinieren.

Beispielsweise erstellt eine Krankenschwester eine Patientenliste in einem Team, die alle Mitglieder des Gesundheitsteams umfasst. Während der Runden greifen die Gesundheitsteams auf ihren mobilen Geräten auf Teams zu und aktualisieren Patienteninformationen in der Liste, die jeder im Team anzeigen kann, um synchron zu bleiben. Bei Rundungssitzungen, in denen das Gesundheitsteam zusammentrat, um wichtige Metriken für die Gesundheitsleistung zu diskutieren und auszuwerten, um sicherzustellen, dass ein Patient auf dem richtigen Weg zum Entladen ist, kann es diese Informationen mithilfe von Teams auf einem großen Bildschirm teilen. health team members who aren't on site can join remotely.

Hier ist eine Beispielliste, die für die Patientenrundeung eingerichtet wurde.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Screenshot der Beispielliste zum Runden von Patienten":::

Weitere Informationen finden Sie unter "Verwalten der [App "Listen" für Ihre Organisation in Teams.](../../manage-lists-app.md)

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Nachverfolgen und Überwachen von Aufgaben mit der App "Aufgaben"

Mithilfe [von "Aufgaben"](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) in Teams können Sie Aufgaben für Ihr gesamtes Gesundheitsteam nachverfolgen. Ihr Gesundheitsteam kann Aufgaben auf jedem Gerät, auf dem Teams ausgeführt wird, jederzeit erstellen, zuweisen und planen, Aufgaben kategorisieren und den Status aktualisieren.

Weitere Informationen finden Sie unter "Verwalten der [App "Aufgaben" für Ihre Organisation in Microsoft Teams.](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Optimieren von Genehmigungen mit der App "Genehmigungen"

Verwenden [Sie Genehmigungen,](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) um alle Ihre Anforderungen und Prozesse mit Ihrem Team zu optimieren. Erstellen, verwalten und teilen Sie Genehmigungen direkt von Ihrem Hub aus für die Teamarbeit. Starten Sie einen Genehmigungsablauf von demselben Ort aus, an dem Sie einen Chat, in einer Kanal-Unterhaltung oder über die Genehmigungs-App selbst senden. Wählen Sie einfach einen Genehmigungstyp aus, fügen Sie Details hinzu, fügen Sie Dateien an, und wählen Sie genehmigende Benutzer aus. Nach der Einsenden werden genehmigende Benutzer benachrichtigt, können die Anfrage überprüfen und entsprechend handeln.

Sie können die Genehmigungs-App für Ihre Organisation zulassen und zu Ihren Teams hinzufügen. Weitere Informationen zum Verwalten von Apps finden Sie unter ["Verwalten Ihrer Apps" im Microsoft Teams Admin Center.](../../manage-apps.md)

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Erstellen, Verwalten und Teilen von Zeitplänen mit der App "Schichten" und der Integration von Frontline workern

Microsoft Teams lässt sich in die App "Schichten" und "Frontline Worker" integrieren, die zum Koordinieren von Funktionen für die Schichtmitarbeiter und vielem mehr verwendet werden können. Beispielsweise können Krankenschwesternmanager in Schichten Zeitpläne für ihre Mitarbeiter einrichten und koordinieren, und Krankenschwestern können Zeitpläne überprüfen und Schichten tauschen. Teams enthält eine integrierte Setuprichtlinie für die Frontline-Worker-App, die Sie Den Frontline Workern in Ihrer Organisation zuweisen können. Standardmäßig beinhaltet diese Richtlinie die Apps für Aktivität, Schichten, Chat und Anrufe. Diese Richtlinie steuert das Verhalten für diese Apps, z. B. das Anheften der App "Schichten" an die App-Leiste, damit das Team schnell darauf zugreifen kann.

Weitere Informationen finden Sie unter "Verwalten der App Schichten" für [Ihre Organisation in Microsoft Teams.](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Helfen Sie Ihren Klinischen und Informationsarbeitern, mit Teams los zu werden

Es stehen viele Ressourcen zur Verfügung, die allen Benutzern in Ihrer Organisation helfen sollen, sich mit der Verwendung von Teams zu arbeiten:

- Besuchen Sie [das Einführungscenter](https://adoption.microsoft.com/microsoft-teams/) für Teams für Ratschläge zum Einführungs von Teams, wenn Sie gerade erst den Weg Ihrer Organisation mit Teams unternehmen oder Teams in weitere Bereiche Ihrer Organisation erweitern.
- Erwägen Sie das Einrichten von [benutzerdefinierten Lernpfaden](https://adoption.microsoft.com/microsoft-365-learning-pathways/) für Ihre Benutzer, um nur die Aufgaben zu erledigen, die sie erledigen müssen.
- Erhalten Sie Hilfe und Schulungen für Ihre Benutzer zum Ausführen grundlegender Aufgaben in Microsoft Teams auf der [Teams-Supportwebsite,](https://support.microsoft.com/teams)einschließlich [kurzer Schulungsvideos.](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) Diese Website bietet auch Hilfe und Schulungen für die Teams-Apps, einschließlich [Listen,](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) [Aufgaben,](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) [Genehmigungen,](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) [Bookings](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b) [und Schichten.](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
