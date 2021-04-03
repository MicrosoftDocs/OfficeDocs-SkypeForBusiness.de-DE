---
title: Zuweisen von Richtlinien zu Benutzern und Gruppen
author: KarliStites
ms.author: kastites
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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie mehr über die verschiedenen Methoden zum Zuweisen von Richtlinien zu Benutzern und Gruppen in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 6b0db8c3da93e561bf374b32d08750d705ded8a2
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574320"
---
# <a name="assign-policies-to-users-and-groups"></a>Zuweisen von Richtlinien zu Benutzern und Gruppen

In diesem Artikel werden die verschiedenen Methoden zum Zuweisen von Richtlinien zu Benutzern und Gruppen in Microsoft Teams beschrieben. Stellen Sie vor dem Lesen sicher, dass Sie Richtlinien in Teams zuweisen gelesen haben [– erste Schritte.](policy-assignment-overview.md)

## <a name="assign-a-policy-to-individual-users"></a>Zuweisen einer Richtlinie zu einzelnen Benutzern

Führen Sie die folgenden Schritte aus, um einem einzelnen Benutzer oder einer kleinen Anzahl von Benutzern gleichzeitig eine Richtlinie zuzuordnen.

### <a name="use-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

So weisen Sie einem Benutzer eine Richtlinie zu:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Benutzer**, und wählen Sie dann den Benutzer aus.
2. Wählen Sie den Benutzer aus, indem Sie links vom Benutzernamen klicken und dann **Einstellungen bearbeiten auswählen.**
3. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, und wählen Sie dann **Übernehmen aus.**

![Zuweisen einer Richtlinie zu einem Benutzer im Teams Admin Center](media/assign-policy-user.png)

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zur Richtlinienseite.
2. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, indem Sie links vom Richtliniennamen klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
5. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Übernehmen aus.**

![Zuweisen einer Richtlinie zu einem Benutzer im Teams Admin Center über eine zweite Methode](media/assign-policy-user2.png)

### <a name="use-powershell"></a>Verwenden von PowerShell

Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets für die Verwaltung. Verwenden Sie ```Grant-``` das Cmdlet für einen bestimmten Richtlinientyp, um die Richtlinie zuzuordnen. Verwenden Sie beispielsweise das ```Grant-CsTeamsMeetingPolicy``` Cmdlet, um Benutzern eine Teams-Besprechungsrichtlinie zuzuordnen. Diese Cmdlets sind im Teams PowerShell-Modul enthalten und in der [Skype for Business-Cmdletreferenz dokumentiert.](https://docs.microsoft.com/powershell/skype)

 Laden Sie die öffentliche [Version von Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) herunter, installieren Sie sie (falls noch nicht), und führen Sie dann die folgenden Schritte aus, um eine Verbindung herzustellen.

> [!NOTE]
> Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams.
>
> Wenn Sie die neueste öffentliche Version von [Teams PowerShell verwenden,](https://www.powershellgallery.com/packages/MicrosoftTeams/)müssen Sie den Skype for Business Online Connector nicht installieren.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

In diesem Beispiel weisen wir einem Benutzer namens Reda eine Teams-Besprechungsrichtlinie mit dem Namen Student Meeting Policy zu.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Weitere Informationen finden Sie unter [Verwalten von Richtlinien über PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).

## <a name="assign-a-policy-to-a-group"></a>Zuweisen einer Richtlinie zu einer Gruppe

Mit der Richtlinienzuordnung zu Gruppen können Sie einer Gruppe von Benutzern, z. B. einer Sicherheitsgruppe oder Verteilerliste, eine Richtlinie zuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.

Die Richtlinienzuweisung zu Gruppen wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, funktioniert aber auch mit größeren Gruppen.

Wenn Sie die Richtlinie zuweisen, wird sie der Gruppe sofort zugewiesen. Die Weitergabe der Richtlinienzuordnung an Die Mitglieder der Gruppe wird jedoch als Hintergrundvorgang ausgeführt und kann je nach Größe der Gruppe einige Zeit dauern. Das gleiche gilt, wenn eine Richtlinie nicht aus einer Gruppe zugewiesen wird oder wenn Mitglieder zu einer Gruppe hinzugefügt oder aus dieser entfernt werden.

Gruppenrichtlinienzuordnungen werden nur an Benutzer übertragen, die direkte Mitglieder der Gruppe sind. Die Zuordnungen werden nicht an Mitglieder geschachtelter Gruppen übertragen.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Was Sie über die Richtlinienzuordnung zu Gruppen wissen müssen

Bevor Sie beginnen, ist es wichtig, Rangfolgeregeln und Gruppenzuordnungsbewertungen zu verstehen.

#### <a name="precedence-rules"></a>Rangfolgeregeln

Für einen bestimmten Richtlinientyp wird die effektive Richtlinie eines Benutzers wie folgt bestimmt:

- Eine Richtlinie, die einem Benutzer direkt zugewiesen ist, hat Vorrang vor jeder anderen Richtlinie desselben Typs, die einer Gruppe zugewiesen ist. Anders ausgedrückt: Wenn einem Benutzer eine Richtlinie eines bestimmten Typs direkt zugewiesen ist, erbt dieser Benutzer keine Richtlinie desselben Typs von einer Gruppe. Dies bedeutet auch, dass Sie eine Richtlinie eines bestimmten Typs, die dem Benutzer direkt zugewiesen wurde, vom Benutzer entfernen müssen, bevor er eine Richtlinie desselben Typs von einer Gruppe erben kann.
- Wenn einem Benutzer keine Richtlinie direkt zugewiesen ist und ein Mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen ist, erbt der Benutzer die Richtlinie der Gruppenzuordnung mit der höchsten Rangfolge.
- Wenn ein Benutzer kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, gilt die globale (organisationsweite Standardrichtlinie) für diesen Richtlinientyp für den Benutzer.

Die effektive Richtlinie eines Benutzers wird gemäß den folgenden Regeln aktualisiert:

- wenn ein Benutzer einer Gruppe hinzugefügt oder aus dieser entfernt wird, der eine Richtlinie zugewiesen ist.
- Eine Richtlinie wird aus einer Gruppe nicht zugewiesen.
- eine Richtlinie, die dem Benutzer direkt zugewiesen ist, wird entfernt.

#### <a name="group-assignment-ranking"></a>Gruppenzuordnungsrangliste

Wenn Sie einer Gruppe eine Richtlinie zuweisen, geben Sie eine Rangfolge für die Gruppenzuordnung an. Dies wird verwendet, um zu bestimmen, welche Richtlinie ein Benutzer als effektive Richtlinie erben soll, wenn der Benutzer Mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen ist.

Die Gruppenzuordnungsrangliste ist relativ zu anderen Gruppenzuordnungen desselben Typs. Wenn Sie z. B. eine Anrufrichtlinie zwei Gruppen zuweisen, legen Sie die Rangfolge einer Aufgabe auf 1 und die andere auf 2, und 1 ist die höchste Bewertung. Die Gruppenzuordnungsrangliste gibt an, welche Gruppenmitgliedschaft im Hinblick auf die Vererbung wichtiger oder relevanter als andere Gruppenmitgliedschaften ist.

Sie verfügen beispielsweise über zwei Gruppen: "Mitarbeiter im Store" und "Store Manager". Beiden Gruppen wird eine Anrufrichtlinie für Teams, eine Anrufrichtlinie für Store-Mitarbeiter und eine Anrufrichtlinie für Store-Manager zugewiesen. Für einen Filialleiter, der sich in beiden Gruppen befindet, ist ihre Rolle als Vorgesetzter relevanter als ihre Rolle als Mitarbeiter. Daher sollte die Anrufrichtlinie, die der Gruppe "Store-Manager" zugewiesen ist, eine höhere Rangfolge haben.

|Gruppe |Name der Anrufrichtlinie von Teams  |Rang|
|---------|---------|---|
|Store-Manager   |Anrufrichtlinie für Store-Manager         |1|
|Mitarbeiter im Store    |Anrufrichtlinie für Mitarbeiter speichern      |2|

Wenn Sie keine Bewertung angeben, wird der Richtlinienzuordnung die niedrigste Bewertung gegeben.

### <a name="in-the-teams-admin-center"></a>Im Teams Admin Center

> [!NOTE]
> Derzeit ist die Richtlinienzuweisung an Gruppen, die das Microsoft Teams Admin Center verwenden, nur für Anrufrichtlinien, Anrufrichtlinien für Anrufer in Teams, Teams-Anrufparkrichtlinie, Teams-Liveereignisse-Richtlinie, Teams-Besprechungsrichtlinie und Teams-Messagingrichtlinie verfügbar. Verwenden Sie powerShell für andere Richtlinientypen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zur Seite Richtlinientyp. Wechseln Sie beispielsweise zu **Besprechungsrichtlinien** für  >  **Besprechungen.**
2. Wählen Sie die **Registerkarte Gruppenrichtlinienzuordnung** aus.
3. Wählen **Sie Gruppe hinzufügen** aus, und gehen Sie dann im Gruppenbereich Richtlinie **zuweisen** wie folgt vor:
    1. Suchen Sie nach der Gruppe, der Sie die Richtlinie zuweisen möchten, und fügen Sie sie hinzu.
    2. Legen Sie die Rangfolge für die Gruppenzuordnung ein.
    3. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten.
    4. Wählen Sie **Übernehmen aus.**
    
![Zuweisen einer Richtlinie zu einer Gruppe im Teams Admin Center](media/assign-policy-group.png)

Wenn Sie eine Gruppenrichtlinienzuordnung entfernen möchten, wählen Sie auf der Registerkarte **Gruppenrichtlinienzuordnung** auf der Seite Richtlinie die Gruppenzuordnung und dann **Entfernen aus.**

Um die Rangfolge einer Gruppenzuordnung zu ändern, müssen Sie zuerst die Gruppenrichtlinienzuordnung entfernen. Führen Sie dann die vorstehenden Schritte aus, um die Richtlinie einer Gruppe zuzuordnen.

### <a name="use-the-powershell-option"></a>Verwenden der PowerShell-Option

> [!NOTE]
> Derzeit ist die Richtlinienzuordnung zu Gruppen, die PowerShell verwenden, nicht für alle Teams-Richtlinientypen verfügbar. Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsGroupPolicyAssignment.](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

Schrittweise Anleitungen finden Sie unter [Installieren von Teams PowerShell](teams-powershell-install.md).

#### <a name="assign-a-policy-to-a-group-of-users"></a>Zuweisen einer Richtlinie zu einer Gruppe von Benutzern

Verwenden Sie [das Cmdlet New-CsGroupPolicyAssignment,](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) um einer Gruppe eine Richtlinie zuzuweisen. Sie können eine Gruppe mithilfe der Objekt-ID, DER SIP-Adresse oder der E-Mail-Adresse angeben.

In diesem Beispiel weisen wir einer Gruppe mit der Zuordnungsrangfolge 1 eine Teams-Besprechungsrichtlinie namens Einzelhandelsmanager-Besprechungsrichtlinie zu.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Erhalten von Richtlinienzuweisungen für eine Gruppe

Verwenden Sie [das Cmdlet Get-CsGroupPolicyAssignment,](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) um alle Richtlinien zu erhalten, die einer Gruppe zugewiesen sind. Beachten Sie, dass Gruppen immer nach ihrer Gruppen-ID aufgelistet werden, auch wenn die SIP-Adresse oder E-Mail-Adresse zum Zuweisen der Richtlinie verwendet wurde.

In diesem Beispiel rufen wir alle Richtlinien ab, die einer bestimmten Gruppe zugewiesen sind.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

In diesem Beispiel geben wir alle Gruppen zurück, denen eine Teams-Besprechungsrichtlinie zugewiesen ist.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Entfernen einer Richtlinie aus einer Gruppe

Verwenden Sie [das Cmdlet Remove-CsGroupPolicyAssignment,](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) um eine Richtlinie aus einer Gruppe zu entfernen. Wenn Sie eine Richtlinie aus einer Gruppe entfernen, werden die Prioritäten anderer Richtlinien desselben Typs, die dieser Gruppe zugewiesen sind und eine niedrigere Rangfolge haben, aktualisiert. Wenn Sie z. B. eine Richtlinie entfernen, die die Rangfolge 2 hat, werden Richtlinien mit der Bewertung 3 und 4 aktualisiert, um deren neue Rangfolge widerspiegeln zu können. In den folgenden beiden Tabellen wird dieses Beispiel dargestellt.

Hier finden Sie eine Liste der Richtlinienzuweisungen und Prioritäten für eine Teams-Besprechungsrichtlinie.

|Gruppenname  |Richtlinienname  |Rang|
|---------|---------|---------|
|Vertrieb    |Vertriebsrichtlinie       | 1        |
|Region "Westen"     |Richtlinie "Westliche Region"         |2         |
|Division    |Divisionsrichtlinie         |3         |
|Tochtergesellschaft   |Nebenrichtlinie        |4         |

Wenn wir die Richtlinie "Westliche Region" aus der Gruppe "Region West" entfernen, werden die Richtlinienzuordnungen und -prioritäten wie folgt aktualisiert.

|Gruppenname  |Richtlinienname  |Rang|
|---------|---------|---------|
|Vertrieb    |Vertriebsrichtlinie       | 1        |
|Division    |Divisionsrichtlinie         |2         |
|Tochtergesellschaft   |Nebenrichtlinie        |3        |

In diesem Beispiel entfernen wir die Teams-Besprechungsrichtlinie aus einer Gruppe.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Ändern einer Richtlinienzuordnung für eine Gruppe

> [!NOTE]
> Das [Cmdlet Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) wird in Kürze verfügbar sein. Wenn Sie in der Zwischenzeit eine Gruppenrichtlinienzuordnung ändern möchten, können Sie die aktuelle Richtlinienzuordnung aus der Gruppe entfernen und dann eine neue Richtlinienzuordnung hinzufügen.

Nachdem Sie einer Gruppe eine Richtlinie zugewiesen haben, können Sie das [Cmdlet Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) verwenden, um die Richtlinienzuordnung dieser Gruppe wie folgt zu ändern:

- Ändern der Bewertung
- Ändern der Richtlinie eines bestimmten Richtlinientyps
- Ändern der Richtlinie eines bestimmten Richtlinientyps und der Bewertung

In diesem Beispiel ändern wir die Anrufparkrichtlinie einer Gruppe in eine Richtlinie mit dem Namen SupportCallPark und die Zuordnungsrangliste in 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Ändern der effektiven Richtlinie für einen Benutzer

Hier sehen Sie ein Beispiel, wie Sie die effektive Richtlinie für einen Benutzer ändern, dem eine Richtlinie direkt zugewiesen ist.

Zuerst verwenden wir das [Cmdlet Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) zusammen mit dem Parameter, um Details zu den Teams-Liveübertragungsrichtlinien zu erhalten, die dem Benutzer ```PolicySource``` zugeordnet sind.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

Die Ausgabe zeigt, dass dem Benutzer direkt eine Liveübertragungsrichtlinie für Teams mit dem Namen "Mitarbeiterereignisse" zugewiesen wurde, die Vorrang vor der Richtlinie namens Vendor Live Events hat, die einer Gruppe zugewiesen ist, der der Benutzer angehört.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Jetzt entfernen wir die Richtlinie "Mitarbeiterereignisse" vom Benutzer. Dies bedeutet, dass dem Benutzer keine Liveübertragungsrichtlinie für Teams mehr direkt zugewiesen ist und er die Richtlinie "Vendor Live Events" erbt, die der Gruppe zugewiesen ist, der der Benutzer angehört.

Verwenden Sie dazu das folgende Cmdlet im Skype for Business PowerShell-Modul.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Verwenden Sie das folgende Cmdlet im Teams PowerShell-Modul, um dies mithilfe einer Batchrichtlinienzuordnung zu erreichen, wobei $users eine Von Ihnen festgelegte Liste von Benutzern ist.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Zuweisen einer Richtlinie zu einer Gruppe von Benutzern

### <a name="use-the-admin-center"></a>Verwenden des Admin Centers

So weisen Sie Benutzern eine Richtlinie in Massen zu:

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers Die Option **Benutzer aus.**
2. Suchen Sie nach den Benutzern, deren Richtlinie Sie zuweisen möchten, oder filtern Sie die Ansicht, um die Benutzer zu sehen, die Sie möchten.
3. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).
4. Wählen **Sie Einstellungen bearbeiten** aus, nehmen Sie die von Ihnen ausgewählten Änderungen vor, und wählen Sie dann Übernehmen **aus.**

Wenn Sie den Status Ihrer Richtlinienzuordnung anzeigen möchten, wählen  Sie im  Banner, das oben auf der Seite Benutzer angezeigt wird, nachdem Sie Übernehmen zum Übermitteln ihrer Richtlinienzuordnung ausgewählt haben, **Aktivitätsprotokoll aus.** Oder wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Dashboard,** und wählen Sie dann unter Aktivitätsprotokoll die Option **Details anzeigen aus.** Im Aktivitätsprotokoll werden Richtlinienzuordnungen zu Batches von mehr als 20 Benutzern über das Microsoft Teams Admin Center aus den letzten 30 Tagen angezeigt. Weitere Informationen finden Sie unter [Anzeigen Ihrer Richtlinienzuordnungen im Aktivitätsprotokoll.](activity-log.md)

### <a name="use-powershell-method"></a>Verwenden der PowerShell-Methode

> [!NOTE]
> Derzeit ist die Batchrichtlinienzuordnung mit PowerShell nicht für alle Teams-Richtlinientypen verfügbar. Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Bei der Batchrichtlinienzuordnung können Sie große Benutzergruppen gleichzeitig eine Richtlinie zuweisen, ohne ein Skript verwenden zu müssen. Sie verwenden das [Cmdlet New-CsBatchPolicyAssignmentOperation,](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) um einen Batch von Benutzern und die Richtlinie zu übermitteln, die Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert. Anschließend können Sie das [Cmdlet Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) verwenden, um den Fortschritt und Status der Zuordnungen in einem Batch nachverfolgt zu haben.

Geben Sie Benutzer nach ihrer Objekt-ID oder der SIP-Adresse (Session Initiation Protocol) an. Die SIP-Adresse eines Benutzers hat häufig denselben Wert wie der User Principal Name (UPN) oder die E-Mail-Adresse, aber dies ist nicht erforderlich. Wenn ein Benutzer mit dem UPN oder der E-Mail angegeben wird, aber einen anderen Wert als seine SIP-Adresse hat, kann die Richtlinienzuweisung für den Benutzer fehlschlagen. Wenn ein Batch doppelte Benutzer enthält, werden die Duplikate vor der Verarbeitung aus dem Batch entfernt, und der Status wird nur für die eindeutigen Benutzer bereitgestellt, die im Batch verblieben sind.

Ein Batch kann bis zu 5.000 Benutzer umfassen. Um optimale Ergebnisse zu erzielen, reichen Sie nicht mehr als ein paar Batches gleichzeitig ein. Zulassen, dass Batches die Verarbeitung abschließen, bevor Sie weitere Batches übermitteln.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Teams PowerShell-Modul

Führen Sie folgendes aus, um das [Microsoft Teams PowerShell-Modul zu installieren.](https://www.powershellgallery.com/packages/MicrosoftTeams) Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installieren und Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul (optional)

Möglicherweise möchten Sie auch das [Azure AD PowerShell für Graph-Modul](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) herunterladen und installieren (sofern noch nicht vorhanden) und eine Verbindung mit Azure AD herstellen, damit Sie eine Liste der Benutzer in Ihrer Organisation abrufen können.

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Azure AD herzustellen.

```powershell
Connect-AzureAD
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit den gleichen Administratoranmeldeinformationen an, die Sie zum Herstellen einer Verbindung mit Teams verwendet haben.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Zuweisen einer Einrichtungsrichtlinie zu einer Gruppe von Benutzern

In diesem Beispiel verwenden wir das [Cmdlet New-CsBatchPolicyAssignmentOperation,](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) um einer Gruppe von Benutzern, die in der Datei "Users_ids.text" aufgeführt sind, eine App-Setuprichtlinie mit dem Namen Hr App Setup Policy zuzuweisen.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

In diesem Beispiel stellen wir eine Verbindung mit Azure AD bereit, um eine Sammlung von Benutzern abzurufen, und weisen dann einer Gruppe von Benutzern, die mithilfe ihrer SIP-Adresse angegeben wurden, eine Nachrichtenrichtlinie mit dem Namen New Hire Messaging Policy zu.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Erhalten des Status einer Batchzuordnung

Führen Sie folgendes aus, um den Status einer Batchzuordnung zu erhalten, wobei "OperationId" die Vorgangs-ID ist, die vom Cmdlet für einen bestimmten ```New-CsBatchPolicyAssignmentOperation``` Batch zurückgegeben wird.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie folgendes aus, um weitere Informationen zu Fehlern zu erhalten, die sich in der -Eigenschaft ```UserState``` befinden.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Teams mit Richtlinien](manage-teams-with-policies.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien in Teams – erste Schritte](policy-assignment-overview.md)
