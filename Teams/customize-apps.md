---
title: Ändern der Darstellung von Apps im Microsoft Teams-Store Ihrer Organisation
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie die Darstellung und das Branding einer App durch Bearbeiten der App-Details und -Metadaten ändern können.
ms.openlocfilehash: 444cf5cda737b9d4b4c3dc7f4032b7eb0877f4aa
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486920"
---
# <a name="customize-appearance-of-apps-in-your-organizations-teams-store"></a>Anpassen der Darstellung von Apps im Microsoft Teams Store Ihrer Organisation

Mit Microsoft Teams können Administratoren die Teams-App anpassen, um die Store-Erfahrung zu verbessern und das Branding ihrer Organisation einzuhalten. Ein App-Entwickler kann zulassen, dass seine App von einem Microsoft Teams-Administrator angepasst wird. Dieser kann dann die App-Eigenschaften basierend auf den Anforderungen der Organisation im Microsoft Teams Admin Center auf der Seite "Apps verwalten" ändern. Die Details, die Sie anpassen können, sind:

* Kurzname
* Kurzbeschreibung
* Vollständige Beschreibung
* URL zur Datenschutzerklärung
* Website-URL
* URL zu Nutzungsbedingungen
* App-Symbol
* Gliederungsfarbe des Symbols
* Akzentfarbe

Informationen zu den verschiedenen Metadatenfeldern der App finden Sie im [Microsoft Teams-Manifestschema](/microsoftteams/platform/resources/schema/manifest-schema) in der Entwicklerdokumentation.

> [!NOTE]
> Quergeladene Apps können in keiner Organisation angepasst werden. Apps in Government Community Cloud High (GCCH) oder Department of Defense (DoD)-Clouds können nicht angepasst werden.

## <a name="customize-details-of-an-app"></a>Anpassen von Details einer App

Führen Sie zum Anpassen einer App die folgenden Schritte aus:

1. Melden Sie sich beim Microsoft Teams Admin Center an.

1. Erweitern Sie **Microsoft Teams-Apps**, und wählen Sie **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)** aus.

1. Überprüfen Sie die Spalte **Anpassbar** der App-Liste und sortieren Sie nach anpassbaren Apps.

   ![Die Spalte "Anpassen" im Admin Center hilft Ihnen, anpassbare Apps anzuzeigen.](media/customizable-apps-in-tac.png)

   Es gibt drei Einstiegspunkte für den Zugriff auf das Anpassungsfeature:

   * Klicken Sie neben der App, die Sie anpassen möchten, und wählen Sie dann **Anpassen** aus.

     ![Die erste Möglichkeit zum Auswählen der Anpassungsoption.](media/select-app-to-customize1.png)

   * Klicken Sie auf den App-Namen und dann auf das Symbol "Bearbeiten" in **Anpassbar**.

     ![Die zweite Möglichkeit zum Auswählen der Anpassungsoption.](media/communities-microsoft.png)

   * Klicken Sie auf den App-Namen, dann auf das **Überlaufmenü**, zeigen Sie auf **Aktionen** und klicken Sie auf "Anpassen".

     ![Die dritte Möglichkeit zum Auswählen der Anpassungsoption.](media/customize-action-menu.png)

1. Erweitern Sie den Abschnitt **Details**, und passen Sie eines oder mehrere der nachfolgend aufgeführten Felder an. Die vom Entwickler als anpassbar ausgewiesenen Felder sind sichtbar.

    * Kurzname
    * Kurzbeschreibung
    * Vollständige Beschreibung
    * Website
    * URL zur Datenschutzerklärung
    * URL zu Nutzungsbedingungen

   ![Die Anpassungseinstellungen.](media/customize-settings.png)

1. Erweitern Sie den Abschnitt **Symbol**.

1. Laden Sie ein Symbol hoch. Verwenden Sie ein Symbol (192 x 192 Pixel) im PNG-Format.

1. Wählen Sie eine Symbolkonturfarbe aus. Verwenden Sie eine transparente Kontur (32 x 32 Pixel) im PNG-Format.

1. Wählen Sie eine App-Akzentfarbe aus, die zum Symbol passt.

   ![Passen Sie die Farboptionen des Symbolbereichs an.](media/customize-app-colors.png)

1. Nachdem Sie die App angepasst haben, klicken Sie auf **Übernehmen**.

1. Klicken Sie auf **Veröffentlichen**, um die angepasste App zu veröffentlichen.

   Die angepasste App wird jetzt auf der Seite **Apps verwalten** aufgeführt. Sie verfügen über nur eine Version der App, da beim Anpassen der App-Features keine Kopie der App erstellt wird.

Jetzt können Ihre Microsoft Teams-Endbenutzer die angepasste App in ihrem Client sehen.

   ![Angepasste App im Microsoft Teams-Client.](media/contoso-app.png)

Beachten Sie die folgenden Details zum Anpassen einer App:

* Wenn Sie Apps und Beschreibungen im Zusammenhang mit einer App anpassen, stellen Sie sicher, dass Sie alle Anpassungsrichtlinien befolgen, sofern dies vom App-Entwickler in seiner Dokumentation oder in den Nutzungsbedingungen angegeben wird. Sie sind auch dafür verantwortlich, die Rechte anderer Personen zu respektieren, falls Sie Bilder von Dritten verwenden.

* Von Administratoren bereitgestellte Anpassungsdaten werden in der nächstgelegenen Region gespeichert.

* Sie sind dafür verantwortlich sicherzustellen, dass Links zu Nutzungsbedingungen oder Datenschutzerklärungen gültig sind und funktionieren.

* Falls der App-Entwickler die Anpassung eines Felds nicht mehr zulässt, wird auf der Seite mit den App-Details eine Meldung angezeigt, die den Administrator über die Felder informiert, die nicht mehr angepasst werden können. Alle an diesem Feld vorgenommenen Änderungen werden auf die ursprünglichen Werte zurückgesetzt.

* Wir empfehlen, App-Anpassungen in einem Microsoft Teams-Testmandanten zu testen, bevor Sie diese Änderungen in Ihrer Produktionsumgebung vornehmen.

* Bei Änderungen am Branding kann es bis zu 24 Stunden dauern, bis sie an alle Benutzer weitergegeben werden.

* Damit eine App angepasst werden kann, können die Entwickler eine neue Version der App bereitstellen. Sie laden die neue Version hoch und entfernen die vorherige Version der App. Wenn Sie eine App angepasst und veröffentlicht haben, ersetzt die neue App, die mit dem App-Anpassungsfeature angepasst wurde, nicht die aktuelle App.

* Im [App-Nutzungsbericht](teams-analytics-and-reports/app-usage-report.md) wird der ursprüngliche Name der App angezeigt, der vom Herausgeber bereitgestellt wird.

* Im Dialogfeld zur Zustimmung der Microsoft Graph-Berechtigung wird der ursprüngliche Name der App angezeigt, der vom Herausgeber bereitgestellt wird. Es hilft Ihnen, eine App genau zu identifizieren und gleichzeitig Berechtigungen dafür bereitzustellen.

## <a name="review-app-details"></a>App-Details überprüfen

Manchmal möchten Sie die App-Details anzeigen, um die Informationen zu überprüfen.

1. Melden Sie sich beim Microsoft Teams Admin Center an.

1. Erweitern Sie **Microsoft Teams-Apps**, und wählen Sie **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)** aus.

1. Klicken Sie auf den App-Namen.

1. Zeigen Sie die App-Details an, einschließlich des ursprünglichen App-Namens **Kurzname des Herausgebers**.

   ![Passen Sie den App-Namen im Symbolbereich an.](media/original-app-version.png)

   Das Feld **Kurzname des Herausgebers** ist nur sichtbar, wenn Sie den Kurznamen der App geändert haben.

## <a name="reset-app-details-to-default-values"></a>Zurücksetzen von App-Details auf Standardwerte

Sie können die App-Details auf die ursprünglichen Werte zurücksetzen, die vom App-Entwickler bereitgestellt wurden. Die Option ist nur für angepasste Apps verfügbar.

1. Wechseln Sie im Microsoft Teams Admin Center zu **Microsoft Teams-Apps** > **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Klicken Sie auf den App-Namen.

1. Wählen Sie im Menü **Aktionen** die Option **Auf Standardwerte zurücksetzen** aus.

   ![Hervorgehobene Auswahl "Auf Standardwerte zurücksetzen".](media/select-reset.png)

## <a name="related-article"></a>Verwandter Artikel

* [Verwalten von Apps](manage-apps.md)
* [Anpassen des App Store Ihrer Organisation](customize-your-app-store.md)
* [Rebranding Ihrer Apps](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
