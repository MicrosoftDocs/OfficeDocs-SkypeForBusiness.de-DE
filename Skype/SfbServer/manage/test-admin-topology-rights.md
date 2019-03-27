---
title: Testen Administratorrechte für die Topologie in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Gewusst wie: Topologie Rechte in Skype für Business Server zu testen.'
ms.openlocfilehash: ad65d42a49d7b85c324766e208e44d6b5e1b632f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888944"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Testen Administratorrechte für die Topologie in Skype für Business Server

| | |
|--|--|
|Zeitplan für die Überprüfung|Nach der anfänglichen Skype für Business Server-Bereitstellung. Je nach Bedarf treten Probleme mit Berechtigungen in Zusammenhang stehen.|
|Test-tool|Windows PowerShell|
|Erforderliche Berechtigungen|Wenn lokal mithilfe der Skype für Business Server-Verwaltungsshell ausführen, müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.<br/><br/>Beim Ausführen eine remote-Instanz von Windows PowerShell verwenden, müssen Benutzer eine RBAC-Rolle zugewiesen werden, die Berechtigung, um das Test-CsSetupPermission-Cmdlet ausgeführt hat. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl aus der Windows PowerShell-Eingabeaufforderung ein:<br/><br/>Get-CsAdminRole \| Where-Object {$_. Cmdlets-match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Beschreibung

Standardmäßig können nur Domänenadministratoren aktivieren eine Skype für Business Server-Topologie und große Änderungen an der Skype für Business Server-Infrastruktur vornehmen. Dies werden kein Problem, solange Ihre Domänen-Admins und Ihre Skype für Serveradministratoren Business ein und dieselbe sind. In vielen Organisationen Skype für Serveradministratoren Business halten Sie nicht über Administratorrechte für die gesamte Domäne. In der Standardeinstellung bedeutet dies, dass diese Administratoren (definiert als Mitglieder der Gruppe RTCUniversalServerAdmins) Skype für topologieänderungen Business Server nicht ausgeführt werden können. Um die Mitglieder der Gruppe "RTCUniversalServerAdmins" das Recht, topologieänderungen vornehmen zu erteilen, müssen Sie die erforderlichen Berechtigungen für die Active Directory mit dem Cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) zuweisen.
 
Das Cmdlet Test-CsSetupPermission stellt sicher, dass die erforderlichen Berechtigungen für die Installation von Skype für Business Server oder einer seiner Komponenten benötigten für den angegebenen Active Directory-Container konfiguriert sind. Wenn die Berechtigungen nicht zugewiesen sind, können Sie dann das Grant-CsSetupPermission-Cmdlet, um Mitglieder der Gruppe RTCUniversalServerAdmins gewähren der Berechtigung zum Installieren und Aktivieren von Skype für Business Server ausführen.

## <a name="running-the-test"></a>Ausführung des Tests

Um festzustellen, ob Berechtigungen für das Setup für eine Active Directory-Container zugewiesen sind, rufen Sie das Cmdlet Test-CsSetupPermission. Geben Sie den distinguished Name des Containers überprüft werden soll. Zum Beispiel stellt dieser Befehl setupberechtigungen für den Container Organisationseinheit = CsServers, dc = Litwareinc, dc = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema für das [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) -Cmdlet.

## <a name="determining-success-or-failure"></a>Bestimmen der Erfolg oder Fehler

Falls von Test-CsSetupPermission ermittelt wird, dass die erforderlichen Berechtigungen für eine Active Directory-Container festgelegt wurden, werden mit dem Cmdlet den Wert True zurückgegeben:

True 

Wenn keine Berechtigungen festgelegt werden, wird Test-CsSetupPermission den Wert False zurück. Beachten Sie, dass dieser Wert in der Regel in viele Warnung Nachrichten eingeschlossen wird. Beispiel:

Warnung: Access steuern (Entry, ACE) Atl-Cs-001\RTCUniversalServerAdmins. Ermöglichen. ExtendedRight; None; None; 1131f6aa-9c07-11D1-f79f-00C04FC2DCD2 

Warnung: Die Zugriffssteuerungseinträge (ACEs) für das Objekt "CN = Computers, DC = Litwareinc, DC = com" sind nicht bereit. 

Falsch 

Warnung: "Test-CsSetupPermission" Verarbeitung wurde abgeschlossen. "2" Warnungen wurden während dieser Ausführung aufgezeichnet. 

Warnung: Ausführliche Ergebnisse "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html" finden Sie unter. 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlschlägt

Obwohl es seltene Ausnahmen, wenn Test-CsSetupPermission, die in der Regel fehlschlägt werden bedeutet, die setup-Berechtigungen für den angegebenen Active Directory-Container nicht zugewiesen. Diese Berechtigungen können mithilfe des Cmdlets Grant-CsSetupPermission zugewiesen werden. Mit diesem Befehl wird beispielsweise dem Container in der Domäne "litwareinc.com" setupberechtigungen gewährt:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema für das [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) -Cmdlet.
