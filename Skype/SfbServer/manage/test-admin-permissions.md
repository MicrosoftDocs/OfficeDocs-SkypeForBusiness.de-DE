---
title: Testen von Administratorberechtigungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Testen von Administratorberechtigungen in Skype for Business Server
ms.openlocfilehash: 1bae61dd4e8d5a8636a64687d279536b4989d104
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279249"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Testen von Administratorberechtigungen in Skype for Business Server

| | |
|--|--|
|Überprüfungszeitplan|Nach der ersten Bereitstellung von Skype for Business Server. Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.|
|Test Tool|Windows PowerShell|
|Erforderliche Berechtigungen|Wenn Benutzer lokal mit der Skype for Business Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.<br><br/>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsOUPermission-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets-Abgleich "Test-CsOUPermission"}|
|||

## <a name="description"></a>Beschreibung

Wenn Sie Skype for Business Server installieren, erhält eine der Aufgaben, die vom Setup-Programm durchgeführt wurden, der RTCUniversalUserAdmins-Gruppe die Active Directory-Berechtigungen, die für die Verwaltung von Benutzern, Computern, Kontakten, Anwendungs Kontakten und inetOrgPerson erforderlich sind. Personen. Wenn Sie die Berechtigungsvererbung in Active Directory deaktiviert haben, kann Setup diese Berechtigungen nicht zuweisen. Infolgedessen können Mitglieder der RTCUniversalUserAdmins-Gruppe keine Skype for Business Server-Entitäten verwalten. Diese Verwaltungsprivilegien stehen nur Domänenadministratoren zur Verfügung. 

Das Cmdlet Test-CsOUPermission überprüft, ob die erforderlichen Berechtigungen zum Verwalten von Benutzern, Computern und anderen Objekten für einen Active Directory-Container festzulegen sind. Wenn diese Berechtigungen nicht gesetzt sind, können Sie dieses Problem beheben, indem Sie das [Cmdlet Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission)ausführen. 

Beachten Sie, dass Grant-CsOUPermission nur Mitgliedern der RTCUniversalUserAdmins-Gruppe Berechtigungen zuweisen kann. Sie können dieses Cmdlet nicht verwenden, um einem beliebigen Benutzer oder einer Gruppe Berechtigungen zu erteilen. Wenn Sie möchten, dass ein anderer Benutzer oder eine andere Gruppe Benutzer Verwaltungsberechtigungen hat, sollten Sie diesen Benutzer (oder die Gruppe) zur Gruppe RTCUniversalUserAdmins hinzufügen. 


## <a name="running-the-test"></a>Ausführen des Tests

Um zu überprüfen, ob Verwaltungsberechtigungen für einen Container festzulegen sind, führen Sie das Cmdlet Test-CsOUPermission gefolgt vom Distinguished Name des Containers und dem Typ der zu überprüfenden Berechtigungen aus. Mit diesem Befehl wird beispielsweise überprüft, ob die Benutzerberechtigungen für die OU ou = Redmond, DC = "litwareinc, DC = com festgesetzt sind:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Wenn Sie mehrere Berechtigungen mithilfe eines einzelnen Befehls überprüfen möchten, schließen Sie die einzelnen in Anführungszeichen eingeschlossenen Berechtigungstypen ein, und trennen Sie diese Typen dann durch Kommas. Mit diesem einen Befehl werden beispielsweise Benutzer-, Computer-und Kontakt Berechtigungen überprüft:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Weitere Informationen finden Sie im [Hilfethema zum Cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die erforderlichen Berechtigungen bereits eingerichtet wurden, gibt Test-CsOUPermission eine Antwort mit einem Wort zurück:

True

Wenn die erforderlichen Berechtigungen nicht festgelegt sind, gibt Test-CsOUPermission den Wert false zurück. Möglicherweise müssen Sie einen Moment suchen, um diesen Wert zu finden. Sie wird in der Regel in mehrere begleitende Warnungen eingebettet. Beispiel:

Warnung: Zugriffssteuerungseintrag (ACE) ATL-CS-001\RTCUniversalUserReadOnlyGroup; ermöglichen ReadProperty ContainerInherit Nachfolger bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

Warnung: die Zugriffssteuerungseinträge (ACEs) für das Objekt "ou = Northamerica, DC = ATL-CS-001\DC =" litwareinc, DC = com "sind nicht bereit. 

Falsch 

Warnung: die Verarbeitung von "Test-CsOUPermission" wurde mit Warnungen abgeschlossen. "2"-Warnungen wurden während dieser Ausführung aufgezeichnet. 

Warnung: detaillierte Ergebnisse finden Sie unter "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn Test-CsOUPermission fehlschlägt, bedeutet dies normalerweise, dass die angegebene Berechtigung nicht der Gruppe RTCUniversalUserAdmins zugewiesen wurde. Mithilfe des Cmdlets Grant-CsOUPermission können Sie dieses Problem beheben und die erforderlichen Berechtigungen zuweisen. Dieser Befehl gibt beispielsweise ou-Berechtigungen für Benutzer, Kontakte und InetOrgPersons an die RTCUniversalUserAdmins-Gruppe:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Weitere Informationen finden Sie im [Hilfethema zum Cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).
