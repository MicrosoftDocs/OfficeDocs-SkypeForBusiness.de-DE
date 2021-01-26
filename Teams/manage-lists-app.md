---
title: Verwalten der App "Listen" für Ihre Organisation
author: cichur
ms.author: v-cichur
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Erfahren Sie, wie Sie die App "Listen" in Teams für Benutzer in Ihrer Organisation verwalten.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365initiative-lists
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: e0fb125ede9300395e045a0c5640abd075547562
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944610"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Verwalten der App "Listen" für Ihre Organisation in Microsoft Teams

## <a name="overview-of-lists"></a>Übersicht über Listen

Mit der App "Listen" in Microsoft Teams können Benutzer in Ihrer Organisation Informationen nachverfolgen, Arbeit organisieren und Workflows verwalten. Mithilfe von Listen können Benutzer Daten wie Probleme, Ressourcen, Routinen, Kontakte, Inventar, Vorfälle, Kredite, Patienten und vieles mehr nachverfolgen, indem sie anpassbare Ansichten, Regeln und Benachrichtigungen verwenden, damit alle Teammitglieder synchron bleiben.

In Teams greifen Benutzer als Registerkarte in einem Kanal auf Listen zu. Klicken Sie, um den Registerkartenkatalog zu öffnen und eine neue Registerkarteninstanz der App "Listen" zu einem Kanal hinzuzufügen, um **+** zu beginnen.

![Listen-App im Registerkartenkatalog](media/lists-tab.png)

Benutzer können neue Listen erstellen oder vorhandene Listen innerhalb desselben Teams oder von einer anderen SharePoint-Website, auf die sie Zugriff haben, anheften. Neue Listen können ganz neu, aus integrierten Vorlagen, basierend auf der Struktur einer vorhandenen Liste oder durch Importieren von Daten aus einer Excel-Arbeitsmappe, erstellt werden. Die App "Listen" steht in Desktop-, Web- und mobilen Clients von Teams zur Verfügung.

![Erstellen einer Liste in der App "Listen"](media/lists-create-list.png)

## <a name="templates"></a>Vorlagen

Vorlagen in Listen sind auf allgemeine Szenarien zur Informationsnachverfolgung für Benutzer zugeschnitten. Jede Vorlage verfügt sowohl auf Listenansichtsebene als auch auf Detailansichtsebene über eine vordefinierte Listenstruktur, Formularlayouts und Formatierungsoptionen, damit die Benutzer schnell beginnen können. Nachdem Sie eine Vorlage ausgewählt haben, erhalten Die Benutzer eine Vorschau der Liste und einige Beispieldaten. Hier sind einige Beispiele dafür, wie Teams in Ihrer Organisation die vordefinierten Vorlagen in Listen verwenden können:

- Verfolgen Sie Probleme nach, und bringen Sie sie mithilfe der Vorlage "Problemverfolgung" zum Abschluss.
- Organisieren Sie alle Ihre Ereignisdetails mit der Vorlage "Veranstaltungsroute".
- Verwenden Sie die Vorlage "Patienten", um die Anforderungen und den Status von Patienten für die Gesundheitsteams in Ihrer Gesundheitsorganisation zur Überwachung und Koordinaten der Pflege zu notigrammen.
- Verfolgen Sie den Status von Kreditanträgen mit der Vorlage "Darlehen".

## <a name="example-scenario"></a>Beispielszenario

Eine Poststelle vor Ort ist für das Sortieren und Ausliefern von E-Mails in ihrem Bezirk zuständig. Jeden Morgen steht in der Poststelle ein Team zusammen, um tägliche Ziele zu überprüfen, Ankündigungen zu teilen und bekannte Vorfälle zu diskutieren.

Nach der Umarmung nehmen die E-Mail-Netzbetreiber ihre E-Mails ab und beginnen ihren Zustellungsweg. Vorfälle können entlang einer Route auftreten, z. B. ein Fahrzeugunfall, hundebezogene Probleme oder soziale Unerstungen. Wenn E-Mail-Netzbetreiber auf einen Vorfall stoßen, verwenden sie Teams auf ihren mobilen Geräten, um die Vorfalldetails zu zeichnen, die in einer Liste im Teamkanal nachverfolgt werden. Alle Teammitglieder, einschließlich der Postbetreiber im Außendienst, können diese Informationen sehen und auf dem Laufenden bleiben.

Vor dem Wechsel zu Teams mussten die E-Mail-Netzbetreiber zurück zum Post office wechseln, um ein Hard Copy-Formular zu erstellen, um einen Vorfall zu melden, der in eine Excel-Tabelle eingegeben wurde. Teams bietet den E-Mail-Netzbetreibern als Erstes ein mobiles Gerät, in dem sie Mithilfe von Listen Vorfälle im Außendienst während deren Auftreten melden, Vorfalldetails mit Teammitgliedern teilen, Unterhaltungen zu ihnen im Kanal führen und Vorfälle zur Lösung vor ort treiben können.

## <a name="what-you-need-to-know-about-lists"></a>Was Sie über Listen wissen müssen

### <a name="lists-is-available-in-every-team-and-channel"></a>Listen sind in jedem Team und Kanal verfügbar.

Listen sind für alle Benutzer von Teams vorinstalliert und stehen direkt im Registerkartenkatalog jedes Teams und Kanals zur Verfügung. Dies bedeutet, dass Benutzer nicht zum Store für Teams-Apps wechseln müssen, um sie zu installieren.

### <a name="lists-and-sharepoint"></a>Listen und SharePoint

Listendaten werden auf der SharePoint Online-Teamwebsite gespeichert. Weitere Informationen zur Interaktion von SharePoint Online mit Teams finden Sie unter ["Interaktion von SharePoint Online und OneDrive for Business mit Teams".](SharePoint-OneDrive-interact.md)

In SharePoint festgelegte Berechtigungen gelten für Listen, die in der App "Listen" erstellt wurden. Standardmäßig erben Listen Berechtigungen von der Website, zu der sie gehören. Diese Berechtigungen steuern die Arten von Aktionen, die Benutzer ausführen können, z. B. ob sie Listen erstellen oder bearbeiten können. Weitere Informationen finden Sie unter [Berechtigungsstufen in SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) sowie [Benutzerberechtigungen und Berechtigungsstufen in SharePoint Server.](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)

In bestimmten Szenarien möchten Sie möglicherweise einschränken, welche Aktionen Benutzer in Listen ausführen können. Beispielsweise bearbeitet eine Person in einem Team eine Listenansicht, wodurch sie für alle Teammitglieder geändert wird, und Sie möchten nur dem Teambesitzer oder bestimmten Teammitgliedern das Bearbeiten von Listenansichten gestatten. Weitere Informationen finden Sie unter ["Anpassen von Berechtigungen für eine SharePoint-Liste oder -Bibliothek".](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)

> [!NOTE]
> An diesem Punkt sind besitzer- und mitgliederberechtigungen in einem Team in keinem Fall mit Berechtigungen auf der Teamwebsite verknüpft, die das Verhalten von Listen oder der Listen-App steuern. Basierend auf Kundenfeedback und -verwendung wird dies jedoch für eine zukünftige Produktiteration berücksichtigt.  

### <a name="limitations"></a>Einschränkungen

Mit Listen erhalten Benutzer eine Desktop-, Web- und mobile Erfahrung. Es ist wichtig zu wissen, dass Benutzer mithilfe von Listen im mobilen Client von Teams keine neuen Listen erstellen oder vorhandene Listen anheften können. Zum Anzeigen oder Bearbeiten einer Liste im mobilen Client von Teams muss zuerst eine Liste mithilfe von Listen auf dem Desktop- oder Webclient von Teams erstellt oder hinzugefügt werden.

Gäste können keine Liste erstellen oder löschen. Sie können Listenelemente zu vorhandenen Listen hinzufügen, neue Unterhaltungen zu Listenelementen beginnen und auf vorhandene Unterhaltungen zu Listenelementen antworten.

### <a name="lists-and-the-sharepoint-app"></a>Listen und die SharePoint-App

Wenn Benutzer in Ihrer Organisation Listen mit der SharePoint-App erstellt haben, werden diese Listen automatisch in Listen verschoben, ohne dass eine Aktion des Benutzers erforderlich ist. Um die besten und besten Listenintegrationserfahrungen in Teams zu erhalten, verwenden Sie die App "Listen", und heften Sie ihre vorhandenen Listen an.

## <a name="set-up-lists"></a>Einrichten von Listen

### <a name="enable-or-disable-lists-in-your-organization"></a>Aktivieren oder Deaktivieren von Listen in Ihrer Organisation

Listen sind standardmäßig für alle Benutzer von Teams in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](manage-apps.md) deaktivieren oder aktivieren.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Führen Sie einen der folgenden Schritte aus:

    - Um Listen für Ihre Organisation zu deaktivieren, suchen Sie nach der App "Listen", wählen Sie sie aus, und klicken Sie dann auf **"Blockieren".**
    - Um Listen für Ihre Organisation zu aktivieren, suchen Sie nach der Listen-App, wählen Sie sie aus, und klicken Sie dann auf **"Zulassen".**

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>Aktivieren oder Deaktivieren von Listen für bestimmte Benutzer in Ihrer Organisation

Wenn Sie zulassen oder blockieren möchten, dass bestimmte Benutzer in Ihrer Organisation [](manage-apps.md) Listen verwenden können, stellen Sie sicher, dass Listen für Ihre Organisation auf der Seite "Apps verwalten" aktiviert ist. Erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie sie diesen Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

## <a name="search-the-audit-log-for-list-events"></a>Durchsuchen des Überwachungsprotokolls nach Listenereignissen

Listen werden mit Überwachung auf Unternehmensebene aktiviert, sodass Sie im Überwachungsprotokoll im Security & Compliance Center nach Listen und Listenelementereignissen suchen können. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

Eine Liste der Überwachungsereignisse, die für die App "Listen" in Teams relevant sind, finden Sie unter ["SharePoint-Listenaktivitäten".](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)

Bevor Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst die Überwachung im [Security & Compliance Center aktivieren.](https://protection.office.com) Beachten Sie, dass Überwachungsdaten nur ab dem Punkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="power-automate-power-apps-and-graph-api"></a>Power Automate, Power Apps und Graph API

Listen unterstützen [Power Automate für](https://docs.microsoft.com/power-automate/flow-types) Workflows und Power [Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) für Listenformulare. Entwickler können die [Listen-API verwenden,](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) um Listendaten über Microsoft Graph als Quelle zu verbinden.

## <a name="give-feedback-or-report-an-issue"></a>Feedback geben oder ein Problem melden
  
Um uns Feedback zu senden  oder ein Problem zu melden, klicken Sie unten im linken Navigationsbereich in Teams auf "Hilfe", und wählen Sie dann "Problem **melden" aus.** Wählen **Sie "Listen"** aus, und geben Sie Dann Ihr Feedback oder Details zu dem problem, das Sie gerade haben, ein.

## <a name="related-topics"></a>Verwandte Themen

- [Liste der Hilfedokumentation](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
