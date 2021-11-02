---
title: Teamvorlagen für Gemeinnützigkeit verwenden
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Erfahren Sie, wie Sie die Teamvorlage „Freiwillige verwalten“ verwalten und verwenden, um schnell und einfach Teams mit Mitarbeitern in Ihrer gemeinnützigen Organisation zu erstellen, die miteinander kommunizieren und bei Aktivitäten der Freiwilligenverwaltung zusammenarbeiten.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f0a6218d9843c0ed99c80c517fe9986f41d79b6
ms.sourcegitcommit: 1957a06d4bae3d42b4e3b6d4bd8ff2752a19d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2021
ms.locfileid: "60641345"
---
# <a name="use-nonprofit-team-templates"></a>Teamvorlagen für Gemeinnützigkeit verwenden

Mit Teamvorlagen in Microsoft Teams können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Teamstruktur aus Einstellungen, Kanälen und vorinstallierten Apps bereitstellen.

Für gemeinnützige Organisationen können Teamvorlagen besonders nützlich sein, da sie Ihnen dabei helfen, innerhalb der gesamten Organisation schnell einheitliche Teams bereitzustellen. Vorlagen helfen den Mitarbeitern auch, sich bei der effektiven Verwendung von Teams zu orientieren.

Teams enthält eine Teamvorlage „Freiwillige verwalten“, die entwickelt wurde, um die Aktivitäten der Freiwilligenverwaltung zu optimieren. Verwenden Sie diese vordefinierte Vorlage, um schnell Teams mit Mitarbeitern zu erstellen, die miteinander kommunizieren und bei Aufgaben und Aktivitäten der Freiwilligenverwaltung zusammenarbeiten.

In diesem Artikel erfahren Sie mehr über die Teamvorlage „Freiwillige verwalten“ und wie Sie diese zum Erstellen eines Teams verwenden. Dieser Artikel bietet Ihnen auch eine Übersicht über das Verwalten von Teamvorlagen im Microsoft Teams Admin Center.

## <a name="manage-volunteers-team-template"></a>Teamvorlage „Freiwillige verwalten“

Bringen Sie Ihre Mitarbeiter zusammen, damit sie miteinander kommunizieren und bei Aufgaben und Aktivitäten der Freiwilligenverwaltung zusammenarbeiten.

Diese Vorlage enthält Kanäle und Apps, die entwickelt wurden, um die Aktivitäten der Freiwilligenverwaltung zu optimieren. Mitarbeiter können Kursmaterialien zum Onboarding und häufig verwendete Dokumente organisieren und freigeben, Berichte anzeigen, sich über wichtige Team- und Ereignisankündigungen auf dem neuesten Stand halten und vieles mehr. Die Vorlage lässt sich auch in [Volunteer Management](/dynamics365/industry/nonprofit/volunteer-management-use)integrieren, einer App, die Teil der[Microsoft Cloud für Gemeinnützige Organisationen](/industry/nonprofit/)ist und Mitarbeitern die Verwaltung von Möglichkeiten für freiwilliges Engagement in Teams ermöglicht.

Hier sind die Kanäle und Apps, die in der Teamvorlage „Freiwillige Verwalten“ enthalten sind.

| Vorlagentyp |TemplateId | Eigenschaften, die mit dieser Vorlage geliefert werden |
| ------------------|-- |----------------------------------------------------- |
|Freiwillige verwalten| `ManageVolunteers` |Kanäle: <ul><li>Allgemein<ul><li>Website&sup1;</li></ul><li>Ankündigungen</li><li>Berichterstellung<ul><li>Power BI&sup1;</li></ul></li><li>Freiwilligenverwaltung<ul><li>Power Apps&sup1;</li></ul></li><li>Engagement-Möglichkeiten<ul><li>Aufgaben&sup1;</li></ul></li><li>Onboarding von Freiwilligen<ul><li>SharePoint&sup1;</li><li>OneNote&sup1;</li></ul></li></ul> Apps: <ul><li>Website</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Aufgaben</li><li>SharePoint</li><li>OneNote</li></ul>|

&Sup1; App zum Kanal als Registerkarte hinzugefügt

## <a name="create-a-team-using-the-manage-volunteers-team-template"></a>Erstellen eines Teams mithilfe der Teamvorlage „Freiwillige verwalten“

### <a name="create-the-team"></a>Erstellen des Teams

Es sind nur wenige schnelle Schritte erforderlich, um ein Team aus der Vorlage „Freiwillige verwalten“ zu erstellen.

1. Wechseln Sie in Teams zu **Teams** > **Beitreten zu oder Erstellen eines Teams** > **Team erstellen**.
2. Wählen Sie die Teamvorlage **Freiwillige verwalten** aus.
3. Wählen Sie eine Datenschutzebene aus:
    - **Privat**: Personen benötigen die Berechtigung des Teambesitzers, um dem Team beizutreten.
    - **Öffentlich**: Jeder in Ihrer Organisation kann dem Team beitreten.
4. Geben Sie Ihrem Team einen Namen, und fügen Sie eine Beschreibung hinzu. Sie können Kanäle auch umbenennen, um das Team anzupassen.
5. Wählen Sie **Erstellen** aus.

Weitere Informationen finden Sie unter [Erstellen eines Teams mit einer Teamvorlage](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

### <a name="add-the-volunteer-management-app-to-the-power-apps-tab"></a>Hinzufügen der App „Freiwilligenverwaltung“ zur Registerkarte „Power Apps“

Um die App „Freiwilligenverwaltung“ in Teams zu verwenden, fügen Sie diese der Registerkarte „Power Apps“ im Kanal „Freiwilligenverwaltung“ hinzu. 

1. Wechseln Sie in Teams zum Team, das Sie erstellt haben, wählen Sie den Kanal „Freiwilligenverwaltung“ und dann die Registerkarte **Power Apps** aus.
2. Wählen Sie in der Dropdownliste **Modellgesteuerte Apps** aus, suchen Sie nach **Freiwilligenverwaltung** und wählen Sie diese aus.
3. Klicken Sie auf **Speichern**.

Weitere Informationen finden Sie unter [Einbetten einer modellgesteuerten App als Registerkarten-App in Teams](/powerapps/teams/embed-model-driven-teams-tab).

## <a name="view-and-manage-team-templates-in-the-teams-admin-center"></a>Anzeigen und Verwalten von Teamvorlagen im Microsoft Teams Admin Center

Wenn Sie ein Administrator sind, können Sie Teamvorlagen im Microsoft Teams Admin Center anzeigen verwalten. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Teams** > **Teamvorlagen**, um die Vorlage „Freiwillige verwalten“ anzuzeigen.

Sie können für Ihre Benutzer auch [Vorlagenrichtlinien erstellen und zuweisen](templates-policies.md), um zu steuern, welche Vorlagen ihnen in Microsoft Teams zum Erstellen von Teams angezeigt werden.

Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Teamvorlagen im Teams Admin Center](get-started-with-teams-templates-in-the-admin-console.md).

## <a name="related-articles"></a>Verwandte Artikel

- [Teams-Hilfedokumentation](https://support.microsoft.com/teams)
- [Dokumentation zu Microsoft Cloud für gemeinnützige Organisationen](/industry/nonprofit/)
