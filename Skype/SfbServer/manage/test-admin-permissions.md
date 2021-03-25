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
localization_priority: Normal
description: Testen von Administratorberechtigungen in Skype for Business Server
ms.openlocfilehash: 535911c26bac5e3f1dadb2c8d59cffe82dc20c7a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122399"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Testen von Administratorberechtigungen in Skype for Business Server

| | |
|--|--|
|Überprüfungszeitplan|Nach der anfänglichen Skype for Business Server-Bereitstellung. Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.|
|Testtool|Windows PowerShell|
|Erforderliche Berechtigungen|Bei der lokalen Ausführung mit der Skype for Business Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.<br><br/>Wenn sie mit einer Remoteinstanz von Windows PowerShell ausgeführt wird, muss Benutzern eine ROLLENSTEUERUNGsrolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsOUPermission verfügt. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus Windows PowerShell, um eine Liste aller Rollen für die Rollenaufforderung zu sehen, die dieses Cmdlet verwenden können:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Beschreibung

Bei der Installation von Skype for Business Server erhält die RTCUniversalUserAdmins-Gruppe durch eine der Aufgaben, die vom Setupprogramm ausgeführt wurden, die Active Directory-Berechtigungen, die zum Verwalten von Benutzern, Computern, Kontakten, Anwendungskontakten und InetOrg-Personen benötigt werden. Wenn Sie die Vererbung von Berechtigungen in Active Directory deaktiviert haben, kann setup diese Berechtigungen nicht zuweisen. Aus diesem Grund können Mitglieder der Gruppe RTCUniversalUserAdmins keine Skype for Business Server-Entitäten verwalten. Diese Verwaltungsberechtigungen stehen nur Domänenadministratoren zur Verfügung. 

Das Test-CsOUPermission überprüft, ob die erforderlichen Berechtigungen zum Verwalten von Benutzern, Computern und anderen Objekten für einen Active Directory-Container festgelegt sind. Wenn diese Berechtigungen nicht festgelegt sind, können Sie dieses Problem beheben, indem Sie das [Grant-CsOUPermission-Cmdlet ausführen.](/powershell/module/skype/Grant-CsOUPermission) 

Beachten Sie, Grant-CsOUPermission nur Mitgliedern der Gruppe "RTCUniversalUserAdmins" Berechtigungen zuweisen können. Sie können dieses Cmdlet nicht verwenden, um einem beliebigen Benutzer oder einer beliebigen Gruppe Berechtigungen zu erteilen. Wenn ein anderer Benutzer oder eine andere Gruppe über Benutzerverwaltungsberechtigungen verfügen soll, sollten Sie diesen Benutzer (oder diese Gruppe) der Gruppe RTCUniversalUserAdmins hinzufügen. 


## <a name="running-the-test"></a>Ausführen des Tests

Um zu überprüfen, ob Verwaltungsberechtigungen für einen Container festgelegt sind, führen Sie das cmdlet Test-CsOUPermission aus, gefolgt vom Distinguished Name des Containers und von der Art der Berechtigungen, die Sie überprüfen. Mit diesem Befehl wird beispielsweise überprüft, ob Benutzerberechtigungen für die OU ou=Redmond,dc=litwareinc,dc=com festgelegt sind:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Um mehrere Berechtigungen mithilfe eines einzigen Befehls zu überprüfen, schließen Sie jeden Berechtigungstyp in Anführungszeichen ein, und trennen Sie diese Typen dann mithilfe von Kommas. Mit diesem befehl werden beispielsweise Benutzer-, Computer- und Kontaktberechtigungen überprüft:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Weitere Informationen finden Sie im [Hilfethema für das cmdlet Test-CsOUPermission Cmdlet](/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Fehler

Wenn die erforderlichen Berechtigungen bereits festgelegt wurden, Test-CsOUPermission eine Ein-Wort-Antwort zurück:

Wahr

Wenn die erforderlichen Berechtigungen nicht festgelegt sind, gibt Test-CsOUPermission wert False zurück. Möglicherweise müssen Sie einen Moment suchen, um diesen Wert zu finden. Sie wird in der Regel in mehrere begleitende Warnungen eingebettet. Zum Beispiel:

WARNUNG: Access Control Entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Absteigende; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

WARNUNG: Die Zugriffssteuerungseinträge (Access Control Entries, ACEs) für das Objekt "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" sind nicht bereit. 

Falsch 

WARNUNG: Die Verarbeitung "Test-CsOUPermission" wurde mit Warnungen abgeschlossen. "2"-Warnungen wurden während dieser Ausführung aufgezeichnet. 

WARNUNG: Ausführliche Ergebnisse finden Sie unter "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test möglicherweise fehlgeschlagen ist

Wenn Test-CsOUPermission fehlert, bedeutet dies in der Regel, dass die angegebene Berechtigung der Gruppe "RTCUniversalUserAdmins" nicht zugewiesen wurde. Sie können dieses Problem beheben und die erforderlichen Berechtigungen mithilfe des cmdlets Grant-CsOUPermission zuweisen. Mit diesem Befehl werden beispielsweise Organisationseinheitenberechtigungen für Benutzer, Kontakte und inetOrgPersons für die Gruppe "RTCUniversalUserAdmins" erteilt:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Weitere Informationen finden Sie im [Hilfethema für das cmdlet Test-CsOUPermission Cmdlet](/powershell/module/skype/test-csoupermission).