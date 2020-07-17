---
title: Verwalten der Listen-App für Ihre Organisation
author: LanaChin
ms.author: v-lanac
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Listen-app in Teams für Benutzer in Ihrer Organisation verwalten.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 1423c17d57c0074f9e6db1091791eb3f17370414
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158693"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Verwalten der Listen-App für Ihre Organisation in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview-of-lists"></a>Übersicht überlisten

Mithilfe der Listen-app in Microsoft Teams können Benutzer in Ihrer Organisation Informationen nachvollziehen, Arbeit organisieren und Workflows verwalten. Mit Listen können Benutzerdaten wie Probleme, Ressourcen, Routinen, Kontakte, Inventar, Vorfälle, Kredite, Patienten und mehr mithilfe von anpassbaren Ansichten, Regeln und Benachrichtigungen nachverfolgen, um alle Personen im Team synchron zu halten.

In Teams greifen Benutzer auf Listen als Registerkarte in einem Kanal zu. Klicken Sie **+** , um den Registerkarten Katalog zu öffnen, und fügen Sie einen neuen Listen-App-Registerkarten-Instanz zu einem Kanal hinzu, um loszulegen. 

![Screenshot der App "Listen" im Reiter Katalog](media/lists-tab.png)

Benutzer können neue Listen erstellen oder vorhandene Listen innerhalb des gleichen Teams oder auf einer anderen SharePoint-Website anheften, auf die Sie Zugriff haben. Neue Listen können von Grund auf neu erstellt werden, von integrierten Vorlagen, basierend auf der Struktur einer vorhandenen Liste oder durch Importieren von Daten aus einer Excel-Arbeitsmappe. Die Listen-APP ist in den Desktop-, Web-und mobilen Clients von Teams verfügbar.

![Screenshot zum Erstellen einer Liste in der App "Listen"](media/lists-create-list.png)

## <a name="templates"></a>Vorlagen

Vorlagen in Listen sind auf häufige Informations Überwachungsszenarien für Benutzer zugeschnitten. Jede Vorlage enthält eine vordefinierte Listenstruktur, Formularlayouts und Formatierungsoptionen sowohl in einer Listenansicht als auch in einer Detail Ansichtsebene, damit Benutzer schnell loslegen können. Nachdem Sie eine Vorlage ausgewählt haben, erhalten die Benutzer eine Vorschau, wie die Liste aussehen wird, sowie einige Beispieldaten. Nachfolgend finden Sie einige Beispiele dafür, wie Teams in Ihrer Organisation die vordefinierten Vorlagen in Listen verwenden können:

- Verfolgen Sie Probleme, und bringen Sie Sie mithilfe der Issue Tracker-Vorlage zum Abschluss.
- Organisieren Sie alle Ihre Veranstaltungsdetails mit der Vorlage für das Event-Reiseplan.
- Verwenden Sie die Vorlage "Patienten", um die Anforderungen und den Status von Patienten für Betreuerteams in Ihrer Gesundheitsorganisation aufzuzeichnen, um die Betreuung zu überwachen und zu koordinieren.
- Nachvollziehen des Status von Darlehensanträgen mit der Vorlage "Kredite"

## <a name="example-scenario"></a>Beispielszenario

Eine lokale Poststelle ist für das Sortieren und die Zustellung von e-Mails in ihrem Distrikt verantwortlich. Jeden Morgen hat die Post ein Team zusammengedrängt, um die täglichen Ziele zu überprüfen, Ankündigungen auszutauschen und bekannte Vorfälle zu besprechen.

Nach dem drängen nehmen e-Mail-Anbieter Ihre e-Mail-Adresse auf und starten deren Übermittlungsroute. Zwischenfälle können entlang einer Route auftreten, beispielsweise ein Fahrzeug Unfall, ein Hund-bezogenes Problem oder ein gesellschaftlicher Unruhe Protest. Wenn e-Mail-Anbieter auf einen Vorfall stoßen, verwenden Sie Teams auf Ihren mobilen Geräten, um die Vorfalldetails aufzuzeichnen, die in einer Liste im Teamkanal nachverfolgt werden. Jeder im Team, einschließlich der e-Mail-Anbieter im Feld, kann diese Informationen sehen und auf dem Laufenden bleiben.

Bevor Sie zu Teams wechseln, mussten e-Mail-Anbieter zum Post Office zurückkehren, um ein Hardcopy-Formular abzuschließen, um einen Vorfall zu melden, der in eine Excel-Tabelle eingegeben wurde. Teams gibt e-Mail-Netzbetreibern zunächst ein Mobiltelefon, erleben Sie, wo Sie Listen verwenden können, um Vorfälle in dem Feld zu melden, während Sie auftreten, geben Sie Vorfalldetails mit Teammitgliedern frei, führen Sie Unterhaltungen über Sie auf dem Kanal aus, und fahren Sie Zwischenfälle auf

## <a name="what-you-need-to-know-about-lists"></a>Was Sie überlisten wissen müssen

### <a name="lists-is-available-in-every-team-and-channel"></a>Listen sind in allen Teams und Kanälen verfügbar

Listen ist für alle Teams-Benutzer vorinstalliert und steht direkt im Reiter Katalog jedes Teams und Kanals zur Verfügung. Das bedeutet, dass Benutzer nicht zum App Store von Teams wechseln müssen, um Sie zu installieren.

### <a name="lists-and-sharepoint"></a>Listen und SharePoint

Listendaten werden auf der SharePoint Online-Teamwebsite gespeichert. Weitere Informationen dazu, wie SharePoint Online mit Teams interagiert, finden Sie unter [Interaktion zwischen SharePoint Online und OneDrive for Business mit Teams](SharePoint-OneDrive-interact.md).

Die in SharePoint gesetzten Berechtigungen gelten für Listen, die in der App "Listen" erstellt wurden. Standardmäßig erben Listenberechtigungen von der Website, zu der Sie gehören. Diese Berechtigungen Regeln die Arten von Aktionen, die Benutzer ausführen können, beispielsweise, ob Sie Listen erstellen oder bearbeiten können. Weitere Informationen finden Sie unter [Berechtigungsstufen in SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) und [Benutzerberechtigungen und Berechtigungsstufen in SharePoint Server](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels).

In bestimmten Szenarien möchten Sie möglicherweise einschränken, welche Aktionen Benutzer in Listen ausführen können. Beispielsweise bearbeitet eine Person in einem Team eine Listenansicht, die Sie für alle Teammitglieder ändert, und Sie möchten nur dem Teambesitzer oder bestimmten Teammitgliedern gestatten, Listenansichten zu bearbeiten. Weitere Informationen finden Sie unter [Anpassen von Berechtigungen für eine SharePoint-Liste oder-Bibliothek](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013).

> [!NOTE]
> An diesem Punkt sind Besitzer-und Mitgliedsberechtigungen in einem Team in keiner Weise mit Berechtigungen auf der Teamwebsite verknüpft, die das Verhalten von Listen oder der App "Listen" Regeln. Basierend auf Kundenfeedback und-Nutzung wird dies jedoch für eine zukünftige Iteration des Produkts berücksichtigt.  

### <a name="limitations"></a>Einschränkungen

Mit Listen erhalten Benutzer eine Desktop-, Web-und mobil Funkfunktionalität. Es ist wichtig zu wissen, dass Benutzer keine neuen Listen erstellen oder vorhandene Listen mithilfe von Listen auf dem mobilen Teams-Client anheften können. Wenn Sie eine Liste auf dem Mobile Teams-Client anzeigen oder bearbeiten möchten, muss zuerst eine Liste erstellt oder mithilfe von Listen auf dem Desktop-oder Webclient von Teams hinzugefügt werden.

Gäste in [privaten Kanälen](private-channels.md) können keine Liste erstellen oder löschen oder eine neue Unterhaltung zu einem Listenelement beginnen. Sie können Listenelemente zu vorhandenen Listen hinzufügen und auf vorhandene Konversationen zu einem Listenelement Antworten. Beachten Sie, dass diese Einschränkungen nur für private Kanäle gelten.

### <a name="lists-and-the-sharepoint-app"></a>Listen und die SharePoint-App

Wenn Benutzer in Ihrer Organisation Listen mithilfe der SharePoint-App erstellt haben, werden diese Listen automatisch in Listen verschoben, ohne dass eine Aktion des Benutzers erforderlich ist. Verwenden Sie die Listen-APP, um die beste und reichste Liste der Integrationsfunktionen in Microsoft Teams zu erhalten, und fixieren Sie Ihre vorhandenen Listen.

## <a name="set-up-lists"></a>Einrichten von Listen

### <a name="enable-or-disable-lists-in-your-organization"></a>Aktivieren oder Deaktivieren von Listen in Ihrer Organisation

Listen ist standardmäßig für alle Teams-Benutzer in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](manage-apps.md) deaktivieren oder aktivieren.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Führen Sie einen der folgenden Schritte aus:

    - Wenn Sie Listen für Ihre Organisation deaktivieren möchten, suchen Sie nach der App "Listen", wählen Sie Sie aus, und klicken Sie dann auf **blockieren**.
    - Um Listen für Ihre Organisation zu aktivieren, suchen Sie nach der App "Listen", wählen Sie Sie aus, und klicken Sie dann auf **zulassen**.

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>Aktivieren oder Deaktivieren von Listen für bestimmte Benutzer in Ihrer Organisation

Wenn Sie bestimmten Benutzern in Ihrer Organisation die Verwendung von Listen erlauben oder blockieren möchten, stellen Sie sicher, dass Listen für Ihre Organisation auf der Seite " [apps verwalten](manage-apps.md) " aktiviert ist, und erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie diese Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

## <a name="search-the-audit-log-for-list-events"></a>Durchsuchen des Überwachungsprotokolls nach Listen Ereignissen

Listen werden für die Überwachung auf Unternehmensebene aktiviert, sodass Sie im Überwachungsprotokoll im Security & Compliance Center nach Listen und Listenelement Ereignissen suchen können. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

Eine Liste der Überwachungsereignisse, die für die Listen-app in Teams relevant sind, finden Sie unter [SharePoint-Listen Aktivitäten](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities).

Bevor Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst die Überwachung im [Security & Compliance Center](https://protection.office.com)aktivieren. Beachten Sie, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="power-automate-power-apps-and-graph-api"></a>Power Automation, Power apps und Graph-API

Listen unterstützt [Power Automation](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint) für Workflows und [Power apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) für Listenformulare. Entwickler können die [Listen-API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) verwenden, um Listendaten als Quelle über Microsoft Graph zu verbinden.

## <a name="give-feedback-or-report-an-issue"></a>Abgeben von Feedback oder melden eines Problems
  
Wenn Sie uns Feedback senden oder ein Problem melden möchten, klicken Sie unten auf der linken Navigationsleiste in Teams auf **Hilfe** , und wählen Sie dann **Problem melden**aus. Wählen Sie **Listen**aus, und geben Sie dann Ihr Feedback oder Details zu dem Problem ein, das Sie gerade erleben.
