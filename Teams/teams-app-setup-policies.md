---
title: Verwalten von Richtlinien für das App-Setup in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informationen zu app-Setup Richtlinien in Microsoft Teams und deren Verwendung zum Anheften von apps zum Anpassen von Teams für Benutzer in Ihrer Organisation.
f1keywords:
- ms.teamsadmincenter.apppolicies.setup
ms.openlocfilehash: e26dc18f056f3493f6fcbdea2edee747d8abfa0b
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548821"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für das App-Setup in Microsoft Teams

> [!NOTE]
> Wenn Sie die Richtlinieneinstellung organisationsweite App-Berechtigungsrichtlinie aktiviert haben, die **Interaktion mit benutzerdefinierten apps zulassen**, werden die APP-Setup Richtlinien möglicherweise noch nicht im Microsoft Teams Admin Center angezeigt. Sie wird zurzeit bereitgestellt und wird in Kürze in Ihrer Organisation zur Verfügung stehen.

Als Administrator können Sie mithilfe von App-Setup Richtlinien Microsoft Teams so anpassen, dass die apps hervorgehoben werden, die für Ihre Benutzer am wichtigsten sind. Sie wählen die Apps aus, die Sie anheften möchten, und legen die Reihenfolge fest, in der Sie angezeigt werden. Mit den Richtlinien für die APP-Einrichtung können Sie apps präsentieren, die Benutzer in Ihrer Organisation benötigen, einschließlich der von Drittanbietern erstellten oder von Entwicklern in Ihrer Organisation. Sie können auch APP-Setup Richtlinien verwenden, um zu verwalten, wie integrierte Features angezeigt werden.

Apps werden an die APP-Leiste angeheftet. Hierbei handelt es sich um die Leiste auf der Seite des Teams-Desktop Clients und am unteren Rand der mobilen Teams (IOS und Android). 

|Desktop Client für Teams  |Mobiler Client für Teams |
|---------|---------|
|![Screenshot des Teams-Desktop Clients](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Screenshot mit dem Mobile-Client von Teams](media/app-setup-policies-mobile-app-bar.png)      |

Sie verwalten App-Setup Richtlinien im Microsoft Teams Admin Center. Sie können die globale Standardrichtlinie (org-Wide) verwenden oder benutzerdefinierte Richtlinien erstellen und diesen Benutzern zuweisen. Benutzer in Ihrer Organisation erhalten automatisch die globale Richtlinie, wenn Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen.

Sie können die Einstellungen in der globalen Richtlinie bearbeiten, um die gewünschten apps einzubeziehen. Wenn Sie Teams für verschiedene Benutzergruppen in Ihrer Organisation anpassen möchten, erstellen Sie eine oder mehrere benutzerdefinierte Richtlinien, und weisen Sie diese zu. Wenn einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen ist, gilt diese Richtlinie für den Benutzer. Wenn einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen ist, gilt die globale Richtlinie für den Benutzer.

![Screenshot mit der Seite "Richtlinien für die APP-Einrichtung"](media/app-setup-policies.png)

> [!NOTE]
> Wenn Sie über Teams für Bildung verfügen, ist es wichtig zu wissen, dass die Aufgaben-App standardmäßig in der globalen Richtlinie angeheftet ist, obwohl Sie in der globalen Richtlinie zurzeit nicht aufgeführt ist. Es handelt sich um die vierte app in der Liste der angehefteten apps auf Teams-Clients.

## <a name="create-a-custom-app-setup-policy"></a>Erstellen einer benutzerdefinierten App-Setup Richtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine benutzerdefinierte Richtlinie zu erstellen.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den**Setup Richtlinien**für **Teams-apps** > .
2. Wählen Sie **neue Richtlinie**aus.
3. Geben Sie einen aussagekräftigen Namen für die Richtlinie ein, und klicken Sie dann auf **apps hinzufügen**.
4. Aktivieren oder deaktivieren Sie das **Hochladen benutzerdefinierter apps zulassen**, je nachdem, ob Sie Benutzer benutzerdefinierte apps in Teams hochladen lassen möchten.
5. Suchen Sie im Bereich **angeheftete apps hinzufügen** nach den apps, die Sie hinzufügen möchten, und klicken Sie dann auf **Hinzufügen**. Sie können apps auch nach App-Berechtigungsrichtlinien filtern. Wenn Sie die Liste der apps ausgewählt haben, klicken Sie auf **Hinzufügen**.

     ![Screenshot mit dem Bereich "angeheftete apps hinzufügen"](media/app-setup-policies-add-apps.png)

6. Ordnen Sie die apps in der Reihenfolge an, in der Sie in Teams angezeigt werden sollen, und klicken Sie dann auf **Speichern**.

    ![Screenshot mit dem Abschnitt "angeheftete Apps"](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Bearbeiten einer APP-Setup Richtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der Global (org-Wide Standard)-Richtlinie und der von Ihnen erstellten benutzerdefinierten Richtlinien.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den**Setup Richtlinien**für **Teams-apps** > .
2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten. 
3. Nehmen Sie hier die gewünschten Änderungen vor. Sie können die Reihenfolge der apps hinzufügen, entfernen und ändern.
4. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Setup Richtlinie für Benutzer

Sie können das Microsoft Teams Admin Center verwenden, um einzelnen Benutzern oder dem Skype for Business PowerShell-Modul eine benutzerdefinierte Richtlinie zuzuweisen, um Gruppen von Benutzern, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe, eine benutzerdefinierte Richtlinie zuzuweisen.

> [!IMPORTANT]
> Es wird empfohlen, PowerShell nur zum Zuweisen von Richtlinien für Benutzer zu verwenden. Verwenden Sie das Microsoft Teams Admin Center, um Richtlinien zu erstellen, zu bearbeiten und zu verwalten.

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a>Zuweisen einer benutzerdefinierten App-Setup Richtlinie für einzelne Benutzer

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.
2. Wählen Sie neben **zugewiesene Richtlinien**die Option **Bearbeiten**aus.
3. Wählen Sie unter **Teams-App-Setup Richtlinie**die APP-Setup Richtlinie aus, die Sie zuweisen möchten, und wählen Sie dann **Speichern**aus.

    ![Screenshot mit dem Bereich "Benutzerrichtlinien bearbeiten"](media/app-setup-policies-assign-policy.png)

Sie können auch eine APP-Setup Richtlinie einem oder mehreren Benutzern wie folgt zuweisen:

1. Wechseln Sie zu den > **Setup Richtlinien**für Apps für **Microsoft Teams Admin Center** > **Teams**.
2. Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken.
3. Wählen Sie **Benutzer verwalten**aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeige namens oder nach dem Benutzernamen nach dem Benutzer, wählen Sie den Namen aus, und wählen Sie dann **Hinzufügen**aus. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.
5. Wenn Sie alle Benutzer hinzugefügt haben, wählen Sie **Speichern**aus.

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>Zuweisen einer benutzerdefinierten App-Setup Richtlinie für Benutzer in einer Gruppe

Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte App-Setup Richtlinie zuweisen. So können Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen. Sie können dies tun, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen. Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).

In diesem Beispiel weisen wir allen Benutzern in der Projektgruppe "Contoso Pharmaceuticals HR" eine benutzerdefinierte App-Setup Richtlinie mit dem Namen "HR-App-Setup Richtlinie" zu.  

> [!NOTE]
> Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.

Rufen Sie die GroupObjectId der jeweiligen Gruppe ab.
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Rufen Sie die Mitglieder der angegebenen Gruppe ab.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Weisen Sie allen Benutzern in der Gruppe eine bestimmte App-Setup Richtlinie zu. In diesem Beispiel handelt es sich um die Richtlinie für die HR-App-Konfiguration.
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
Je nach Anzahl der Mitglieder in der Gruppe kann dieser Befehl mehrere Minuten dauern.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-setup-policies"></a>Arbeiten mit App-Setup Richtlinien

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Welche integrierten App-Setup Richtlinien sind im Microsoft Teams Admin Center enthalten?

- **Global (org-Wide Standard)**: Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie weisen eine andere Richtlinie zu. Bearbeiten Sie die globale Richtlinie, um apps zu anheften, die für Ihre Benutzer am wichtigsten sind.
- **FirstLineWorker**: Diese Richtlinie gilt für First-work-Mitarbeiter. Sie können es den Mitarbeitern in Ihrer Organisation zuweisen. Es ist wichtig zu wissen, dass Sie wie von Ihnen erstellte benutzerdefinierte Richtlinien die Richtlinie Benutzern zuweisen müssen, damit die Einstellungen aktiv sind. Weitere Informationen finden Sie im Abschnitt [Zuweisen einer benutzerdefinierten App-Setup Richtlinie zu Benutzern](#assign-a-custom-app-setup-policy-to-users) dieses Artikels.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Warum kann ich keine app im Bereich "angeheftete apps hinzufügen" finden?

Nicht alle apps können über eine APP-Setup Richtlinie an Teams angeheftet werden. Einige apps unterstützen diese Funktion möglicherweise nicht. Um apps zu finden, die angeheftet werden können, suchen Sie im Bereich **angeheftete apps hinzufügen** nach der app. Registerkarten mit einem persönlichen Bereich (statische Registerkarten) und Bots können an den Desktop Client von Teams angeheftet werden, und diese apps sind im Bereich **angeheftete apps hinzufügen** verfügbar.

Beachten Sie, dass im App Store für Teams alle Teams-apps aufgelistet sind, während der Bereich **angeheftete apps hinzufügen** nur apps enthält, die über eine Richtlinie an Teams angeheftet werden können. 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Ich bin ein Team für Bildungs Administrator. Was muss ich über die Richtlinien für die APP-Einrichtung in Teams für Bildung wissen?

- Die Anruf-App steht in Teams für Education nicht zur Verfügung. Wenn Sie eine neue benutzerdefinierte App-Setup Richtlinie erstellen, wird die aufrufende app in der Liste der apps angezeigt. Die APP wird jedoch nicht an Teams-Clients und Teams für Education angeheftet. Benutzer sehen die Anruf-APP nicht in Teams. 

- Zurzeit werden Richtlinienänderungen nicht für Teams für Education-Benutzer in der Android-App für Teams übernommen. Wir arbeiten an einer neuen Version der APP, die Richtlinienänderungen für Teams für Bildungseinrichtungen unterstützt.

#### <a name="how-many-apps-can-be-added-to-a-policy"></a>Wie viele apps können einer Richtlinie hinzugefügt werden?

Mindestens zwei apps müssen an die mobilen Teams (IOS und Android) angeheftet sein. Wenn eine Richtlinie weniger als zwei apps aufweist, geben die mobilen Clients die Richtlinieneinstellungen nicht wieder und verwenden stattdessen weiterhin die vorhandene Konfiguration.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Wie lange dauert es, bis Richtlinienänderungen wirksam werden?

Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis die Änderungen wirksam werden.

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

Derzeit können Benutzer die Reihenfolge ihrer angehefteten apps auf mobilen Teams, aber nicht auf dem Desktop oder auf Webclients von Teams ändern. 

### <a name="custom-teams-apps"></a>Benutzerdefinierte Teams-apps

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Meine Organisation hat eine benutzerdefinierte Teams-App erstellt und Sie entweder in AppSource oder im Mandanten-App-Katalog veröffentlicht, doch das App-Symbol wird nicht wie erwartet angezeigt, wenn die app in Teams an die APP-Leiste angeheftet wird. Wie kann ich dieses Problem beheben? 

Achten Sie darauf, dass Sie die Richtlinien für das Logo befolgen, bevor Sie die APP übermitteln. Weitere Informationen finden Sie unter [Checkliste für die Übermittlung von Verkäufer Dashboards](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist). 

 ## <a name="related-topics"></a>Verwandte Themen
- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
- [Veröffentlichen einer APP im Mandanten-apps-Katalog des Teams-Clients](tenant-apps-catalog-teams.md)
