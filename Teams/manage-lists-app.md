---
title: Verwalten der Listen-App für Ihre Organisation
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
description: Hier erfahren Sie, wie Sie die Listen-App in Microsoft Teams für Benutzer in Ihrer Organisation verwalten können.
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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944610"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Verwalten der Listen-App für Ihre Organisation in Microsoft Teams

## <a name="overview-of-lists"></a>Übersicht über Listen

Die Listen-App in Microsoft Teams hilft Benutzern in Ihrer Organisation beim Nachverfolgen von Informationen, Organisieren von Tätigkeiten und Verwalten von Arbeitsabläufen. Die Listen-App ermöglicht es Benutzern Daten zu Problemen, Ressourcen, Routinen, Kontakten, Bestand, Vorfällen, Darlehen, Patienten und mehr mithilfe anpassbarer Ansichten, Regeln und Benachrichtigungen nachzuverfolgen, damit alle Teammitglieder auf dem neuesten Stand bleiben.

In Microsoft Teams greifen Benutzer auf Listen über eine eigene Registerkarte in einem Kanal zu. Klicken Sie zum Loslegen auf das **+**, um den Registerkartenkatalog zu öffnen und einem Kanal eine neue Listen-App-Registerkarteninstanz hinzuzufügen.

![Listen-App im Registerkartenkatalog](media/lists-tab.png)

Benutzer können neue Listen erstellen oder im selben Team vorhandene bzw. Listen von einer anderen SharePoint-Website anheften, auf die sie Zugriff haben. Neue Listen können vollkommen neu erstellt, aus integrierten Vorlagen, basierend auf der Struktur einer bestehenden Liste oder durch Importieren von Daten aus einer Excel-Arbeitsmappe erstellt werden. Die Listen-App ist in Microsoft Teams Desktop-, Web- und mobilen Clients verfügbar.

![Erstellen einer Liste in der Listen-App](media/lists-create-list.png)

## <a name="templates"></a>Vorlagen

Die Vorlagen in der Listen-App sind auf allgemeine Szenarien für Benutzer zur Nachverfolgung von Informationen zugeschnitten. Jede Vorlage weist eine vordefinierte Listenstruktur auf und umfasst Formularlayouts sowie Formatierungsoptionen auf Listenansichts- und Detailansichtsebene, um Benutzern den Einstieg zu erleichtern. Nachdem er eine Vorlage ausgewählt hat, werden dem Benutzer eine Vorschau des Aussehens der Liste angezeigt sowie einige Beispieldaten zur Verfügung gestellt. Nachfolgend sind einige Beispiele dafür aufgeführt, wie Teams in Ihrer Organisation die vordefinierten Vorlagen in der Listen-App verwenden können:

- Verfolgen von Problemen und deren Lösung mithilfe der Vorlage zur Problemverfolgung
- Organisieren aller Ereignisinformationen mithilfe der Vorlage für Ereignisabläufe
- Verwenden Sie die Patienten-Vorlage zum Erfassen von Bedürfnissen und Zustand von Patienten für die Teams in Ihrer Gesundheitsorganisation, um die Pflege zu überwachen und zu koordinieren.
- Verfolgen des Status von Kreditanträgen mit der Vorlage für Darlehen

## <a name="example-scenario"></a>Beispielszenario

Eine lokale Poststelle ist für das Sortieren und Zustellen von Briefen in ihrem Stadtteil zuständig. Jeden Morgen trifft sich in der Poststelle das ganze Team, um Tagesziele zu überprüfen, Neuigkeiten weiterzugeben und bekannte Vorfälle zu besprechen. 

Nach dem Treffen machen sich die Postboten auf den Weg, um die Briefe zuzustellen. Unterwegs kann es zu Zwischenfällen wie einem Verkehrsunfall, einem Problem mit Hunden oder sozialen Unruhen kommen. Wenn Postboten auf ein Problem stoßen, verwenden sie Microsoft Teams auf ihren Mobilgeräten, um die Details dazu zu erfassen, die in einer Liste im Teamkanal nachverfolgt werden. Jeder im Team, einschließlich der Postboten vor Ort, kann diese Informationen sehen und darüber auf dem Laufenden bleiben.

Vor dem Übergang zu Microsoft Teams mussten die Postboten zum Postbüro zurückkehren und ein Papierformular ausfüllen, um einen Vorfall zu melden, und dieses musste dann händisch in eine Excel-Tabelle übertragen werden. Microsoft Teams stellt eine mobile Lösung für Postboten dar, über die sie mithilfe der Listen-App Vorfälle im Außendienst melden, Vorfalldetails mit Teammitgliedern teilen, sich im Kanal darüber unterhalten und Vorfälle einer Lösung zuführen können.

## <a name="what-you-need-to-know-about-lists"></a>Wissenswertes über die Listen-App

### <a name="lists-is-available-in-every-team-and-channel"></a>Die Listen-App ist in jedem Team und Kanal verfügbar.

Die Listen-App ist für alle Microsoft Teams-Benutzer vorinstalliert und steht direkt im Registerkartenkatalog jedes Teams und Kanals zur Verfügung. Dies bedeutet, dass Benutzer nicht zum Microsoft Teams-App Store wechseln müssen, um sie zu installieren.

### <a name="lists-and-sharepoint"></a>Die Listen-App und SharePoint

Listen-App-Daten werden auf der SharePoint Online-Teamsite gespeichert. Weitere Informationen zur Interaktion zwischen SharePoint Online und Microsoft Teams finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](SharePoint-OneDrive-interact.md).

In SharePoint festgelegte Berechtigungen gelten für in der Listen-App erstellte Listen. Listen erben standardmäßig Berechtigungen von der Website, zu der sie gehören. Von diesen Berechtigungen hängt ab, welche Art von Aktionen Benutzer ausführen können, z. B. ob sie Listen erstellen oder bearbeiten können. Weitere Informationen finden Sie unter [Berechtigungsstufen in SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) und [Benutzerberechtigungen und Berechtigungsstufen in SharePoint Server](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels).

In bestimmten Szenarien möchten Sie eventuell einschränken, welche Aktionen Benutzer in Listen ausführen können. Wenn beispielsweise jemand in einem Team eine Listenansicht bearbeitet, ändert diese sich für alle Teammitglieder, daher möchten Sie möglicherweise nur dem Teambesitzer oder bestimmten Teammitgliedern das Bearbeiten von Listenansichten gestatten. Weitere Informationen finden Sie unter [Anpassen von Berechtigungen für eine SharePoint-Liste oder -Bibliothek](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013).

> [!NOTE]
> Derzeit sind Besitzer- und Mitgliederberechtigungen in einem Team nicht mit Berechtigungen auf der Teamwebsite verknüpft, die das Verhalten von Listen oder der Listen-App steuern. Dies wird jedoch je nach Kundenfeedback und -nutzung in einer zukünftigen Iteration des Produkts berücksichtigt werden.  

### <a name="limitations"></a>Einschränkungen

Mit der Listen-App verfügen Benutzer über eine Desktop-, Web- und mobile Umgebung. Es ist wichtig zu wissen, dass Benutzer mithilfe der Listen-App im mobilen Microsoft Teams-Client keine neuen Listen erstellen oder vorhandene Listen anheften können. Um eine Liste im mobilen Microsoft Teams-Client anzeigen oder bearbeiten zu können, muss zuerst eine Liste mithilfe der Listen-App auf dem Microsoft Teams-Desktop- oder -Webclient erstellt oder hinzugefügt werden.

Gäste können keine Liste erstellen oder löschen. Sie können vorhandenen Listen Listenelemente hinzufügen, neue Unterhaltungen zu Listenelementen beginnen und auf vorhandene Unterhaltungen zu Listenelementen antworten.

### <a name="lists-and-the-sharepoint-app"></a>Die Listen-App und die SharePoint-App

Wenn Benutzer in Ihrer Organisation Listen mithilfe der SharePoint-App erstellt haben, werden diese automatisch in die Listen-App verschoben, ohne dass hierzu eine Aktion des Benutzers erforderlich ist. Verwenden Sie für die beste und vollständigste Listenintegration die Listen-App, und heften Sie vorhandene Listen an.

## <a name="set-up-lists"></a>Einrichten der Listen-App

### <a name="enable-or-disable-lists-in-your-organization"></a>Aktivieren oder Deaktivieren der Listen-App in Ihrer Organisation

"Listen" ist standardmäßig für alle Microsoft Teams-Benutzer in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](manage-apps.md) deaktivieren oder aktivieren.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Führen Sie einen der folgenden Schritte aus:

    - Wenn Sie "Listen" für Ihre Organisation deaktivieren möchten, suchen Sie nach der App "Listen", wählen Sie sie aus, und klicken Sie dann auf **Blockieren**.
    - Wenn Sie "Listen" für Ihre Organisation aktivieren möchten, suchen Sie nach der App "Listen", wählen Sie sie aus, und klicken Sie dann auf **Zulassen**.

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>Aktivieren oder Deaktivieren von "Listen" für bestimmte Benutzer in Ihrer Organisation

Wenn Sie die Nutzung von "Listen" für bestimmte Benutzer in Ihrer Organisation zulassen oder blockieren möchten, stellen Sie sicher, dass die App für Ihre Organisation auf der Seite [Apps verwalten](manage-apps.md) aktiviert ist, und erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie diese den betreffenden Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

## <a name="search-the-audit-log-for-list-events"></a>Durchsuchen des Überwachungsprotokolls nach Listenereignissen

Für Listen ist die Überwachung auf Unternehmensebene aktiviert, sodass Sie im Überwachungsprotokoll im Security & Compliance Center nach Listen und Listenelementereignissen suchen können. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

Eine Liste der Überwachungsereignisse, die für die Listen-App in Microsoft Teams relevant sind, finden Sie unter [SharePoint-Listenaktivitäten](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities).

Damit Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst im [Security & Compliance Center](https://protection.office.com) die Überwachung aktivieren. Denken Sie daran, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="power-automate-power-apps-and-graph-api"></a>Power Automate, Power Apps und Graph-API

Die Listen-App unterstützt [Power Automate](https://docs.microsoft.com/power-automate/flow-types) für Workflows und [Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) für Listenformulare. Entwickler können die [Listen-API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) verwenden, um Listendaten als Quelle über Microsoft Graph zu verbinden.

## <a name="give-feedback-or-report-an-issue"></a>Feedback senden oder Problem melden
  
Wenn Sie uns Feedback senden oder ein Problem melden möchten, klicken Sie am unteren Ende der linken Navigationsleiste in Microsoft Teams auf **Hilfe**, und wählen Sie dann **Problem melden** aus. Wählen Sie **Listen** aus, und geben Sie dann Ihr Feedback oder die Details zu dem aufgetretenen Problem ein.

## <a name="related-topics"></a>Verwandte Themen

- [Listen-Hilfedokumentation](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
