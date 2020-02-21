---
title: Veröffentlichen von apps im Microsoft Teams-Mandanten-App-Katalog
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Leitfaden zum Veröffentlichen von apps im Microsoft Teams-App-Katalog für Mandanten.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161614"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a>Veröffentlichen von apps im Microsoft Teams-Mandanten-App-Katalog
=======================================================

Sie können den Microsoft Teams-Mandanten-App-Katalog verwenden, um Branchenanwendungen zu testen und an Ihre Organisation zu verteilen.

Mit dem App-Katalog für Team Mandanten können Sie branchenspezifische Anwendungen verteilen, die speziell für Ihre Organisation entwickelt wurden und auf die Sie sich verlassen, um wichtige Geschäftsfunktionen abzuschließen.

Wenn Sie Apps für Ihre Organisation veröffentlichen möchten, müssen Sie sich mit einem Konto mit der Rolle globaler Administrator oder Team Dienstadministrator beim Team-Client anmelden und dann die folgenden Schritte ausführen.

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a>Veröffentlichen einer APP im Mandanten-App-Katalog vom Team-Client

> [!NOTE]
> In diesen Schritten wird beschrieben, wie Sie eine App mithilfe des Teams-Clients veröffentlichen. Sie können eine APP auch auf der Seite " **apps verwalten** " im Microsoft Teams Admin Center veröffentlichen. Weitere Informationen finden Sie unter [Verwalten von apps in Teams](manage-apps.md).

### <a name="get-a-teams-app-package"></a>Abrufen eines Teams-App-Pakets

Ein Team-App-Paket wird mithilfe von [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)erstellt. Nachdem Sie das App-Paket installiert haben, können Sie es dem Mandanten-App-Katalog hinzufügen. Während alle Benutzer in Ihrer Organisation den App-Katalog anzeigen können, haben nur globale Administratoren und Teams-Dienstadministratoren die Möglichkeit, diese zu veröffentlichen und zu verwalten.

### <a name="go-to-the-tenant-app-catalog"></a>Wechseln zum Mandanten-App-Katalog

Starten Sie Teams, und melden Sie sich mit ihren globalen oder Teams-Dienstadministrator Anmeldeinformationen an. Wählen Sie auf der linken Seite der APP **apps** aus, und wählen Sie dann den neuen Abschnitt aus, der für Ihre spezifische Organisation benannt ist (in diesem Beispiel Contoso). Benutzer in Ihrer Organisation können apps im Katalog anzeigen und für Teams installieren, deren Mitglied Sie sind.

![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a>Hinzufügen einer App zum Mandanten-App-Katalog

1. Wählen Sie auf der Seite **apps** die Option **Hochladen eines benutzerdefinierten App** > -**Uploads für Contoso**aus.

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image02.png)

    (Sie können auch **für mich oder meine Teams hochladen**wählen, die als *Sideloading*bezeichnet wird. Sideloading stellt die app nur für Ihre Teams oder für die von Ihnen ausgewählten Teams zur Verfügung.)

2. Navigieren Sie zum App-Paket, und wählen Sie es aus, und klicken Sie dann auf **Öffnen**.

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image03.png)

Wenn Sie zu Ihrem Mandanten-App-Katalog zurückkehren, wird die neue Enterprise-app vorhanden sein. Beachten Sie, dass nur Sie und Mitglieder Ihrer Organisation auf diesen app-Katalog zugreifen können.

### <a name="update-an-app-in-the-tenant-app-catalog"></a>Aktualisieren einer APP im Mandanten-App-Katalog

1. Wählen Sie in Ihrem Mandanten-App-Katalog "**...**" aus. Klicken Sie oben rechts in der APP, die Sie aktualisieren möchten.

2. Navigieren Sie zum aktualisierten App-Paket, und wählen Sie es aus, und klicken Sie dann auf **Öffnen**.

    ![Screenshot des Teams-APP-Speichers mit dem App-Katalog](media/private-app-store-teams-image04.png)

Die APP wird auf Version 2,0 überarbeitet. In diesem Menü können Sie auch die APP für Ihr gesamtes Unternehmen löschen.

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a>Verwenden des Microsoft Teams admin Centers zum Verwalten des Mandanten-App-Katalogs

Wenn Sie apps haben, die Fehlerbehebungen benötigen, können Sie Apps für Benutzer vorübergehend in einer APP-Berechtigungsrichtlinie deaktivieren.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams-apps** > -**Berechtigungsrichtlinien**.
2. Wählen Sie die APP-Berechtigungsrichtlinie aus, die Sie bearbeiten möchten, und klicken Sie dann auf **Bearbeiten**.
3. Wählen Sie unter **Mandanten-apps**die Option **bestimmte apps blockieren und alle anderen zulassen**aus, und fügen Sie dann die apps hinzu, die Sie blockieren möchten.

Durch das Deaktivieren einer APP wird verhindert, dass Benutzer mit der APP interagieren, ohne die APP vollständig zu löschen. Diese Steuerelemente bieten zusätzliche Flexibilität und Steuern beim Verwalten von apps in Ihrer Organisation.

Weitere Informationen finden Sie unter [Verwalten von App-Berechtigungsrichtlinien in Teams](teams-app-permission-policies.md).