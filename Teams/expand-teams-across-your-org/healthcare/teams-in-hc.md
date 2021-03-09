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
description: Erfahren Sie mehr über Die Gesundheitsfunktionen wie Microsoft Teams Telehealth, EHR-Integration, Integration des Frontline-Workersystems und die Patienten-App.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 1bf890c7ffb6fa13730870cb1f4eabecb5df7c85
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558384"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Erste Schritte mit Teams für Organisationen im Gesundheitswesen

Microsoft Teams bietet eine Reihe von Telemedicine-Features, die für Krankenhäuser und andere Organisationen des Gesundheitswesens nützlich sind. Die Teams-Features werden zur Unterstützung von Krankenhäusern entwickelt:

- Virtuelle Besuche und Integration von Electronic Healthcare Record (EHR)
- Teams-Richtlinienpakete
- Sicheres Messaging
- Teams-Vorlagen
- Pflegekoordinierung und Zusammenarbeit

Diese Funktionalität ist Teil der Microsoft Cloud für Gesundheitswesen. Erfahren Sie mehr über die Verwendung dieser Lösung, die Funktionen aus Azure, Dynamics 365 und Microsoft 365 bei [Microsoft Cloud for Healthcare vereint.](https://docs.microsoft.com/industry/healthcare)

Schauen Sie sich das folgende Video an, um mehr über die Verwendung der Gesundheitssammlung zu erfahren, um die Zusammenarbeit von Gesundheitsteams in Microsoft Teams zu verbessern.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> Der Inhalt in diesem Abschnitt setzt voraus, dass Sie Teams bereits in Ihrer Organisation bereitgestellt haben. Wenn Sie Noch kein Rollout von Teams abgeschlossen haben, lesen Sie zunächst [So wird's gemacht: Rollout von Microsoft Teams.](../../How-to-roll-out-teams.md)

Die folgenden Szenarien stehen für Organisationen des Gesundheitswesens zur Verfügung:

| Szenario | Beschreibung | Anforderungen |
| -------- | -------- | -------- |
| [Virtuelle Besuche mit Integration von Electronic Healthcare Record (EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Planen, Verwalten und Durchführen virtueller Besuche mit Patienten. Dieses Szenario verbindet Microsoft Teams und die Epische Plattform, um virtuelle Besuche zu unterstützen. | Aktives Abonnement für Microsoft Cloud for Healthcare oder eigenständiges Microsoft Teams EHR Connector-Angebot. <br> Benutzer müssen über eine geeignete Microsoft 365- oder Office 365-Lizenz verfügen, die Microsoft Teams-Besprechungen* enthält. <br> Organisationen müssen mit der Epischen Version November 2018 oder höher verfügen. <br>[Details zu den EHR-Anforderungen](ehr-admin.md#before-you-begin) |
| [Virtuelle Besuche mit Microsoft Bookings und der Bookings-App](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Planen, Verwalten und Durchführen virtueller Besuche mit Patienten. Dieses Szenario basiert auf Microsoft Bookings, um virtuelle Besuche zu unterstützen. | Microsoft Bookings muss für die Organisation aktiviert sein. <br> Alle Benutzer der Bookings-App und alle an Besprechungen teilnehmenden Mitarbeiter müssen über eine Lizenz verfügen, die die Planung von Teams-Besprechungen* unterstützt. <br>[Details zu den Bookings-Anforderungen](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Teams-Richtlinienpakete](#teams-policy-packages)| Stellen Sie sicher, dass Klinische Mitarbeiter, Informationsmitarbeiter und Patientenraumgeräte über den geeigneten Zugriff auf die Funktionen von Teams verfügen.| Benutzer müssen über eine entsprechende Lizenz* verfügen. |
| [Sicheres Messaging](#secure-messaging) | Machen Sie sich schneller auf dringende Nachrichten aufmerksam, und vertrauen Sie darauf, dass die Nachricht empfangen und gelesen wurde. | Benutzer müssen über eine entsprechende Lizenz* verfügen.  |
| [Teams-Vorlagen](#teams-templates-for-healthcare-organizations) | Erstellen Sie Teams, die eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten Apps für kommunikation und Zusammenarbeit innerhalb einer Station, eines Pods oder einer Abteilung oder zwischen mehreren Abteilungen, Pods und Abteilungen in einem Krankenhaus enthalten. | Benutzer müssen über eine entsprechende Lizenz* verfügen.  |
| [Pflegekoordinierung und Zusammenarbeit](#care-coordination-and-collaboration) | Ärzte und Mitarbeiter können intern an Terminplänen, Dokumenten, Aufgaben und so weiter zusammenarbeiten.| Benutzer müssen über eine entsprechende Lizenz* verfügen. |

*Office 365 A3, A5, E3 und E5 sowie Microsoft 365 Business Standard, A3, A5, E3 und E5 werden unterstützt. Weitere Informationen zur allgemeinen Teams-Lizenzierung finden Sie unter [Verwalten des Benutzerzugriffs auf Teams](../../user-access.md).

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Virtuelle Besuche und Integration von Electronic Healthcare Record (EHR)

Verwenden Sie die vollständige Besprechungsplattform in Microsoft Teams, um virtuelle Besuche mit Patienten zu planen, zu verwalten und zu führen.

- Wenn Ihre Organisation bereits elektronische Krankenakten oder EHR verwendet, können Sie Microsoft Teams integrieren, um eine nahtlose Benutzererfahrung zu ermöglichen. Microsoft Teams Electronic Health Record (EHR) Connector erleichtert Es Ärzten, einen virtuellen Patientenbesuch oder eine Beratung mit einem anderen Anbieter in Teams direkt über das EHR-System zu starten. Weitere Informationen finden Sie unter [Virtuelle Besuche mit Teams – Integration in EHR](ehr-admin.md).
- Wenn Sie keine unterstützte EHR verwenden, können Sie Microsoft Bookings und die Bookings-App in Teams verwenden. Weitere Informationen finden Sie unter [Bookings-App und virtuelle Besuche in Microsoft Teams.](../../bookings-app-admin.md)

![Virtuelle Besuche mit Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Teams-Richtlinienpakete

Wenden Sie Teams-Richtlinienpakete an, um zu definieren, welche verschiedenen Rollen in Teams zu tun sind. Geben Sie beispielsweise Richtlinien für:

- Klinische Mitarbeiter, z. B. registrierte Krankenschwestern, Krankenschwestern, Ärzte und Sozialarbeiter, damit sie voll auf Chats, Anrufe, Schichtverwaltung und Besprechungen zugreifen können.
- Informationsmitarbeiter in Ihrer Gesundheitsorganisation, z. B. IT-Mitarbeiter, Mitarbeiter für Die Datenverarbeitung, Finanzmitarbeiter und Compliance officers, können voll auf Chats, Anrufe und Besprechungen zugreifen.
- Patientenräume, um die Einstellungen für Patientenraumgeräte zu steuern.

Weitere Informationen finden Sie unter [Teams-Richtlinienpakete für das Gesundheitswesen.](../../policy-packages-healthcare.md)

## <a name="secure-messaging"></a>Sicheres Messaging

Secure Messaging unterstützt die Zusammenarbeit innerhalb von Integritätsteams, einschließlich mehrerer neuer Features:

- Ein Nachrichtensender kann eine besondere Priorität für seine Nachricht festlegen, sodass der Empfänger wiederholt benachrichtigt wird, bis er die Nachricht gelesen hat.
- Ein Nachrichtensender kann eine Lesebestätigung anfordern, sodass er benachrichtigt wird, wenn eine gesendete Nachricht vom Nachrichtenempfänger gelesen wurde.

Zusammen ermöglichen diese Features eine schnellere Aufmerksamkeit auf dringende Nachrichten und vertrauen darauf, dass die Nachricht empfangen und gelesen wurde. Neue Gesundheitsteams, die diese Features verwenden, können pro Patient erstellt werden. Diese Features sind richtlinienbasierter Und können Einzelnen oder ganzen Teams zugewiesen werden.

Weitere Informationen finden Sie unter [Erste Schritte mit Secure Messaging-Richtlinien für Organisationen im Gesundheitswesen.](messaging-policies-hc.md)

Im Zusammenhang mit secure messaging steht auch die Möglichkeit, andere Mandanten von Organisationen des Gesundheitswesens zu unterstützen, wodurch eine reichhaltigere Kommunikation zwischen Mandanten ermöglicht wird. (Siehe [Verwalten des externen Zugriffs (Verbund) in Microsoft Teams](../../manage-external-access.md)).

## <a name="teams-templates-for-healthcare-organizations"></a>Teams-Vorlagen für Organisationen im Gesundheitswesen

Neue Vorlagen zum Erstellen von Teams wurden für eine Krankenhauseinstellung entwickelt, und weitere werden in Kürze erwartet. Dies erleichtert die Erstellung von Teams, die Mitarbeiter des Gesundheitswesens verwenden, um die Behandlung von Patienten in verschiedenen Abteilungen oder Krankenstationen zu koordinieren. Weitere Informationen finden Sie unter [Erste Schritte mit Teams-Vorlagen für Organisationen im Gesundheitswesen.](healthcare-templates.md) Teams können für interne Abteilungen wie Kardiologie oder Pflegeabteilungen gestartet werden, und weitere Vorlagen sind in der Entwicklung.

## <a name="care-coordination-and-collaboration"></a>Pflegekoordinierung und Zusammenarbeit

Bringen Sie Ihr Gesundheitsteam zusammen, um die Pflege zu koordinieren und mit Microsoft Teams zusammenzuarbeiten.

![Gesundheitswesen: Zusammenarbeiten mit Ihrem Gesundheitsteam in Teams](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams ermöglicht Es Ärzten, Ärzten, Krankenpflegern und anderen Mitarbeitern, effizient mit den in Microsoft Teams enthaltenen Features für die Zusammenarbeit zusammenzuarbeiten, z. B.:

- Richten Sie Teams und Kanäle für Ihre Gesundheitsteams und Informationsmitarbeiter ein. Verwenden Sie Kanäle mit Registerkarten als Möglichkeit, ihre Arbeit zu strukturieren, mit zusätzlicher Hilfe von Registerkarten, an die sie Informationsquellen anheften können.
- Chatten, Posten von Nachrichten und Kommunizieren. Ihr Team kann dauerhafte Unterhaltungen über unterschiedliche Patienten führen, die Aufmerksamkeit benötigen.
- Rufen Sie an, und treffen Sie sich mit Mitgliedern des Integritätsteams. Richten Sie einzelne Besprechungen ein, oder verwenden Sie Kanalbesprechungen zum Verwalten täglicher Besprechungen, und nutzen Sie dabei die Leistung von Teams-Audio-, Video-, Bildschirmfreigabe-, Aufzeichnungs- und Transkriptionsfeatures.
- Speichern und teilen Sie Dateien und Dokumente. Ihr Integritätsteam ist Teil eines einzelnen virtualisierten Teams, das an Office-Dokumenten arbeitet und zusammenarbeitet.

Darüber hinaus kann Ihr Team Apps in Teams verwenden, um:

- Freigeben von Listen und Nachverfolgen von Informationen mit der Listen-App
- Nachverfolgen und Überwachen von Aufgaben mit der Aufgaben-App
- Optimieren von Genehmigungen mit der App "Genehmigungen"
- Erstellen, Verwalten und Freigeben von Zeitplänen mit der Schicht-App

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Freigeben von Listen und Nachverfolgen von Informationen mit der Listen-App

> [!NOTE]
> Ab dem 30. Oktober 2020 wurde die Patienten-App eingestellt und durch die App [Listen](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams ersetzt. Mit Listen können Pflegeteams in Ihrer Gesundheitsorganisation Patientenlisten für Szenarien erstellen, die von Runden und inübergreifenden Teambesprechungen bis hin zur allgemeinen Patientenüberwachung reichen.

Die App Listen in Teams hilft Teams dabei, Informationen nachverfolgt und Ihre Arbeit zu organisieren. Die App ist für alle Teams-Benutzer vorinstalliert und steht als Registerkarte in jedem Team und Kanal zur Verfügung. Listen können von Grund auf neu erstellt werden, aus vordefinierten Vorlagen oder durch Importieren von Daten nach Excel.

Gesundheitsteams können die Vorlage Patienten verwenden, um zu beginnen. Sie können Listen erstellen, um die Bedürfnisse und den Status von Patienten nachverfolgt zu haben. Vorhandene Patientendaten in Excel-Tabellen können zum Erstellen einer Liste in Teams hinzugefügt werden. Diese Listen können für Szenarien wie Runden und Patientenüberwachung verwendet werden, um die Pflege zu koordinieren.

Beispielsweise erstellt eine Krankenschwester eine Patientenliste in einem Team, die alle Mitglieder des Gesundheitsteams umfasst. Während der Runden zugrifft das Integritätsteam auf seinen mobilen Geräten auf Teams und aktualisiert Patienteninformationen in der Liste, die jeder im Team anzeigen kann, um synchron zu bleiben. Bei Rundensitzungen, in denen das Gesundheitsteam zusammentrat, um wichtige Metriken zur Integritätsleistung zu diskutieren und auszuwerten, um sicherzustellen, dass sich ein Patient auf dem richtigen Weg zur Entladung befindet, kann er diese Informationen mithilfe von Teams auf einem großen Bildschirm teilen. Mitglieder des Integritätsteams, die nicht auf der Website sind, können remote beitreten.

Hier ist eine Beispielliste, die für das Runden von Patienten eingerichtet wurde.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Screenshot der Beispielliste zum Runden von Patienten":::

Weitere Informationen finden Sie unter [Verwalten der Listen-App für Ihre Organisation in Teams.](../../manage-lists-app.md)

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Nachverfolgen und Überwachen von Aufgaben mit der Aufgaben-App

Verwenden [Sie Aufgaben](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) in Teams, um Aufgaben für Ihr gesamtes Integritätsteam nachverfolgt zu haben. Ihr Integritätsteam kann Aufgaben jederzeit auf jedem Gerät mit Teams erstellen, zuweisen und planen, Aufgaben kategorisieren und den Status aktualisieren.

Weitere Informationen finden Sie unter [Verwalten der Aufgaben-App für Ihre Organisation in Microsoft Teams.](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Optimieren von Genehmigungen mit der App "Genehmigungen"

Verwenden [Sie Genehmigungen,](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) um alle Ihre Anforderungen und Prozesse mit Ihrem Team zu optimieren. Erstellen, Verwalten und Freigeben von Genehmigungen direkt von Ihrem Hub aus für Teamarbeit. Starten Sie einen Genehmigungsfluss von derselben Stelle aus, an der Sie einen Chat senden, in einer Kanal unterhaltung oder über die Genehmigungs-App selbst. Wählen Sie einfach einen Genehmigungstyp aus, fügen Sie Details hinzu, fügen Sie Dateien an, und wählen Sie genehmigende Benutzer aus. Nach der Einsenden werden genehmigende Benutzer benachrichtigt und können die Anforderung überprüfen und entsprechend handeln.

Sie können die App "Genehmigungen" für Ihre Organisation zulassen und zu Ihren Teams hinzufügen. Weitere Informationen finden Sie unter [Verfügbarkeit von Teams-Genehmigungen.](../../approval-admin.md)

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Erstellen, Verwalten und Freigeben von Zeitplänen mit der Schicht-App und der Integration von Frontline Workern

Microsoft Teams ist in die App Schichten und Frontline Worker integriert, die zum Koordinieren von Schichtpersonalfunktionen und mehr verwendet werden können. In Schichten können Krankenschwesternmanager beispielsweise Zeitpläne für ihre Mitarbeiter einrichten und koordinieren, und Krankenschwestern können Zeitpläne überprüfen und Schichten austauschen. Teams enthält eine integrierte Einrichtungsrichtlinie für die Frontline Worker-App, die Sie Den Frontline-Mitarbeitern in Ihrer Organisation zuweisen können. Standardmäßig beinhaltet diese Richtlinie die Apps für Aktivität, Schichten, Chat und Anrufe. Diese Richtlinie steuert das Verhalten für diese Apps, z. B. das Anheften der Schicht-App an die App-Leiste, damit das Team schnell darauf zugreifen kann.

Weitere Informationen finden Sie unter [Verwalten der Schicht-App für Ihre Organisation in Microsoft Teams.](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Helfen Sie Ihren Mitarbeitern in Klinischen Und Informationen, mit Teams zu arbeiten

Es stehen viele Ressourcen zur Verfügung, die allen Benutzern in Ihrer Organisation helfen, sich mit der Verwendung von Teams zu bequemen:

- Besuchen Sie [das Einführungscenter](https://adoption.microsoft.com/microsoft-teams/) für Teams, um Tipps zum Roll-out von Teams zu erhalten, wenn Sie einfach die Reise Ihrer Organisation mit Teams beginnen oder Teams in weitere Bereiche Ihrer Organisation erweitern möchten.
- Erwägen Sie, benutzerdefinierte [Lernpfade](https://adoption.microsoft.com/microsoft-365-learning-pathways/) für Ihre Benutzer so einrichten, dass sie nur die Aufgaben abdecken können, die sie ausführen müssen.
- Erhalten Sie Hilfe und Schulungen für Ihre Benutzer zum Ausführen grundlegender Aufgaben in Microsoft Teams auf der Microsoft Teams-Supportwebsite, einschließlich [kurzer Schulungsvideos.](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) [](https://support.microsoft.com/teams) Diese Website bietet auch Hilfe und Schulungen für die Teams-Apps, einschließlich [Listen,](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) [Aufgaben,](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) [Genehmigungen,](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) [Bookings](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)und [Schichten.](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
