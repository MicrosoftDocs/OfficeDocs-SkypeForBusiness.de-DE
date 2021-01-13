---
title: Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
description: Lernen Sie die verschiedenen Methoden zum Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 5d213c53de22994d46e7d7faf54a8dfd687806d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821305"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams

Als Administrator steuern Sie mithilfe von Richtlinien die Teams-Features, die Benutzern in Ihrer Organisation zur Verfügung stehen. Beispielsweise gibt es Anrufrichtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen.

Organisationen verfügen über verschiedene Arten von Benutzern mit eindeutigen Anforderungen und benutzerdefinierten Richtlinien, die Sie erstellen und zuweisen, damit Sie Richtlinieneinstellungen auf verschiedene Benutzergruppen basierend auf diesen Anforderungen anpassen können.

Um das Verwalten von Richtlinien in Ihrer Organisation zu vereinfachen, bietet Teams mehrere Möglichkeiten zum Zuweisen von Richtlinien zu Benutzern. Sie können eine Richtlinie direkt den Benutzern zuweisen, entweder einzeln oder im Maßstab über eine Batchzuordnung, oder zu einer Gruppe, deren Mitglieder die Benutzer sind. Sie können auch Richtlinienpakete verwenden, um Benutzern in Ihrer Organisation, die ähnliche Rollen haben, eine voreingestellte Sammlung von Richtlinien zuzuordnen. Die von Ihnen auswählende Option hängt von der Anzahl der Richtlinien, die Sie verwalten, und der Anzahl der Benutzer ab, die Sie zuweisen. Wenn Sie die globalen (organisationsweiten Standard)-Richtlinien so festlegen, dass sie für die größte Anzahl von Benutzern in Ihrer Organisation gelten, müssen Sie nur den Benutzern Richtlinien zuweisen, die spezielle Richtlinien erfordern.

In diesem Artikel werden die verschiedenen Methoden beschrieben, mit denen Sie Benutzern Richtlinien zuweisen können, sowie die empfohlenen Szenarien für die Verwendung von Was.

## <a name="which-policy-takes-precedence"></a>Welche Richtlinie hat Vorrang?

Ein Benutzer verfügt über eine effektive Richtlinie für jeden Richtlinientyp. Es ist möglich oder sogar wahrscheinlich, dass einem Benutzer eine Richtlinie direkt zugewiesen wurde und außerdem Mitglied einer oder mehreren Gruppen ist, denen eine Richtlinie desselben Typs zugewiesen ist. Welche Richtlinie hat in solchen Szenarien Vorrang?  Die effektive Richtlinie eines Benutzers wird gemäß den Rangfolgeregeln wie folgt bestimmt.

Wenn einem Benutzer direkt eine Richtlinie zugewiesen wird (entweder einzeln oder über eine Batchzuweisung), hat diese Richtlinie Vorrang. Im folgenden Beispiel ist die effektive Richtlinie des Benutzers die "Quadratische Besprechungsrichtlinie", die dem Benutzer direkt zugewiesen wird.

![Diagramm, das zeigt, wie eine direkt zugewiesene Richtlinie Vorrang hat](media/assign-policies-example-directly-assigned.png)

Wenn einem Benutzer eine Richtlinie eines bestimmten Typs nicht direkt zugewiesen wurde, hat die Einer Gruppe zugewiesene Richtlinie Vorrang, deren Mitglied der Benutzer ist. Wenn ein Benutzer Mitglied mehrerer Gruppen ist, hat [](#group-assignment-ranking) die Richtlinie mit der höchsten Gruppenzuweisungsrangfolge für den angegebenen Richtlinientyp Vorrang.

In diesem Beispiel ist die effektive Richtlinie des Benutzers die Exec Teams- und HD-Richtlinie, die die höchste Zuweisungsrangfolge im Vergleich zu anderen Gruppen hat, denen der Benutzer mitglied ist und denen auch eine Richtlinie desselben Richtlinientyps zugewiesen ist.  

![Diagramm, das zeigt, wie eine von einer Gruppe geerbte Richtlinie Vorrang hat](media/assign-policies-example-group.png)

Wenn einem Benutzer eine Richtlinie nicht direkt zugewiesen wurde oder kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen wurde, erhält der Benutzer die globale Richtlinie (organisationsweite Standardrichtlinie) für diesen Richtlinientyp. Hier ist ein Beispiel.

![Diagramm, das zeigt, wie eine globale Richtlinie vorrangig ist](media/assign-policies-example-global.png)

Weitere Informationen finden Sie unter ["Rangfolgeregeln".](#precedence-rules)

## <a name="ways-to-assign-policies"></a>Möglichkeiten zum Zuweisen von Richtlinien

Im Folgenden finden Sie eine Übersicht über die Möglichkeiten zum Zuweisen von Richtlinien zu Benutzern und die empfohlenen Szenarien für die einzelnen Szenarien. Klicken Sie auf die Links, um weitere Informationen zu erhalten.

Bevor Sie einzelnen Benutzern oder Gruppen Richtlinien zuweisen, beginnen Sie, indem Sie die globalen [(organisationsweiten Standard)-Richtlinien](#set-the-global-policies) so festlegen, dass sie für die größte Anzahl von Benutzern in Ihrer Organisation gelten.  Nachdem die globalen Richtlinien festgelegt wurden, müssen Sie nur noch den Benutzern Richtlinien zuweisen, die spezielle Richtlinien erfordern.

|So geht's  |Wenn...  | Wird verwendet...
|---------|---------|----|
|[Zuweisen einer Richtlinie zu einzelnen Benutzern](#assign-a-policy-to-individual-users)    | Sie sind neu in Teams und haben gerade erst begonnen, oder Sie müssen nur einer kleinen Anzahl von Benutzern eine oder mehrere Richtlinien zuweisen. |Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Skype for Business Online -PowerShell-Modul
|[Zuweisen einer Richtlinie zu einer Gruppe](#assign-a-policy-to-a-group) |Sie müssen Richtlinien basierend auf der Gruppenmitgliedschaft eines Benutzers zuweisen. Sie möchten beispielsweise allen Benutzern in einer Sicherheitsgruppe oder Verteilerliste eine Richtlinie zuweisen.| Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Teams -PowerShell-Modul|
|[Zuweisen einer Richtlinie zu einer Gruppe von Benutzern](#assign-a-policy-to-a-batch-of-users)   | Sie müssen großen Gruppen von Benutzern Richtlinien zuweisen. Sie möchten beispielsweise Hunderte oder Tausende von Benutzern in Ihrer Organisation gleichzeitig eine Richtlinie zuweisen.  |Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Teams -PowerShell-Modul|
| [Zuweisen eines Richtlinienpakets zu Benutzern](#assign-a-policy-package-to-users)  | Sie müssen bestimmten Benutzergruppen in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zuweisen. Weisen Sie beispielsweise Lehrkräften in Ihrer Schule das Richtlinienpaket für Bildungseinrichtungen (Teacher) zu, um ihnen Vollzugriff auf Chats, Anrufe und Besprechungen sowie das Richtlinienpaket für Bildungseinrichtungen (Schüler/Studierende sekundärer Bildungseinrichtungen) zu geben, um bestimmte Funktionen wie private Anrufe zu beschränken.  |Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Teams -PowerShell-Modul|
| [Zuweisen eines Richtlinienpakets zu einer Gruppe](#assign-a-policy-package-to-a-group) (in der privaten Vorschau)   |Sie müssen einer Gruppe von Benutzern in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zuweisen. Beispielsweise möchten Sie ein Richtlinienpaket allen Benutzern in einer Sicherheitsgruppe oder Verteilerliste zuweisen. |Das Microsoft Teams Admin Center (in Kürze verfügbar) oder die PowerShell-Cmdlets im Teams -PowerShell-Modul|
| [Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern](#assign-a-policy-package-to-a-batch-of-users)|Sie müssen einer Gruppe von Benutzern in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zuweisen. Weisen Sie beispielsweise allen Lehrkräften in Ihrer Schule das Richtlinienpaket für Bildungseinrichtungen zu, indem Sie eine Batchzuweisung verwenden, um ihnen vollzugriff auf Chats, Anrufe und Besprechungen zu ermöglichen, und weisen Sie das Richtlinienpaket für Bildungseinrichtungen (Schüler/Studierende sekundärer Bildungseinrichtungen) einer Gruppe von sekundären Schülern/Studenten zu, um bestimmte Funktionen wie private Anrufe zu beschränken.|PowerShell-Cmdlets im Teams -PowerShell-Modul|


## <a name="set-the-global-policies"></a>Festlegen der globalen Richtlinien

Führen Sie die folgenden Schritte aus, um die globalen (organisationsweiten Standard)-Richtlinien für jeden Richtlinientyp zu festlegen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zur Richtlinienseite für den Richtlinientyp, den Sie aktualisieren möchten. Beispielsweise Teams Teams-Richtlinien,  >     >  **Besprechungsrichtlinien,** **Messagingrichtlinien** oder   >  **Sprachanrufrichtlinien.**
2. Wählen Sie die **globale (organisationsweite Standardrichtlinie)** aus, um die aktuellen Einstellungen anzeigen.
3. Aktualisieren Sie die Richtlinie nach Bedarf, und wählen Sie dann **"Übernehmen" aus.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie zum Festlegen der globalen Richtlinien mithilfe von PowerShell den globalen Bezeichner.  Überprüfen Sie zunächst die aktuelle globale Richtlinie, um zu bestimmen, welche Einstellung Sie ändern möchten.

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

Aktualisieren Sie als Nächstes die globale Richtlinie nach Bedarf.  Sie müssen nur Werte für die Einstellungen angeben, die Sie ändern möchten. 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>Zuweisen einer Richtlinie zu einzelnen Benutzern

Führen Sie die folgenden Schritte aus, um eine Richtlinie einem einzelnen Benutzer oder einer kleinen Anzahl von Benutzern gleichzeitig zuzuordnen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

So weisen Sie einem Benutzer eine Richtlinie zu:

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Wählen Sie den Nutzer aus, indem Sie links neben den Nutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.
3. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **"Übernehmen".**

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zur Seite "Richtlinie".
2. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, indem Sie links des Richtliniennamens klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
5. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **"Übernehmen" aus.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets für die Verwaltung. Verwenden Sie das ```Grant-``` Cmdlet für einen bestimmten Richtlinientyp, um die Richtlinie zuzuordnen. Verwenden Sie beispielsweise das ```Grant-CsTeamsMeetingPolicy``` Cmdlet, um Benutzern eine Besprechungsrichtlinie für Teams zuzuordnen. Diese Cmdlets sind im Skype for Business Online -PowerShell-Modul enthalten und werden in der [Skype for Business-Cmdlet-Referenz dokumentiert.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

 Laden Sie das [Skype for Business Online -PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366) herunter, installieren Sie es (falls noch nicht), und führen Sie dann die folgenden Schritte aus, um eine Verbindung mit Skype for Business Online herzustellen und eine Sitzung zu starten.

> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
>
> Wenn Sie die neueste öffentliche Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie Skype for Business Online Connector nicht installieren.

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

In diesem Beispiel weisen wir einem Benutzer namens Reda eine Team-Besprechungsrichtlinie mit dem Namen "Besprechungsrichtlinie für Schüler/Studenten" zu.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Weitere Informationen finden Sie unter ["Verwalten von Richtlinien über PowerShell".](teams-powershell-managing-teams.md#manage-policies-via-powershell)

## <a name="assign-a-policy-to-a-group"></a>Zuweisen einer Richtlinie zu einer Gruppe

Mit der Richtlinienzuweisung zu Gruppen können Sie einer Benutzergruppe, z. B. einer Sicherheitsgruppe oder Verteilerliste, eine Richtlinie zuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.

Die Richtlinienzuweisung zu Gruppen wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, funktioniert aber auch mit größeren Gruppen.

Wenn Sie die Richtlinie zuweisen, wird sie der Gruppe sofort zugewiesen. Beachten Sie jedoch, dass die Weitergabe der Richtlinienzuweisung an Mitglieder der Gruppe als Hintergrundvorgang ausgeführt wird und je nach Größe der Gruppe einige Zeit dauern kann. Dasselbe gilt, wenn eine Richtlinie nicht mehr einer Gruppe zugewiesen wird oder Wenn Mitglieder zu einer Gruppe hinzugefügt oder aus ihr entfernt werden.

Gruppenrichtlinienzuweisungen werden nur an Benutzer weiterveriert, die direkte Mitglieder der Gruppe sind. Die Zuordnungen werden nicht an Mitglieder von geschachtelten Gruppen aufgeteilt.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Wichtige Informationen zur Richtlinienzuweisung zu Gruppen

Bevor Sie beginnen, ist es wichtig, die Rangfolgeregeln und die Rangfolge von Gruppenzuweisungen zu verstehen.

#### <a name="precedence-rules"></a>Rangfolgeregeln

Für einen bestimmten Richtlinientyp wird die effektive Richtlinie eines Benutzers wie folgt bestimmt:

- Eine Richtlinie, die einem Benutzer direkt zugewiesen ist, hat Vorrang vor allen anderen Richtlinien desselben Typs, der einer Gruppe zugewiesen ist. Anders ausgedrückt: Wenn einem Benutzer eine Richtlinie eines bestimmten Typs direkt zugewiesen wird, erbt dieser Benutzer keine Richtlinie desselben Typs von einer Gruppe. Dies bedeutet auch, dass Sie, wenn ein Benutzer eine Richtlinie eines bestimmten Typs besitzt, die ihm direkt zugewiesen wurde, diese Richtlinie vom Benutzer entfernen müssen, bevor er eine Richtlinie desselben Typs von einer Gruppe erben kann.
- Wenn einem Benutzer keine Richtlinie direkt zugewiesen wurde und ein Mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen wurde, erbt der Benutzer die Richtlinie der Gruppenzuordnung, die die höchste Rangfolge hat.
- Wenn ein Benutzer kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, gilt die globale Richtlinie (organisationsweite Standardrichtlinie) für diesen Richtlinientyp für den Benutzer.

Die effektive Richtlinie eines Benutzers wird gemäß diesen Regeln aktualisiert, wenn ein Benutzer einer Gruppe hinzugefügt oder aus dieser entfernt wird, der eine Richtlinie zugewiesen ist, eine Richtlinie einer Gruppe nicht zugewiesen wird oder eine Richtlinie, die dem Benutzer direkt zugewiesen wurde, entfernt wird.

#### <a name="group-assignment-ranking"></a>Gruppenzuordnungsrangfolge
 
Wenn Sie einer Gruppe eine Richtlinie zuweisen, geben Sie eine Rangfolge für die Gruppenzuweisung an. Dies wird verwendet, um zu bestimmen, welche Richtlinie ein Benutzer als effektive Richtlinie erben soll, wenn der Benutzer Mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen wird.

Die Gruppenzuordnungsrangfolge ist relativ zu anderen Gruppenzuordnungen desselben Typs. Wenn Sie beispielsweise eine Anrufrichtlinie zwei Gruppen zuweisen, legen Sie die Rangfolge einer Aufgabe auf "1" und die andere auf "2" und "1" auf "2" als höchste Rangfolge ab. Die Gruppenzuordnungsrangfolge gibt an, welche Gruppenmitgliedschaft im Hinblick auf die Vererbung wichtiger oder relevanter als andere Gruppenmitgliedschaften ist.
 
Sie haben z. B. zwei Gruppen: "Mitarbeiter des Ladengeschäfts" und "Ladenmanager". Beiden Gruppen ist eine Anrufrichtlinie für Teams, die Anrufrichtlinie für Mitarbeiter der Filialen bzw. die Anrufrichtlinie für Ladenmanager zugewiesen. Für einen Store-Manager, der in beiden Gruppen ist, ist ihre Rolle als Manager relevanter als ihre Rolle als Mitarbeiter. Daher sollte die Anrufrichtlinie, die der Gruppe "Ladenleiter" zugewiesen ist, eine höhere Rangfolge haben.

|Gruppe |Name der Anrufrichtlinie in Teams  |Rang|
|---------|---------|---|
|Store Manager   |Anrufrichtlinie für Store-Manager         |1|
|Mitarbeiter des Ladengeschäfts    |Anrufrichtlinie für Mitarbeiter der Filialen      |2|

Wenn Sie keine Bewertung angeben, wird die Richtlinienzuweisung die niedrigste Bewertung erhalten. 

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

> [!NOTE]
> Derzeit ist die Richtlinienzuweisung an Gruppen, die das Microsoft Teams Admin Center verwenden, nur für Anrufrichtlinie für Teams, Teams-Anrufparkrichtlinie, Teams-Richtlinie, Teams-Liveereignisse-Richtlinie, Microsoft Teams-Besprechungsrichtlinie und Microsoft Teams-Messaging-Richtlinie verfügbar. Verwenden Sie PowerShell für andere Richtlinientypen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zur Seite "Richtlinientyp". Wechseln Sie beispielsweise zu **Besprechungsrichtlinien** für  >  **Besprechungen.**
2. Wählen Sie die **Registerkarte "Gruppenrichtlinienzuordnung"** aus.
3. Wählen **Sie "Gruppe hinzufügen"** aus, und gehen Sie dann im Bereich "Richtlinie zu Gruppe **zuweisen"** wie folgt vor:
    1. Suchen Sie nach der Gruppe, der Sie die Richtlinie zuweisen möchten, und fügen Sie sie hinzu.
    2. Legen Sie die Rangfolge für die Gruppenzuweisung an.
    3. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten. 
    4. Wählen Sie **"Übernehmen"** aus.

Um eine Gruppenrichtlinienzuweisung zu  entfernen, wählen Sie auf der Registerkarte "Gruppenrichtlinienzuordnung" auf der Seite "Richtlinie" die Gruppenzuweisung und dann "Entfernen" **aus.**

Um die Bewertung einer Gruppenzuordnung zu ändern, müssen Sie zuerst die Gruppenrichtlinienzuordnung entfernen. Führen Sie dann die vorstehenden Schritte aus, um die Richtlinie einer Gruppe zuzuordnen.

### <a name="using-powershell"></a>Verwendung von PowerShell

> [!NOTE]
> Derzeit ist die Richtlinienzuweisung zu Gruppen, die PowerShell verwenden, nicht für alle Teams-Richtlinientypen verfügbar. Eine Liste der unterstützten Richtlinientypen finden Sie unter ["New-CsGroupPolicyAssignment".](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams -PowerShell-Modul

Eine schrittweise Anleitung finden Sie unter ["Installieren von Teams PowerShell".](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>Zuweisen einer Richtlinie zu einer Benutzergruppe

Sie verwenden das [Cmdlet "New-CsGroupPolicyAssignment",](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) um einer Gruppe eine Richtlinie zuzuweisen. Sie können eine Gruppe mithilfe der Objekt-ID, der SIP-Adresse oder der E-Mail-Adresse angeben.

In diesem Beispiel weisen wir einer Gruppe mit der Aufgabenrangfolge "1" eine Team-Besprechungsrichtlinie namens "Einzelhandelsmanager-Besprechungsrichtlinie" zu.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Erhalten von Richtlinienzuweisungen für eine Gruppe

Verwenden Sie [das Cmdlet "Get-CsGroupPolicyAssignment",](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) um alle Richtlinien einer Gruppe zuzuweisen. Beachten Sie, dass Gruppen immer nach ihrer Gruppen-ID aufgelistet werden, auch wenn deren SIP-Adresse oder E-Mail-Adresse zum Zuweisen der Richtlinie verwendet wurde.

In diesem Beispiel rufen wir alle Richtlinien ab, die einer bestimmten Gruppe zugewiesen sind.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

In diesem Beispiel geben wir alle Gruppen zurück, denen eine Besprechungsrichtlinie für Teams zugewiesen ist.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Entfernen einer Richtlinie aus einer Gruppe

Verwenden Sie [das Cmdlet "Remove-CsGroupPolicyAssignment",](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) um eine Richtlinie aus einer Gruppe zu entfernen. Wenn Sie eine Richtlinie aus einer Gruppe entfernen, werden die Prioritäten anderer Richtlinien desselben Typs, die dieser Gruppe zugewiesen sind und eine niedrigere Rangfolge haben, aktualisiert. Wenn Sie z. B. eine Richtlinie entfernen, die eine Rangfolge von 2 hat, werden Richtlinien mit einer Rangfolge von 3 und 4 aktualisiert, um ihre neue Rangfolge widerspiegeln. In den beiden folgenden Tabellen ist dieses Beispiel dargestellt.

Hier ist eine Liste der Richtlinienzuweisungen und Prioritäten für eine Teams-Besprechungsrichtlinie.

|Gruppenname  |Richtlinienname  |Rang|
|---------|---------|---------|
|Vertrieb    |Vertriebsrichtlinie       | 1        |
|West Region     |Richtlinie "Region Westen"         |2         |
|Division    |Abteilungsrichtlinie         |3         |
|Niederlassung   |Richtlinien für Niederlassungen        |4         |

Wenn wir die Richtlinie "Region Westen" aus der Gruppe "Region Westen" entfernen, werden die Richtlinienzuweisungen und -prioritäten wie folgt aktualisiert.

|Gruppenname  |Richtlinienname  |Rang|
|---------|---------|---------|
|Vertrieb    |Vertriebsrichtlinie       | 1        |
|Division    |Abteilungsrichtlinie         |2         |
|Niederlassung   |Richtlinien für Niederlassungen        |3        |

In diesem Beispiel entfernen wir die Besprechungsrichtlinie für Teams aus einer Gruppe.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Ändern einer Richtlinienzuweisung für eine Gruppe

> [!NOTE]
> Das [Cmdlet "Set-CsGroupPolicyAssignment"](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) wird in Kürze zur Verfügung stehen. In der Zwischenzeit können Sie zum Ändern einer Gruppenrichtlinienzuweisung die aktuelle Richtlinienzuweisung aus der Gruppe entfernen und dann eine neue Richtlinienzuweisung hinzufügen.

Nachdem Sie einer Gruppe eine Richtlinie zugewiesen haben, können Sie das [Cmdlet "Set-CsGroupPolicyAssignment"](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) verwenden, um die Richtlinienzuweisung dieser Gruppe wie folgt zu ändern:

- Ändern der Rangfolge
- Ändern der Richtlinie eines bestimmten Richtlinientyps
- Ändern der Richtlinie eines bestimmten Richtlinientyps und der Rangfolge

In diesem Beispiel ändern wir die Anruf parkrichtlinie für Teams einer Gruppe in eine Richtlinie namens "SupportCallPark" und die Zuweisungsrangfolge in "3".

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Ändern der effektiven Richtlinie für einen Benutzer

Hier ist ein Beispiel für das Ändern der effektiven Richtlinie für einen Benutzer, dem eine Richtlinie direkt zugewiesen ist.

Zuerst verwenden wir das [Cmdlet "Get-CsUserPolicyAssignment"](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) zusammen mit dem Parameter, um Details zu den Richtlinien für Liveübertragungen in Teams zu erhalten, die dem ```PolicySource``` Benutzer zugeordnet sind. 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

Die Ausgabe zeigt, dass dem Benutzer direkt eine Teams-Liveübertragungsrichtlinie namens "Mitarbeiterereignisse" zugewiesen wurde, die Vorrang vor der Richtlinie namens "Vendor Live Events" hat, die einer Gruppe zugewiesen ist, der der Benutzer angehört.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Jetzt entfernen wir die Richtlinie "Mitarbeiterereignisse" vom Benutzer. Dies bedeutet, dass dem Benutzer keine Richtlinie für Liveereignisse in Teams mehr direkt zugewiesen ist und die Richtlinie "Anbieter-Liveereignisse" erbt, die der Gruppe zugewiesen ist, der der Benutzer angehört. 

Verwenden Sie dazu das folgende Cmdlet im Skype for Business PowerShell-Modul.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Sie können das folgende Cmdlet im Teams -PowerShell-Modul verwenden, um dies im Maßstab einer Batchrichtlinienzuordnung zu erreichen, wobei $users eine Liste von Benutzern ist, die Sie angeben.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Zuweisen einer Richtlinie zu einer Gruppe von Benutzern

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

So weisen Sie Benutzern eine Richtlinie als Massenrichtlinie zu:

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers **"Benutzer" aus.**
2. Suchen Sie nach den Benutzern, den Sie die Richtlinie zuweisen möchten, oder filtern Sie die Ansicht so, dass die von Ihnen gesuchten Benutzer angezeigt werden.
3. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).
4. Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.

Klicken Sie zum Anzeigen des Status Ihrer Richtlinienzuweisung im  Banner oben auf  der Seite "Benutzer", nachdem Sie auf "Übernehmen" klicken, um Ihre Richtlinienzuweisung zu übermitteln, auf **"Aktivitätsprotokoll".** Oder wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zum **Dashboard,** und klicken Sie dann unter "Aktivitätsprotokoll" auf **"Details** **anzeigen".** Im Aktivitätsprotokoll werden Richtlinienzuweisungen zu Gruppen von mehr als 20 Benutzern aus den letzten 30 Tagen über das Microsoft Teams Admin Center angezeigt. Weitere Informationen finden Sie unter [Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll.](activity-log.md)

### <a name="using-powershell"></a>Verwendung von PowerShell

> [!NOTE]
> Derzeit ist die Batchrichtlinienzuweisung mithilfe von PowerShell nicht für alle Richtlinientypen von Teams verfügbar. Eine Liste der unterstützten Richtlinientypen finden Sie unter ["New-CsBatchPolicyAssignmentOperation".](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
 
Mit der Batchrichtlinienzuweisung können Sie großen Gruppen von Benutzern gleichzeitig eine Richtlinie zuweisen, ohne ein Skript verwenden zu müssen. Sie verwenden das [Cmdlet "New-CsBatchPolicyAssignmentOperation",](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) um eine Gruppe von Benutzern und die Richtlinie zu übermitteln, die Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert. Anschließend können Sie das [Cmdlet "Get-CsBatchPolicyAssignmentOperation"](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) verwenden, um den Fortschritt und Status der Aufgaben in einem Batch zu verfolgen.

Sie können Benutzer nach ihrer Objekt-ID oder der Sip-Adresse (Session Initiation Protocol) angeben. Beachten Sie, dass die SIP-Adresse eines Benutzers häufig den gleichen Wert wie der Benutzerprinzipalname (User Principal Name, UPN) oder die E-Mail-Adresse hat, dies ist jedoch nicht erforderlich. Wenn ein Benutzer mit dem UPN oder der E-Mail-Adresse angegeben wird, dieser aber einen anderen Wert als seine SIP-Adresse hat, kann die Richtlinienzuweisung für den Benutzer nicht ausgeführt werden. Wenn ein Batch doppelte Benutzer enthält, werden die Duplikate vor der Verarbeitung aus dem Batch entfernt, und der Status wird nur für die eindeutigen Benutzer bereitgestellt, die im Batch verblieben sind. 

Ein Batch kann bis zu 5.000 Benutzer umfassen. Um optimale Ergebnisse zu erzielen, übermitteln Sie nicht mehr als ein paar Batches gleichzeitig. Lassen Sie zu, dass Batches die Verarbeitung abschließen, bevor weitere Batches übermittelt werden.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams -PowerShell-Modul

Führen Sie Folgendes aus, um das [Microsoft Teams -PowerShell-Modul zu installieren.](https://www.powershellgallery.com/packages/MicrosoftTeams) Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie Folgendes aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installieren und Herstellen einer Verbindung mit dem Azure AD PowerShell for Graph-Modul (optional)

Möglicherweise möchten Sie auch das [Azure AD PowerShell for](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) Graph-Modul herunterladen und installieren (sofern noch nicht vorhanden) und eine Verbindung mit Azure AD herstellen, damit Sie eine Liste der Benutzer in Ihrer Organisation abrufen können.

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Azure AD herzustellen.

```powershell
Connect-AzureAD
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit den gleichen Administratoranmeldeinformationen an, mit denen Sie eine Verbindung mit Teams hergestellt haben.

#### <a name="assign-a-policy-to-a-batch-of-users"></a>Zuweisen einer Richtlinie zu einer Gruppe von Benutzern

In diesem Beispiel verwenden wir das [Cmdlet "New-CsBatchPolicyAssignmentOperation",](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) um einer Gruppe von Benutzern, die in der Datei "Users_ids.text" aufgeführt sind, eine App-Setuprichtlinie namens "HR-App-Setuprichtlinie" zuzuweisen.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

In diesem Beispiel stellen wir eine Verbindung mit Azure AD bereit, um eine Sammlung von Benutzern abzurufen, und weisen dann einer Gruppe von Benutzern, die über ihre SIP-Adresse angegeben wurden, eine Messagingrichtlinie mit dem Namen "Messagingrichtlinie für neue Mitarbeiter" zu.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Anzeigen des Status einer Batchzuordnung

Führen Sie Folgendes aus, um den Status einer Batchzuordnung zu erhalten, wobei "OperationId" die Vorgangs-ID ist, die vom Cmdlet für einen bestimmten ```New-CsBatchPolicyAssignmentOperation``` Batch zurückgegeben wird.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie Folgendes aus, um weitere Informationen zu Fehlern zu erhalten, die sich in der Eigenschaft ```UserState``` befinden.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Weitere Informationen finden Sie unter ["Get-CsBatchPolicyAssignmentOperation".](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="assign-a-policy-package-to-users"></a>Zuweisen eines Richtlinienpakets zu Benutzern

Ein Richtlinienpaket in Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die in Ihrer Organisation über die gleichen oder ähnliche Rollen verfügen. Jedes Richtlinienpaket ist auf eine Benutzerrolle ausgelegt und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die für diese Rolle typische Aktivitäten unterstützen. Einige Beispiele für Richtlinienpakete sind das Bildungspaket (Lehrer) und das Paket für Gesundheitswesen (Klinischer Mitarbeiter). Weitere Informationen finden Sie unter ["Verwalten von Richtlinienpaketen in Teams".](manage-policy-packages.md)

### <a name="assign-a-policy-package-to-one-user"></a>Zuweisen eines Richtlinienpakets zu einem Benutzer

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Klicken Sie auf der Seite des Benutzers auf  "Richtlinien", und klicken Sie dann neben "Richtlinienpaket" auf **"Bearbeiten".**
3. Wählen Sie **im Bereich "Richtlinienpaket zuweisen"** das Paket aus, das Sie zuweisen möchten, und klicken Sie dann auf **"Speichern".**

### <a name="assign-a-policy-package-to-multiple-users"></a>Zuweisen eines Richtlinienpakets zu mehreren Benutzern

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu "Richtlinienpakete", und wählen Sie dann das Richtlinienpaket aus, das Sie zuweisen möchten, indem Sie links neben dem Paketnamen klicken.
2. Klicken Sie **auf "Benutzer verwalten".**
3. Suchen Sie im Bereich **Nutzer verwalten** anhand des Anzeigenamens oder des Nutzernamens nach dem Nutzer, wählen Sie den Namen und dann **Hinzufügen** aus. Wiederholen Sie diesen Schritt für jeden Nutzer, den Sie hinzufügen möchten.
4. Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.

## <a name="assign-a-policy-package-to-a-group"></a>Ein Richtlinienpaket einer Gruppe zuweisen

**Dieses Feature ist derzeit lediglich als private Vorschau verfügbar**

Die Gruppenzuweisung von Richtlinienpaketen ermöglicht es Ihnen, mehrere Richtlinien einer Gruppe von Benutzern wie z. B. einer Sicherheitsgruppe oder einer Verteilerliste zuzuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.

Die Zuweisung von Richtlinienpaketen zu Gruppen wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, funktioniert aber auch mit größeren Gruppen. 

Wenn Sie das Richtlinienpaket zuweisen, wird es sofort der Gruppe zugewiesen. Beachten Sie jedoch, dass die Weitergabe der Richtlinienzuweisung an Mitglieder der Gruppe als Hintergrundvorgang ausgeführt wird und je nach Größe der Gruppe einige Zeit dauern kann. Dasselbe gilt, wenn eine Richtlinie nicht mehr einer Gruppe zugewiesen wird oder Wenn Mitglieder zu einer Gruppe hinzugefügt oder aus ihr entfernt werden.

> [!IMPORTANT]
> Bevor Sie beginnen, ist es wichtig, die [Rangfolgeregeln und](#precedence-rules) die Rangfolge von [Gruppenzuweisungen zu verstehen.](#group-assignment-ranking) Lesen und verstehen Sie die Konzepte in ["Wichtige](#what-you-need-to-know-about-policy-assignment-to-groups) Informationen zur Richtlinienzuweisung zu Gruppen weiter oben in diesem Artikel".

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a>Verwenden des Microsoft Teams Admin Centers (in Kürze verfügbar)

Die Zuweisung von Richtlinienpaketen zu Gruppen im Microsoft Teams Admin Center wird in Kürze folgen. Hier finden Sie die neuesten Updates.

### <a name="using-powershell"></a>Verwendung von PowerShell

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams -PowerShell-Modul

Eine schrittweise Anleitung finden Sie unter ["Installieren von Teams PowerShell".](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Zuweisen eines Richtlinienpakets zu einer Benutzergruppe

Sie verwenden das [Cmdlet Grant-CsGroupPolicyPackageAssignment,](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) um einer Gruppe ein Richtlinienpaket zuzuweisen. Sie können eine Gruppe mithilfe der Objekt-ID, der SIP-Adresse oder der E-Mail-Adresse angeben. Wenn Sie das Richtlinienpaket zuweisen, geben Sie eine [Gruppenzuordnungsrangfolge](#group-assignment-ranking) für jeden Richtlinientyp im Richtlinienpaket an. 

In diesem Beispiel weisen wir das Richtlinienpaket Education_Teacher einer Gruppe mit der Zuweisungsrangfolge 1 für TeamsAppSetupPolicy und TeamsMeetingBroadcastPolicy und der Rangfolge 2 für TeamsMeetingPolicy zu.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern

Mit der Batchrichtlinienpaketzuweisung können Sie großen Gruppen von Benutzern gleichzeitig ein Richtlinienpaket zuweisen, ohne ein Skript verwenden zu müssen. Sie verwenden das [Cmdlet "New-CsBatchPolicyAssignmentOperation",](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) um eine Gruppe von Benutzern und das Richtlinienpaket zu übermitteln, das Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert. Anschließend können Sie das [Cmdlet "Get-CsBatchPolicyAssignmentOperation"](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) verwenden, um den Fortschritt und Status der Aufgaben in einem Batch zu verfolgen.

Sie können Benutzer nach ihrer Objekt-ID oder der Sip-Adresse (Session Initiation Protocol) angeben. Beachten Sie, dass die SIP-Adresse eines Benutzers häufig den gleichen Wert wie der Benutzerprinzipalname (User Principal Name, UPN) oder die E-Mail-Adresse hat, dies ist jedoch nicht erforderlich. Wenn ein Benutzer mit dem UPN oder der E-Mail-Adresse angegeben wird, dieser aber einen anderen Wert als seine SIP-Adresse hat, kann die Richtlinienzuweisung für den Benutzer nicht ausgeführt werden. Wenn ein Batch doppelte Benutzer enthält, werden die Duplikate vor der Verarbeitung aus dem Batch entfernt, und der Status wird nur für die eindeutigen Benutzer bereitgestellt, die im Batch verblieben sind. 

Ein Batch kann bis zu 5.000 Benutzer umfassen. Um optimale Ergebnisse zu erzielen, übermitteln Sie nicht mehr als ein paar Batches gleichzeitig. Lassen Sie zu, dass Batches die Verarbeitung abschließen, bevor weitere Batches übermittelt werden.

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams -PowerShell-Modul

Führen Sie Folgendes aus, um das [Microsoft Teams -PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern noch nicht vorhanden). Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie Folgendes aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

### <a name="assign-a-policy-package-to-a-batch-of-users"></a>Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern

In diesem Beispiel verwenden wir das [Cmdlet "New-CsBatchPolicyAssignmentOperation",](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) um das Education_PrimaryStudent Richtlinienpaket einem Batch von Benutzern zuzuweisen.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a>Anzeigen des Status einer Batchzuordnung

Führen Sie Folgendes aus, um den Status einer Batchzuordnung zu erhalten, wobei "OperationId" die Vorgangs-ID ist, die vom Cmdlet für einen bestimmten ```New-CsBatchPolicyAssignmentOperation``` Batch zurückgegeben wird.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie Folgendes aus, um weitere Informationen zu Fehlern zu erhalten, die sich in der Eigenschaft ```UserState``` befinden.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Weitere Informationen finden Sie unter ["Get-CsBatchPolicyAssignmentOperation".](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) 

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
