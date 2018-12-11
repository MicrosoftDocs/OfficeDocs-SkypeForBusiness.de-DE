---
title: Testen Administratorberechtigungen in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Testen Sie Administratorberechtigungen in Skype für Business Server
ms.openlocfilehash: 528f12a01483750360a54a2e4d8fe516cf1b2d46
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222954"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Testen Administratorberechtigungen in Skype für Business Server

| | |
|--|--|
|Zeitplan für die Überprüfung|Nach der anfänglichen Skype für Business Server-Bereitstellung. Je nach Bedarf treten Probleme mit Berechtigungen in Zusammenhang stehen.|
|Test-tool|Windows PowerShell|
|Erforderliche Berechtigungen|Wenn lokal mithilfe der Skype für Business Server-Verwaltungsshell ausführen, müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.<br><br/>Beim Ausführen eine remote-Instanz von Windows PowerShell verwenden, müssen Benutzer eine RBAC-Rolle zugewiesen werden, die Berechtigung, um das Test-CsOUPermission-Cmdlet ausgeführt hat. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl aus der Windows PowerShell-Eingabeaufforderung ein:<br/><br/>Get-CsAdminRole \| Where-Object {$_. Cmdlets-match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Beschreibung

Bei der Installation von Skype für Business Server bietet eine der Aufgaben, die vom Setup-Programm ausgeführt wurde der Gruppe RTCUniversalUserAdmins ist die Active Directory-Berechtigungen, die zum Verwalten von Benutzern, Computern, Kontakten, anwendungskontakte und beliebiges erforderlich sind Personen. Wenn Sie die Vererbung von Berechtigungen in Active Directory deaktiviert haben, werden Setup kann nicht diese Berechtigungen zugewiesen. Daher wird nicht Mitglied der Gruppe RTCUniversalUserAdmins Skype für Business Server Entitäten verwalten können. Die von Verwaltungsberechtigungen werden nur für Domänen-Admins verfügbar. 

Das Test-CsOUPermission-Cmdlet stellt sicher, dass die erforderlichen Berechtigungen zum Verwalten von Benutzern, Computern und anderen Objekten auf einem Active Directory-Container festgelegt sind. Wenn diese Berechtigungen nicht festgelegt werden, können Sie dieses Problem beheben, durch Ausführen des [Grant-CsOUPermission-Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission). 

Beachten Sie, dass Grant-CsOUPermission nur Mitglieder der Gruppe RTCUniversalUserAdmins zuweisen kann. Mit diesem Cmdlet können Sie einen beliebigen Benutzer oder eine Gruppe Berechtigungen erteilen. Wenn Sie einen anderen Benutzer oder eine Gruppe Benutzerverwaltungsberechtigungen haben möchten, sollten Sie der Gruppe RTCUniversalUserAdmins Benutzer (oder die Gruppe) hinzufügen. 


## <a name="running-the-test"></a>Ausführung des Tests

Um sicherzustellen, dass die von Verwaltungsberechtigungen für einen Container festgelegt sind, führen Sie das Test-CsOUPermission-Cmdlet, gefolgt von den distinguished Name des Containers und den Typ der Berechtigungen, mit denen Sie überprüfen möchten. Beispielsweise mit diesem Befehl wird überprüft, ob Berechtigungen für einen Benutzer in der Organisationseinheit Organisationseinheit festgelegt sind = Redmond, dc = Litwareinc, dc = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Überprüfen mit einem einzelnen Befehl mehrere Berechtigungen, schließen Sie jeden Berechtigungstyp in Anführungszeichen eingeschlossen und dann diese Typen durch ein Komma getrennt. Dieser Befehl beispielsweise überprüft, ob Benutzer, Computer und Kontaktobjekte Berechtigungen:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Weitere Informationen finden Sie im [Hilfethema für das Test-CsOUPermission-Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Bestimmen der Erfolg oder Fehler

Wenn bereits die erforderlichen Berechtigungen festgelegt wurden, werden Test-CsOUPermission Wort Antwort zurückgegeben:

True

Wenn die erforderlichen Berechtigungen nicht festgelegt werden, wird Test-CsOUPermission den Wert False zurück. Möglicherweise müssen Sie die Suche für einen Moment Zeit, um diesen Wert zu ermitteln. Es wird in der Regel in mehrere zugehörige Warnungen eingebettet werden. Beispiel:

Warnung: Access steuern (Entry, ACE) Atl-Cs-001\RTCUniversalUserReadOnlyGroup. ermöglichen. ReadProperty; ContainerInherit; Untergeordnete Elemente; 00aa003049e2-bf967aba-0de6 - 11d 0; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

Warnung: Die Zugriffssteuerungseinträge (ACEs) für das Objekt "OU = NorthAmerica, DC = Atl-Cs-001\DC = Litwareinc, DC = com" sind nicht bereit. 

Falsch 

Warnung: "Test-CsOUPermission" Verarbeitung wurde abgeschlossen. "2" Warnungen wurden während dieser Ausführung aufgezeichnet. 

Warnung: Ausführliche Ergebnisse "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" finden Sie unter. 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlschlägt

Wenn der Test-CsOUPermission ein Fehler auftritt, bedeutet dies normalerweise, dass die angegebene Berechtigung der Gruppe RTCUniversalUserAdmins ist nicht zugewiesen wurde. Sie können dieses Problem beheben, und weisen die erforderlichen Berechtigungen, mit dem Grant-CsOUPermission-Cmdlet. Mit diesem Befehl erteilt beispielsweise OU-Berechtigungen für Benutzer, Kontakte und InetOrgPersons der Gruppe RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Weitere Informationen finden Sie im [Hilfethema für das Test-CsOUPermission-Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).