---
title: Testen von Administratorberechtigungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: So testen Sie Administratorberechtigungen in Skype for Business Server
ms.openlocfilehash: 08721b556de6e7b162eb76fbed953dae422b33b7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580559"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Testen von Administratorberechtigungen in Skype for Business Server

|&nbsp; |&nbsp; |
|--|--|
|Überprüfungszeitplan|Nach der ersten Skype for Business Server Bereitstellung. Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.|
|Testtool|Windows PowerShell|
|Erforderliche Berechtigungen|Bei der lokalen Ausführung mithilfe der Skype for Business Server Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe "RTCUniversalServerAdmins" sein.<br><br/>Bei Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsOUPermission verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Windows PowerShell Eingabeaufforderung aus:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Beschreibung

Wenn Sie Skype for Business Server installieren, erhält die Gruppe "RTCUniversalUserAdmins" eine der Aufgaben, die vom Setupprogramm ausgeführt wurden, die Active Directory-Berechtigungen, die zum Verwalten von Benutzern, Computern, Kontakten, Anwendungskontakten und InetOrg-Personen erforderlich sind. Wenn Sie die Berechtigungsvererbung in Active Directory deaktiviert haben, kann Setup diese Berechtigungen nicht zuweisen. Daher können Mitglieder der Gruppe "RTCUniversalUserAdmins" Skype for Business Server Entitäten nicht verwalten. Diese Verwaltungsberechtigungen sind nur für Domänenadministratoren verfügbar. 

Das cmdlet Test-CsOUPermission überprüft, ob die erforderlichen Berechtigungen zum Verwalten von Benutzern, Computern und anderen Objekten in einem Active Directory-Container festgelegt sind. Wenn diese Berechtigungen nicht festgelegt sind, können Sie dieses Problem beheben, indem Sie das [Cmdlet Grant-CsOUPermission](/powershell/module/skype/Grant-CsOUPermission)ausführen. 

Beachten Sie, dass Grant-CsOUPermission nur Mitgliedern der Gruppe "RTCUniversalUserAdmins" Berechtigungen zuweisen können. Sie können dieses Cmdlet nicht verwenden, um einem beliebigen Benutzer oder einer beliebigen Gruppe Berechtigungen zu erteilen. Wenn ein anderer Benutzer oder eine andere Gruppe über Benutzerverwaltungsberechtigungen verfügen soll, sollten Sie diesen Benutzer (oder diese Gruppe) der Gruppe "RTCUniversalUserAdmins" hinzufügen. 


## <a name="running-the-test"></a>Ausführen des Tests

Um zu überprüfen, ob Die Verwaltungsberechtigungen für einen Container festgelegt sind, führen Sie das cmdlet Test-CsOUPermission gefolgt vom distinguished Name des Containers und dem Typ der Berechtigungen aus, die Sie überprüfen. Mit diesem Befehl wird beispielsweise überprüft, ob Benutzerberechtigungen für die OU ou=Redmond,dc=litwareinc,dc=com festgelegt sind:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Um mehrere Berechtigungen mithilfe eines einzigen Befehls zu überprüfen, schließen Sie jeden Berechtigungstyp in Anführungszeichen ein, und trennen Sie diese Typen dann durch Kommas. Der folgende Befehl überprüft beispielsweise die Benutzer-, Computer- und Kontaktberechtigungen:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Weitere Informationen finden Sie im [Hilfethema zum Cmdlet Test-CsOUPermission.](/powershell/module/skype/test-csoupermission)

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Fehler

Wenn die erforderlichen Berechtigungen bereits festgelegt wurden, gibt Test-CsOUPermission eine Antwort mit einem Wort zurück:

Wahr

Wenn die erforderlichen Berechtigungen nicht festgelegt sind, gibt Test-CsOUPermission den Wert False zurück. Möglicherweise müssen Sie einen Moment suchen, um diesen Wert zu finden. Es wird in der Regel in mehrere begleitende Warnungen eingebettet. Zum Beispiel:

WARNUNG: Zugriffssteuerungseintrag (Access Control Entry, ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; zulassen; ReadProperty; ContainerInherit; Nachfolger; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

WARNUNG: Die Zugriffssteuerungseinträge (Access Control Entries, ACEs) für das Objekt "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" sind nicht bereit. 

False 

WARNUNG: Die Verarbeitung von "Test-CsOUPermission" wurde mit Warnungen abgeschlossen. Während dieser Ausführung wurden "2"-Warnungen aufgezeichnet. 

WARNUNG: Detaillierte Ergebnisse finden Sie unter "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test möglicherweise fehlgeschlagen ist

Wenn Test-CsOUPermission fehlschlägt, bedeutet dies in der Regel, dass die angegebene Berechtigung nicht der Gruppe "RTCUniversalUserAdmins" zugewiesen wurde. Sie können dieses Problem beheben und die erforderlichen Berechtigungen zuweisen, indem Sie das Cmdlet Grant-CsOUPermission verwenden. Mit diesem Befehl werden der Gruppe "RTCUniversalUserAdmins" oe-Berechtigungen für Benutzer, Kontakte und inetOrgPersons erteilt:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Weitere Informationen finden Sie im [Hilfethema zum Cmdlet Test-CsOUPermission.](/powershell/module/skype/test-csoupermission)