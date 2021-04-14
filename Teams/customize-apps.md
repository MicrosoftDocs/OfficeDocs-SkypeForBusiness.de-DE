---
title: Anpassen von Microsoft-Apps in Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: vaagarw
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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Apps in Microsoft Teams anpassen.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9e9c7d250f60c3cc100f7d95b26f662ca8af6305
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697790"
---
# <a name="customize-apps-in-microsoft-teams"></a>Anpassen von Apps in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

 Microsoft Teams bietet App-Anpassungen, um die Benutzererfahrung von Teams zu verbessern. Einige App-Entwickler lassen zu, dass eine App vom Teams-Administrator angepasst wird. Der Administrator kann die App-Eigenschaften basierend auf den organisationsbezogenen Anforderungen über die Seite "Apps verwalten" des Teams Admin Center **anpassen oder neubranden.** Die Details, die Sie anpassen können, sind:

- Kurzname
- Kurzbeschreibung
- Vollständige Beschreibung
- URL der Datenschutzrichtlinien
- Website-URL
- URL der Nutzungsbedingungen
- Symbol "Farbe"
- Symbol "Gliederung"
- Akzentfarbe

Details zu den Feldern, die Sie anpassen können, finden Sie im [Schema "Teams-Manifest".](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema)

> [! HINWEIS Das Anpassen von Apps wird derzeit in Government Community Cloud High (GCCH) oder Department of Defense (DoD) nicht unterstützt.

## <a name="customize-the-apps-details"></a>Anpassen der Details der App

Führen Sie die folgenden Schritte aus, um mit dem Anpassen einer App zu beginnen:

1. Melden Sie sich beim Microsoft Teams Admin Center an.
2. Erweitern **Sie Teams-Apps,** und wählen **Sie Apps verwalten aus.**
3. Überprüfen Sie die **Anpassbare** Spalte der Apps-Liste, und sortieren Sie nach anpassbaren Apps.

   ![Die sortierte Spalte "Anpassen"](media/customize-column.png)

   Es gibt drei Einstiegspunkte für den Zugriff auf das Anpassungsfeature:

   - Wählen Sie neben der App aus, die Sie anpassen möchten, und wählen Sie dann **Anpassen aus.**

     ![Auswahloption anpassen 1](media/select-app-to-customize1.png)

   - Wählen Sie den Namen der App und dann **Anpassbar aus.**

     ![Auswahloption anpassen 2](media/app-details-customizable.png)

   - Wählen Sie den Namen der App und dann **in der Dropdownliste Aktionen** die Option Anpassen aus. 

     ![Auswahloption anpassen 3](media/customize-action-menu.png)

4. Erweitern Sie den **Abschnitt Details,** und passen Sie die folgenden Felder an:

    - Kurzname
    - Kurzbeschreibung
    - Vollständige Beschreibung
    - Website
    - URL der Datenschutzrichtlinien
    - URL der Nutzungsbedingungen

   ![Einstellungen anpassen](media/customize-settings.png)

> [!Note]
> Nur die Felder, die der App-Entwickler als anpassbar zugewiesen hat, sind sichtbar.

5. Erweitern Sie **den Abschnitt Symbol.**

   a. Laden Sie ein Symbol hoch. Verwenden Sie ein Vollfarbsymbol (192 x 192) Pixel im PNG-Format.

   b. Wählen Sie eine Symbolkonturfarbe aus. Verwenden Sie ein transparentes Gliederungspixel (32 x 32) im PNG-Format.

   c. Wählen Sie eine App-Akzentfarbe aus, die dem Symbol entspricht.

    ![Anpassen der Farboptionen des Symbolbereichs](media/customize-app-colors.png)

6. Nachdem Ihre App angepasst wurde, wählen Sie **Übernehmen aus.**

7. Wählen **Sie Veröffentlichen aus,** um die angepasste App zu veröffentlichen.

   Die angepasste App wird jetzt auf der Seite Apps **verwalten** aufgeführt. Sie verfügen nur über eine Version der App, da durch das Anpassen der App-Features keine Kopie der App erstellt wird.

Jetzt können Ihre Teams-Endbenutzer ihren Teams-Client öffnen, um die angepasste App zu sehen.

   ![Angepasste App im Teams-Client](media/find-customized-app.png)

### <a name="special-considerations-for-customizing-an-app"></a>Besondere Überlegungen zum Anpassen einer App

Die folgende Notiz enthält wichtige Details zum Anpassen einer App.

> [!Note]
> - Achten Sie beim Anpassen von Apps und jeder Beschreibung im Zusammenhang mit einer App darauf, dass Sie alle Anpassungsrichtlinien einhalten, wenn sie vom App-Herausgeber in der Dokumentation oder den Nutzungsbedingungen angegeben werden. Sie sind auch für die Einhaltung der Rechte anderer Personen in Bezug auf Bilder von Drittanbietern verantwortlich, die Sie möglicherweise verwenden.
> - Vom Administrator bereitgestellte Anpassungsdaten werden in der nächstgelegenen Region gespeichert.
> - Sie sind dafür verantwortlich sicherzustellen, dass Links zu Nutzungsbedingungen oder Datenschutzrichtlinien gültig sind.
> - Für den Fall, dass der App-Herausgeber ein Feld nicht mehr anpassbar macht, wird auf der Seite "App-Details" eine Meldung angezeigt, in der der Administrator über die Felder informiert wird, die nicht mehr angepasst werden können. Alle an diesem Feld vorgenommenen Änderungen werden auf die ursprünglichen Werte zurückgesetzt.
> - Änderungen am Branding können bis zu 24 Stunden dauern, bis die Benutzer die Änderungen sehen können.

## <a name="review-app-details"></a>Überprüfen von App-Details

Möglicherweise möchten Sie die App-Details anzeigen, um die Informationen zu überprüfen.

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Erweitern Sie **Microsoft Teams-Apps**, und wählen Sie **Apps verwalten** aus.

3. Wählen Sie den Namen der App aus.

4. Anzeigen der App-Details, einschließlich des ursprünglichen App-Namens **Kurzer Name von Publisher.**

   ![Anpassen des Namens der Symbolpanel-App](media/app-details-original-name.png)

   Das **Feld "Kurzer Name aus Herausgeber"** ist nur sichtbar, wenn Sie den kurzen Namen der App geändert haben.

## <a name="reset-app-details-to-default"></a>Zurücksetzen von App-Details auf Standard

Sie können die App-Details jederzeit auf die ursprünglichen Einstellungen zurücksetzen.

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Erweitern **Sie Teams-Apps,** und wählen **Sie Apps verwalten aus.**

3. Wählen Sie den Namen der App aus.

4. Wählen **Sie in der Dropdownliste** Aktionen die Option Auf Standard **zurücksetzen** aus.

   ![Zurücksetzen auf "Standard hervorgehoben" auswählen](media/select-reset.png)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wie lange dauert es, bis meine Benutzer die angepasste App sehen?**

Obwohl der Administrator die Änderungen im Teams Admin Center sofort sehen kann, kann es bis zu 24 Stunden dauern, bis die Endbenutzer die Änderungen sehen.  

**Kann der App-Anbieter die App für seine Kunden anpassen?**

 Nein, der Administrator eines Mandanten muss die App für seinen Mandanten über das Teams Admin Center anpassen.

**Wird die angepasste App automatisch bereitgestellt, um meine aktuelle benutzerdefinierte App in einem Mandanten zu ersetzen?**

Nein, die Mandantenadministratoren müssen jede benutzerdefinierte App manuell entfernen und die angepasste Version der App veröffentlichen. Wenn Sie eine App angepasst und als benutzerdefinierte App veröffentlicht haben, ersetzt die neue App, die mithilfe der App-Anpassungsfunktion angepasst wurde, nicht die aktuelle benutzerdefinierte App.  

**Werden im Bericht zur App-Nutzung auch die angepassten Werte angezeigt, z. B. angepasster kurzer Name?**

 Nein, der Bericht zur App-Nutzung zeigt weiterhin den ursprünglichen Namen der app an, die vom Herausgeber gesendet wurde.

**Welche Apps kann ich mithilfe der App-Anpassungsfunktion anpassen?**

Sie können nur Apps anpassen, die vom App Publisher angepasst werden können. Der App-Herausgeber muss sich dafür entscheiden, damit seine Kunden die App anpassen können.

**Werden die angepassten Eigenschaften auf dem Genehmigungsbildschirm für Diagrammberechtigungen angezeigt?**

Nein, auf dem Bildschirm "Berechtigungsgenehmigung" wird weiterhin der ursprüngliche Wert angezeigt, der vom Herausgeber gesendet wurde.

## <a name="related-article"></a>Verwandter Artikel

- [Verwalten von Apps](manage-apps.md)
- [Anpassen Ihres App Store](customize-your-app-store.md)
