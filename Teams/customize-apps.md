---
title: Verwenden der App-Anpassung zum Branding der Apps für die Anforderungen Ihrer Organisation
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
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
ms.openlocfilehash: 6903d6bcd190869046c6f2e1a134c43cde3a1f07
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837695"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>Verwenden der App-Anpassung zum Aktualisieren des Brandings von Apps im Teams Store Ihrer Organisation

Microsoft Teams-Administratoren können das Erscheinungsbild einiger Teams-Apps ändern, um den Endbenutzern ihrer Organisation eine personalisierte Markenerfahrung zu bieten. Solche Änderungen können die Teams Store-Erfahrung für Endbenutzer verbessern und dazu beitragen, das Branding der Organisation einzuhalten. Administratoren können z. B. die Beschreibung und das Symbol einer App ändern. Die Anpassung erleichtert es Endbenutzern, die App als interne Tools zu identifizieren, den organisationsspezifischen Anwendungsfall zu verstehen und sie mit Vertrauen zu verwenden. Administratoren nehmen diese Aktualisierungen vor, indem sie einige Metadaten oder Eigenschaften einer App ändern. Die Änderungen sind nur innerhalb ihrer Organisation verfügbar. Diese Funktionalität wird als App-Anpassung bezeichnet.

Administratoren können Apps nur anpassen, wenn der App-Entwickler die Anpassung ihrer App zulässt. Während Teams eine Option zum Anpassen der folgenden Eigenschaften bietet, steuern App-Entwickler, welche Eigenschaften tatsächlich von jedem Administrator angepasst werden können.

* Kurzname
* Kurzbeschreibung
* Vollständige Beschreibung
* URL zur Datenschutzerklärung
* Website-URL
* URL zu Nutzungsbedingungen
* App-Symbol
* Gliederungsfarbe des Symbols
* Akzentfarbe

Ausführliche Informationen zu jeder dieser Eigenschaften finden Sie im [Teams-Manifestschema](/microsoftteams/platform/resources/schema/manifest-schema) in der Teams-Entwicklerdokumentation.

> [!NOTE]
> Sie müssen über eine Teams-Clientlizenz verfügen, um App-Informationen anpassen zu können.

## <a name="verify-if-an-app-is-customizable"></a>Überprüfen, ob eine App anpassbar ist

Alle Apps können nicht angepasst werden. Wenn ein App-Entwickler die Anpassung seiner App zulässt, können Sie nur dann die Darstellung der App ändern. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die App Ihrer Wahl anpassbar ist oder nicht:

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **Teams-Apps** >  zu **[Verwalten von Apps](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Wenn die Spalte " **Anpassbar** " nicht sichtbar ist, wählen Sie optional "Spalten :::image type="icon" source="media/settings-icon-16px.svg"::: bearbeiten" aus, und aktivieren Sie die Option " **Anpassbar** " auf **"Ein**".

1. Durchsuchen Sie die App, die Sie mithilfe des App-Namens anpassen möchten. Überprüfen Sie in der Spalte **"Anpassbar** ", ob der App-Entwickler die Anpassung der App zulässt oder nicht.

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="Der Screenshot zeigt, dass Sie mithilfe der anpassbaren Spalte im Admin Center überprüfen können, ob eine App anpassbar ist oder nicht.":::

Um alle anpassbaren Apps im Teams-Store zu finden, sortieren Sie die Spalte **"Anpassbar** ".

## <a name="customize-an-app"></a>Anpassen einer App

Führen Sie die folgenden Schritte aus, um das Aussehen und Verhalten einer App im Teams Store Ihrer Organisation zu ändern:

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **Teams-Apps** >  zu **[Verwalten von Apps](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Durchsuchen Sie die App, die Sie mithilfe des App-Namens anpassen möchten [, und stellen Sie sicher, dass sie angepasst werden kann](#verify-if-an-app-is-customizable).

1. Führen Sie einen der folgenden Schritte aus, um die Benutzeroberfläche zum Anpassen einzelner Metadatenfelder zu öffnen:

   * Wählen Sie die Zeile einer App aus, und wählen Sie dann auf der Symbolleiste auf der Seite "Apps verwalten" die Option **"Anpassen**:::image type="icon" source="media/edit-pen-icon.png":::" aus.

   * Wählen Sie den App-Namen aus, um die Seite mit den App-Details zu öffnen, und wählen Sie dann unter **"Anpassbar**" das Symbol "Bearbeiten" :::image type="icon" source="media/edit-pen-icon.png"::: aus.

   * Wählen Sie den App-Namen aus, um die Seite mit den App-Details zu öffnen, und wählen Sie dann **"Aktionen****anpassen"** >  aus.

     :::image type="content" source="media/customize-action-menu.png" alt-text="Der Screenshot zeigt eine Option zum Anpassen einer App, indem Sie das Menü &quot;Aktionen&quot; öffnen und auf der Seite &quot;App-Details&quot; die Option &quot;Anpassen&quot; auswählen." lightbox="media/customize-action-menu-expanded.png":::

1. Passen Sie eines oder mehrere der verfügbaren Felder an. Nur diese Metadatenfelder werden angezeigt und können vom App-Entwickler zugelassen werden. Die Einschränkungen für einige der Felder finden Sie unter [Überlegungen und Einschränkungen anpassbarer Felder](#considerations-and-limitations-of-app-customization).

   :::image type="content" source="media/customize-settings.png" alt-text="Der Screenshot zeigt den Namen und die Beschreibung auf der benutzerdefinierten Benutzeroberfläche an.":::

1. Nachdem Sie die App angepasst haben, klicken Sie auf **Übernehmen**. Informationen zum Überprüfen der vorgenommenen Änderungen finden Sie in den [App-Vorschaudetails](#preview-app-customizations). Informationen zum Rückgängigmachen der Änderungen finden Sie unter [Zurücksetzen von App-Details auf Standardwerte](#reset-app-details-to-default-values).

1. Wählen Sie **"Veröffentlichen** " aus, um die angepasste App im Store Ihrer Organisation zu veröffentlichen.

Die App wird auf der Seite **"Apps verwalten"** und im Teams-Store und -Client (verfügbar über web, mobil oder Desktopclient) mit den aktualisierten Details aufgeführt. Die Anzeige der Änderung kann einige Stunden dauern.

## <a name="preview-app-customizations"></a>Vorschau von App-Anpassungen

Um die Änderungen nach dem Speichern der Anpassungen anzuzeigen, zeigen Sie die Seite mit den App-Details an.

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **Teams-Apps** >  zu **[Verwalten von Apps](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Um die Seite mit den App-Details zu öffnen, wählen Sie den App-Namen aus.

1. Zeigen Sie die App-Details an, einschließlich des ursprünglichen App-Namens im Feld **"Kurzname vom Herausgeber"**. Das Feld ist nur sichtbar, wenn Sie den Kurznamen der App geändert haben.

   :::image type="content" source="media/original-app-version.png" alt-text="Der Screenshot zeigt den geänderten Kurznamen einer App.":::

Nach ein paar Stunden können Ihre Teams-Benutzer die angepasste App im Teams-Store in ihrem Client (Web, Mobil und Desktop) sehen.

   :::image type="content" source="media/contoso-app.png" alt-text="Der Screenshot zeigt eine angepasste App im Teams-Client.":::

## <a name="considerations-and-limitations-of-app-customization"></a>Überlegungen und Einschränkungen der App-Anpassung

Berücksichtigen Sie die folgenden Details zur App-Anpassungsfunktionalität:

* Sie können nur [Apps von Drittanbietern](deploy-apps-microsoft-teams-landing-page.md#third-party-apps-validated-by-microsoft) und keine [benutzerdefinierten Apps](deploy-apps-microsoft-teams-landing-page.md#custom-apps) anpassen.

* Sie können keine App in Government Community Cloud High (GCCH) und DoD-Umgebungen (Department of Defense) anpassen.

* Eine App kann nur angepasst werden, wenn sie vom App-Entwickler erlaubt wird.

* Änderungen an beliebigen Apps sind nur in Ihrer Organisation verfügbar.

* Sie verfügen nur über eine Version der App, da durch anpassen der App-Details keine Kopie der App erstellt wird.

* Wenn Sie Apps und beschreibungen im Zusammenhang mit einer App anpassen, stellen Sie sicher, dass Sie die Richtlinien befolgen, die App-Entwickler in ihrer Dokumentation oder in den Nutzungsbedingungen angeben. Halten Sie sich bei der Verwendung von Bildern von Drittanbietern an die Urheberrechtsgesetze.

* Admin bereitgestellten Anpassungsdaten werden im nächstgelegenen Datenspeicherbereich gespeichert.

* Sie sind dafür verantwortlich sicherzustellen, dass Links zu Nutzungsbedingungen oder Datenschutzrichtlinien gültig sind.

* Falls der App-Entwickler nicht mehr zulässt, dass ein Feld angepasst werden kann, wird auf der Seite mit den App-Details eine Meldung angezeigt, die den Administrator über ein solches Feld informiert. Alle am Feld vorgenommenen Änderungen werden auf den ursprünglichen Wert zurückgesetzt.

* Wir empfehlen, App-Anpassungen in einem Microsoft Teams-Testmandanten zu testen, bevor Sie diese Änderungen in Ihrer Produktionsumgebung vornehmen. Um einen Testmandanten zu erhalten, folgen Sie den Anweisungen beim [Erstellen Ihres Testmandanten](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant).

* Aktualisierungen bis zu 24 Stunden dauern, bis sie im Client für alle Benutzer und Administratorkonten angezeigt werden.

* Damit eine vorhandene App angepasst werden kann, kann der Entwickler eine neue Version der App im Teams Store bereitstellen.

* Der [App-Verwendungsbericht](teams-analytics-and-reports/app-usage-report.md) zeigt den ursprünglichen Namen der App an, die vom Herausgeber bereitgestellt wird, auch wenn die angepasste App von Endbenutzern verwendet wird.

* Im Dialogfeld zur Zustimmung der Microsoft Graph-Berechtigung wird der ursprüngliche Name der App angezeigt, der vom Herausgeber bereitgestellt wird. Es hilft Ihnen, eine App genau zu identifizieren und gleichzeitig Berechtigungen dafür bereitzustellen.

* Durch das Anpassen einer App werden keine App-Funktionen geändert.

Die Einschränkungen für einige der anpassbaren Felder sind unten aufgeführt:

| Anpassbares Feld | Berücksichtigung |
|:---|:---|
| Beliebige URL-Felder | Stellen Sie sicher, dass gültige und sichere URLs mithilfe von `https`. |
| Kurzbeschreibung | Die Kurzbeschreibung muss weniger als 80 Zeichen lang sein. Wiederholen Sie nicht, was in der vollständigen Beschreibung enthalten ist. |
| Symbol | Transparentes Gliederungssymbol im PNG-Format mit einer Auflösung von 32 x 32 Pixeln. |
| Farbsymbol | Vollfarbsymbol im PNG-Format mit einer Auflösung von 192 x 192 Pixel. |
| Akzentfarbe | Die Farbe muss ihrem Symbolhintergrund entsprechen. |

## <a name="troubleshoot-app-customization"></a>Problembehandlung bei der App-Anpassung

| Fehler und Probleme | Mögliche Behebung oder Verständnis des Problems |
| --- | --- |
| Meine Updates sind für meine Endbenutzer nicht verfügbar. | Warten Sie einige Stunden, bis die Änderungen weitergegeben wurden. |
| Ich kann eine App nicht anpassen. | Überprüfen Sie, ob die [App anpassbar ist oder nicht](#verify-if-an-app-is-customizable).|
| Ich habe mit dem Anpassen einer App begonnen, kann meine Änderungen jedoch nicht speichern oder anwenden. | Halten Sie sich an die Einschränkungen der Felder. Suchen nach Fehlern auf der Benutzeroberfläche und den [Einschränkungen der App-Anpassung](#considerations-and-limitations-of-app-customization) |
| Seite "Apps verwalten" wird nicht ordnungsgemäß geladen. Die Liste der Apps wird nicht angezeigt. | Admin verwendeten Konto muss die Teams-Lizenz zugewiesen sein. |

<!--- Check ICM for error string. --->

## <a name="reset-app-details-to-default-values"></a>Zurücksetzen von App-Details auf Standardwerte

Sie können die App-Details auf die ursprünglichen Werte zurücksetzen, die vom App-Entwickler bereitgestellt wurden. Die Option ist nur für angepasste Apps verfügbar.

1. Wechseln Sie im Microsoft Teams Admin Center zu **Microsoft Teams-Apps** > **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Um die Seite mit den App-Details zu öffnen, wählen Sie den App-Namen aus.

1. Wählen Sie im Menü **"Aktionen****" die Option "Auf Standard zurücksetzen"** aus.

   :::image type="content" source="media/reset-app-customization.png" alt-text="Der Screenshot zeigt die Option &quot;Auf Standard zurücksetzen&quot; für eine angepasste App.":::

## <a name="related-articles"></a>Verwandte Artikel

* [Anpassen des App Store Ihrer Organisation](customize-your-app-store.md)
* [Neubrandieren Ihres App-Communitybeitrags](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
