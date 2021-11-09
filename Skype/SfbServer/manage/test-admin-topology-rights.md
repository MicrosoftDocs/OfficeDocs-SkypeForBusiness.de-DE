---
title: Testen von Administratortopologierechten in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: So testen Sie Topologierechte in Skype for Business Server
ms.openlocfilehash: 6f4eed0271d9dd6d099d19287f7caa37148f6026
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861312"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Testen von Administratortopologierechten in Skype for Business Server

|&nbsp; |&nbsp; |
|--|--|
|Überprüfungszeitplan|Nach der ersten Skype for Business Server Bereitstellung. Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.|
|Testtool|Windows PowerShell|
|Erforderliche Berechtigungen|Bei lokaler Ausführung mithilfe der Skype for Business Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe "RTCUniversalServerAdmins" sein.<br/><br/>Bei Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsSetupPermission verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Windows PowerShell Eingabeaufforderung aus:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Beschreibung

Standardmäßig können nur Domänenadministratoren eine Skype for Business Server Topologie aktivieren und umfangreiche Änderungen an der Skype for Business Server Infrastruktur vornehmen. Dies ist kein Problem, solange Ihre Domänenadministratoren und Ihre Skype for Business Server-Administratoren identisch sind. In vielen Organisationen besitzen Skype for Business Server Administratoren keine Administratorrechte für die gesamte Domäne. Das bedeutet standardmäßig, dass diese Administratoren (definiert als Mitglieder der Gruppe "RTCUniversalServerAdmins") keine Skype for Business Server Topologieänderungen vornehmen können. Um Mitgliedern der Gruppe "RTCUniversalServerAdmins" das Recht zu geben, Topologieänderungen vorzunehmen, müssen Sie die erforderlichen Active Directory-Berechtigungen mithilfe des [Cmdlets Grant-CsSetupPermission](/powershell/module/skype/Grant-CsSetupPermission) zuweisen.
 
Das Cmdlet Test-CsSetupPermission überprüft, ob die erforderlichen Berechtigungen zum Installieren Skype for Business Server oder einer seiner Komponenten im angegebenen Active Directory-Container konfiguriert sind. Wenn die Berechtigungen nicht zugewiesen sind, können Sie das Cmdlet Grant-CsSetupPermission ausführen, um Mitgliedern der Gruppe "RTCUniversalServerAdmins" das Recht zu geben, Skype for Business Server zu installieren und zu aktivieren.

## <a name="running-the-test"></a>Ausführen des Tests

Rufen Sie das Cmdlet Test-CsSetupPermission auf, um zu bestimmen, ob Setupberechtigungen für einen Active Directory-Container zugewiesen sind. Geben Sie den Distinguished Name des zu überprüfenden Containers an. Mit diesem Befehl werden beispielsweise Setupberechtigungen für den Container ou=CsServers,dc=litwareinc,dc=com überprüft:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema zum Cmdlet ["Test-CsSetupPermission".](/powershell/module/skype/Test-CsSetupPermission)

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Fehler

Wenn Test-CsSetupPermission feststellt, dass die erforderlichen Berechtigungen bereits für einen Active Directory-Container festgelegt wurden, gibt das Cmdlet den Wert True zurück:

Wahr 

Wenn keine Berechtigungen festgelegt sind, gibt Test-CsSetupPermission den Wert False zurück. Beachten Sie, dass dieser Wert in der Regel in viele Warnmeldungen eingeschlossen wird. Beispiel:

WARNUNG: Zugriffssteuerungseintrag (Access Control Entry, ACE) atl-cs-001\RTCUniversalServerAdmins; Zulassen; ExtendedRight; Keine; Keine; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

WARNUNG: Die Zugriffssteuerungseinträge (Access Control Entries, ACEs) für das Objekt "CN=Computers,DC=litwareinc,DC=com" sind nicht bereit. 

Falsch 

WARNUNG: Die Verarbeitung von "Test-CsSetupPermission" wurde mit Warnungen abgeschlossen. Während dieser Ausführung wurden "2"-Warnungen aufgezeichnet. 

WARNUNG: Detaillierte Ergebnisse finden Sie unter "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test möglicherweise fehlgeschlagen ist

Es gibt zwar selten Ausnahmen, wenn Test-CsSetupPermission fehlschlägt, bedeutet dies in der Regel, dass keine Setupberechtigungen für den angegebenen Active Directory-Container zugewiesen werden. Diese Berechtigungen können mithilfe des Cmdlets Grant-CsSetupPermission zugewiesen werden. Beispielsweise gewährt dieser Befehl Setupberechtigungen für den Computercontainer in der Domäne litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema zum Cmdlet ["Test-CsSetupPermission".](/powershell/module/skype/Test-CsSetupPermission)