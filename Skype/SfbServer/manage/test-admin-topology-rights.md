---
title: Testen von Administratortopologierechten in Skype for Business Server
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
description: So testen Sie Topologierechte in Skype for Business Server
ms.openlocfilehash: a6bbebd44387911fdb69679a16ab052c673f0b10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832845"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Testen von Administratortopologierechten in Skype for Business Server

| | |
|--|--|
|Überprüfungszeitplan|Nach der anfänglichen Skype for Business Server-Bereitstellung. Bei Bedarf, wenn probleme im Zusammenhang mit Berechtigungen auftreten.|
|Testtool|Windows PowerShell|
|Erforderliche Berechtigungen|Bei der lokalen Ausführung mithilfe der Skype for Business Server-Verwaltungsshell müssen Benutzer Mitglied der Sicherheitsgruppe "RTCUniversalServerAdmins" sein.<br/><br/>Wenn die Ausführung mit einer Remoteinstanz von Windows PowerShell wird, muss Benutzern eine rollengesteuerte Zugriffssteuerungsrolle zugewiesen sein, die über die Berechtigung zum Ausführen des Test-CsSetupPermission verfügt. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um eine Liste aller rollen rbAC-Rollen, die dieses Cmdlet verwenden können, Windows PowerShell sehen:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Beschreibung

Standardmäßig können nur Domänenadministratoren eine Skype for Business Server-Topologie aktivieren und umfangreiche Änderungen an der Skype for Business Server-Infrastruktur vornehmen. Dies ist kein Problem, solange Ihre Domänenadministratoren und Ihre Skype for Business Server-Administratoren ein und dasselbe sind. In vielen Organisationen verfügen Skype for Business Server-Administratoren nicht über Administratorrechte für die gesamte Domäne. Das bedeutet standardmäßig, dass diese Administratoren (definiert als Mitglieder der Gruppe "RTCUniversalServerAdmins") keine Skype for Business Server-Topologieänderungen vornehmen können. Um Mitgliedern der Gruppe "RTCUniversalServerAdmins" das Recht zu erteilen, Topologieänderungen vorzunehmen, müssen Sie die erforderlichen Active Directory-Berechtigungen mithilfe des Cmdlets ["Grant-CsSetupPermission"](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) zuweisen.
 
Das Test-CsSetupPermission überprüft, ob die erforderlichen Berechtigungen, die zum Installieren von Skype for Business Server oder einer seiner Komponenten erforderlich sind, im angegebenen Active Directory-Container konfiguriert sind. Wenn die Berechtigungen nicht zugewiesen sind, können Sie das Cmdlet Grant-CsSetupPermission ausführen, um Mitgliedern der Gruppe "RTCUniversalServerAdmins" das Recht zum Installieren und Aktivieren von Skype for Business Server zu erteilen.

## <a name="running-the-test"></a>Ausführen des Tests

Rufen Sie das Cmdlet "Test-CsSetupPermission auf, um zu ermitteln, ob setupberechtigungen für einen Active Test-CsSetupPermission zugewiesen sind. Geben Sie den Distinguished Name des zu überprüfende Containers an. Mit diesem Befehl werden beispielsweise die Setupberechtigungen für den Container "ou=CsServers,dc=litwareinc,dc=com" überprüft:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Test-CsSetupPermission".](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn Test-CsSetupPermission ermittelt, dass die erforderlichen Berechtigungen bereits für einen Active Directory-Container festgelegt wurden, gibt das Cmdlet den Wert "True" zurück:

Richtig 

Wenn keine Berechtigungen festgelegt sind, gibt Test-CsSetupPermission den Wert "False" zurück. Beachten Sie, dass dieser Wert in der Regel in viele Warnmeldungen eingeschlossen wird. Beispiel:

WARNUNG: Zugriffssteuerungseintrag (Access Control Entry, ACE) atl-cs-001\RTCUniversalServerAdmins; Zulassen; ExtendedRight; Keine; Keine; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

WARNUNG: Die Zugriffssteuerungseinträge (Access Control Entries, ACEs) für das Objekt "CN=Computers,DC=litwareinc,DC=com" sind nicht bereit. 

False 

WARNUNG: Die Verarbeitung "Test-CsSetupPermission" wurde mit Warnungen abgeschlossen. "2"-Warnungen wurden während dieser Ausführung aufgezeichnet. 

WARNUNG: Detaillierte Ergebnisse finden Sie unter "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test möglicherweise fehlgeschlagen ist

Obwohl es selten Ausnahmen gibt, bedeutet dies Test-CsSetupPermission, dass für den angegebenen Active Test-CsSetupPermission keine Setupberechtigungen zugewiesen sind. Diese Berechtigungen können mithilfe des cmdlets Grant-CsSetupPermission zugewiesen werden. Mit diesem Befehl werden beispielsweise Setupberechtigungen für den Container "Computer" in der Domäne "litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Test-CsSetupPermission".](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)
