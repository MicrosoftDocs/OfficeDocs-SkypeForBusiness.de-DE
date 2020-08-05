---
title: Hochladen Ihrer benutzerdefinierten apps im Microsoft Teams Admin Center
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke, vaibhava
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
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Ihre benutzerdefinierten apps im App Store Ihrer Organisation im Microsoft Teams Admin Center hochladen.
ms.openlocfilehash: 68d7dbc16ca3aa6258fd5f976688240095226934
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552849"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Veröffentlichen einer benutzerdefinierten app durch Hochladen eines App-Pakets

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams-App veröffentlichen, steht Sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten, eine benutzerdefinierte APP zu veröffentlichen, und die Art und Weise, wie Sie Sie verwenden, hängt davon ab, wie Sie die App abrufen. In **diesem Artikel wird beschrieben, wie Sie eine benutzerdefinierte App veröffentlichen, indem Sie ein App-Paket (im ZIP-Format) hochladen, das von einem Entwickler gesendet wird**. Die andere Methode, die eine benutzerdefinierte APP genehmigt, wird verwendet, wenn ein Entwickler eine APP über die Team-App-Übermittlungs-API direkt an die Seite " <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">apps verwalten</a> " sendet. Weitere Informationen zu dieser Methode finden Sie unter <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Veröffentlichen einer benutzerdefinierten APP, die über die Team-App-Übermittlungs-API übermittelt</a>wurde.

Dieser Artikel enthält End-to-End-Anleitungen, wie Sie Ihre Teams-APP von der Entwicklung zur Bereitstellung in die Erkennung bringen. Dieser Leitfaden konzentriert sich auf die Team Aspekte der APP und ist für Administratoren und IT-Experten vorgesehen. Weitere Informationen zum Entwickeln von Teams-apps finden Sie in der <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Entwicklerdokumentation für Teams</a>.

![Übersicht über Ihre APP von der Entwicklung bis zur Bereitstellung](media/upload-custom-apps.png)

## <a name="develop"></a>Entwickeln

### <a name="create-your-app"></a>Erstellen Ihrer APP

Die Microsoft Teams-Entwicklerplattform macht es Entwicklern einfach, ihre eigenen apps und Dienste zu integrieren, um die Produktivität zu verbessern, Entscheidungen schneller zu treffen und Zusammenarbeit um vorhandene Inhalte und Workflows zu schaffen. Auf der Microsoft Teams-Plattform erstellte apps sind Brücken zwischen dem Team-Client und Ihren Diensten und Workflows und bringen diese direkt in den Kontext ihrer Zusammenarbeitsplattform. Weitere Informationen finden Sie in der <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Entwicklerdokumentation für Teams</a>.

## <a name="validate"></a>Überprüfen

### <a name="get-the-app-package"></a>Abrufen des App-Pakets

Wenn die APP für die Verwendung in der Produktion bereit ist, sollte der Entwickler ein App-Paket erstellen. Sie können dafür <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> verwenden. Sie senden Ihnen die Datei im ZIP-Format.

Microsoft verwendet <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">Diese Richtlinien</a> , um sicherzustellen, dass apps den Qualitäts-und Sicherheitsstandards des globalen Teams Apps Store entsprechen.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Zulassen, dass vertrauenswürdige Benutzer benutzerdefinierte apps hochladen

Um zu überprüfen, ob die app in Ihrem Produktions Mandanten ordnungsgemäß funktioniert, müssen Sie es selbst und/oder vertrauenswürdigen Benutzern ermöglichen, benutzerdefinierte apps im Produktions Mandanten hochzuladen. Dazu verwenden Sie <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">App-Setup Richtlinien</a> .

> [!NOTE]
> Wenn es Ihnen unangenehm ist, die APP für die Überprüfung an Ihren Produktions Mandanten zu überprüfen, auch für sich selbst oder für vertrauenswürdige Benutzer, können Sie diesen Schritt überspringen und die Schritte in den Abschnitten [hochladen](#upload) und [Einrichten und verwalten](#set-up-and-manage) ausführen, um die nicht validierte App im App Store Ihrer Organisation zu veröffentlichen. Dann beschränken Sie den Zugriff auf diese APP nur auf sich selbst und auf Benutzer, denen Sie vertrauen. Diese Benutzer können dann die APP aus dem App Store Ihrer Organisation abrufen, um eine Validierung durchzuführen. Verwenden Sie nach der Überprüfung der APP dieselben Berechtigungsrichtlinien, um Access zu öffnen und die APP für die Produktion zu verwenden.

Führen Sie die folgenden Schritte aus, um vertrauenswürdigen Benutzern das Hochladen benutzerdefinierter apps zu ermöglichen:

1. Aktivieren Sie die Einstellung **Interaktion mit benutzerdefinierten apps in** der organisationsweiten App zulassen. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**, und klicken Sie dann auf **organisationsweite App-Einstellungen**.
    2. Aktivieren Sie unter **benutzerdefinierte apps**die Option **Interaktion mit benutzerdefinierten apps zulassen**, und klicken Sie dann auf **Speichern**.
2. Deaktivieren Sie die Einstellung **benutzerdefinierte apps hochladen** in der globalen App-Setup Richtlinie. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**den  >  **Setup Richtlinien**für Teams-apps, und klicken Sie dann auf die **globale (org-Wide Standard)-** Richtlinie.
    2. Deaktivieren Sie **benutzerdefinierte apps hochladen**, und klicken Sie dann auf **Speichern**.
3. Erstellen Sie eine neue Richtlinie für die APP-Einrichtung, die das Hochladen benutzerdefinierter apps und die Zuweisung an Ihre vertrauenswürdigen Benutzer ermöglicht. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den Setup Richtlinien für **Teams-apps**  >  **Setup policies**, und klicken Sie dann auf **Hinzufügen**. Geben Sie der neuen Richtlinie einen Namen und eine Beschreibung, aktivieren Sie **benutzerdefinierte apps hochladen**, und klicken Sie dann auf **Speichern**.
    2. Wählen Sie die neu erstellte Richtlinie aus, und klicken Sie dann auf **Benutzer verwalten**. Suchen Sie nach einem Benutzer, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf über **nehmen**. Wiederholen Sie diesen Schritt, um die Richtlinie allen vertrauenswürdigen Benutzern zuzuweisen.

        ![Screenshot der Seite "App-Setup Richtlinie hinzufügen"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Diese Benutzer können jetzt das App-Manifest hochladen, um zu überprüfen, ob die APP im Produktions Mandanten ordnungsgemäß funktioniert.

## <a name="upload"></a>Hochladen

Wenn Sie die APP für Benutzer im App Store Ihrer Organisation verfügbar machen möchten, laden Sie die APP hoch. Sie können dies auf der Seite " <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">apps verwalten</a> " im Microsoft Teams Admin Center tun.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**.
2. Klicken Sie auf **hochladen**, klicken Sie auf **Datei auswählen**, und wählen Sie dann das App-Paket aus, das Sie vom Entwickler erhalten haben.

   ![Screenshot des Uploads einer APP im Admin Center](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Einrichten und verwalten

### <a name="control-access-to-the-app"></a>Steuern des Zugriffs auf die APP

Standardmäßig können alle Benutzer in Ihrer Organisation auf die APP im App Store Ihrer Organisation zugreifen. Um zu beschränken und zu steuern, wer die Berechtigung zum Verwenden der APP hat, können Sie eine APP-Berechtigungsrichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anheften und Installieren der APP für Benutzer

Standardmäßig müssen Benutzer die APP im App Store Ihrer Organisation finden, um Sie zu finden und zu durchsuchen. Um Benutzern das Abrufen der APP zu erleichtern, können Sie die app in Teams an die APP-Leiste anheften. Erstellen Sie dazu eine APP-Setup Richtlinie, und weisen Sie Sie Benutzern zu. Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Verwalten von App-Setup Richtlinien in Teams</a>.

## <a name="discover-and-adopt"></a>Entdecken und übernehmen

Benutzer, die über Berechtigungen für die APP verfügen, können Sie im App Store Ihrer Organisation finden. Wechseln Sie auf der Seite "Apps" zu **erstellt für *den Namen Ihrer Organisation* ** , um die benutzerdefinierten Apps ihrer Organisation zu finden.

![Screenshot der Seite "Apps" mit der veröffentlichten App ](media/custom-app-lifecycle-discovery.png)

Wenn Sie eine APP-Setup Richtlinie erstellt und zugewiesen haben, wird die app in Teams an die APP-Leiste angeheftet, damit die Benutzer, denen die Richtlinie zugewiesen wurde, einfach darauf zugreifen können.

## <a name="update"></a>Aktualisieren

Um eine APP zu aktualisieren, sollten Entwickler weiterhin die Schritte in den Abschnitten [entwickeln](#develop) und über [prüfen](#validate) ausführen.

Sie können die APP auf der Seite "Apps verwalten" im Microsoft Teams Admin Center aktualisieren. Gehen Sie dazu in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**. Klicken Sie auf den Namen der APP, und klicken Sie dann auf **Aktualisieren**. Dadurch wird die vorhandene App ersetzt, und für die aktualisierte APP bleiben alle Richtlinien für App-Berechtigungen und die APP-Setup Richtlinien erzwungen.

### <a name="end-user-update-experience"></a>Benutzer-Update-Benutzeroberfläche

In den meisten Fällen wird die neue Version nach Abschluss eines APP-Updates automatisch für Endbenutzer angezeigt. Es gibt jedoch einige Updates für das <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams-Manifest</a> , für die eine Benutzerakzeptanz erforderlich ist:

* Ein bot wurde hinzugefügt oder entfernt
* Eine vorhandene bot-Eigenschaft "botId" wurde geändert
* Eine vorhandene bot-Eigenschaft "isNotificationOnly" wurde geändert
* Die "supportsFiles"-Eigenschaft des bot wurde geändert
* Eine Messaging Erweiterung wurde hinzugefügt oder entfernt
* Ein neuer Connector wurde hinzugefügt
* Eine neue statische Registerkarte wurde hinzugefügt
* Eine neue konfigurierbare Registerkarte wurde hinzugefügt
* Eigenschaften innerhalb von "webApplicationInfo" geändert

![Screenshot der Liste "Apps" mit apps, für die eine neue Version verfügbar ist](media/manage-your-custom-apps-update1.png)

![Screenshot der Upgrade-Option für eine APP](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Verwandte Themen

- [Veröffentlichen einer benutzerdefinierten APP, die über die APP-Übermittlungs-API der Teams gesendet wird](submit-approve-custom-apps.md)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
