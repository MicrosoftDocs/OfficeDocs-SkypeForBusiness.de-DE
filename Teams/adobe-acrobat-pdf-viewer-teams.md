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
ms.openlocfilehash: fd74ece7ba59b437fcd8b47bd184cdcfd150438d
ms.sourcegitcommit: 4708fc1c2b8523e1074aed06b1dd6950c039f200
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2022
ms.locfileid: "67002338"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-teams"></a>Adobe Acrobat als PDF-Standardanzeige in Teams

> [!NOTE]
> Adobe Acrobat als PDF-Standardoberfläche in Teams ist derzeit nur in der öffentlichen Vorschau verfügbar. [Aktivieren Sie die öffentliche Vorschau](public-preview-doc-updates.md#enable-public-preview) für Ihren Mandanten, bevor Sie dieses Feature verwenden. Stellen Sie sicher, dass Endbenutzer die Microsoft Teams-Clientversion in die öffentliche Vorschau ändern, um Adobe Acrobat als PDF-Viewer in Teams zu erleben.

Als Administrator können Sie Adobe Acrobat als Standard-App zum Anzeigen und Bearbeiten von PDF-Dateien in Microsoft Teams festlegen. Ihre Endbenutzer benötigen kein Adobe Acrobat-Abonnement oder eine Adobe-ID, um PDF-Dateien anzuzeigen, zu durchsuchen, zu kommentieren und anmerkungen zu machen.

## <a name="set-up-adobe-acrobat-app"></a>Einrichten der Adobe Acrobat-App

Führen Sie die folgenden Schritte aus, um Adobe Acrobat als Standard-App zum Anzeigen von PDF-Dateien einzurichten:

1. Melden Sie sich beim Teams Admin Center an, und wechseln Sie zu "**[Apps verwalten"](https://admin.teams.microsoft.com/policies/manage-apps)** der **Teams-App** > .

1. Suchen Sie nach der Adobe Acrobat-App, und wählen Sie **die Adobe Acrobat-App** aus.

   > [!NOTE]
   >
   > * Stellen Sie sicher, dass der Adobe Acrobat-App-Status auf **"Zulässig**" festgelegt ist. Aktivieren Sie andernfalls den Umschalter " **Zulässig** ".
   > * Wenn in der App-Berechtigungsrichtlinie oder den organisationsweiten App-Einstellungen, die die App blockiert haben, eine Administratoreinstellung vorhanden ist, stellen Sie sicher, dass Sie die App in der [App-Berechtigungsrichtlinie](teams-app-permission-policies.md) oder [organisationsweiten App-Einstellungen](teams-app-permission-policies.md) zulassen.

1. Wählen Sie auf der Registerkarte **"Berechtigungen** " die **Option "Berechtigung überprüfen**" aus.

1. Wählen Sie **"Annehmen"** aus.

   :::image type="content" source="media/permission-policy.png" alt-text="Screenshot der App-Berechtigung im Teams Admin Center." lightbox="media/teams-app-adobe-acrobat-permission.png":::

## <a name="install-adobe-acrobat-app-for-all-users"></a>Installieren der Adobe Acrobat-App für alle Benutzer

Sie können die globale Richtlinie (organisationsweite Standardrichtlinie) verwenden, um die Adobe Acrobat-App für alle Benutzer zuzuweisen und verfügbar zu machen. Dieser Schritt löst ein Signal in Teams aus, um die App als Standarddateihandler für PDF-Dateien festzulegen. Führen Sie die folgenden Schritte aus, um die Adobe Acrobat-App für alle Benutzer zuzuweisen:

1. Wechseln Sie im Teams Admin Center zu den [**Setuprichtlinien**](https://admin.teams.microsoft.com/policies/app-setup) für **Teams-Apps** > .

1. Wählen Sie auf der Registerkarte " **Richtlinien verwalten** " **die Option "Global" (organisationsweite Standardeinstellung)** und dann " **Bearbeiten"** aus.

   :::image type="content" source="media/setup-policies.png" alt-text="Screenshot der Setuprichtlinien für die Adobe Acrobat-App im Teams Admin Center.":::

1. Wählen Sie unter "Installierte Apps" die Option **"Apps hinzufügen"** aus.

1. Suchen Sie **Adobe Acrobat**, wählen Sie neben dem App-Namen " **Hinzufügen"** und dann " **Hinzufügen"** aus.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Screenshot, der zeigt, wie Die Adobe Acrobat-App für alle Benutzer hinzugefügt wird." lightbox="media/add-adobe-acrobat-app.png":::

1. Klicken Sie auf **Speichern**.

Nachdem Sie "Speichern" ausgewählt haben, ist die Adobe Acrobat-App mit Teams so konfiguriert, dass alle PDF-Dateien in der Adobe Acrobat-App aus der Chat-, Kanal- oder Datei-App geöffnet werden.

Wenn Sie die Adobe Acrobat-App selektiv für einige bestimmte Personen oder für eine Gruppe zulassen möchten, können Sie eine [benutzerdefinierte App-Berechtigungsrichtlinie](teams-app-permission-policies.md) zuweisen.

Kennen Sie die folgenden Informationen zu dieser Funktionalität:

* Nachdem die Richtlinie eingerichtet wurde, dauert es in der Regel [einige Stunden](teams-app-setup-policies.md) , bis die App für Benutzer verfügbar ist.
Nachdem die Richtlinie eingerichtet wurde, ist die installierte App nach einigen Stunden für Benutzer verfügbar.
* Das Anzeigen von PDF-Dateien, die in Kanälen als Registerkarte angeheftet sind, und das Anzeigen von PDF-Dateien in der Aufgaben-App wird weiterhin von der nativen Teams-Umgebung unterstützt.
* Adobe Acrobat als PDF-Standardanzeige in Teams funktioniert nur auf Desktop- und Webclients. Sie wird auf dem mobilen Client nicht unterstützt.
* Benutzer benötigen einen Adobe Acrobat-Plan, um Premium-Tools wie "PDF exportieren", "Seiten organisieren", "Dateien kombinieren", "PDF komprimieren" und "PDF schützen" verwenden zu können.

> [!NOTE]
> Wenn beim Signieren bei der Adobe Acrobat-App Probleme auftreten, können Sie Teams im Browser öffnen und sich anmelden. Dies ist ein bekanntes Problem und wird bis September 2022 behoben.

## <a name="faqs"></a>Faqs

* Wie entferne ich die Adobe Acrobat-App vom Teams-Client?
  
  Endbenutzer können die App vom Microsoft Teams-Client deinstallieren, und der Administrator kann die Adobe Acrobat-App aus der Setuprichtlinie entfernen.

* Können Administratoren die Adobe Acrobat-App blockieren, nachdem sie als Standardhandler festgelegt wurde?
  
  Ja, aber bevor der Administrator die App blockiert, entfernen Sie die Setuprichtlinie, um sicherzustellen, dass die Endbenutzer sicher wieder auf die Microsoft Teams-Standardumgebung zurückgeführt werden.
