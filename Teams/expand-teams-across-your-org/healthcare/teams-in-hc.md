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
description: Informieren Sie sich zu den Gesundheitsfunktionen wie Microsoft Teams Telemedizin, EKA-Integration, Systemintegration von Mitarbeiter in Service und Produktion und der Patienten-App.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: f6048d2413ea92e377358af43c7348abbbe00be1
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760598"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Erste Schritte mit Teams für Organisationen im Gesundheitswesen

Microsoft Teams bietet eine Reihe von Telemedizin-Funktionen, die für Krankenhäuser und andere Organisationen im Gesundheitswesen nützlich sind. Teams-Funktionen werden derzeit entwickelt, um Krankenhäuser mit Folgendem zu unterstützen:

- Virtuelle Besuche und Integration von elektronischen Gesundheitsakten (EGA)
- Teams-Richtlinienpakete
- Sicheres Messaging
- Teams-Vorlagen
- Pflegekoordination und Zusammenarbeit

Diese Funktionalität ist Bestandteil der Microsoft-Cloud für das Gesundheitswesen. Erfahren Sie mehr über die Verwendung dieser Lösung, die Funktionen von Azure, Dynamics 365 und Microsoft 365 bei[Microsoft Cloud für das Gesundheitswesen](/industry/healthcare) zusammenbringt.

Sehen Sie sich das folgende Video an, um mehr über die Verwendung der Sammlung zum Gesundheitswesen zur Verbesserung der Zusammenarbeit im Gesundheitsteam in Microsoft Teams zu erfahren.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> Für den Inhalt in diesem Abschnitt wird davon ausgegangen, dass Sie Teams bereits in Ihrer Organisation bereitgestellt haben. Wenn Sie noch kein Rollout von Teams durchgeführt haben, lesen Sie zunächst den Artikel [Rollout von Microsoft Teams](../../deploy-overview.md).

Die folgenden Szenarien sind für Organisationen im Gesundheitswesen verfügbar:

| Szenario | Beschreibung | Anforderungen |
| -------- | -------- | -------- |
| [Virtuelle Besuche mit Integration von elektronischen Gesundheitsakten (EGA)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Planen, verwalten und führen Sie virtuelle Besuche bei den Patienten durch. Dieses Szenario verbindet Microsoft Teams und die Epic-Plattform zur Unterstützung virtueller Besuche. | Aktives Abonnement von Microsoft Cloud für das Gesundheitswesen oder Abonnement des eigenständigen Microsoft Teams EGA-Verbinder-Angebots. <br> Benutzer müssen über eine entsprechende Microsoft 365- oder Office 365-Lizenz verfügen, die Microsoft Teams-Besprechungen* umfasst. <br> Organisationen müssen über eine Epic-Version von November 2018 oder höher verfügen. <br>[Details zu den EGA-Anforderungen](ehr-admin.md#before-you-begin) |
| [Virtuelle Besuche mit Microsoft Bookings und der Bookings-App](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Planen, verwalten und führen Sie virtuelle Besuche bei den Patienten durch. Dieses Szenario basiert auf Microsoft Bookings, um virtuelle Besuche zu unterstützen. | Microsoft Bookings muss für die Organisation aktiviert sein. <br> Alle Benutzer der Bookings-App und alle an Besprechungen teilnehmenden Mitarbeiter müssen über eine Lizenz verfügen, die die Planung von Teams-Besprechungen unterstützt*. <br>[Details zu den Anforderungen für Bookings](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Microsoft Teams-Richtlinienpakete](#teams-policy-packages)| Stellen Sie sicher, dass Geräte von Klinikmitarbeitern, von Information-Workers und in den Patientenzimmern über den entsprechenden Zugriff auf Teamfunktionen verfügen.| Benutzer müssen über eine entsprechende Lizenz* verfügen. |
| [Sicheres Messaging](#secure-messaging) | Erhalten Sie schnellere Aufmerksamkeit für dringende Nachrichten und haben Sie die Gewissheit, dass die Nachricht empfangen und gelesen wurde. | Benutzer müssen über eine entsprechende Lizenz* verfügen.  |
| [Teams-Vorlagen](#teams-templates-for-healthcare-organizations) | Erstellen Sie Teams, die eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten Apps für die Kommunikation und Zusammenarbeit in einer Station, eines Pods, einer Abteilung oder zwischen mehreren Stationen, Pods oder Abteilungen innerhalb eines Krankenhauses enthalten. | Benutzer müssen über eine entsprechende Lizenz* verfügen.  |
| [Pflegekoordination und Zusammenarbeit](#care-coordination-and-collaboration) | Kliniker und Mitarbeiter können intern an Zeitplänen, Dokumenten, Aufgaben und so weiter zusammenarbeiten.| Benutzer müssen über eine entsprechende Lizenz* verfügen. |

*Office 365 A3, A5, E3 und E5 sowie Microsoft 365 Business Standard, A3, A5, E3 und E5 werden unterstützt. Weitere Informationen zur allgemeinen Teams-Lizenzierung finden Sie unter [Verwalten des Benutzerzugriffs auf Teams](../../user-access.md).

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Virtuelle Besuche und Integration von elektronischen Gesundheitsakten (EGA)

Nutzen Sie die vollständige Besprechungsplattform in Microsoft Teams, um virtuelle Besuche mit den Patienten zu planen, zu verwalten und durchzuführen.

- Wenn In Ihrer Organisation bereits elektronische Gesundheitsakten (EGA) verwendet werden, können Sie Microsoft Teams integrieren, um nahtloser arbeiten zu können. Microsoft Teams EGA-Konnektor (Elektronische Gesundheitsakte) erleichtert den Klinikärzten den Start eines virtuellen Patientenbesuchs oder einer Beratung mit einem anderen Anbieter in Teams direkt aus dem EGA-System. Weitere Informationen finden Sie unter [Virtuelle Besuche mit Teams – Integration in die EGA](ehr-admin.md).
- Wenn Sie keine unterstützte EGA verwenden, können Sie Microsoft Bookings und die Bookings-App in Teams verwenden. Weitere Informationen finden Sie unter [Bookings-App und virtuelle Besuche in Microsoft Teams](../../bookings-app-admin.md).

![Virtuelle Besuche mit Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Teams-Richtlinienpakete

Wenden Sie Teams-Richtlinienpakete an, um zu definieren, was unterschiedlichen Rollen in Teams tun können. Legen Sie beispielsweise Richtlinien fest für:

- Klinikmitarbeiter wie z. B. registrierte Krankenschwestern, Krankenpfleger, Ärzte und Sozialarbeiter, damit sie voll auf Chats, Anrufe, Schichtverwaltung und Besprechungen zugreifen können.
- Information Workers in Ihrer Organisation im Gesundheitswesen, z. B. IT-Personal, Informatiker, Mitarbeiter der Finanzabteilung und Compliance-Beauftragte, können Vollzugriff auf Chats, Anrufe und Besprechungen haben.
- Patientenzimmer, zur Steuerung der Einstellungen für Geräte in Patientenzimmern.

Weitere Informationen finden Sie unter [Teams Policy-Pakete für das Gesundheitswesen](../../policy-packages-healthcare.md).

## <a name="secure-messaging"></a>Sicheres Messaging

Sicheres Messaging unterstützt die Zusammenarbeit innerhalb von Gesundheitsteams, einschließlich mehrerer neuer Features:

- Ein Absender einer Nachricht kann eine besondere Priorität für seine Nachricht festlegen, sodass der Empfänger wiederholt benachrichtigt wird, bis er die Nachricht gelesen hat.
- Ein Absender einer Nachricht kann eine Lesebestätigung anfordern, sodass er benachrichtigt wird, wenn eine von ihm gesendete Nachricht vom Empfänger der Nachricht gelesen wurde.

Zusammen sorgen diese Funktionen für schnellere Aufmerksamkeit für dringende Nachrichten und die Gewissheit, dass die Nachricht empfangen und gelesen wurde. Neue Gesundheitsteams, die diese Features verwenden, können auf Patientenbasis erstellt werden. Diese Features sind richtlinienbasiert und können einzelnen Personen oder ganzen Teams zugewiesen werden.

Weitere Informationen finden Sie unter [Erste Schritte mit Richtlinien für Sicheres Messaging für Organisationen im Gesundheitswesen](messaging-policies-hc.md).

Ebenfalls mit sicherem Messaging verbunden ist die Möglichkeit, andere Mandanten von Organisationen im Gesundheitswesen zu verbinden, was eine umfassendere Kommunikation zwischen den Mandanten ermöglicht. (Siehe [Verwaltung des externen Zugriffs (Verbund) in Microsoft Teams](../../manage-external-access.md)).

## <a name="teams-templates-for-healthcare-organizations"></a>Teams-Vorlagen für Organisationen im Gesundheitswesen

Neue Vorlagen zum Erstellen von Teams wurden entwickelt, um sie auf eine Krankenhaus-Umgebung anzuwenden, und in Kürze werden weitere Vorlagen erwartet. Dies erleichtert die Erstellung von Teams, die von Mitarbeitern des Gesundheitswesens verwendet werden, um die Pflege der Patienten in verschiedenen Abteilungen oder Stationen zu koordinieren. Weitere Informationen finden Sie unter [Erste Schritte mit Teams-Vorlagen für Organisationen im Gesundheitswesen](./healthcare-templates-admin-console.md). Teams kann für interne Abteilungen wie die Kardiologie oder für Pflegeabteilungen gestartet werden. Mehr Vorlagen sind bereits in Entwicklung.

## <a name="care-coordination-and-collaboration"></a>Pflegekoordination und Zusammenarbeit

Bringen Sie Ihr Gesundheitsteam zusammen, um die Pflege zu koordinieren und mit Microsoft Teams zusammenzuarbeiten.

![Gesundheitswesen: Zusammenarbeit mit Ihrem Gesundheitsteam in Teams](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams ermöglicht Ärzten, Klinikern, Krankenschwestern und anderen Mitarbeitern eine effiziente Zusammenarbeit mit den in Microsoft Teams enthaltenen Funktionen für die Zusammenarbeit, wie z. B.:

- Einrichten von Teams und Kanälen für Ihre Gesundheitsteams und Information Worker. Verwenden von Kanälen mit Registerkarten als eine Möglichkeit zur Strukturierung ihrer Arbeit, mit zusätzlicher Hilfe von Registerkarten, an die sie Informationsquellen anheften können.
- Chatten Sie, schreiben Sie Nachrichten und kommunizieren Sie. Ihr Team kann anhaltende Gespräche über verschiedenen Patienten führen, die Aufmerksamkeit benötigen.
- Rufen Sie Mitglieder des Gesundheitsteams an und treffen Sie diese. Richten Sie individuelle Besprechungen ein, oder verwenden Sie Kanalbesprechungen, um tägliche Besprechungen zu verwalten, beides mit den leistungsstarken Audio-, Video-, Bildschirmfreigabe-, Aufzeichnungs- und Transkriptionsfunktionen von Teams.
- Speicher Sie Dateien und Dokumente und geben Sie diese frei. Ihr Gesundheitsteam ist Teil eines einzelnen virtualisierten Teams, das an Office-Dokumenten zusammenarbeitet.

Darüber hinaus kann Ihr Team Apps in Teams verwenden, um Folgendes zu tun:

- Freigeben von Listen und Nachverfolgen von Informationen mit der Listen-App
- Nachverfolgen und Überwachen von Aufgaben mit der Tasks-App
- Optimieren von Genehmigungen mit der App für Genehmigungen.
- Erstellen, Verwalten und Freigeben von Zeitplänen mit der App für Schichten.

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Freigeben von Listen und Nachverfolgen von Informationen mit der Listen-App

> [!NOTE]
> Mit Wirkung vom 30. Oktober 2020 wurde die App "Patienten" zurückgezogen und durch die App [Listen ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams ersetzt. Mit Listen können Pflegeteams in Ihrer Organisation im Gesundheitswesen Patientenlisten für Szenarien erstellen, die von Visiten und interdisziplinären Teambesprechungen bis zur allgemeinen Patientenüberwachung reichen.

Die Listen-App in Microsoft Teams hilft Benutzern in Ihrer Organisation beim Nachverfolgen von Informationen und beim Organisieren von Arbeitsabläufen. Die App ist für alle Microsoft Teams-Benutzer vorinstalliert und steht in jedem Team und Kanal als Registerkarte zur Verfügung. Listen können neu erstellt werden, aus vordefinierten Vorlagen oder durch Importieren von Daten in Excel.

Gesundheitsteams können für die ersten Schritte die Vorlage "Patienten" verwenden. Sie können Listen erstellen, um die Bedürfnisse und den Status der Patienten nachzuverfolgen. Vorhandene Patientendaten in Excel-Tabellen können integriert werden, um in Teams eine Liste zu erstellen. Diese Listen können für Szenarien wie Visiten und Patientenüberwachung verwendet werden, um die Pflege zu koordinieren.

Eine verantwortliche Krankenschwester erstellt beispielsweise eine Patientenliste in einem Team, welche alle Mitglieder des Gesundheitsteams einschließt. Während der Visite greift das Gesundheitsteam über seine Mobilgeräte auf Teams zu und aktualisiert die Patienteninformationen in der Liste, die alle Teammitglieder einsehen können, um auf dem gleichen Stand zu bleiben. Bei Visiten, bei denen sich das Gesundheitsteam versammelt, um wichtige Gesundheitsleistungskennzahlen zu besprechen und auszuwerten, um sicherzustellen, dass sich ein Patient auf einem guten Weg zur Entlassung befindet, können sie diese Informationen mithilfe von Teams auf einem großen Bildschirm teilen. Mitglieder des Gesundheitsteams, die nicht vor Ort sind, können von Remote teilnehmen.

Hier ist eine Beispielliste, die für Patientenvisiten eingerichtet wurde.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Screenshot einer Beispielliste für Patientenvisiten":::

Weitere Informationen finden Sie unter [Verwalten der Listen-App für Ihre Organisation in Teams](../../manage-lists-app.md).

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Nachverfolgen und Überwachen von Aufgaben mit der Tasks-App

Verwenden Sie [Tasks](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) in Teams, um Aufgaben für das gesamte Gesundheitsteam nachzuverfolgen. Ihr Gesundheitsteam kann Aufgaben auf jedem Gerät, auf dem Teams ausgeführt wird, jederzeit erstellen, zuweisen und planen, Aufgaben kategorisieren und den Status aktualisieren. IT-Profis und Administratoren können auch Aufgaben für bestimmte Teams in Ihrer Organisation veröffentlichen. Sie können beispielsweise eine Reihe von Aufgaben für neue Sicherheitsprotokolle oder einen neuen Aufnahmeschritt veröffentlichen, welche im gesamten Spital zu verwenden sind.

Weitere Informationen finden Sie unter [Verwalten der Tasks-App für Ihre Organisation in Microsoft Teams](../../manage-tasks-app.md).

### <a name="streamline-approvals-with-the-approvals-app"></a>Optimieren von Genehmigungen mit der App für Genehmigungen.

Verwenden Sie [Genehmigungen](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) in Microsoft Teams, um alle Ihre Anforderungen und Prozesse mit Ihrem Team zu optimieren. Erstellen, verwalten und teilen Sie Genehmigungen direkt von Ihrem Teamarbeitshub aus. Starten Sie einen Genehmigungsablauf von demselben Ort aus, an dem Sie einen Chat senden, in einer Kanalunterhaltung oder über die Genehmigungsapp selbst. Wählen Sie einfach einen Genehmigungstyp aus, fügen Sie Details hinzu, fügen Sie Dateien an, und wählen Sie genehmigende Benutzer aus. Sobald dies übermittelt wurde, werden die genehmigenden Benutzer benachrichtigt und sie können die Anforderung überprüfen und entsprechend agieren.

Sie können die Genehmigungs-App für Ihre Organisation zulassen und ihren Teams hinzufügen. Weitere Informationen finden Sie unter [Verfügbarkeit der Teams-Genehmigungs-App](../../approval-admin.md).

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Erstellen, Verwalten und Freigeben von Zeitplänen mit der App „Schichten“ und der Integration von Mitarbeitern in Service und Produktion

Microsoft Teams ist mit der App "Schichten" und Mitarbeitern in Service und Produktion integriert, was unter anderem zur Koordinieren von Schichtbesetzungsfunktionen verwendet werden kann. So können Pflegemanager beispielsweise in Schichten Zeitpläne für ihre Mitarbeiter einrichten und koordinieren, und Pflegekräfte können Zeitpläne überprüfen und Schichten tauschen. Microsoft Teams umfasst eine integrierte App-Setup-Richtlinie für Mitarbeiter in Service und Produktion, die Sie ihnen in Ihrem Unternehmen zuweisen können. Standardmäßig beinhaltet diese Richtlinie die Apps für Aktivität, Schichten, Chat und Anrufe. Diese Richtlinie steuert das Verhalten für diese Apps, z. B. das Anheften der Schichten-App an die App-Leiste, damit das Team schnell darauf zugreifen kann.

Weitere Informationen finden Sie unter [Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Unterstützen der Klinikmitarbeiter und Information Worker bei den ersten Arbeiten mit Teams

Es stehen viele Ressourcen zur Verfügung, die allen Benutzern in Ihrer Organisation dabei helfen sollen, sich schnell an die Verwendung von Teams zu gewöhnen:

- Im [Teams Adoption Center](https://adoption.microsoft.com/microsoft-teams/) finden Sie Tipps zur Einführung von Teams, wenn Sie gerade erst mit der Einführung von Teams in Ihrem Unternehmen beginnen, oder um Teams auf weitere Bereiche Ihres Unternehmens auszuweiten.
- Erwägen Sie die Einrichtung benutzerdefinierter [Lernpfade](https://adoption.microsoft.com/microsoft-365-learning-pathways/), damit ihre Benutzer nur die notwendigen Aufgaben durchlaufen müssen.
- Auf der [Teams-Supportwebsite](https://support.microsoft.com/teams) erhalten Sie Hilfe und Schulungen für Ihre Benutzer zum Ausführen grundlegender Aufgaben in Microsoft Teams, einschließlich [Videos mit Kurzschulungen](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7). Diese Website bietet auch Hilfe und Schulungen für die Teams-Apps, einschließlich [Listen](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db), [Tasks](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070), [Genehmigungen](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3), [Bookings](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b) und [-Schichten](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821).
