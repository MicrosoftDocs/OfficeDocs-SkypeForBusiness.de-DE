---
title: Verwenden der App-Anpassung zum Branding der Apps für die Anforderungen Ihrer Organisation
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
description: Erfahren Sie, wie Sie die Metadaten und das Erscheinungsbild einer App ändern, um sie für eine bessere Akzeptanz in Ihrer Organisation neu zu formatieren.
ms.openlocfilehash: 0a1ae462933768e0c5a53db6c7379e5cd8b9bf05
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647479"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>Verwenden der App-Anpassung zum Aktualisieren des Brandings von Apps im Teams Store Ihrer Organisation

Microsoft Teams-Administratoren können das Erscheinungsbild einiger Teams-Apps ändern, um den Endbenutzern ihrer Organisation eine personalisierte Markenerfahrung zu bieten. Solche Änderungen können die Teams Store-Erfahrung für Endbenutzer verbessern und dazu beitragen, das Branding der Organisation einzuhalten. Administratoren können z. B. die Beschreibung und das Symbol einer App ändern, die endbenutzern ihrer Organisation die Identifizierung der App, das Verständnis ihrer Verwendung und die zusätzliche Bedeutung erleichtert. Administratoren nehmen diese Änderungen vor, indem sie einige Metadaten oder Eigenschaften einer App ändern. Die Änderungen sind nur innerhalb ihrer Organisation verfügbar. Diese Funktionalität wird als App-Anpassung bezeichnet.

Administratoren können Apps nur anpassen, wenn der App-Entwickler die Anpassung ihrer App zulässt. Während Teams eine Option zum Anpassen einiger Eigenschaften bietet, steuern App-Entwickler die Eigenschaften, die tatsächlich von jedem Administrator angepasst werden können.

Als Administrator können Sie die folgenden Eigenschaften anpassen.

* Kurzname
* Kurzbeschreibung
* Vollständige Beschreibung
* URL zur Datenschutzerklärung
* Website-URL
* URL zu Nutzungsbedingungen
* App-Symbol
* Gliederungsfarbe des Symbols
* Akzentfarbe

Ausführliche Informationen zu den einzelnen Metadatenfeldern finden Sie im [Teams-Manifestschema](/microsoftteams/platform/resources/schema/manifest-schema) in der Teams-Entwicklerdokumentation.

> [!NOTE]
> Die App-Anpassungsfunktionalität ist für benutzerdefinierte Apps nicht verfügbar. Administratoren können keine App in Government Community Cloud High (GCCH)- und Department of Defense (DoD)-Umgebungen anpassen.

## <a name="verify-if-an-app-is-customizable"></a>Überprüfen, ob eine App anpassbar ist

Alle Apps können nicht angepasst werden. Wenn ein App-Entwickler ihnen die Anpassung der App ermöglicht, können Sie nur dann die App-Anpassungsfunktionalität verwenden, um das Erscheinungsbild der App zu ändern. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die App Ihrer Wahl anpassbar ist oder nicht:

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **Teams-Apps** >  zu **[Verwalten von Apps](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Durchsuchen Sie die App, die Sie mithilfe des App-Namens anpassen möchten. Überprüfen Sie in der Spalte **"Anpassbar** ", ob der App-Entwickler die Anpassung der App zulässt oder nicht. Wenn die Spalte nicht sichtbar ist, wählen Sie "Spalten :::image type="icon" source="media/settings-icon-16px.svg"::: bearbeiten" aus, und aktivieren Sie die Option "**Anpassbar****".**

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="Der Screenshot zeigt, dass Sie mithilfe der anpassbaren Spalte im Admin Center überprüfen können, ob eine App anpassbar ist oder nicht.":::

Um alle anpassbaren Apps im Teams-Store zu finden, sortieren Sie die Spalte "Anpassbar".

## <a name="customize-the-details-of-an-app"></a>Anpassen der Details einer App

Führen Sie die folgenden Schritte aus, um das Aussehen und Verhalten einer App so zu ändern, wie sie im Teams Store Ihrer Organisation angezeigt wird:

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **Teams-Apps** >  zu **[Verwalten von Apps](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Durchsuchen Sie die App, die Sie mithilfe des App-Namens anpassen möchten, und stellen Sie sicher, dass sie angepasst werden kann.

1. Führen Sie einen der folgenden Schritte aus, um die Benutzeroberfläche zum Anpassen einzelner Metadatenfelder zu öffnen:

   * Wählen Sie die Zeile einer App aus, und wählen Sie dann auf der Symbolleiste auf der Seite "Apps verwalten" die Option **"Anpassen**:::image type="icon" source="media/edit-pen-icon.png":::" aus.

   * Wählen Sie den App-Namen aus, um die Seite mit den App-Details zu öffnen, und wählen Sie dann unter **"Anpassbar**" das Symbol "Bearbeiten" :::image type="icon" source="media/edit-pen-icon.png"::: aus.

   * Wählen Sie den App-Namen, dann **"Aktionen"** und dann **"Anpassen"** aus.

     :::image type="content" source="media/customize-action-menu.png" alt-text="Der Screenshot zeigt eine Option zum Anpassen einer App, indem Sie das Menü &quot;Aktionen&quot; öffnen und auf der Seite &quot;App-Details&quot; die Option &quot;Anpassen&quot; auswählen." lightbox="media/customize-action-menu-expanded.png":::

1. Passen Sie eines oder mehrere der verfügbaren Felder an. Ein App-Entwickler kann nur einige der Metadatenfelder anpassen. Siehe [Überlegungen und Einschränkungen anpassbarer Felder](#considerations-and-limitations-of-app-customization).

   :::image type="content" source="media/customize-settings.png" alt-text="Der Screenshot zeigt den Namen und die Beschreibung auf der benutzerdefinierten Benutzeroberfläche an.":::

1. Nachdem Sie die App angepasst haben, klicken Sie auf **Übernehmen**. Informationen zum Überprüfen der vorgenommenen Änderungen finden Sie in den [App-Vorschaudetails](#preview-app-details). Informationen zum Rückgängigmachen der Änderungen finden Sie unter [Zurücksetzen von App-Details auf Standardwerte](#reset-app-details-to-default-values).

1. Wählen Sie **"Veröffentlichen** " aus, um die angepasste App zu veröffentlichen, und sehen Sie sie auf der Seite **"Apps verwalten"** .

<!---
   :::image type="content" source="media/customize-app-colors.png" alt-text="Screenshot showing the icon color options that can be customized.":::
--->

## <a name="preview-app-details"></a>Vorschau von App-Details

Um die Änderungen nach dem Speichern der Anpassung anzuzeigen, zeigen Sie die Seite mit den App-Details an.

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **Teams-Apps** >  zu **[Verwalten von Apps](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Um die Seite mit den App-Details zu öffnen, wählen Sie den App-Namen aus.

1. Zeigen Sie die App-Details an, einschließlich des ursprünglichen App-Namens im Feld **"Kurzname vom Herausgeber"**. Das Feld ist nur sichtbar, wenn Sie den Kurznamen der App geändert haben.

   :::image type="content" source="media/original-app-version.png" alt-text="Der Screenshot zeigt den geänderten Kurznamen einer App.":::

Ihre Teams-Benutzer können die angepasste App im Teams-Store in ihrem Client sehen.

   :::image type="content" source="media/contoso-app.png" alt-text="Der Screenshot zeigt eine angepasste App im Teams-Client.":::

## <a name="considerations-and-limitations-of-app-customization"></a>Überlegungen und Einschränkungen der App-Anpassung

Berücksichtigen Sie die folgenden Details zur App-Anpassungsfunktionalität:

* Sie verfügen über nur eine Version der App, da beim Anpassen der App-Features keine Kopie der App erstellt wird.

* Wenn Sie Apps und beschreibungen im Zusammenhang mit einer App anpassen, stellen Sie sicher, dass Sie die Richtlinien befolgen, die App-Entwickler in ihrer Dokumentation oder in den Nutzungsbedingungen angeben. Halten Sie sich bei der Verwendung von Bildern von Drittanbietern an die Urheberrechtsgesetze.

* Von Administratoren bereitgestellte Anpassungsdaten werden in der nächstgelegenen Region gespeichert.

* Sie sind dafür verantwortlich sicherzustellen, dass Links zu Nutzungsbedingungen oder Datenschutzrichtlinien gültig sind.

* Falls der App-Entwickler die Anpassung eines Felds nicht mehr zulässt, wird auf der Seite mit den App-Details eine Meldung angezeigt, die den Administrator über die Felder informiert, die nicht mehr angepasst werden können. Alle an diesem Feld vorgenommenen Änderungen werden auf die ursprünglichen Werte zurückgesetzt.

* Wir empfehlen, App-Anpassungen in einem Microsoft Teams-Testmandanten zu testen, bevor Sie diese Änderungen in Ihrer Produktionsumgebung vornehmen. Um einen Testmandanten zu erhalten, folgen Sie den Anweisungen beim [Erstellen Ihres Testmandanten](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant).

* Es dauert bis zu 24 Stunden, bis Änderungen an alle Benutzer weitergegeben werden.

* Damit eine App angepasst werden kann, können die Entwickler eine neue Version der App bereitstellen. Sie laden die neue Version hoch und entfernen die vorherige Version der App. Wenn Sie eine App angepasst und veröffentlicht haben, ersetzt die neue App, die mit dem App-Anpassungsfeature angepasst wurde, nicht die aktuelle App.

* Im [App-Nutzungsbericht](teams-analytics-and-reports/app-usage-report.md) wird der ursprüngliche Name der App angezeigt, der vom Herausgeber bereitgestellt wird.

* Im Dialogfeld zur Zustimmung der Microsoft Graph-Berechtigung wird der ursprüngliche Name der App angezeigt, der vom Herausgeber bereitgestellt wird. Es hilft Ihnen, eine App genau zu identifizieren und gleichzeitig Berechtigungen dafür bereitzustellen.

Die Einschränkungen für die anpassbaren Felder sind unten aufgeführt:

| Anpassbares Feld | Berücksichtigung |
|:---|:---|
| Beliebige URL-Felder | Stellen Sie sicher, dass gültige und sichere URLs mithilfe von `https`. |
| Kurzbeschreibung | Die Kurzbeschreibung darf weniger als 80 Zeichen lang sein und darf nicht wiederholt werden, was in der vollständigen Beschreibung enthalten ist. |
| Symbol | Transparentes Gliederungssymbol im PNG-Format mit einer Auflösung von 32 x 32 Pixeln. |
| Farbsymbol | Vollfarbsymbol im PNG-Format mit einer Auflösung von 192 x 192 Pixel. |
| Akzentfarbe | Die Farbe muss ihrem Symbolhintergrund entsprechen. |

## <a name="reset-app-details-to-default-values"></a>Zurücksetzen von App-Details auf Standardwerte

Sie können die App-Details auf die ursprünglichen Werte zurücksetzen, die vom App-Entwickler bereitgestellt wurden. Die Option ist nur für angepasste Apps verfügbar.

1. Wechseln Sie im Microsoft Teams Admin Center zu **Microsoft Teams-Apps** > **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Um die Seite mit den App-Details zu öffnen, wählen Sie den App-Namen aus.

1. Wählen Sie im Menü **"Aktionen****" die Option "Auf Standard zurücksetzen"** aus.

   :::image type="content" source="media/reset-app-customization.png" alt-text="Der Screenshot zeigt die Option &quot;Auf Standard zurücksetzen&quot; für eine angepasste App.":::

## <a name="related-articles"></a>Verwandte Artikel

* [Anpassen des App Store Ihrer Organisation](customize-your-app-store.md)
* [Rebranding Ihrer Apps](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
