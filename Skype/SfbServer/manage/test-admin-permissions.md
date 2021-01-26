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
description: So testen Sie Administratorberechtigungen in Skype for Business Server
ms.openlocfilehash: 27ae50cca0018985ad59dbc4487dd3630cb5cf87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800090"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Testen von Administratorberechtigungen in Skype for Business Server

| | |
|--|--|
|Überprüfungszeitplan|Nach der anfänglichen Skype for Business Server-Bereitstellung. Bei Bedarf, wenn probleme im Zusammenhang mit Berechtigungen auftreten.|
|Testtool|Windows PowerShell|
|Erforderliche Berechtigungen|Bei der lokalen Ausführung mithilfe der Skype for Business Server-Verwaltungsshell müssen Benutzer Mitglied der Sicherheitsgruppe "RTCUniversalServerAdmins" sein.<br><br/>Wenn sie mit einer Remoteinstanz von Windows PowerShell ausgeführt werden, muss Benutzern eine rollengesteuerte Zugriffssteuerungsrolle zugewiesen sein, die über die Berechtigung zum Ausführen des Test-CsOUPermission verfügt. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um eine Liste aller rollen rbAC-Rollen, die dieses Cmdlet verwenden können, Windows PowerShell sehen:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Beschreibung

Bei der Installation von Skype for Business Server erhält die Gruppe "RTCUniversalUserAdmins" durch eine der vom Setupprogramm ausgeführten Aufgaben die Active Directory-Berechtigungen, die zum Verwalten von Benutzern, Computern, Kontakten, Anwendungskontakten und InetOrg-Personen erforderlich sind. Wenn Sie die Vererbung von Berechtigungen in Active Directory deaktiviert haben, kann Setup diese Berechtigungen nicht zuweisen. Aus diesem Grund können Mitglieder der Gruppe "RTCUniversalUserAdmins" keine Skype for Business Server-Entitäten verwalten. Diese Verwaltungsrechte stehen nur Domänenadministratoren zur Verfügung. 

Das Test-CsOUPermission überprüft, ob die erforderlichen Berechtigungen zum Verwalten von Benutzern, Computern und anderen Objekten für einen Active Directory-Container festgelegt sind. Wenn diese Berechtigungen nicht festgelegt sind, können Sie dieses Problem beheben, indem Sie das [Cmdlet "Grant-CsOUPermission" ausführen.](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) 

Beachten SieGrant-CsOUPermission nur Mitgliedern der Gruppe "RTCUniversalUserAdmins" Berechtigungen zuweisen können. Sie können dieses Cmdlet nicht verwenden, um einem beliebigen Benutzer oder einer beliebigen Gruppe Berechtigungen zu erteilen. Wenn ein anderer Benutzer oder eine andere Gruppe über Benutzerverwaltungsberechtigungen verfügen soll, sollten Sie diesen Benutzer (oder diese Gruppe) der Gruppe "RTCUniversalUserAdmins" hinzufügen. 


## <a name="running-the-test"></a>Ausführen des Tests

Um zu überprüfen, ob Verwaltungsberechtigungen für einen Container festgelegt sind, führen Sie das Cmdlet Test-CsOUPermission aus, gefolgt vom Distinguished Name des Containers und dem Zu überprüfenden Berechtigungstyp. Mit diesem Befehl wird beispielsweise überprüft, ob Benutzerberechtigungen für die OU ou=Redmond,dc=litwareinc,dc=com festgelegt sind:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Um mehrere Berechtigungen mithilfe eines einzelnen Befehls zu überprüfen, schließen Sie jeden Berechtigungstyp in Anführungszeichen ein, und trennen Sie diese Typen dann durch Kommas. Mit dem folgenden Befehl werden beispielsweise Benutzer-, Computer- und Kontaktberechtigungen überprüft:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Weitere Informationen finden Sie im [Hilfethema zum Test-CsOUPermission Cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die erforderlichen Berechtigungen bereits festgelegt wurden, gibt Test-CsOUPermission eine Ein-Wort-Antwort zurück:

Richtig

Wenn die erforderlichen Berechtigungen nicht festgelegt sind, gibt Test-CsOUPermission den Wert "False" zurück. Möglicherweise müssen Sie einen Moment suchen, um diesen Wert zu finden. Sie wird in der Regel in mehrere begleitende Warnungen eingebettet. Beispiel:

WARNUNG: Zugriffssteuerungseintrag (Access Control Entry, ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Absteigend; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

WARNUNG: Die Zugriffssteuerungseinträge (Access Control Entries, ACEs) für das Objekt "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" sind nicht bereit. 

False 

WARNUNG: Die Verarbeitung "Test-CsOUPermission" wurde mit Warnungen abgeschlossen. "2"-Warnungen wurden während dieser Ausführung aufgezeichnet. 

WARNUNG: Detaillierte Ergebnisse finden Sie unter "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test möglicherweise fehlgeschlagen ist

Wenn Test-CsOUPermission fehlert, bedeutet dies in der Regel, dass die angegebene Berechtigung der Gruppe "RTCUniversalUserAdmins" nicht zugewiesen wurde. Sie können dieses Problem beheben und die erforderlichen Berechtigungen mithilfe des cmdlets Grant-CsOUPermission zuweisen. Mit diesem Befehl werden der Gruppe "RTCUniversalUserAdmins" beispielsweise Organisationseinheitenberechtigungen für Benutzer, Kontakte und InetOrgPersons erteilt:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Weitere Informationen finden Sie im [Hilfethema zum Test-CsOUPermission Cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).
