---
title: Adobe Acrobat als PDF-Standardanzeige in Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Erfahren Sie, wie Sie Adobe Acrobat als Standard-PDF-Viewer festlegen, um PDF-Dateien in Microsoft Teams anzuzeigen und zu bearbeiten.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 913081ee0efc87d66ed304f3de5e9f00b69232fa
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156743"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>Adobe Acrobat als PDF-Standardanzeige in Microsoft Teams

> [!NOTE]
> Adobe Acrobat als PDF-Standardoberfläche in Microsoft Teams ist derzeit nur in der öffentlichen Vorschau verfügbar. Um diese Funktion verwenden zu können, müssen Administratoren die [öffentliche Vorschau](public-preview-doc-updates.md#enable-public-preview) für ihren Mandanten aktivieren und sicherstellen, dass die Endbenutzer die Microsoft Teams-Clientversion in die öffentliche Vorschau ändern.

Als Administrator können Sie Adobe Acrobat als Standard-App zum Anzeigen und Bearbeiten von PDF-Dateien in Microsoft Teams festlegen. Ihre Endbenutzer können PDF-Dateien ohne Adobe Acrobat-Abonnement oder Adobe-ID anzeigen, durchsuchen, kommentieren und kommentieren.

## <a name="set-up-adobe-acrobat-app"></a>Einrichten der Adobe Acrobat-App

Stellen Sie vor dem Einrichten der App sicher, dass Sie die Verwendung von Apps in Ihrem Mandanten zulassen, dass Sie die Adobe Acrobat-App ausdrücklich zugelassen haben und die App-Berechtigungsrichtlinien dies zulassen. Führen Sie die folgenden Schritte aus, um Adobe Acrobat als Standard-App für PDF-Dateien einzurichten:

1. Melden Sie sich beim Teams Admin Center an, und wechseln Sie zu "**[Apps verwalten"](https://admin.teams.microsoft.com/policies/manage-apps)** der **Teams-App** > .

1. Suchen Sie nach der Adobe Acrobat-App, und wählen Sie sie aus.

1. Wählen Sie auf der Registerkarte **"Berechtigungen** " die **Option "Berechtigung überprüfen**" aus.

   :::image type="content" source="media/permission-policy.png" alt-text="Screenshot der App-Berechtigung im Teams Admin Center." lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. Wählen Sie **"Annehmen"** aus.

## <a name="install-adobe-acrobat-app-for-all-users"></a>Installieren der Adobe Acrobat-App für alle Benutzer

Führen Sie die folgenden Schritte aus, um die Adobe Acrobat-App allen Benutzern zuzuweisen und verfügbar zu machen:

1. Wechseln Sie im Teams Admin Center zu den [**Setuprichtlinien**](https://admin.teams.microsoft.com/policies/app-setup) für **Teams-Apps** > .

1. Wählen Sie auf der Registerkarte " **Richtlinien verwalten** " **die Option "Global" (organisationsweite Standardeinstellung)** und dann " **Bearbeiten"** aus.

   :::image type="content" source="media/setup-policies.png" alt-text="Screenshot der Setuprichtlinien für die Adobe Acrobat-App im Teams Admin Center.":::

1. Wählen Sie unter "Installierte Apps" die Option **"Apps hinzufügen"** aus.

1. Suchen Sie **Adobe Acrobat**, wählen Sie neben dem App-Namen " **Hinzufügen"** und dann " **Hinzufügen"** aus.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Screenshot, der zeigt, wie Die Adobe Acrobat-App für alle Benutzer hinzugefügt wird." lightbox="media/add-adobe-acrobat-app.png":::

1. Klicken Sie auf **Speichern**.

Nachdem Sie "Speichern" ausgewählt haben, verwendet Teams die Adobe Acrobat-App als Standarddateihandler für PDF-Dateien.

Wenn Sie die Adobe Acrobat-App selektiv für einige Personen oder für eine Gruppe zulassen möchten, können Sie eine [benutzerdefinierte App-Berechtigungsrichtlinie](teams-app-permission-policies.md) zuweisen.

Kennen Sie die folgenden Informationen zu dieser Funktionalität:

* Nachdem die Richtlinie eingerichtet wurde, dauert es in der Regel [einige Stunden](teams-app-setup-policies.md) , bis die App für Benutzer verfügbar ist.
* Nachdem die Richtlinie eingerichtet wurde, ist die installierte App nach einigen Stunden für Benutzer verfügbar.
* Das Anzeigen von PDF-Dateien, die in Kanälen als Registerkarte angeheftet sind, und das Anzeigen von PDF-Dateien in der Aufgaben-App wird weiterhin von der nativen Teams-Umgebung unterstützt.
* Adobe Acrobat als PDF-Standardanzeige in Teams funktioniert nur auf Desktop- und Webclients. Sie wird auf dem mobilen Client nicht unterstützt.
* Benutzer benötigen einen Adobe Acrobat-Plan, um die Premium-Tools wie "PDF exportieren", "Seiten organisieren", "Dateien kombinieren", "PDF komprimieren" und "PDF schützen" verwenden zu können.
* Um die App zu deinstallieren, können Endbenutzer die App aus dem Teams-Client entfernen. Admin können die Adobe Acrobat-App mithilfe der Setuprichtlinie entfernen.
* Wenn Sie die Adobe Acrobat-App blockieren, entfernen Sie sie aus der Setuprichtlinie. Dadurch wird sichergestellt, dass die Endbenutzererfahrung wieder auf die Verwendung des nativen PDF-Datei-Viewers zurückgesetzt wird.
* Wenn beim Anmelden bei der Adobe Acrobat-App Probleme auftreten, melden Sie sich über den Teams-Desktopclient im Browser an.
