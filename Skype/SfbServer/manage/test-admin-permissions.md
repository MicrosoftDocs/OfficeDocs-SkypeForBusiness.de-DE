---
title: Testen von Administratorberechtigungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Testen von Administratorberechtigungen in Skype for Business Server
ms.openlocfilehash: 1e06c87dcf0e436d72c510a2bc8d9f2aa2051620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030158"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Testen von Administratorberechtigungen in Skype for Business Server

| | |
|--|--|
|Überprüfungszeitplan|Nach der anfänglichen Skype for Business Server-Bereitstellung. Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.|
|Test Tool|Windows PowerShell|
|Erforderliche Berechtigungen|Bei der lokalen Ausführung mithilfe der Skype for Business Server Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.<br><br/>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsOUPermission verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets – Match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Beschreibung

Bei der Installation von Skype for Business Server gibt eine der Aufgaben, die vom Setup Programm ausgeführt wurden, der RTCUniversalUserAdmins-Gruppe die Active Directory Berechtigungen, die zum Verwalten von Benutzern, Computern, Kontakten, Anwendungs Kontakten und inetOrgPerson erforderlich sind. Personen. Wenn Sie die Vererbung von Berechtigungen in Active Directory deaktiviert haben, kann Setup diese Berechtigungen nicht zuweisen. Daher können Mitglieder der RTCUniversalUserAdmins-Gruppe Skype for Business Server Entitäten nicht verwalten. Diese Verwaltungsprivilegien sind nur für Domänenadministratoren verfügbar. 

Das Cmdlet Test-CsOUPermission überprüft, ob die erforderlichen Berechtigungen zum Verwalten von Benutzern, Computern und anderen Objekten für einen Active Directory Container festgelegt sind. Wenn diese Berechtigungen nicht festgelegt sind, können Sie dieses Problem beheben, indem Sie das [Grant-CsOUPermission-Cmdlet](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)ausführen. 

Beachten Sie, dass Grant-CsOUPermission nur Mitgliedern der RTCUniversalUserAdmins-Gruppe Berechtigungen zuweisen kann. Dieses Cmdlet kann nicht verwendet werden, um einem beliebigen Benutzer oder einer Gruppe Berechtigungen zu erteilen. Wenn Sie möchten, dass ein anderer Benutzer oder eine andere Gruppe über Benutzer Verwaltungsberechtigungen verfügt, sollten Sie diesen Benutzer (oder diese Gruppe) der Gruppe RTCUniversalUserAdmins hinzufügen. 


## <a name="running-the-test"></a>Durchführen des Tests

Um zu überprüfen, ob Verwaltungsberechtigungen für einen Container festgelegt sind, führen Sie das Cmdlet Test-CsOUPermission, gefolgt von dem Distinguished Name des Containers und dem Typ der Berechtigungen aus, die Sie überprüfen möchten. Mit diesem Befehl wird beispielsweise überprüft, ob die Benutzerberechtigungen für die OU ou = Redmond, DC = litwareinc, DC = com festgelegt sind:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Wenn Sie mehrere Berechtigungen mithilfe eines einzelnen Befehls überprüfen möchten, schließen Sie die in Anführungszeichen eingeschlossenen Berechtigungstypen ein, und trennen Sie diese Typen dann durch Kommas. Mit diesem Befehl werden beispielsweise Benutzer-, Computer-und Kontakt Berechtigungen überprüft:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Weitere Informationen finden Sie im [Hilfethema zum Cmdlet Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die erforderlichen Berechtigungen bereits festgelegt wurden, gibt Test-CsOUPermission eine Antwort mit einem Wort zurück:

Wahr

Wenn die erforderlichen Berechtigungen nicht festgelegt sind, gibt Test-CsOUPermission den Wert false zurück. Möglicherweise müssen Sie einen Moment suchen, um diesen Wert zu finden. Sie wird in der Regel in mehrere begleitende Warnungen eingebettet. Beispiel:

Warnung: Zugriffssteuerungseintrag (Access Control Entry, ACE) ATL-CS-001\RTCUniversalUserReadOnlyGroup; ermöglichen ReadProperty ContainerInherit Nachfolger bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

Warnung: die Zugriffssteuerungseinträge (ACEs) für das Objekt "ou = Northamerica, DC = ATL-CS-001\DC = litwareinc, DC = com" sind nicht verfügbar. 

False 

Warnung: "Test-CsOUPermission"-Verarbeitung wurde mit Warnungen abgeschlossen. "2"-Warnungen wurden während dieser Ausführung aufgezeichnet. 

Warnung: detaillierte Ergebnisse finden Sie unter "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn "Test-CsOUPermission" fehlschlägt, bedeutet dies normalerweise, dass die angegebene Berechtigung nicht der RTCUniversalUserAdmins-Gruppe zugewiesen wurde. Sie können dieses Problem beheben und die erforderlichen Berechtigungen mithilfe des Cmdlets Grant-CsOUPermission zuweisen. Mit diesem Befehl erhalten Sie beispielsweise die OU-Berechtigungen für Benutzer, Kontakte und InetOrgPersons für die RTCUniversalUserAdmins-Gruppe:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Weitere Informationen finden Sie im [Hilfethema zum Cmdlet Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).
