---
title: Adobe Acrobat als ein Standard-PDF-Viewer in Teams
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
description: Erfahren Sie, wie Sie Adobe Acrobat als einen Standard-PDF-Viewer festlegen, um PDF-Dateien in Microsoft Teams anzuzeigen und zu bearbeiten.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 88babd01496738825cbe655215532e311a32f541
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270880"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>Adobe Acrobat als ein Standard-PDF-Viewer in Microsoft Teams

> [!NOTE]
> Adobe Acrobat als eine Standard-PDF-Erfahrung in Microsoft Teams ist derzeit nur in der Public Preview verfügbar. Um diese Funktion nutzen zu können, müssen Administratoren für ihren Mandanten [Public Preview aktivieren](public-preview-doc-updates.md#enable-public-preview) und sicherstellen, dass die Endbenutzer die Teams-Clientversion in die Public Preview ändern.

Als Administrator können Sie Adobe Acrobat als die Standard-App festlegen, um PDF-Dateien in Microsoft Teams anzuzeigen und zu bearbeiten. Ihre Endbenutzer können PDF-Dateien ohne ein Adobe Acrobat-Abonnement oder eine Adobe-ID anzeigen, durchsuchen, kommentieren und mit Anmerkungen versehen.

Führen Sie die folgenden Schritte als Voraussetzungen aus, um die Adobe Acrobat-App als Standardhandler für PDF-Dateien in Ihrem Mandanten zu konfigurieren:

* [Lassen Sie die Adobe Acrobat-App zu](#allow-adobe-acrobat-app-in-your-tenant).
* [Installieren Sie die Adobe Acrobat-App](#install-adobe-acrobat-app-for-all-users).

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>Zulassen der Adobe Acrobat-App in Ihrem Mandanten

Stellen Sie vor dem Einrichten der App sicher, dass Sie die Verwendung von Apps in Ihrem Mandanten zulassen, dass Sie die Adobe Acrobat-App ausdrücklich zugelassen haben und dass die App-Berechtigungsrichtlinien sie zulassen. Führen Sie die folgenden Schritte aus, um Adobe Acrobat als die Standard-App für PDF-Dateien einzurichten:

1. Melden Sie sich beim Teams Admin Center an, und wechseln Sie zu **Teams-App** > **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Suchen Sie nach der Adobe Acrobat-App, und wählen Sie diese aus.

1. Wählen Sie auf der Registerkarte **Berechtigungen** die Option **Berechtigung prüfen** aus.

   :::image type="content" source="media/permission-policy.png" alt-text="Screenshot der App-Berechtigung im Teams Admin Center." lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. Wählen Sie **Annehmen** aus.

## <a name="install-adobe-acrobat-app-for-all-users"></a>Installieren der Adobe Acrobat-App für alle Benutzer

Führen Sie die folgenden Schritte aus, um die Adobe Acrobat-App für alle Benutzer zuzuweisen und verfügbar zu machen:

1. Wechseln Sie im Teams Admin Center zu **Teams-App** > [**Setuprichtlinien**](https://admin.teams.microsoft.com/policies/app-setup).

1. Wählen Sie unter der Registerkarte **Richtlinien verwalten** die Option **Global (organisationsweiter Standard)** und dann **Bearbeiten** aus.

   :::image type="content" source="media/setup-policies.png" alt-text="Screenshot der Setuprichtlinien für die Adobe Acrobat-App im Teams Admin Center.":::

1. Wählen Sie unter „Installierte Apps“ die Option **Apps hinzufügen** aus.

1. Suchen Sie **Adobe Acrobat**, wählen Sie **Hinzufügen** neben dem App-Namen und dann **Hinzufügen** aus.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Screenshot, der zeigt, wie die Adobe Acrobat-App für alle Benutzer hinzugefügt wird." lightbox="media/add-adobe-acrobat-app.png":::

1. Klicken Sie auf **Speichern**.

Nachdem Sie „Speichern“ ausgewählt haben, verwendet Teams die Adobe Acrobat-App als Standarddateihandler für PDF-Dateien.

Wenn Sie die Adobe Acrobat-App selektiv für einige Personen oder für eine Gruppe zulassen möchten, können Sie eine [benutzerdefinierte App-Berechtigungsrichtlinie](teams-app-permission-policies.md) zuweisen.

Sie sollten die folgenden Informationen über diese Funktion kennen:

* Nachdem die Richtlinie eingerichtet wurde, dauert es in der Regel [einige Stunden](teams-app-setup-policies.md), bis die App für Benutzer verfügbar ist.
* Das Anzeigen von PDF-Dateien, die in Kanälen als eine Registerkarte angeheftet sind, und das Anzeigen von PDF-Dateien in der App „Aufgaben“ wird weiterhin von der nativen Teams-Erfahrung unterstützt.
* Adobe Acrobat als ein Standard-PDF-Viewer in Teams funktioniert nur auf Desktop- und Webclients. Es wird auf dem mobilen Client nicht unterstützt.
* Benutzer benötigen einen Adobe Acrobat-Plan, um die Premium-Tools wie „PDF exportieren“, „Seiten organisieren“, „Dateien kombinieren“, „PDF komprimieren“ und „PDF schützen“ zu verwenden.
* Um die App zu deinstallieren, können Endbenutzer die App aus dem Teams-Client entfernen. Der Administrator kann die Adobe Acrobat-App mithilfe der Setuprichtlinie entfernen.
* Wenn Sie die Adobe Acrobat-App blockieren, entfernen Sie diese aus der Setuprichtlinie. Dadurch wird sichergestellt, dass das Endbenutzererlebnis auf die Verwendung des nativen PDF-Datei-Viewers zurückgesetzt wird.
* Wenn beim Anmelden bei der Adobe Acrobat-App aus dem Teams-Desktopclient Probleme auftreten, verwenden Sie Teams im Browser, um sich anzumelden.
