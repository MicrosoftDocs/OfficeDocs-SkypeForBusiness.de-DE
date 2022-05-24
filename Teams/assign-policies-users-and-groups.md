---
title: Zuweisen von Richtlinien zu Benutzern und Gruppen
author: mkbond007
ms.author: mabond
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Lernen Sie die verschiedenen Methoden zum Zuweisen von Richtlinien zu Benutzern und Gruppen in Microsoft Teams kennen.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 60d3835a3cdda752dab0305b68b68e91446e10d7
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646434"
---
# <a name="assign-policies-to-users-and-groups"></a>Zuweisen von Richtlinien zu Benutzern und Gruppen

In diesem Artikel werden die verschiedenen Methoden zum Zuweisen von Richtlinien zu Benutzern und Gruppen in Microsoft Teams beschrieben. Stellen Sie vor dem Lesen sicher, dass Sie ["Richtlinien zuweisen" in Teams gelesen haben – erste Schritte](policy-assignment-overview.md).

## <a name="assign-a-policy-to-individual-users"></a>Zuweisen einer Richtlinie zu einzelnen Benutzern

Führen Sie die folgenden Schritte aus, um einem einzelnen Benutzer oder einer kleinen Anzahl von Benutzern gleichzeitig eine Richtlinie zuzuweisen.

### <a name="use-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

So weisen Sie einem Benutzer eine Richtlinie zu:

1. Wechseln Sie in der linken Navigationsleiste des [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) zu **UsersManage** >  users.
2. Wählen Sie den Benutzer aus, indem Sie links neben dem Benutzernamen klicken, und wählen Sie dann " **Einstellungen bearbeiten"** aus.
3. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, und wählen Sie dann **"Übernehmen"** aus.

![Weisen Sie einem Benutzer im Teams Admin Center eine Richtlinie zu.](media/assign-policy-user.png)

> [!NOTE]
> Um die Zuweisung einer speziellen Richtlinie von einem Benutzer aufzuheben, können Sie jede Richtlinie auf **"Global" (organisationsweite Standardeinstellung)** festlegen.

Sie können auch die folgenden Schritte ausführen, um einem Benutzer eine Richtlinie zuzuweisen:

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zur Richtlinienseite.
2. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, indem Sie links neben dem Richtliniennamen klicken.
3. Wählen Sie **Nutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
5. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **"Übernehmen"** aus.

![Weisen Sie einem Benutzer im Teams Admin Center über die zweite Methode eine Richtlinie zu.](media/assign-policy-user2.png)

### <a name="use-powershell"></a>Verwenden von PowerShell

Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets für die Verwaltung. Verwenden Sie das `Grant-` Cmdlet für einen bestimmten Richtlinientyp, um die Richtlinie zuzuweisen. Verwenden Sie beispielsweise das `Grant-CsTeamsMeetingPolicy` Cmdlet, um Benutzern eine Teams Besprechungsrichtlinie zuzuweisen. Diese Cmdlets sind im Teams PowerShell-Modul enthalten und in der [Skype for Business Cmdlet-Referenz](/powershell/skype) dokumentiert.

 Laden Sie die [Teams öffentlichen PowerShell-Version](https://www.powershellgallery.com/packages/MicrosoftTeams/) herunter, installieren Sie sie (falls noch nicht geschehen), und führen Sie dann die folgenden Schritte aus, um eine Verbindung herzustellen.

> [!NOTE]
> Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams.
>
> Wenn Sie die neueste [Teams öffentlichen PowerShell-Version](https://www.powershellgallery.com/packages/MicrosoftTeams/) verwenden, müssen Sie den Skype for Business Online Connector nicht installieren.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

In diesem Beispiel weisen wir einem Benutzer mit dem Namen "Reda" eine Teams Besprechungsrichtlinie mit dem Namen "Richtlinie für Schülerbesprechungen" zu.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Weitere Informationen finden Sie [unter Verwalten von Richtlinien über PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).

## <a name="assign-a-policy-to-a-group"></a>Zuweisen einer Richtlinie zu einer Gruppe

Mithilfe der Richtlinienzuweisung zu Gruppen können Sie einer Benutzergruppe eine Richtlinie zuweisen, z. B. einer Sicherheitsgruppe, einer Organisationseinheit oder einer Verteilerliste. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.

Die Richtlinienzuweisung zu Gruppen wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, funktioniert aber auch mit größeren Gruppen.

Wenn Sie die Richtlinie zuweisen, wird sie sofort der Gruppe zugewiesen. Die Weitergabe der Richtlinienzuweisung an Mitglieder der Gruppe wird jedoch als Hintergrundvorgang ausgeführt und kann je nach Größe der Gruppe einige Zeit in Anspruch nehmen. Dasselbe gilt, wenn eine Richtlinie einer Gruppe nicht zugewiesen wird oder wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden.

Gruppenrichtlinienzuweisungen werden nur an Benutzer weitergegeben, die direkte Mitglieder der Gruppe sind. Die Zuweisungen werden nicht an Mitglieder geschachtelter Gruppen weitergegeben.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Was Sie über die Richtlinienzuweisung zu Gruppen wissen müssen

Bevor Sie beginnen, ist es wichtig, die Rangfolgeregeln und die Rangfolge der Gruppenzuweisungen zu verstehen.

#### <a name="precedence-rules"></a>Rangfolgeregeln

Für einen bestimmten Richtlinientyp wird die effektive Richtlinie eines Benutzers wie folgt bestimmt:

- Eine Richtlinie, die einem Benutzer direkt zugewiesen ist, hat Vorrang vor jeder anderen Richtlinie desselben Typs, die einer Gruppe zugewiesen ist. Mit anderen Worten: Wenn einem Benutzer direkt eine Richtlinie eines bestimmten Typs zugewiesen wird, erbt dieser Benutzer keine Richtlinie desselben Typs von einer Gruppe. Dies bedeutet auch, dass Sie, wenn ein Benutzer über eine Richtlinie eines bestimmten Typs verfügt, die ihm direkt zugewiesen wurde, diese Richtlinie vom Benutzer entfernen müssen, bevor er eine Richtlinie desselben Typs von einer Gruppe erben kann.
- Wenn einem Benutzer keine Richtlinie direkt zugewiesen ist und mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen ist, erbt der Benutzer die Richtlinie der Gruppenzuweisung, die die höchste Rangfolge aufweist.
- Wenn ein Benutzer kein Mitglied von Gruppen ist, denen eine Richtlinie zugewiesen ist, gilt die globale (organisationsweite Standardrichtlinie) für diesen Richtlinientyp für den Benutzer.

Die effektive Richtlinie eines Benutzers wird gemäß den folgenden Regeln aktualisiert:

- wenn ein Benutzer einer Gruppe hinzugefügt oder daraus entfernt wird, der eine Richtlinie zugewiesen ist.
- eine Richtlinie einer Gruppe nicht zugewiesen ist.
- Eine Richtlinie, die dem Benutzer direkt zugewiesen ist, wird entfernt.

#### <a name="group-assignment-ranking"></a>Gruppenzuordnungsrangfolge

> [!NOTE]
> Ein bestimmter Richtlinientyp kann maximal 64 Gruppen in allen Richtlinieninstanzen für diesen Typ zugewiesen werden.

Wenn Sie einer Gruppe eine Richtlinie zuweisen, geben Sie eine Rangfolge für die Gruppenzuweisung an. Dies wird verwendet, um zu bestimmen, welche Richtlinie ein Benutzer als effektive Richtlinie erben soll, wenn der Benutzer Mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen ist.

Die Rangfolge der Gruppenzuweisungen ist relativ zu anderen Gruppenzuweisungen desselben Typs. Wenn Sie beispielsweise zwei Gruppen eine Anrufrichtlinie zuweisen, legen Sie die Rangfolge einer Aufgabe auf 1 und die andere auf 2 fest, wobei 1 die höchste Rangfolge ist. Die Gruppenzuordnungsbewertung gibt an, welche Gruppenmitgliedschaft im Hinblick auf die Vererbung wichtiger oder relevanter ist als andere Gruppenmitgliedschaften.

Angenommen, Sie haben zwei Gruppen, Store Mitarbeiter und Store Manager. Beiden Gruppen wird eine Teams Anrufrichtlinie zugewiesen, Store Mitarbeiteranrufrichtlinie bzw. Store Manager-Anrufrichtlinie. Für einen Store-Manager, der sich in beiden Gruppen befindet, ist ihre Rolle als Manager relevanter als ihre Rolle als Mitarbeiter. Daher sollte die Anrufrichtlinie, die der Gruppe Store Manager zugewiesen ist, eine höhere Rangfolge aufweisen.

|Gruppe |Teams des Namens der Anrufrichtlinie  |Rang|
|---------|---------|---|
|Store Manager   |anrufrichtlinie für Store-Manager         |1|
|Store Mitarbeiter    |anrufrichtlinie für Store Mitarbeiter      |2|

Wenn Sie keine Rangfolge angeben, wird der Richtlinienzuweisung die niedrigste Rangfolge zugewiesen.

### <a name="in-the-teams-admin-center"></a>Im Teams Admin Center

> [!NOTE]
> Derzeit ist die Richtlinienzuweisung zu Gruppen, die das Microsoft Teams Admin Center verwenden, nur für Teams Anrufrichtlinie, Teams Anrufparkrichtlinie, Teams Richtlinie, Teams Richtlinie für Liveereignisse, Teams Besprechungsrichtlinie und Teams Messagingrichtlinie verfügbar. Verwenden Sie für andere Richtlinientypen PowerShell.

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zur Seite "Richtlinientyp". Wechseln Sie beispielsweise zu **MeetingsMeeting-Richtlinien** > .
2. Wählen Sie die Registerkarte " **Gruppenrichtlinienzuweisung** " aus.
3. Wählen Sie **"Gruppe hinzufügen"** aus, und führen Sie dann im **Gruppenbereich "Richtlinie zuweisen** " die folgenden Schritte aus:
    1. Suchen Sie nach der Gruppe, der Sie die Richtlinie zuweisen möchten, und fügen Sie sie hinzu.
    2. Legen Sie die Rangfolge für die Gruppenzuweisung fest.
    3. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten.
    4. Wählen Sie **"Übernehmen" aus**.
    
![Weisen Sie einer Gruppe im Teams Admin Center eine Richtlinie zu.](media/assign-policy-group.png)

Um eine Gruppenrichtlinienzuweisung zu entfernen, wählen Sie auf der Registerkarte " **Gruppenrichtlinienzuweisung** " der Richtlinienseite die Gruppenzuweisung und dann " **Entfernen"** aus.

Um die Rangfolge einer Gruppenzuweisung zu ändern, müssen Sie zuerst die Gruppenrichtlinienzuweisung entfernen. Führen Sie dann die vorstehenden Schritte aus, um die Richtlinie einer Gruppe zuzuweisen.

### <a name="use-the-powershell-option"></a>Verwenden der PowerShell-Option

> [!NOTE]
> Derzeit ist die Richtlinienzuweisung zu Gruppen, die PowerShell verwenden, nicht für alle Teams Richtlinientypen verfügbar. Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) .

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

Eine schrittweise Anleitung finden [Sie unter "Installieren Teams PowerShell](teams-powershell-install.md)".

#### <a name="assign-a-policy-to-a-group-of-users"></a>Zuweisen einer Richtlinie zu einer Gruppe von Benutzern

Verwenden Sie das Cmdlet [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) , um einer Gruppe eine Richtlinie zuzuweisen. Sie können eine Gruppe mithilfe der Objekt-ID, SIP-Adresse oder E-Mail-Adresse angeben.

In diesem Beispiel weisen wir einer Gruppe mit der Zuordnungsrangfolge 1 eine Teams Besprechungsrichtlinie namens "Retail Managers Meeting Policy" zu.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Abrufen von Richtlinienzuweisungen für eine Gruppe

Verwenden Sie das Cmdlet ["Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) ", um alle Richtlinien abzurufen, die einer Gruppe zugewiesen sind. Beachten Sie, dass Gruppen immer nach ihrer Gruppen-ID aufgeführt werden, auch wenn ihre SIP-Adresse oder E-Mail-Adresse zum Zuweisen der Richtlinie verwendet wurde.

In diesem Beispiel rufen wir alle Richtlinien ab, die einer bestimmten Gruppe zugewiesen sind.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

In diesem Beispiel geben wir alle Gruppen zurück, denen eine Teams Besprechungsrichtlinie zugewiesen ist.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Entfernen einer Richtlinie aus einer Gruppe

Verwenden Sie das Cmdlet [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) , um eine Richtlinie aus einer Gruppe zu entfernen. Wenn Sie eine Richtlinie aus einer Gruppe entfernen, werden die Prioritäten anderer Richtlinien desselben Typs aktualisiert, die dieser Gruppe zugewiesen sind und eine niedrigere Rangfolge aufweisen. Wenn Sie z. B. eine Richtlinie mit der Rangfolge 2 entfernen, werden Richtlinien mit der Rangfolge 3 und 4 aktualisiert, um deren neue Rangfolge widerzuspiegeln. Die folgenden beiden Tabellen zeigen dieses Beispiel.

Hier ist eine Liste der Richtlinienzuweisungen und Prioritäten für eine Teams Besprechungsrichtlinie.

|Gruppenname  |Richtlinienname  |Rang|
|---------|---------|---------|
|Vertrieb    |Vertriebsrichtlinie       | 1        |
|West Region     |Politik der Region West         |2         |
|Aufteilung    |Abteilungsrichtlinie         |3         |
|Tochtergesellschaft   |Subsidiäre Richtlinie        |4         |

Wenn wir die Richtlinie "Westregion" aus der Gruppe "Westregion" entfernen, werden die Richtlinienzuweisungen und Prioritäten wie folgt aktualisiert.

|Gruppenname  |Richtlinienname  |Rang|
|---------|---------|---------|
|Vertrieb    |Vertriebsrichtlinie       | 1        |
|Aufteilung    |Abteilungsrichtlinie         |2         |
|Tochtergesellschaft   |Subsidiäre Richtlinie        |3        |

In diesem Beispiel wird die Teams Besprechungsrichtlinie aus einer Gruppe entfernt.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Ändern einer Richtlinienzuweisung für eine Gruppe

> [!NOTE]
> Das [Cmdlet Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) wird in Kürze verfügbar sein. In der Zwischenzeit können Sie zum Ändern einer Gruppenrichtlinienzuweisung die aktuelle Richtlinienzuweisung aus der Gruppe entfernen und dann eine neue Richtlinienzuweisung hinzufügen.

Nachdem Sie einer Gruppe eine Richtlinie zugewiesen haben, können Sie das Cmdlet [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) verwenden, um die Richtlinienzuweisung dieser Gruppe wie folgt zu ändern:

- Ändern der Rangfolge
- Ändern der Richtlinie eines bestimmten Richtlinientyps
- Ändern der Richtlinie eines bestimmten Richtlinientyps und der Rangfolge

In diesem Beispiel ändern wir die Richtlinie für das Teams Parken von Anrufen einer Gruppe in eine Richtlinie namens "SupportCallPark" und die Zuordnungsrangfolge in "3".

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Ändern der effektiven Richtlinie für einen Benutzer

Hier ist ein Beispiel für das Ändern der effektiven Richtlinie für einen Benutzer, dem eine Richtlinie direkt zugewiesen ist.

Zunächst verwenden wir das Cmdlet ["Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment)" zusammen mit dem `PolicySource` Parameter, um Details der dem Benutzer zugeordneten Teams Besprechungsübertragungsrichtlinien abzurufen.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

Die Ausgabe zeigt, dass dem Benutzer direkt eine Teams Richtlinie für Besprechungsübertragungen mit dem Namen "Mitarbeiterereignisse" zugewiesen wurde, die Vorrang vor der Richtlinie namens "Vendor Live Events" hat, die einer Gruppe zugewiesen ist, zu der der Benutzer gehört.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Jetzt entfernen wir die Richtlinie für Mitarbeiterereignisse vom Benutzer. Dies bedeutet, dass dem Benutzer keine Teams Richtlinie für Besprechungsübertragungen direkt zugewiesen ist und die Richtlinie "Vendor Live Events" erbt, die der Gruppe zugewiesen ist, zu der der Benutzer gehört.

Verwenden Sie dazu das folgende Cmdlet im Skype for Business PowerShell-Modul.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Verwenden Sie das folgende Cmdlet im Teams PowerShell-Modul, um dies bei einer Batchrichtlinienzuweisung im großen Maßstab zu tun, wobei $users eine Liste von Benutzern ist, die Sie angeben.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Zuweisen einer Richtlinie zu einer Gruppe von Benutzern

### <a name="use-the-admin-center"></a>Verwenden des Admin Centers

So weisen Sie Benutzern massenhaft eine Richtlinie zu:

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center **"Benutzer**" aus.
2. Suchen Sie nach den Benutzern, den Sie die Richtlinie zuweisen möchten, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.
3. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).
4. Wählen Sie **"Einstellungen bearbeiten"** aus, nehmen Sie die gewünschten Änderungen vor, und wählen Sie dann **"Übernehmen"** aus.

Um den Status Ihrer Richtlinienzuweisung anzuzeigen, wählen Sie im Banner, das oben auf der Seite **"Benutzer** " angezeigt wird, nachdem Sie " **Übernehmen"** ausgewählt haben, um Ihre Richtlinienzuweisung zu übermitteln, **"Aktivitätsprotokoll**" aus. Oder wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zu **Dashboard**, und wählen Sie dann unter **"Aktivitätsprotokoll**" die Option "**Details anzeigen"** aus. Das Aktivitätsprotokoll zeigt Richtlinienzuweisungen zu Batches von mehr als 20 Benutzern über das Microsoft Teams Admin Center der letzten 30 Tage an. Weitere Informationen finden [Sie unter Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll](activity-log.md).

### <a name="use-powershell-method"></a>Verwenden der PowerShell-Methode

> [!NOTE]
> Derzeit ist die Batchrichtlinienzuweisung mithilfe von PowerShell nicht für alle Teams Richtlinientypen verfügbar. Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) .

Mit der Batchrichtlinienzuweisung können Sie eine Richtlinie gleichzeitig großen Gruppen von Benutzern zuweisen, ohne ein Skript verwenden zu müssen. Sie verwenden das Cmdlet ["New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) ", um eine Reihe von Benutzern und die Richtlinie zu übermitteln, die Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert. Anschließend können Sie das Cmdlet ["Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) " verwenden, um den Fortschritt und Status der Zuordnungen in einem Batch nachzuverfolgen.

Geben Sie Benutzer anhand ihrer Objekt-ID oder SIP-Adresse (Session Initiation Protocol) an. Die SIP-Adresse eines Benutzers hat häufig denselben Wert wie der Benutzerprinzipalname (User Principal Name, UPN) oder die E-Mail-Adresse, dies ist jedoch nicht erforderlich. Wenn ein Benutzer mithilfe seines UPN oder seiner E-Mail angegeben wird, aber einen anderen Wert als seine SIP-Adresse aufweist, schlägt die Richtlinienzuweisung für den Benutzer fehl. Wenn ein Batch doppelte Benutzer enthält, werden die Duplikate vor der Verarbeitung aus dem Batch entfernt, und der Status wird nur für die im Batch verbleibenden eindeutigen Benutzer bereitgestellt.

Ein Batch kann bis zu 5.000 Benutzer umfassen. Um optimale Ergebnisse zu erzielen, übermitteln Sie nicht mehr als ein paar Batches gleichzeitig. Zulassen, dass Batches die Verarbeitung abschließen, bevor weitere Batches gesendet werden.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Teams PowerShell-Modul

Führen Sie die folgenden Schritte aus, um das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren. Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie Folgendes aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installieren und Herstellen einer Verbindung mit azure AD PowerShell für Graph Modul (optional)

Möglicherweise möchten Sie auch [azure AD PowerShell für Graph Modul herunterladen und installieren](/powershell/azure/active-directory/install-adv2) (falls noch nicht geschehen), und eine Verbindung mit Azure AD herstellen, damit Sie eine Liste der Benutzer in Ihrer Organisation abrufen können.

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Azure AD herzustellen.

```powershell
Connect-AzureAD
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit denselben Administratoranmeldeinformationen an, die Sie zum Herstellen einer Verbindung mit Teams verwendet haben.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Zuweisen einer Setuprichtlinie zu einer Gruppe von Benutzern

In diesem Beispiel verwenden wir das Cmdlet ["New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) ", um einer Gruppe von Benutzern, die in der Datei "users_ids.text" aufgeführt sind, eine App-Setuprichtlinie namens "HR App Setup Policy" zuzuweisen.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $user_ids -OperationName "Example 1 batch"
```

In diesem Beispiel stellen wir eine Verbindung mit Azure AD her, um eine Sammlung von Benutzern abzurufen und dann einer Gruppe von Benutzern, die mithilfe ihrer SIP-Adresse angegeben werden, eine Messagingrichtlinie mit dem Namen "New Hire Messaging Policy" zuzuweisen.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Abrufen des Status einer Batchzuordnung

Führen Sie Folgendes aus, um den Status einer Batchzuordnung abzurufen, wobei "OperationId" die Vorgangs-ID ist, die `New-CsBatchPolicyAssignmentOperation` vom Cmdlet für einen bestimmten Batch zurückgegeben wird.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie Folgendes aus, um weitere Informationen zu Fehlern zu erhalten, die sich in der `UserState` Eigenschaft befinden.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Teams mit Richtlinien](manage-teams-with-policies.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien in Teams – erste Schritte](policy-assignment-overview.md)
