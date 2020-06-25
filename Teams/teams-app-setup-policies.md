---
title: Verwalten von Richtlinien für das App-Setup in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie App-Setup Richtlinien in Microsoft Teams für Benutzer in Ihrer Organisation verwenden und verwalten.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ef4ff711aa385c062ca6d507363b4d1a1a5d88e4
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868566"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das App-Setup in Microsoft Teams

> [!NOTE]
> Wenn Sie die organisationsweite app-Einstellung aktiviert haben, die **Interaktion mit benutzerdefinierten apps zulassen**, werden die APP-Setup Richtlinien möglicherweise noch nicht im Microsoft Teams Admin Center angezeigt. Sie wird zurzeit bereitgestellt und wird in Kürze in Ihrer Organisation zur Verfügung stehen.

Als Administrator können App-Einrichtungsrichtlinien für Folgendes einrichten:

- Passen Sie Teams so an, dass jene Apps hervorgehoben werden, die für Ihre Benutzer am wichtigsten sind. Sie wählen die Apps aus, die Sie anheften möchten, und legen die Reihenfolge fest, in der Sie angezeigt werden. Durch das Anpinnen können Sie Apps vorstellen, die von Benutzern in Ihrer Organisation benötigt werden, beispielsweise Apps von Drittanbietern oder von Entwicklern in Ihrer Organisation.
- Legen Sie fest, ob Benutzer Apps in Microsoft Teams anheften können.
- Installieren von apps im Auftrag von Benutzern **(in der Vorschau)** Sie wählen die Apps aus, die standardmäßig für Benutzer installiert werden, wenn Sie Teams starten. Beachten Sie, dass Benutzer weiterhin Apps selbst installieren können, wenn die Ihnen zugewiesene [App-Berechtigungsrichtlinie](teams-app-permission-policies.md) dies zulässt.

Apps werden an die App-Leiste angeheftet. Hierbei handelt es sich um die Leiste am seitlichen Rand im Microsoft Teams-Desktopclient bzw. am unteren Rand in mobilen Teams-Clients (iOS und Android).

|Desktop Client für Teams  |Mobiler Client für Teams |
|---------|---------|
|![Screenshot des Teams-Desktop Clients](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Screenshot mit dem Mobile-Client von Teams](media/app-setup-policies-mobile-app-bar.png)      |

Um die vorinstallierten apps anzuzeigen, klicken Benutzer in der APP-Leiste auf **... Weitere apps** in den Teams-Desktop-und-Webclients und wischen Sie in den mobilen Clients nach oben.

Sie verwalten App-Setup Richtlinien im Microsoft Teams Admin Center. Sie können die globale Standardrichtlinie (Org-wide default) verwenden oder benutzerdefinierte Richtlinien erstellen und diese Benutzern zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

Sie können die Einstellungen in der globalen Richtlinie bearbeiten, um die gewünschten apps einzubeziehen. Wenn Sie Teams für verschiedene Benutzergruppen in Ihrer Organisation anpassen möchten, erstellen Sie eine oder mehrere benutzerdefinierte Richtlinien, und weisen Sie diese zu. Sofern einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen wurde, gilt diese Richtlinie für den Benutzer. Wurde einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen, gilt für diesen Benutzer die globale Standardrichtlinie.

![Screenshot mit der Seite "Richtlinien für die APP-Einrichtung"](media/app-setup-policies.png)

> [!NOTE]
> Wenn Sie über Teams für Bildung verfügen, ist es wichtig zu wissen, dass die Aufgaben-App standardmäßig in der globalen Richtlinie angeheftet ist, obwohl Sie in der globalen Richtlinie zurzeit nicht aufgeführt ist. Es handelt sich um die vierte app in der Liste der angehefteten apps auf Teams-Clients.

## <a name="create-a-custom-app-setup-policy"></a>Erstellen einer benutzerdefinierten App-Setup Richtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine benutzerdefinierte Richtlinie zu erstellen.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**den  >  **Setup Richtlinien**für Teams-apps.
2. Klicken Sie auf **Hinzufügen**.
    ![Screenshot mit der Seite "Richtlinien zum Hinzufügen von Apps"](media/app-setup-policies-add.png)
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Aktivieren oder deaktivieren Sie Benutzer **definierte apps hochladen**, je nachdem, ob Sie Benutzer benutzerdefinierte apps in Teams hochladen lassen möchten. Sie können diese Einstellung nicht ändern, wenn **apps von Drittanbietern** in den [organisationsweiten App-Einstellungen](manage-apps.md#manage-org-wide-app-settings)deaktiviert sind.
5. Aktivieren oder deaktivieren Sie das **Zulassen von Benutzer anheften**, je nachdem, ob Benutzer Ihre APP-Leiste personalisieren lassen möchten, indem Sie apps an Sie anheften.
6. Gehen Sie wie folgt vor, um Apps für Benutzer **(in der Vorschau)** zu installieren:

    1. Klicken Sie unter **installierte apps**auf **apps hinzufügen**.
    2. Suchen Sie im Bereich **installierte apps hinzufügen** nach den apps, die Sie beim Starten von Teams automatisch für Benutzer installieren möchten. Sie können apps auch nach App-Berechtigungsrichtlinien filtern. Wenn Sie die Liste der apps ausgewählt haben, klicken Sie auf **Hinzufügen**.

        ![Screenshot mit dem Bereich "installierte apps hinzufügen"](media/app-setup-policies-add-installed-apps.png)

7. Gehen Sie wie folgt vor, um apps zu anheften:

    1. Klicken Sie unter **angeheftete apps**auf **apps hinzufügen**.
    2. Suchen Sie im Bereich **angeheftete apps hinzufügen** nach den apps, die Sie hinzufügen möchten, und klicken Sie dann auf **Hinzufügen**. Sie können apps auch nach App-Berechtigungsrichtlinien filtern. Wenn Sie die Liste der zu anheftenden apps ausgewählt haben, klicken Sie auf **Hinzufügen**.

         ![Screenshot mit dem Bereich "angeheftete apps hinzufügen"](media/app-setup-policies-add-apps.png)

    3. Ordnen Sie die apps in der Reihenfolge an, in der Sie in Teams angezeigt werden sollen, und klicken Sie dann auf **Speichern**.

        ![Screenshot mit dem Abschnitt "angeheftete Apps"](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Bearbeiten einer APP-Setup Richtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der Global (org-Wide Standard)-Richtlinie und der von Ihnen erstellten benutzerdefinierten Richtlinien.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**den  >  **Setup Richtlinien**für Teams-apps.
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie hier die gewünschten Änderungen vor.
4. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Setup Richtlinie für Benutzer

Mit dem Microsoft Teams Admin Center können Sie einzelnen Benutzern oder dem Skype for Business PowerShell-Modul eine benutzerdefinierte Richtlinie zuweisen, um Benutzern in einer Gruppe, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe, eine benutzerdefinierte Richtlinie zuzuweisen.

### <a name="assign-a-custom-app-setup-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Setup Richtlinie für Benutzer

So weisen Sie einem Benutzer eine Richtlinie zu:

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Wählen Sie den Nutzer aus, indem Sie links neben den Nutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.
3. Wählen Sie unter **App-Setup Richtlinie**die APP-Setup Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf über **nehmen**.

So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.
2. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).
3. Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.  

Sie können auch die folgenden Schritte ausführen:

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**den  >  **Setup Richtlinien**für Teams-apps.
2. Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
5. Nachdem Sie das Hinzufügen von Benutzern abgeschlossen haben, wählen Sie **Speichern**aus.

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>Zuweisen einer benutzerdefinierten App-Setup Richtlinie für Benutzer in einer Gruppe

Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte App-Setup Richtlinie zuweisen. So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen. Dies ist möglich, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen. Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Überblick über PowerShell für Microsoft Teams](teams-powershell-overview.md).

In diesem Beispiel weisen wir allen Benutzern in der Projektgruppe "Contoso Pharmaceuticals HR" eine benutzerdefinierte App-Setup Richtlinie mit dem Namen "HR-App-Setup Richtlinie" zu.  

> [!NOTE]
> Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.

Abrufen der GroupObject-ID der jeweiligen Gruppe.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Abrufen der Mitglieder der gewählten Gruppe.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Weisen Sie allen Benutzern in der Gruppe eine bestimmte App-Setup Richtlinie zu. In diesem Beispiel handelt es sich um die Richtlinie für die HR-App-Konfiguration.
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.UserPrincipalName}
``` 
Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-setup-policies"></a>Arbeiten mit App-Setup Richtlinien

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Welche integrierten App-Setup Richtlinien sind im Microsoft Teams Admin Center enthalten?

- **Global (org-Wide Standard)**: Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie weisen eine andere Richtlinie zu. Bearbeiten Sie die globale Richtlinie, um apps zu anheften, die für Ihre Benutzer am wichtigsten sind.
- **FirstLineWorker**: Diese Richtlinie gilt für First-work-Mitarbeiter. Sie können es den Mitarbeitern in Ihrer Organisation zuweisen. Es ist wichtig zu wissen, dass Sie wie von Ihnen erstellte benutzerdefinierte Richtlinien die Richtlinie Benutzern zuweisen müssen, damit die Einstellungen aktiv sind. Weitere Informationen finden Sie im Abschnitt [Zuweisen einer benutzerdefinierten App-Setup Richtlinie zu Benutzern](#assign-a-custom-app-setup-policy-to-users) dieses Artikels.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich keine app im Bereich "angeheftete apps hinzufügen" finden?

Nicht alle apps können über eine APP-Setup Richtlinie an Teams angeheftet werden. Einige apps unterstützen diese Funktion möglicherweise nicht. Um apps zu finden, die angeheftet werden können, suchen Sie im Bereich **angeheftete apps hinzufügen** nach der app. Registerkarten mit einem persönlichen Bereich (statische Registerkarten) und Bots können an den Desktop Client von Teams angeheftet werden, und diese apps sind im Bereich **angeheftete apps hinzufügen** verfügbar.

Beachten Sie, dass im App Store für Teams alle Teams-apps aufgelistet sind, während der Bereich **angeheftete apps hinzufügen** nur apps enthält, die über eine Richtlinie an Teams angeheftet werden können. 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Ich bin ein Team für Bildungs Administrator. Was muss ich über die Richtlinien für die APP-Einrichtung in Teams für Bildung wissen?

Die Anruf-App steht in Teams für Education nicht zur Verfügung. Wenn Sie eine neue benutzerdefinierte App-Setup Richtlinie erstellen, wird die aufrufende app in der Liste der apps angezeigt. Die APP wird jedoch nicht an Teams-Clients und Teams für Education angeheftet. Benutzer sehen die Anruf-APP nicht in Teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Wie viele angeheftete Apps können einer Richtlinie hinzugefügt werden?

Mindestens zwei apps müssen an die mobilen Teams (IOS und Android) angeheftet sein. Wenn eine Richtlinie weniger als zwei apps aufweist, geben die mobilen Clients die Richtlinieneinstellungen nicht wieder und verwenden stattdessen weiterhin die vorhandene Konfiguration.

Die Anzahl der angehefteten apps, die Sie einer Richtlinie hinzufügen können, ist unbegrenzt.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Wie lange dauert es, bis Richtlinienänderungen wirksam werden?

Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Wie können Benutzer alle Ihre angehefteten apps in Teams anzeigen?

Um alle apps anzuzeigen, die für einen Benutzer angeheftet sind, müssen die Benutzer möglicherweise die folgenden Schritte ausführen, abhängig von der Anzahl der installierten apps und der Größe des Teams-Clientfensters.

|Desktop Client für Teams |Mobiler Client für Teams |
|---------|---------|
|Klicken Sie in der APP-Leiste auf der Seite von Teams auf **... Weitere apps**.| Wischen Sie in der APP-Leiste am unteren Rand von Teams nach oben.|
|![Screenshot mit weiteren apps im Desktop Client von Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Screenshot mit weiteren apps im mobilen Team-Client](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Was muss ich über die Mobile Teams-Umgebung wissen?

Die Mobile-Clients von Teams (IOS und Android) unterstützen derzeit keine persönlichen apps mit statischen Registerkarten. Je nach den in der Richtlinie festgelegten apps werden apps, die an den Desktop Client von Teams angeheftet wurden, möglicherweise nicht in den mobilen Teams angezeigt. Persönliche Bots werden weiterhin im Chat auf mobilen Clients angezeigt.

Mit den mobilen Teams von Teams werden Benutzern Kern Teams-apps wie Aktivitäten, Chats und Teams angezeigt, und Sie können einige Erstanbieter-apps von Microsoft anheften, beispielsweise Schichten.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Können Benutzer die Reihenfolge der apps ändern, die über eine Richtlinie angeheftet wurden?

Benutzer können die Reihenfolge ihrer angehefteten apps auf den Desktop-und mobilen Clients von Teams ändern, wenn die Option **Benutzer anheften zulassen** aktiviert ist. Benutzer können die Reihenfolge ihrer angehefteten apps auf den Microsoft Teams-Webclients nicht ändern.

#### <a name="does-user-pinning-take-precedence"></a>Hat das Anheften des Benutzers Vorrang?

Wenn die dem Benutzer zugewiesene App-Setup Richtlinie geändert wird, um das Anheften der Benutzer-APP zu blockieren, entfernt Teams alle apps, die an die APP-Leiste angeheftet sind. Wenn die Richtlinie dann geändert wird, um Benutzer-App-anheften zuzulassen, müssen Benutzer ihre zuvor angehefteten apps erneut anheften.

### <a name="custom-teams-apps"></a>Benutzerdefinierte Teams-apps

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Meine Organisation hat eine benutzerdefinierte Teams-App erstellt und Sie entweder in AppSource oder im Mandanten-App-Katalog veröffentlicht, doch das App-Symbol wird nicht wie erwartet angezeigt, wenn die app in Teams an die APP-Leiste angeheftet wird. Wie kann ich dieses Problem beheben?

Achten Sie darauf, dass Sie die Richtlinien für das Logo befolgen, bevor Sie die APP übermitteln. Weitere Informationen finden Sie unter [Checkliste für die Übermittlung von Verkäufer Dashboards](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview). 

## <a name="related-topics"></a>Verwandte Themen

- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
- [Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)
