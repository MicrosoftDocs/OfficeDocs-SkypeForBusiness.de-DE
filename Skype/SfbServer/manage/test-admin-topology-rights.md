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
description: Testen von Topologierechten in Skype for Business Server
ms.openlocfilehash: d9c0ec5560dcb6f1a6872f0b38f2930e46b2364c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122389"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Testen von Administratortopologierechten in Skype for Business Server

| | |
|--|--|
|Überprüfungszeitplan|Nach der anfänglichen Skype for Business Server-Bereitstellung. Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.|
|Testtool|Windows PowerShell|
|Erforderliche Berechtigungen|Bei der lokalen Ausführung mit der Skype for Business Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.<br/><br/>Wenn sie mit einer Remoteinstanz von Windows PowerShell ausgeführt wird, muss Benutzern eine ROLLENSTEUERUNGsrolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsSetupPermission verfügt. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus Windows PowerShell, um eine Liste aller Rollen für die Rollenaufforderung zu sehen, die dieses Cmdlet verwenden können:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Beschreibung

Standardmäßig können nur Domänenadministratoren eine Skype for Business Server-Topologie aktivieren und umfangreiche Änderungen an der Skype for Business Server-Infrastruktur vornehmen. Dies ist kein Problem, solange Ihre Domänenadministratoren und Ihre Skype for Business Server-Administratoren identisch sind. In vielen Organisationen verfügen Skype for Business Server-Administratoren nicht über Administratorrechte für die gesamte Domäne. Standardmäßig bedeutet dies, dass diese Administratoren (definiert als Mitglieder der Gruppe RTCUniversalServerAdmins) keine Skype for Business Server-Topologieänderungen vornehmen können. Um Mitgliedern der Gruppe RTCUniversalServerAdmins das Recht zum Vornehmen von Topologieänderungen zu erteilen, müssen Sie die erforderlichen Active Directory-Berechtigungen mithilfe des [Grant-CsSetupPermission-Cmdlets](/powershell/module/skype/Grant-CsSetupPermission) zuweisen.
 
Das Test-CsSetupPermission überprüft, ob die erforderlichen Berechtigungen, die zum Installieren von Skype for Business Server oder einer seiner Komponenten erforderlich sind, für den angegebenen Active Directory-Container konfiguriert sind. Wenn die Berechtigungen nicht zugewiesen sind, können Sie das cmdlet Grant-CsSetupPermission ausführen, um Mitgliedern der Gruppe RTCUniversalServerAdmins das Recht zum Installieren und Aktivieren von Skype for Business Server zu erteilen.

## <a name="running-the-test"></a>Ausführen des Tests

Um zu ermitteln, ob Setupberechtigungen für einen Active Directory-Container zugewiesen sind, rufen Sie das cmdlet Test-CsSetupPermission auf. Geben Sie den Distinguished Name des zu überprüfende Containers an. Mit diesem Befehl werden beispielsweise die Setupberechtigungen für den Container ou=CsServers,dc=litwareinc,dc=com überprüft:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema für das [Cmdlet Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Fehler

Wenn Test-CsSetupPermission feststellt, dass die erforderlichen Berechtigungen bereits für einen Active Directory-Container festgelegt wurden, gibt das Cmdlet den Wert True zurück:

Wahr 

Wenn berechtigungen nicht festgelegt sind, gibt Test-CsSetupPermission den Wert False zurück. Beachten Sie, dass dieser Wert in der Regel in vielen Warnmeldungen eingeschlossen wird. Zum Beispiel:

WARNUNG: Access Control Entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; Keine; Keine; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

WARNUNG: Die Zugriffssteuerungseinträge (Access Control Entries, ACEs) für das Objekt "CN=Computers,DC=litwareinc,DC=com" sind nicht bereit. 

Falsch 

WARNUNG: Die Verarbeitung "Test-CsSetupPermission" wurde mit Warnungen abgeschlossen. "2"-Warnungen wurden während dieser Ausführung aufgezeichnet. 

WARNUNG: Ausführliche Ergebnisse finden Sie unter "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test möglicherweise fehlgeschlagen ist

Obwohl es selten Ausnahmen gibt, bedeutet Test-CsSetupPermission, dass für den angegebenen Active Directory-Container keine Setupberechtigungen zugewiesen werden. Diese Berechtigungen können über das cmdlet Grant-CsSetupPermission werden. Mit diesem Befehl werden beispielsweise Setupberechtigungen für den Computers-Container in der Domäne litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema für das [Cmdlet Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)