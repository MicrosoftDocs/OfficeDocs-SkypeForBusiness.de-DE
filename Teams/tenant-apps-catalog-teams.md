---
title: Veröffentlichen von apps im Microsoft Teams-Mandanten-apps-Katalog
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Leitfaden zum Veröffentlichen von apps im Microsoft Teams-Mandanten-apps-Katalog.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 547461cee1b172fccf9fe021347cff36ba8a9d79
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708231"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a>Veröffentlichen von apps im Microsoft Teams-Mandanten-apps-Katalog
=======================================================

Sie können den Microsoft Teams-Mandanten-apps-Katalog verwenden, um Branchenanwendungen zu testen und an Ihre Organisation zu verteilen.

Der Katalog "Teams-Mandanten-Apps" ermöglicht es Ihnen, branchenspezifische Anwendungen zu verteilen, die speziell für Ihre Organisation entwickelt wurden und auf die Sie sich verlassen, um wichtige Geschäftsfunktionen abzuschließen.

Wenn Sie Apps für Ihre Organisation veröffentlichen möchten, müssen Sie sich mit einem Konto mit den Rollen des globalen Administrators oder des Teams für Dienstadministratoren bei Ihrem Team-Client anmelden, und folgen Sie dann den nachstehenden Anweisungen.

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a>Veröffentlichen einer APP im Mandanten-apps-Katalog des Teams-Clients

> [!NOTE]
> Sie müssen beim Microsoft Teams-Client mit einem Konto angemeldet sein, das über die Rolle "globaler Administrator" oder "Team Dienstadministrator" verfügt, um Apps für Ihre Organisation zu veröffentlichen. Weitere Informationen finden Sie [unter Verwenden von Administratorrollen zum Verwalten von Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).

### <a name="get-a-teams-app-package"></a>Abrufen eines Teams-App-Pakets

Ein Team-App-Paket wird mithilfe von [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)erstellt. Nachdem Sie das App-Paket installiert haben, können Sie es dem Enterprise-App-Katalog hinzufügen. Während alle Benutzer im Mandanten den App-Katalog anzeigen können, haben nur globale Administratoren und Teams-Dienstadministratoren die Möglichkeit, diese zu veröffentlichen und zu verwalten.

### <a name="go-to-the-tenant-apps-catalog"></a>Wechseln zum Mandanten-apps-Katalog

Starten Sie den Microsoft Teams-Client, und melden Sie sich mit Ihren Dienstadministrator Anmeldeinformationen für Global oder Teams an. Wählen Sie auf der linken Seite der APP **apps** aus, und wählen Sie dann den neuen Abschnitt aus, der für Ihre spezifische Organisation benannt ist (in diesem Beispiel Contoso). Benutzer in Ihrer Organisation können apps im Katalog anzeigen und für Teams installieren, deren Mitglied Sie sind.

![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>Hinzufügen einer App zum Mandanten-apps-Katalog

1. Wählen Sie auf der Seite **apps** die Option **Hochladen eines benutzerdefinierten App** > -**Uploads für Contoso**aus.

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image02.png)

    (Sie können auch **für mich oder meine Teams hochladen**wählen, die als *Sideloading*bezeichnet wird. Sideloading stellt die app nur für Ihre Teams oder für die von Ihnen ausgewählten Teams zur Verfügung.)

2. Navigieren Sie zum App-Paket, und wählen Sie es aus, und klicken Sie dann auf **Öffnen**.

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image03.png)

Wenn Sie zu Ihrem Mandanten-apps-Katalog zurückkehren, wird die neue Enterprise-app vorhanden sein. Beachten Sie, dass nur Sie und Mitglieder Ihrer Organisation auf diesen app-Katalog zugreifen können.

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>Aktualisieren einer APP im Mandanten-apps-Katalog

1. Wählen Sie in Ihrem Mandanten-apps-Katalog "**...**" aus. Klicken Sie oben rechts in der APP, die Sie aktualisieren möchten.

2. Navigieren Sie zum aktualisierten App-Paket, und wählen Sie es aus, und klicken Sie dann auf **Öffnen**.

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image04.png)

Die APP wird auf Version 2,0 überarbeitet. In diesem Menü können Sie auch die APP für Ihr gesamtes Unternehmen löschen.

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>Verwenden des Office 365-Administrator Portals zum Verwalten des Mandanten-apps-Katalogs

Wenn Sie apps haben, die Fehlerbehebungen benötigen, können Sie apps vorübergehend über die Microsoft 365 Admin Center-#a0 **Teams Admin Center** > **Teams apps** > -**Berechtigungsrichtlinien** > <Richtliniennamen deaktivieren, beispielsweise "Global (org-Wide Standard)" #a3 **Mandanten-apps** > bestimmte apps blockieren und alle anderen Personen und Ihre APP zur Liste hinzufügen.

![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image05.png)

Durch das Deaktivieren einer APP wird verhindert, dass Benutzer mit der APP interagieren, ohne die APP vollständig zu löschen. Diese Steuerelemente bieten Ihnen zusätzliche Flexibilität und Kontrolle beim Verwalten von apps in Ihrem Unternehmen.
