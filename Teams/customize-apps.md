---
title: Ändern der Darstellung von Apps im Teams Store Ihrer Organisation
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Apps in Microsoft Teams anpassen.
ms.openlocfilehash: 3f8a8a3c1922de230573628926a1aff2eee6ee06
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124370"
---
# <a name="customize-appearance-of-apps-in-your-organizations-teams-store"></a>Anpassen der Darstellung von Apps im Teams Store Ihrer Organisation

Microsoft Teams können Administratoren Teams App anpassen, um die Store-Erfahrung zu verbessern und das Branding ihrer Organisation einzuhalten. Ein App-Entwickler kann zulassen, dass seine App von einem Teams-Administrator angepasst wird. Anschließend können Sie die App-Eigenschaften basierend auf den Organisatorischen Anforderungen auf der Seite "Apps verwalten" im Teams Admin Center aktualisieren. Die Details, die Sie anpassen können, sind:

* Kurzname
* Kurzbeschreibung
* Vollständige Beschreibung
* URL der Datenschutzrichtlinie
* Website-URL
* Nutzungsbedingungen-URL
* App-Symbol
* Gliederungsfarbe des Symbols
* Akzentfarbe

Informationen zu den verschiedenen Metadatenfeldern der App finden Sie im [Teams Manifestschema](/microsoftteams/platform/resources/schema/manifest-schema) in der Entwicklerdokumentation.

> [!NOTE]
> Quergeladene Apps können in keiner Organisation angepasst werden. Sie können keine App in Government Community Cloud High -Clouds (GCCH) oder DoD-Clouds (Department of Defense) anpassen.

## <a name="customize-details-of-an-app"></a>Anpassen von Details einer App

Führen Sie zum Anpassen einer App die folgenden Schritte aus:

1. Melden Sie sich beim Microsoft Teams Admin Center an.

1. Erweitern Sie **Teams Apps**, und wählen Sie **["Apps verwalten" aus](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Überprüfen Sie die Spalte **"Anpassbar"** der Liste "Apps", und sortieren Sie nach anpassbaren Apps.

   ![Die Spalte "Anpassen" im Admin Center hilft Ihnen, anpassbare Apps anzuzeigen.](media/customizable-apps-in-tac.png)

   Es gibt drei Einstiegspunkte für den Zugriff auf das Anpassungsfeature:

   * Wählen Sie neben der App aus, die Sie anpassen möchten, und wählen Sie dann **"Anpassen"** aus.

     ![Die Option "Auswahl anpassen" 1.](media/select-app-to-customize1.png)

   * Wählen Sie den App-Namen und dann das Symbol "Bearbeiten" in **"Anpassbar"** aus.

     ![Die Option "Auswahl anpassen 2".](media/communities-microsoft.png)

   * Wählen Sie den App-Namen aus, klicken Sie auf das **Überlaufmenü** , zeigen Sie auf **"Aktionen"** , und wählen Sie "Anpassen" aus.

     ![Die Option "Auswahl anpassen" 3.](media/customize-action-menu.png)

1. Erweitern Sie den Abschnitt **"Details** ", und passen Sie eines oder mehrere der folgenden Felder an. Die vom Entwickler als anpassbar zugewiesenen Felder sind sichtbar.

    * Kurzname
    * Kurzbeschreibung
    * Vollständige Beschreibung
    * Website
    * URL der Datenschutzrichtlinie
    * Nutzungsbedingungen-URL

   ![Die Einstellungen anpassen.](media/customize-settings.png)

1. Erweitern Sie den Abschnitt **"Symbol"** .

1. Hochladen ein Symbol. Verwenden Sie ein Symbol (192 x 192 Pixel) im PNG-Format.

1. Wählen Sie eine Symbolgliederungsfarbe aus. Verwenden Sie eine transparente Gliederung (32 x 32 Pixel) im PNG-Format.

1. Wählen Sie eine App-Akzentfarbe aus, die dem Symbol entspricht.

   ![Passen Sie die Farboptionen des Symbolbereichs an.](media/customize-app-colors.png)

1. Nachdem Sie die App angepasst haben, wählen Sie **"Übernehmen"** aus.

1. Wählen Sie **"Veröffentlichen"** aus, um die angepasste App zu veröffentlichen.

   Die angepasste App wird jetzt auf der Seite **"Apps verwalten"** aufgeführt. Sie verfügen nur über eine Version der App, da durch anpassen der App-Features keine Kopie der App erstellt wird.

Jetzt können Ihre Teams Endbenutzer die angepasste App in ihrem Client sehen.

   ![Angepasste App in Teams Client.](media/contoso-app.png)

Beachten Sie die folgenden Details zum Anpassen einer App:

* Wenn Sie Apps und eine Beschreibung im Zusammenhang mit einer App anpassen, stellen Sie sicher, dass Sie alle Anpassungsrichtlinien befolgen, wenn sie vom App-Herausgeber in der Dokumentation oder den Nutzungsbedingungen bereitgestellt werden. Sie sind auch dafür verantwortlich, die Rechte anderer personen in Bezug auf bilder von Drittanbietern zu respektieren, die Sie möglicherweise verwenden.

* Admin bereitgestellten Anpassungsdaten werden in der nächstgelegenen Region gespeichert.

* Sie sind dafür verantwortlich sicherzustellen, dass Links zu Nutzungsbedingungen oder Datenschutzrichtlinien gültig sind.

* Falls der App-Herausgeber nicht mehr zulässt, dass ein Feld angepasst werden kann, wird auf der Seite mit den App-Details eine Meldung angezeigt, die den Administrator über die Felder informiert, die nicht mehr angepasst werden können. Alle an diesem Feld vorgenommenen Änderungen werden auf die ursprünglichen Werte zurückgesetzt.

* Es wird empfohlen, Änderungen an der App-Anpassung in einem Teams Testmandanten zu testen, bevor Sie diese Änderungen in Ihrer Produktionsumgebung vornehmen.

* Änderungen am Branding können bis zu 24 Stunden dauern, bis sie an alle Benutzer weitergegeben werden.

* Damit eine App angepasst werden kann, können die Entwickler eine neue Version der App bereitstellen. Sie laden die neue Version hoch und entfernen die vorherige Version der App. Wenn Sie eine App angepasst und veröffentlicht haben, ersetzt die neue App, die mit dem App-Anpassungsfeature angepasst wurde, nicht die aktuelle App.

* Der [App-Verwendungsbericht](teams-analytics-and-reports/app-usage-report.md) zeigt den ursprünglichen Namen der App an, die vom Herausgeber bereitgestellt wird.

* Im Dialogfeld zur Zustimmung der Microsoft Graph-Berechtigung wird der ursprüngliche Name der App angezeigt, die vom Herausgeber bereitgestellt wird. Es hilft Ihnen, eine App genau zu identifizieren und gleichzeitig Berechtigungen dafür bereitzustellen.

## <a name="review-app-details"></a>Überprüfen von App-Details

Möglicherweise möchten Sie die App-Details anzeigen, um die Informationen zu überprüfen.

1. Melden Sie sich beim Microsoft Teams Admin Center an.

1. Erweitern Sie **Teams Apps**, und wählen Sie **["Apps verwalten" aus](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Wählen Sie den App-Namen aus.

1. Zeigen Sie die App-Details an, einschließlich des ursprünglichen App-Namens **Short name from publisher**.

   ![Passen Sie den Namen der Symbolbereich-App an.](media/original-app-version.png)

   Der **Kurzname aus dem Herausgeberfeld** ist nur sichtbar, wenn Sie den Kurznamen der App geändert haben.

## <a name="reset-app-details-to-default-values"></a>Zurücksetzen von App-Details auf Standardwerte

Sie können die App-Details auf die ursprünglichen Werte zurücksetzen, die vom App-Entwickler bereitgestellt werden. Die Option ist nur für angepasste Apps verfügbar.

1. Greifen Sie Teams Admin Center **auf Teams Apps** > **[verwalten](https://admin.teams.microsoft.com/policies/manage-apps)** zu.

1. Wählen Sie den App-Namen aus.

1. Wählen Sie im Menü **"Aktionen**" die **Option "Auf Standard zurücksetzen"** aus.

   ![Wählen Sie "Auf Standard zurücksetzen" hervorgehoben aus.](media/select-reset.png)

## <a name="related-article"></a>Verwandter Artikel

* [Verwalten von Apps](manage-apps.md)
* [Anpassen des App Store Ihrer Organisation](customize-your-app-store.md)
* [Umbenennen Ihrer Apps](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
