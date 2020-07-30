---
title: Verwenden der APP-Übermittlungs-API für Teams zum übermitteln und genehmigen Ihrer benutzerdefinierten apps
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
description: Hier erfahren Sie, wie Sie benutzerdefinierte apps genehmigen, die mit der APP-Übermittlungs-API von Teams in Microsoft Teams gesendet werden.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4c3563dc028c8566d29906e4e42a2002a197e71d
ms.sourcegitcommit: 8812db47b45d171d47e71f87e84ab1828590392d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46523695"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Veröffentlichen einer benutzerdefinierten APP, die über die APP-Übermittlungs-API der Teams gesendet wird

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Übersicht

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams-App veröffentlichen, steht Sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten, eine benutzerdefinierte APP zu veröffentlichen, und die Art und Weise, wie Sie Sie verwenden, hängt davon ab, wie Sie die App abrufen. In **diesem Artikel wird erläutert, wie Sie eine benutzerdefinierte App genehmigen und veröffentlichen, die von einem Entwickler über die APP-Übermittlungs-API der Teams gesendet wird**. Die andere Methode, mit der eine benutzerdefinierte App hochgeladen wird, wird verwendet, wenn ein Entwickler Ihnen ein App-Paket im ZIP-Format sendet. Weitere Informationen zu dieser Methode finden Sie unter [Veröffentlichen einer benutzerdefinierten app durch Hochladen eines App-Pakets](manage-your-custom-apps.md).
 
Dieser Artikel enthält End-to-End-Anleitungen, wie Sie Ihre Teams-APP von der Entwicklung zur Bereitstellung in die Erkennung bringen. Sie erhalten einen Überblick über die verbundenen Erfahrungen, die von Teams im App-Lebenszyklus bereitgestellt werden, um zu rationalisieren, wie benutzerdefinierte apps im App Store Ihrer Organisation entwickelt, bereitgestellt und verwaltet werden.

Wir decken jeden Schritt des Lebenszyklus ab, einschließlich der Art, in der Entwickler benutzerdefinierte apps direkt an das Microsoft Teams Admin Center übermitteln können, um Sie zu überprüfen und zu genehmigen, festzulegen, wie Richtlinien für die Verwaltung von Apps für Benutzer in Ihrer Organisation und wie Ihre Benutzer Sie in Teams entdecken.

![Übersicht über Ihre APP von der Entwicklung bis zur Bereitstellung](media/custom-app-lifecycle.png)

Dieser Leitfaden konzentriert sich auf die Team Aspekte der APP und ist für Administratoren und IT-Experten vorgesehen. Informationen zum Entwickeln von Teams-apps finden Sie in der <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Entwicklerdokumentation für Teams</a>.

## <a name="develop"></a>Entwickeln

### <a name="create-the-app"></a>Erstellen der APP

Die Microsoft Teams-Entwicklerplattform macht es Entwicklern einfach, ihre eigenen apps und Dienste zu integrieren, um die Produktivität zu verbessern, Entscheidungen schneller zu treffen und Zusammenarbeit um vorhandene Inhalte und Workflows zu schaffen. Auf der Microsoft Teams-Plattform erstellte apps sind Brücken zwischen dem Team-Client und Ihren Diensten und Workflows und bringen diese direkt in den Kontext ihrer Zusammenarbeitsplattform. Weitere Informationen finden Sie in der <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Entwicklerdokumentation für Teams</a>.

### <a name="submit-the-app"></a>Übermitteln der APP

Wenn die APP für die Verwendung in der Produktion bereit ist, kann der Entwickler die App mithilfe der APP-Übermittlungs-API für Teams einreichen, die von der Diagramm-API, einer integrierten Entwicklungsumgebung (IDE) wie Visual Studio-Code oder einer Plattform wie Power apps und Power Virtual-Agents aufgerufen werden kann. Dadurch wird die APP auf der Seite " <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">apps verwalten</a> " im Microsoft Teams Admin Center zur Verfügung gestellt, wo Sie, der Administrator, Sie überprüfen und genehmigen kann. 

Die auf Microsoft Graph integrierte API für die APP-Übermittlung von Teams ermöglicht es Ihrer Organisation, sich auf der Plattform Ihrer Wahl zu entwickeln und den Prozess der Übermittlung von Genehmigungen für benutzerdefinierte apps in Teams zu automatisieren.

Im folgenden sehen Sie ein Beispiel dafür, wie dieser APP-Übermittlungs Schritt in Visual Studio-Code aussieht:

![Screenshot des Übermittelns einer APP in Visual Studio-Code](media/custom-app-lifecycle-submit-app.png)

Beachten Sie, dass dies die APP im App Store Ihrer Organisation noch nicht veröffentlicht. In diesem Schritt wird die APP an das Microsoft Teams Admin Center übermittelt, in dem Sie Sie für die Veröffentlichung im App Store Ihrer Organisation genehmigen können.

## <a name="validate"></a>Überprüfen

Auf der Seite " <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">apps verwalten</a> " im Microsoft Teams Admin Center (in der linken Navigationsleiste wechseln Sie zu **Teams apps**  >  **Verwalten von apps**) erhalten Sie einen Überblick über alle Teams-Apps für Ihre Organisation. Mit dem Widget **Ausstehende Genehmigung** oben auf der Seite können Sie wissen, wann eine benutzerdefinierte App zur Genehmigung übermittelt wird.

In der Tabelle zeigt eine neu übermittelte App automatisch einen **Veröffentlichungsstatus** von " **gesendet** " und " **Status** **blockiert**" an. Sie können die Spalte **Veröffentlichungsstatus** in absteigender Reihenfolge sortieren, um die app schnell zu finden.

![Screenshot der Seite "Apps verwalten" mit ausstehenden Anforderungen und App-Status ](media/custom-app-lifecycle-validate-app.png)

Klicken Sie auf den Namen der APP, um zur Seite App-Details zu wechseln. Auf der Registerkarte **Info** können Sie Details zur App anzeigen, einschließlich Beschreibung, Status, Absender und APP-ID.

![Screenshot der APP-Detailseite für eine übermittelte App](media/custom-app-lifecycle-app-details.png)

## <a name="publish"></a>Veröffentlichen

Wenn Sie bereit sind, die APP für die Benutzer zur Verfügung zu stellen, veröffentlichen Sie die app.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**.
2. Klicken Sie auf den Namen der APP, um zur Seite App-Details zu wechseln, und wählen Sie dann im Feld **Veröffentlichungsstatus** die Option **veröffentlichen**aus.

    Nachdem Sie die App veröffentlicht haben, wird der **Veröffentlichungsstatus** in **veröffentlicht** geändert, und der **Status** wird automatisch in **zulässig**geändert.

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

Um eine APP zu aktualisieren, sollten Entwickler weiterhin die Schritte im Abschnitt " [entwickeln](#develop) " ausführen.

Wenn der Entwickler ein Update an eine veröffentlichte benutzerdefinierte App sendet, erhalten Sie im Widget **Ausstehende Genehmigung** der Seite <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">apps verwalten</a> eine Benachrichtigung. In der Tabelle wird der **Veröffentlichungsstatus** der APP auf über **mittelt aktualisieren**gesetzt.

![Screenshot der Seite "Apps verwalten" mit ausstehenden Anforderungen und App-Status ](media/custom-app-lifecycle-update-submitted.png)

So überprüfen und veröffentlichen Sie ein App-Update:

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**.
2. Klicken Sie auf den Namen der APP, um zur Seite App-Details zu wechseln, und wählen Sie dann **Update verfügbar** aus, um die Details des Updates zu überprüfen.

    ![Screenshot der Seite "Apps verwalten" mit ausstehenden Anforderungen und App-Status ](media/custom-app-lifecycle-update-app.png)
3. Wenn Sie fertig sind, wählen Sie **veröffentlichen** aus, um das Update zu veröffentlichen. Dadurch wird die vorhandene App ersetzt, die Versionsnummer aktualisiert und der **Veröffentlichungsstatus** in **veröffentlicht**geändert. Alle Richtlinien für App-Berechtigungen und Richtlinien für die APP-Einrichtung bleiben für die aktualisierte APP erzwungen.

    Wenn Sie das Update ablehnen, bleibt die frühere Version der App veröffentlicht.

Beachten Sie Folgendes:

- Wenn eine APP genehmigt wird, kann jede Person eine Aktualisierung an die APP übermitteln. Dies bedeutet, dass andere Entwickler, einschließlich des Entwicklers, der die APP ursprünglich übermittelt hat, ein Update an die APP übermitteln können.
- Wenn ein Entwickler eine APP absendet und die Anforderung aussteht, kann nur derselbe Entwickler ein Update an die APP übermitteln. Andere Entwickler können ein Update erst senden, nachdem die APP genehmigt wurde.

### <a name="update-experience-for-users"></a>Update-Benutzeroberfläche

In den meisten Fällen wird die neue Version nach dem Veröffentlichen eines APP-Updates automatisch für die Benutzer angezeigt. Es gibt jedoch einige Updates für das <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams-Manifest</a> , für die eine Benutzerakzeptanz erforderlich ist:

* Ein bot wurde hinzugefügt oder entfernt
* Eine vorhandene bot-Eigenschaft "botId" wurde geändert
* Eine vorhandene bot-Eigenschaft "isNotificationOnly" wurde geändert
* Die "supportsFiles"-Eigenschaft des bot wurde geändert
* Eine Messaging Erweiterung wurde hinzugefügt oder entfernt
* Ein neuer Connector wurde hinzugefügt
* Eine neue statische Registerkarte wurde hinzugefügt
* Eine neue konfigurierbare Registerkarte wurde hinzugefügt
* Eigenschaften innerhalb von "webApplicationInfo" geändert

![Screenshot mit apps, für die eine neue Version verfügbar ist](media/manage-your-custom-apps-update1.png)

![Screenshot der Upgrade-Option für eine APP](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
