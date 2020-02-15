---
title: Testen der Rechte der Administrator Topologie in Skype for Business Server
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
description: Vorgehensweise Testen von topologischen rechten in Skype for Business Server
ms.openlocfilehash: de2f5752bdcd9096a47595fd7ffd10a3ab799d9c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030148"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Testen der Rechte der Administrator Topologie in Skype for Business Server

| | |
|--|--|
|Überprüfungszeitplan|Nach der anfänglichen Skype for Business Server-Bereitstellung. Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.|
|Test Tool|Windows PowerShell|
|Erforderliche Berechtigungen|Bei der lokalen Ausführung mithilfe der Skype for Business Server Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.<br/><br/>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsSetupPermission verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets – Match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Beschreibung

Standardmäßig können nur Domänenadministratoren eine Skype for Business Server Topologie aktivieren und umfangreiche Änderungen an der Skype for Business Server Infrastruktur vornehmen. Dies ist kein Problem, solange die Domänenadministratoren und die Skype for Business Server Administratoren identisch sind. In vielen Organisationen verfügen Skype for Business Server Administratoren nicht über Administratorrechte für die gesamte Domäne. Standardmäßig bedeutet dies, dass diese Administratoren (definiert als Mitglieder der Gruppe "RTCUniversalServerAdmins") keine Änderungen an Skype for Business Server Topologie vornehmen können. Um Mitgliedern der RTCUniversalServerAdmins-Gruppe das Recht zu geben, Topologie-Änderungen vorzunehmen, müssen Sie mithilfe des Cmdlets [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) die erforderlichen Active Directory Berechtigungen zuweisen.
 
Das Cmdlet Test-CsSetupPermission überprüft, ob die erforderlichen Berechtigungen, die zum Installieren von Skype for Business Server oder einer seiner Komponenten erforderlich sind, für den angegebenen Active Directory Container konfiguriert sind. Wenn die Berechtigungen nicht zugewiesen sind, können Sie das Grant-CsSetupPermission-Cmdlet ausführen, um Mitgliedern der RTCUniversalServerAdmins-Gruppe das Recht zu geben, Skype for Business Server zu installieren und zu aktivieren.

## <a name="running-the-test"></a>Durchführen des Tests

Rufen Sie das Cmdlet Test-CsSetupPermission auf, um zu bestimmen, ob Setup Berechtigungen für einen Active Directory Container zugewiesen sind. Geben Sie den Distinguished Name des Containers an, der überprüft werden soll. Mit diesem Befehl werden beispielsweise die Setup Berechtigungen für den Container ou = CsServers, DC = litwareinc, DC = com überprüft:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn Test-CsSetupPermission feststellt, dass die erforderlichen Berechtigungen bereits für einen Active Directory Container festgelegt wurden, gibt das Cmdlet den Wert true zurück:

Wahr 

Wenn Berechtigungen nicht festgelegt sind, gibt Test-CsSetupPermission den Wert false zurück. Beachten Sie, dass dieser Wert in der Regel in viele Warnmeldungen eingeschlossen wird. Beispiel:

Warnung: Zugriffssteuerungseintrag (Access Control Entry, ACE) ATL-CS-001\RTCUniversalServerAdmins; Ermöglichen ExtendedRight; Keine Keine 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

Warnung: die Zugriffssteuerungseinträge (ACEs) für das Objekt "CN = Computers, DC = litwareinc, DC = com" sind nicht verfügbar. 

False 

Warnung: "Test-CsSetupPermission"-Verarbeitung wurde mit Warnungen abgeschlossen. "2"-Warnungen wurden während dieser Ausführung aufgezeichnet. 

Warnung: detaillierte Ergebnisse finden Sie unter "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-ABE2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Obwohl es seltene Ausnahmen gibt, wenn Test-CsSetupPermission fehlschlägt, bedeutet dies normalerweise, dass dem angegebenen Active Directory Container keine Setup Berechtigungen zugewiesen sind. Diese Berechtigungen können mithilfe des Cmdlets Grant-CsSetupPermission zugewiesen werden. Beispielsweise erteilt dieser Befehl dem Computer Container in der Domäne litwareinc.com Setup Berechtigungen:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .
