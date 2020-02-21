---
title: Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag
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
description: Informieren Sie sich über die verschiedenen Möglichkeiten, wie Sie Ihren Benutzern in Microsoft Teams Richtlinien zuweisen können.
f1keywords: ''
ms.openlocfilehash: cb1c5fd43379388327de5e517409f01f7f52ed1b
ms.sourcegitcommit: d7be89019dd5a3b88b0840bddf1b88fea8598ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170761"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams

> [!NOTE]
> **Zwei der in diesem Artikel beschriebenen Features von Microsoft Teams, die Zuweisung von [Batch Richtlinien](#assign-a-policy-to-a-batch-of-users) und die [Richtlinienzuweisung zu Gruppen](#assign-a-policy-to-a-group), befinden sich derzeit in der Vorschau.**

Als Administrator verwenden Sie Richtlinien, um die Teamfunktionen zu steuern, die Benutzern in Ihrer Organisation zur Verfügung stehen. So gibt es beispielsweise Anruf Richtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen.

Organisationen verfügen über unterschiedliche Arten von Benutzern mit eindeutigen Anforderungen und benutzerdefinierten Richtlinien, die Sie erstellen und zuweisen, damit Sie die Richtlinieneinstellungen basierend auf den Anforderungen an unterschiedliche Benutzergruppen anpassen können.

Um das Verwalten von Richtlinien in Ihrer Organisation zu vereinfachen, bietet Teams verschiedene Möglichkeiten, Richtlinien für Benutzer zuzuweisen. Sie können Benutzern eine Richtlinie entweder einzeln oder im Maßstab über eine Batch Zuordnung oder einer Gruppe, der der Benutzer angehört, direkt zuweisen. Sie können auch Richtlinien Pakete verwenden, um Benutzern in Ihrer Organisation, die über ähnliche Rollen verfügen, eine vordefinierte Sammlung von Richtlinien zuzuweisen. Die von Ihnen ausgewählte Option richtet sich nach der Anzahl der Richtlinien, die Sie verwalten, und der Anzahl der Benutzer, denen Sie zuweisen.

In diesem Artikel werden die verschiedenen Möglichkeiten beschrieben, wie Sie Benutzern Richtlinien zuweisen können, sowie die empfohlenen Szenarien für die Verwendung von was.

## <a name="which-policy-takes-precedence"></a>Welche Richtlinie hat Vorrang?

Ein Benutzer verfügt über eine gültige Richtlinie für die einzelnen Richtlinientypen. Es ist möglich oder sogar wahrscheinlich, dass einem Benutzer direkt eine Richtlinie zugewiesen wird, und er ist auch ein Mitglied einer oder mehrerer Gruppen, denen eine Richtlinie desselben Typs zugewiesen ist. Welche Richtlinie hat in diesen Szenarien Vorrang?  Die effektive Richtlinie eines Benutzers wird wie folgt gemäß den Regeln für die Rangfolge bestimmt.

Wenn einem Benutzer direkt eine Richtlinie zugewiesen wird (entweder einzeln oder über eine Batch Zuordnung), hat diese Richtlinie Vorrang. Im folgenden Beispiel ist die effektive Richtlinie des Benutzers die Lincoln Square-Besprechungsrichtlinie, die dem Benutzer direkt zugewiesen ist.

![Diagramm, das zeigt, wie eine direkt zugewiesene Richtlinie Vorrang hat](media/assign-policies-example-directly-assigned.png)

Wenn einem Benutzer keine Richtlinie eines bestimmten Typs direkt zugewiesen wird, hat die der Gruppe zugewiesene Richtlinie Vorrang. Wenn ein Benutzer ein Mitglied mehrerer Gruppen ist, hat die Richtlinie, die die höchste [Gruppen Zuordnungs Rangfolge](#group-assignment-ranking) für den angegebenen Richtlinientyp aufweist, Vorrang.

In diesem Beispiel ist die effektive Richtlinie des Benutzers die Exec Teams-und HD-Richtlinie, die die höchste Zuordnungs Rangfolge relativ zu anderen Gruppen aufweist, in der der Benutzer Mitglied ist und dem auch eine Richtlinie desselben Richtlinientyps zugewiesen ist.  

![Diagramm, das zeigt, wie eine von Group geerbte Richtlinie Vorrang hat](media/assign-policies-example-group.png)

Wenn einem Benutzer keine Richtlinie direkt zugewiesen wurde oder kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, erhält der Benutzer die globale (organisationsweite Standardrichtlinie) für diesen Richtlinientyp. Hier ist ein Beispiel.

![Diagramm, das zeigt, wie eine globale Richtlinie Vorrang hat](media/assign-policies-example-global.png)

Weitere Informationen finden Sie unter [Prioritätsregeln](#precedence-rules).

## <a name="ways-to-assign-policies"></a>Methoden zum Zuweisen von Richtlinien

Im folgenden finden Sie eine Übersicht über die Methoden zum Zuweisen von Richtlinien zu Benutzern sowie zu den empfohlenen Szenarien für die einzelnen Benutzer. Klicken Sie auf die Links, um weitere Informationen zu erhalten.

|Tun Sie dies  |Wenn...  | Verwenden von...
|---------|---------|----|
|[Zuweisen einer Richtlinie für einzelne Benutzer](#assign-a-policy-to-individual-users)    | Sie sind neu bei Microsoft Teams und haben gerade erst begonnen, oder Sie müssen nur einer kleinen Anzahl von Benutzern eine oder mehrere Richtlinien zuweisen. |Das Microsoft Teams Admin Center oder PowerShell-Cmdlets im Skype for Business Online PowerShell-Modul
| [Zuweisen eines Richtlinienpakets](#assign-a-policy-package)   | Sie müssen bestimmten Gruppen von Benutzern in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zuweisen. Weisen Sie beispielsweise Lehrern in Ihrer Bildungseinrichtung das Richtlinienpaket Education (Teacher) zu, um Ihnen den vollständigen Zugriff auf Chats, Anrufe und Besprechungen sowie das Richtlinienpaket Education (Secondary School Student) für sekundäre Schüler zu gewähren, um bestimmte Funktionen wie private Anrufe.  |Das Microsoft Teams Admin Center oder PowerShell-Cmdlets im PowerShell-Modul von Teams|
|[Zuweisen einer Richtlinie zu einem Batch von Benutzern](#assign-a-policy-to-a-batch-of-users) (in der Vorschau)   | Sie müssen einem umfangreichen Satz von Benutzern Richtlinien zuweisen. So möchten Sie beispielsweise Hunderten oder tausenden Benutzern in Ihrer Organisation gleichzeitig eine Richtlinie zuweisen.  |PowerShell-Cmdlets im PowerShell-Modul von Teams|
|[Zuweisen einer Richtlinie zu einer Gruppe](#assign-a-policy-to-a-group) (in der Vorschau)   |Sie müssen Richtlinien basierend auf der Gruppenmitgliedschaft eines Benutzers zuweisen. So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe oder Organisationseinheit eine Richtlinie zuweisen.| PowerShell-Cmdlets im PowerShell-Modul von Teams|
| Zuweisen eines Richtlinienpakets zu einem Batch von Benutzern (in Kürze verfügbar) |||
| Zuweisen eines Richtlinienpakets zu einer Gruppe (in Kürze verfügbar)   | ||

## <a name="assign-a-policy-to-individual-users"></a>Zuweisen einer Richtlinie für einzelne Benutzer

Führen Sie die folgenden Schritte aus, um einem einzelnen Benutzer oder einer kleinen Anzahl von Benutzern gleichzeitig eine Richtlinie zuzuweisen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

So weisen Sie einem Benutzer eine Richtlinie zu:

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.
2. Wählen Sie den Benutzer aus, indem Sie links neben dem Benutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.
3. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf über **nehmen**.

Wenn Sie bis zu 20 Benutzern gleichzeitig eine Richtlinie zuweisen möchten, lesen Sie [Bearbeiten der Benutzereinstellungen für Teams in Massen](edit-user-settings-in-bulk.md).

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zur Seite Richtlinie.
2. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, indem Sie links neben dem Richtliniennamen klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.
5. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Speichern**aus.

### <a name="using-powershell"></a>Verwenden von PowerShell

Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets zum Verwalten. Verwenden Sie ```Grant-``` das Cmdlet für einen bestimmten Richtlinientyp, um die Richtlinie zuzuweisen. Verwenden Sie beispielsweise das ```Grant-CsTeamsMeetingPolicy``` Cmdlet, um Benutzern eine Teams-Besprechungsrichtlinie zuzuweisen. Diese Cmdlets sind Bestandteil des Skype for Business Online PowerShell-Moduls und werden im [Skype for Business-Cmdlet Reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)dokumentiert.

 Laden Sie das [Skype for Business Online PowerShell-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366) herunter, und installieren Sie es (falls noch nicht geschehen), und führen Sie dann die folgenden Schritte aus, um eine Verbindung mit Skype for Business Online herzustellen und eine Sitzung zu starten.

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

In diesem Beispiel weisen wir eine Teams-Besprechungsrichtlinie mit dem Namen "Student-Besprechungsrichtlinie" einem Benutzer mit dem Namen "Sie" zu.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Weitere Informationen finden Sie unter [Verwalten von Richtlinien über PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).

## <a name="assign-a-policy-package"></a>Zuweisen eines Richtlinienpakets

Ein Richtlinienpaket in Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die über die gleichen oder ähnlichen Rollen in Ihrer Organisation verfügen. Jedes Richtlinienpaket ist auf eine Benutzerrolle zugeschnitten und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die für diese Rolle typische Aktivitäten unterstützen. Einige Beispiele für Richtlinien Pakete sind das Paket "Education (Teacher)" und "Healthcare (Clinical Worker)".

Wenn Sie Benutzern ein Richtlinienpaket zuweisen, werden die Richtlinien im Paket erstellt, und Sie können dann die Einstellungen jeder Richtlinie im Paket anpassen, um die Anforderungen der Benutzer zu erfüllen.

Weitere Informationen zu Richtlinien Paketen, einschließlich Schritt-für-Schritt-Anleitungen zum Zuweisen und Verwalten dieser Pakete, finden Sie unter [Verwalten von Richtlinien Paketen in Teams](manage-policy-packages.md).

## <a name="assign-a-policy-to-a-batch-of-users"></a>Zuweisen einer Richtlinie zu einem Benutzer Batch

[!INCLUDE [preview-feature](includes/preview-feature.md)]
 
Mit der Batch Richtlinienzuweisung können Sie eine Richtlinie für große Benutzergruppen gleichzeitig zuweisen, ohne ein Skript verwenden zu müssen. Sie verwenden das ```New-CsBatchPolicyAssignmentOperationd``` Cmdlet, um einen Benutzer Batch und die Richtlinie, die Sie zuweisen möchten, zu übermitteln. Die Aufgaben werden als Hintergrundvorgang verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert. Anschließend können Sie das ```Get-CsBatchPolicyAssignmentOperation``` Cmdlet verwenden, um den Fortschritt und den Status der Aufgaben in einem Batch zu verfolgen.

Ein Batch kann bis zu 20.000-Benutzer enthalten. Sie können Benutzer nach ihrer Objekt-ID, dem Benutzerprinzipalnamen (User Principal Name, UPN), der SIP-Adresse (Session Initiation Protocol) oder der e-Mail-Adresse angeben.

> [!NOTE]
> Derzeit steht die Zuweisung von Batch Richtlinien für alle Teams-Richtlinientypen nicht zur Verfügung. Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) .

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

> [!NOTE]
> Die Cmdlets befinden sich in der Pre-Release-Version des Teams PowerShell-Moduls. Führen Sie die folgenden Schritte aus, um zunächst die allgemein verfügbare Version des Teams PowerShell-Moduls (sofern installiert) zu deinstallieren, und installieren Sie dann die neueste Vorabversion des Moduls aus dem PowerShell-Test Katalog.

Wenn Sie dies noch nicht getan haben, führen Sie die folgenden Schritte aus, um den PowerShell-Test Katalog als vertrauenswürdige Quelle zu registrieren.

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

Wenn Sie die allgemein verfügbare Version des Teams PowerShell-Moduls installiert haben, führen Sie die folgenden Schritte aus, um Sie zu deinstallieren.

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

Führen Sie die folgenden Schritte aus, um das aktuelle Microsoft Teams PowerShell-Modul aus dem PowerShell-Test Katalog zu installieren.

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installieren und Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul (optional)

Möglicherweise möchten Sie auch [das Azure AD PowerShell für Graph-Modul](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (falls noch nicht geschehen) herunterladen und installieren und eine Verbindung mit Azure AD herstellen, damit Sie eine Liste der Benutzer in Ihrer Organisation abrufen können.

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Azure AD herzustellen.

```powershell
Connect-AzureAD
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit denselben Administratoranmeldeinformationen an, die Sie für die Verbindung zu Teams verwendet haben.

### <a name="assign-a-policy-to-a-batch-of-users"></a>Zuweisen einer Richtlinie zu einem Benutzer Batch

In diesem Beispiel verwenden wir das ```New-CsBatchPolicyAssignmentOperation``` Cmdlet, um eine APP-Setup Richtlinie mit dem Namen "HR-App-Setup Richtlinie" einem Batch von Benutzern zuzuweisen, die in der Datei "Users_ids. Text" aufgeführt sind.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

In diesem Beispiel stellen wir eine Verbindung mit Azure AD her, um eine Sammlung von Benutzern abzurufen, und weisen dann eine Messagingrichtlinie mit dem Namen "New Hire Messaging Policy" einem Batch von Benutzern zu, die mithilfe Ihres UPNs angegeben wurden.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

Weitere Informationen finden Sie unter [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).

### <a name="get-the-status-of-a-batch-assignment"></a>Abrufen des Status einer Stapelverarbeitungs Zuordnung

Führen Sie die folgenden Schritte aus, um den Status einer Stapelverarbeitungs Zuweisung abzurufen, wobei Vorgangskennung die Vorgangs-ID ist ```New-CsBatchPolicyAssignmentOperation``` , die vom Cmdlet für einen bestimmten Batch zurückgegeben wird.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie die folgenden Schritte aus, um weitere Informationen zu ```UserState``` Fehlern zu erhalten, die in der Eigenschaft enthalten sind.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="assign-a-policy-to-a-group"></a>Zuweisen einer Richtlinie zu einer Gruppe

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Mit der Richtlinienzuweisung zu Gruppen können Sie einer Gruppe von Benutzern eine Richtlinie zuweisen, beispielsweise eine Sicherheitsgruppe oder eine Organisationseinheit. Die Richtlinienzuweisung wird nach Rangfolgeregeln an Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden Ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.

Sie verwenden das ```New-CsGroupPolicyAssignment``` Cmdlet, um einer Gruppe eine Richtlinie zuzuweisen. Sie können eine Gruppe mithilfe der Objekt-ID, der SIP-Adresse oder der e-Mail-Adresse angeben.

Wenn Sie die Richtlinie zuweisen, wird Sie sofort der Gruppe zugewiesen. Beachten Sie jedoch, dass die Verteilung der Richtlinienzuweisung an Mitglieder der Gruppe als Hintergrundvorgang ausgeführt wird und je nach Größe der Gruppe einige Zeit in Anspruch nehmen kann. Das gleiche gilt, wenn eine Richtlinie aus einer Gruppe nicht zugewiesen wird oder wenn Mitglieder einer Gruppe hinzugefügt oder aus ihr entfernt werden.

> [!NOTE]
> Derzeit steht die Richtlinienzuweisung zu Gruppen nicht für alle Teams-Richtlinientypen zur Verfügung. Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Was Sie über die Richtlinienzuweisung zu Gruppen wissen müssen

Bevor Sie beginnen, ist es wichtig, die Rangfolge von Prioritätsregeln und die Rangfolge von Gruppenaufgaben zu verstehen.

#### <a name="precedence-rules"></a>Rangfolgeregeln

Für einen bestimmten Richtlinientyp wird die effektive Richtlinie eines Benutzers entsprechend den folgenden Bedingungen bestimmt:

- Eine Richtlinie, die einem Benutzer direkt zugewiesen ist, hat Vorrang vor jeder anderen Richtlinie desselben Typs, die einer Gruppe zugewiesen ist. Anders ausgedrückt: Wenn einem Benutzer eine Richtlinie eines bestimmten Typs direkt zugewiesen wird, erbt dieser Benutzer keine Richtlinie desselben Typs aus einer Gruppe. Dies bedeutet auch, dass Sie diese Richtlinie vom Benutzer entfernen müssen, bevor Sie eine Richtlinie desselben Typs aus einer Gruppe erben können, wenn ein Benutzer über eine Richtlinie eines bestimmten Typs verfügt, der Ihnen direkt zugewiesen wurde.
- Wenn einem Benutzer nicht direkt eine Richtlinie zugewiesen wurde und es sich um ein Mitglied von zwei oder mehr Gruppen handelt und für jede Gruppe eine Richtlinie desselben Typs zugewiesen ist, erbt der Benutzer die Richtlinie der Gruppenaufgabe, die die höchste Rangfolge aufweist.
- Wenn ein Benutzer nicht Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, gilt die globale (organisationsweite Standardrichtlinie) für diesen Richtlinientyp für den Benutzer.

Die effektive Richtlinie eines Benutzers wird entsprechend diesen Regeln aktualisiert, wenn ein Benutzer zu einer Gruppe hinzugefügt oder daraus entfernt wird, der eine Richtlinie zugewiesen ist, eine Richtlinie von einer Gruppe nicht zugewiesen wird oder eine Richtlinie entfernt wird, die dem Benutzer direkt zugewiesen ist.

#### <a name="group-assignment-ranking"></a>Gruppen Zuordnungs Rangfolge
 
Wenn Sie einer Gruppe eine Richtlinie zuweisen, geben Sie eine Rangfolge für die Gruppenzuordnung an. Damit wird ermittelt, welche Richtlinie ein Benutzer als effektive Richtlinie erben soll, wenn der Benutzer ein Mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen ist.

Die Rangfolge der Gruppenzuweisungen ist relativ zu anderen Gruppenzuordnungen desselben Typs. Wenn Sie beispielsweise zwei Gruppen eine Anrufrichtlinie zuweisen, legen Sie die Rangfolge einer Zuordnung auf 1 und die andere auf 2, wobei 1 die höchste Rangliste ist. Die Gruppen Zuordnungs Rangfolge gibt an, welche Gruppenmitgliedschaft wichtiger oder relevanter als andere Gruppenmitgliedschaften im Hinblick auf die Vererbung ist.
 
Angenommen, Sie verfügen über zwei Gruppen, Store-Mitarbeiter und Store-Manager. Beiden Gruppen wird eine Anrufrichtlinie für Teams zugewiesen, und Sie können die Anruf Richtlinien für die Mitarbeiter und die Geschäftsmanager anrufen. Bei einem Store Manager, der sich in beiden Gruppen befindet, ist ihre Rolle als Manager relevanter als ihre Rolle als Mitarbeiter, sodass die Anrufrichtlinie, die der Gruppe Store Managers zugewiesen ist, eine höhere Rangfolge aufweisen sollte.

|Gruppe |Anruf Richtlinienname für Teams  |Rang|
|---------|---------|---|
|Store-Manager   |Anruf Richtlinien für Store-Manager         |1|
|Speichern von Mitarbeitern    |Speichern von Mitarbeiter Anruf Richtlinien      |2|

Wenn Sie kein Ranking angeben, erhält die Richtlinienzuweisung die niedrigste Rangfolge.

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

> [!NOTE]
> Die Cmdlets befinden sich in der Pre-Release-Version des Teams PowerShell-Moduls. Führen Sie die folgenden Schritte aus, um zunächst die allgemein verfügbare Version des Teams PowerShell-Moduls (sofern installiert) zu deinstallieren, und installieren Sie dann die neueste Vorabversion des Moduls aus dem PowerShell-Test Katalog.

Wenn Sie dies noch nicht getan haben, führen Sie die folgenden Schritte aus, um den PowerShell-Test Katalog als vertrauenswürdige Quelle zu registrieren.

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

Wenn Sie die allgemein verfügbare Version des Teams PowerShell-Moduls installiert haben, führen Sie die folgenden Schritte aus, um Sie zu deinstallieren.

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

Führen Sie die folgenden Schritte aus, um das aktuelle Microsoft Teams PowerShell-Modul aus dem PowerShell-Test Katalog zu installieren.

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

### <a name="assign-a-policy-to-a-group"></a>Zuweisen einer Richtlinie zu einer Gruppe

In diesem Beispiel verwenden wir das ```New-CsGroupPolicyAssignment``` Cmdlet, um einer Gruppe mit einer Zuordnungs Rangfolge von 1 eine Teams-Besprechungsrichtlinie mit dem Namen "Einzelhandels Manager-Besprechungsrichtlinie" zuzuweisen.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

Weitere Informationen finden Sie unter [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).

### <a name="get-policy-assignments-for-a-group"></a>Abrufen von Richtlinienzuweisungen für eine Gruppe

Verwenden Sie ```Get-CsGroupPolicyAssignment``` das Cmdlet, um alle Richtlinien abzurufen, die einer Gruppe zugewiesen sind. Beachten Sie, dass Gruppen immer nach ihrer Gruppen-ID aufgeführt werden, auch wenn die SIP-Adresse oder e-Mail-Adresse zum Zuweisen der Richtlinie verwendet wurde.

In diesem Beispiel rufen wir alle Richtlinien ab, die einer bestimmten Gruppe zugeordnet sind.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

In diesem Beispiel geben wir alle Gruppen zurück, denen eine Teams-Besprechungsrichtlinie zugewiesen ist.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

Weitere Informationen finden Sie unter [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).

### <a name="remove-a-policy-from-a-group"></a>Entfernen einer Richtlinie aus einer Gruppe

Verwenden Sie ```Remove-CsGroupPolicyAssignment``` das Cmdlet, um eine Richtlinie aus einer Gruppe zu entfernen. Wenn Sie eine Richtlinie aus einer Gruppe entfernen, werden die Prioritäten anderer Richtlinien desselben Typs, die dieser Gruppe zugewiesen sind und die eine niedrigere Rangfolge aufweisen, aktualisiert. Wenn Sie beispielsweise eine Richtlinie entfernen, die eine Rangfolge von 2 aufweist, werden Richtlinien mit einer Rangfolge von 3 und 4 aktualisiert, um Ihre neue Rangfolge wiederzugeben. In den beiden folgenden Tabellen wird dieses Beispiel gezeigt.

Nachfolgend finden Sie eine Liste der Richtlinienzuweisungen und Prioritäten für eine Team-Besprechungsrichtlinie.

|Gruppenname  |Richtlinienname  |Rang|
|---------|---------|---------|
|Vertrieb    |Vertriebsrichtlinien       | 1        |
|Region West     |West Regions-Richtlinie         |2         |
|Division    |Abteilungsrichtlinien         |3         |
|Tochter   |Subsidiäre Richtlinie        |4         |

Wenn die West Region-Richtlinie aus der Gruppe "West Region" entfernt wird, werden die Richtlinienzuweisungen und-Prioritäten wie folgt aktualisiert.

|Gruppenname  |Richtlinienname  |Rang|
|---------|---------|---------|
|Vertrieb    |Vertriebsrichtlinien       | 1        |
|Division    |Abteilungsrichtlinien         |2         |
|Tochter   |Subsidiäre Richtlinie        |3        |

In diesem Beispiel entfernen wir die Besprechungsrichtlinie für Teams aus einer Gruppe.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

Weitere Informationen finden Sie unter [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).

### <a name="change-a-policy-assignment-for-a-group"></a>Ändern einer Richtlinien Aufgabe für eine Gruppe

Nachdem Sie einer Gruppe eine Richtlinie zugewiesen haben, können Sie das ```Set-CsGroupPolicyAssignmentd``` Cmdlet verwenden, um die Richtlinienzuweisung dieser Gruppe wie folgt zu ändern:

- Ändern der Rangfolge
- Ändern der Richtlinie eines bestimmten Richtlinientyps
- Ändern der Richtlinie eines bestimmten Richtlinientyps und der Rangfolge

In diesem Beispiel ändern wir die Richtlinie für die Anruf Park Richtlinie einer Gruppe in eine Richtlinie mit dem Namen SupportCallPark und die Zuordnungs Rangfolge auf 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

Weitere Informationen finden Sie unter [Satz-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).

### <a name="change-the-effective-policy-for-a-user"></a>Ändern der effektiven Richtlinie für einen Benutzer

Im folgenden finden Sie ein Beispiel für das Ändern der effektiven Richtlinie für einen Benutzer, dem eine Richtlinie direkt zugewiesen ist.

Zunächst verwenden wir das ```Get-CsUserPolicyAssignment``` Cmdlet zusammen mit dem ```PolicySource``` Parameter, um Details zu den Broadcast Richtlinien für Teams zu erhalten, die dem Benutzer zugeordnet sind. Weitere Informationen finden Sie unter [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

Die Ausgabe zeigt, dass dem Benutzer direkt eine Team-Broadcast Richtlinie mit dem Namen "Employee Events" zugewiesen wurde, die Vorrang vor der Richtlinie namens "Vendor Live Events" hat, die einer Gruppe zugeordnet ist, der der Benutzer angehört.

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Jetzt entfernen wir die Mitarbeiter-Ereignis Richtlinie des Benutzers. Das bedeutet, dass der Benutzer nicht mehr über eine Broadcast Richtlinie für Teams verfügt, die Ihnen direkt zugewiesen wurde, und erbt die Richtlinie für Anbieter-Live Ereignisse, die der Gruppe zugewiesen ist, der der Benutzer angehört. 

Verwenden Sie dazu das folgende Cmdlet im Skype for Business PowerShell-Modul.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Sie können das folgende Cmdlet im Teams PowerShell-Modul verwenden, um dies bei einer Batch Richtlinienzuweisung zu tun, wobei $users eine Liste der von Ihnen angegebenen Benutzer ist.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)