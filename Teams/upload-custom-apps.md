---
title: Hochladen Ihrer benutzerdefinierten Apps im Microsoft Teams Admin Center
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre benutzerdefinierten Apps in den App Store Ihrer Organisation im Microsoft Teams Admin Center hochladen.
ms.openlocfilehash: d95635546da7337c9c18ee0fddf7b40a5bf061c3
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397116"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Eine benutzerdefinierte App veröffentlichen, indem Sie ein App-Paket hochladen

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams-App veröffentlichen, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App, und die Art, die Sie verwenden, hängt davon ab, wie Sie die App abrufen. **Dieser Artikel befasst sich mit dem Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets (im .zip-Format), das Ihnen ein Entwickler sendet**. Die andere Methode, die Genehmigung einer benutzerdefinierten App, wird verwendet, wenn ein Entwickler eine App über die Teams-App-Übermittlungs-API direkt an die Seite [Apps verwalten](manage-apps.md) sendet. Weitere Informationen zu dieser Methode finden Sie unter [Veröffentlichen einer benutzerdefinierten App, die über die Teams App Submission API eingereicht wurde](submit-approve-custom-apps.md).

Dieser Artikel bietet eine durchgängige Anleitung, wie Sie Ihre Teams-Anwendung von der Entwicklung über die Bereitstellung bis zur Ermittlung bringen. Dieser Leitfaden konzentriert sich auf die Teams-Aspekte der App und richtet sich an Administratoren und IT-Experten. Weitere Informationen zum Entwickeln von Teams-Apps finden Sie in der [Teams-Entwicklerdokumentation](/microsoftteams/platform/).

![Übersicht über Ihre App von der Entwicklung bis zur Bereitstellung.](media/upload-custom-apps.png)

## <a name="create-your-app"></a>Erstellen der Anwendung

Die Microsoft Teams-Entwicklerplattform macht es Entwicklern leicht, Ihre eigenen Apps und Dienste zu integrieren, um die Produktivität zu verbessern, Entscheidungen schneller zu treffen und die Zusammenarbeit mit bestehenden Inhalten und Workflows zu fördern. Auf der Teams-Plattform erstellte Apps sind Brücken zwischen dem Teams-Client und Ihren Diensten und Workflows, die sie direkt in den Kontext Ihrer Plattform für die Zusammenarbeit bringen. Weitere Informationen finden Sie in der [Teams-Entwicklerdokumentation](/microsoftteams/platform/).

## <a name="validate"></a>Validieren

### <a name="get-the-app-package"></a>Abrufen des App-Pakets

Wenn die App für die Verwendung in der Produktion bereit ist, sollte der Entwickler ein App-Paket erstellen. Sie können [App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview) verwenden. Sie senden Ihnen die Datei im .zip Format.

Alle Apps im Teams-Store durchlaufen eine obligatorische [App-Validierung](overview-of-app-validation.md), um den Qualitäts- und Sicherheitsstandards des globalen Teams-App-Stores zu entsprechen. Darüber hinaus ermutigt Microsoft App-Entwickler nachdrücklich, an einem optionalen [App-Compliance-Programm](overview-of-app-certification.md) teilzunehmen, das verbesserte Compliance-, Sicherheits- und Datenschutzkontrollen vorsieht. Weitere Informationen finden Sie unter [Teams-App-Validierungsrichtlinien](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines).

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Zulassen, dass vertrauenswürdige Benutzer benutzerdefinierte Apps hochladen

Um zu überprüfen, ob die App in Ihrem Produktionsmandanten ordnungsgemäß funktioniert, müssen Sie sich selbst und/oder vertrauenswürdigen Benutzern erlauben, benutzerdefinierte Apps in den Produktionsmandanten hochzuladen. Dazu verwenden Sie [App-Setuprichtlinien](teams-app-setup-policies.md).

> [!NOTE]
> Wenn Sie die App zur Überprüfung in Ihren Produktionsmandanten hochladen möchten, selbst für sich selbst oder vertrauenswürdige Benutzer, können Sie diesen Schritt überspringen und die Schritte in den Abschnitten [Hochladen](#upload) und [Einrichten und Verwalten](#set-up-and-manage) ausführen, um die nicht überprüfte App im App Store Ihrer Organisation zu veröffentlichen. Beschränken Sie dann den Zugriff auf diese App auf sich selbst und die Benutzer, denen Sie vertrauen. Diese Benutzer können dann die App aus dem App Store Ihrer Organisation abrufen, um eine Überprüfung durchzuführen. Nachdem die App überprüft wurde, verwenden Sie die gleichen Berechtigungsrichtlinien, um den Zugriff zu öffnen und die App für die Produktionsverwendung einzusetzen.

Führen Sie die folgenden Schritte aus, um vertrauenswürdigen Benutzern das Hochladen benutzerdefinierter Apps zu ermöglichen:

1. Aktivieren Sie die organisationsweit App-Einstellung **Zulassen der Interaktion mit benutzerdefinierten Apps**. Gehen Sie dazu so vor:

    1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Teams-Apps** > **verwalten**", und wählen Sie dann **organisationsweite App-Einstellungen** aus.

    1. Aktivieren Sie unter **"Benutzerdefinierte Apps**" die Option **"Interaktion mit benutzerdefinierten Apps zulassen**", und wählen Sie dann **"Speichern"** aus.

1. Deaktivieren Sie die Einstellung **Benutzerdefinierte Apps hochladen** in der globalen App-Setuprichtlinie. Gehen Sie dazu so vor:

    1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu den **Setuprichtlinien** für **Teams-Apps** > , und wählen Sie dann die **globale Richtlinie (organisationsweite Standardrichtlinie)** aus.

    1. Deaktivieren Sie **"Benutzerdefinierte Apps hochladen**", und wählen Sie " **Speichern"** aus.

1. Erstellen Sie eine neue App-Setuprichtlinie, die das Hochladen von benutzerdefinierten Apps erlaubt, und weisen Sie diese Ihren vertrauenswürdigen Benutzern zu. Gehen Sie dazu so vor:

    1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu den **Setuprichtlinien** für **Teams-Apps** > , und wählen Sie dann "**Hinzufügen"** aus. Geben Sie der neuen Richtlinie einen Namen und eine Beschreibung, aktivieren **Sie "Benutzerdefinierte Apps hochladen**", und wählen Sie dann **"Speichern"** aus.

    1. Wählen Sie die neue Richtlinie aus, die Sie erstellt haben, und wählen Sie dann **"Benutzer verwalten"** aus. Suchen Sie nach einem Benutzer, wählen Sie **"Hinzufügen"** und dann " **Übernehmen"** aus. Wiederholen Sie diesen Schritt, um die Richtlinie allen vertrauenswürdigen Benutzern zuzuweisen.

       :::image type="content" source="media/manage-your-lob-apps-new-app-setup-policy.png" alt-text="Screenshot der Seite &quot;App-Setuprichtlinie hinzufügen&quot;.":::

Diese Benutzer können nun das App-Manifest hochladen, um zu überprüfen, ob die App im Produktionsmandanten ordnungsgemäß funktioniert.

## <a name="upload"></a>Hochladen

Um die App für Benutzer im App Store Ihrer Organisation verfügbar zu machen, laden Sie die App hoch.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Wählen Sie **"Hochladen**", " **Hochladen**" und dann das App-Paket aus, das Sie vom Entwickler erhalten haben, und wählen Sie **"Öffnen**" aus.

   ![Screenshot des Benutzerdefinierten App-Uploads im Admin Center.](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>Einrichten und Verwalten

### <a name="control-access-to-the-app"></a>Steuern des Zugriffs auf die App

Standardmäßig können alle Benutzer in Ihrer Organisation auf die App im App Store Ihrer Organisation zugreifen. Um einzuschränken und zu steuern, wer über die Berechtigung zur Verwendung der App verfügt, können Sie eine App-Berechtigungsrichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anheften und Installieren der App zum Ermitteln für Benutzer

Standardmäßig müssen Benutzer, um die App zu finden, den App-Store Ihres Unternehmens aufrufen und dort nach ihr suchen oder suchen lassen. Um Benutzern den Zugriff auf die App zu erleichtern, können Sie die App an die App-Leiste in Teams anheften. Um die App anzuheften, erstellen Sie eine App-Setuprichtlinie, und weisen Sie sie Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Durchsuchen der Audit-Protokolle nach App-Ereignissen in Teams

Sie können das Überwachungsprotokoll durchsuchen, um die Teams-Apps-Aktivität in Ihrer Organisation anzuzeigen. Weitere Informationen zur Überwachung von Teams-Aktivitäten finden Sie unter [Überwachungsprotokoll nach Ereignissen in Teams durchsuchen](audit-app-management-activities.md).

Damit Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst im [Security & Compliance Center](https://sip.protection.office.com/homepage) die Überwachung aktivieren. Weitere Informationen finden Sie unter [Die Überwachungsprotokollsuche ein- oder ausschalten](/microsoft-365/compliance/turn-audit-log-search-on-or-off). Denken Sie daran, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="discover-and-adopt"></a>Entdecken und übernehmen

Endbenutzer, die über Berechtigungen für die App verfügen, können sie im App Store Ihrer Organisation finden. Wechseln Sie auf der Seite Apps zu **Erstellt für *Ihren Organisationsnamen***, um die benutzerdefinierten Apps Ihrer Organisation zu finden.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Screenshot des Teams Store mit einer für die Organisation veröffentlichten benutzerdefinierten App" lightbox="media/custom-app-lifecycle-discovery.png":::

Wenn Sie eine App-Setuprichtlinie erstellt und zugewiesen haben, wird die App an die App-Leiste in Teams angeheftet, damit die Benutzer, denen die Richtlinie zugewiesen wurde, leicht darauf zugreifen können.

## <a name="update-a-custom-app"></a>Aktualisieren einer benutzerdefinierten App

Zum Aktualisieren einer App führen Entwickler die Schritte in den Abschnitten [App erstellen](#create-your-app) und [Überprüfen](#validate) aus.

Sie können die App auf der Seite „Apps verwalten“ im Microsoft Teams Admin Center aktualisieren. Um die App zu aktualisieren, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu "Apps verwalten" von **Teams-Apps** > . wählen Sie den App-Namen und dann **"Aktualisieren"** aus. Durch das Aktualisieren der App wird die vorhandene App ersetzt, und alle App-Berechtigungsrichtlinien und App-Setuprichtlinien bleiben für die aktualisierte App erzwungen.

### <a name="end-user-update-experience"></a>Benutzeroberfläche für Endbenutzerupdates

In den meisten Fällen wird die neue Version nach Abschluss einer App-Aktualisierung automatisch für Endbenutzer angezeigt. Weitere Informationen finden Sie unter [Benutzeroberfläche für Endbenutzerupdates](apps-update-experience.md).

## <a name="remove-a-custom-app-from-your-organizations-store"></a>Entfernen einer benutzerdefinierten App aus dem Store Ihrer Organisation

Gehen Sie folgendermaßen vor, um eine App zu entfernen:

1. Melden Sie sich beim Microsoft Teams Admin Center an.
1. Zugreifen auf die Seite **Teams-Apps** > **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Klicken Sie auf den Namen der Anwendung, um die Detailseite der Anwendung zu öffnen.
1. Wählen Sie neben dem App-Banner **"Aktionen löschen"** >  aus.
1. Wählen Sie im Dialogfeld **Löschen** aus.

## <a name="related-articles"></a>Verwandte Artikel

* [Eine benutzerdefinierte App veröffentlichen, die über die Teams-App Submission API eingereicht wurde](submit-approve-custom-apps.md)
* [Verwalten Sie Ihre Apps im Microsoft Teams Admin Center](manage-apps.md)
* [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
* [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
* [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
