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
description: Testen von Topologie-rechten in Skype for Business Server
ms.openlocfilehash: 1664a7e7d2b202b596a882e4b393cc15220806c9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817311"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Testen der Rechte der Administrator Topologie in Skype for Business Server

| | |
|--|--|
|Überprüfungszeitplan|Nach der ersten Bereitstellung von Skype for Business Server. Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.|
|Test Tool|Windows PowerShell|
|Erforderliche Berechtigungen|Wenn Benutzer lokal mit der Skype for Business Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.<br/><br/>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsSetupPermission-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets-Abgleich "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Beschreibung

Standardmäßig können nur Domänenadministratoren eine Skype for Business Server-Topologie aktivieren und große Änderungen an der Skype for Business Server-Infrastruktur vornehmen. Das ist kein Problem, solange Ihre Domain-Administratoren und Ihre Skype for Business Server-Administratoren ein und dasselbe sind. In vielen Organisationen verfügen Skype for Business Server-Administratoren nicht über Administratorrechte für die gesamte Domäne. Standardmäßig bedeutet dies, dass diese Administratoren (als Mitglieder der RTCUniversalServerAdmins-Gruppe definiert) keine Änderungen an der Skype for Business Server-Topologie vornehmen können. Um Mitgliedern der RTCUniversalServerAdmins-Gruppe das Recht zu geben, Topologie-Änderungen vorzunehmen, müssen Sie mithilfe des Cmdlets [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) die erforderlichen Active Directory-Berechtigungen zuweisen.
 
Das Cmdlet Test-CsSetupPermission überprüft, ob die erforderlichen Berechtigungen für die Installation von Skype for Business Server oder einer seiner Komponenten für den angegebenen Active Directory-Container konfiguriert sind. Wenn die Berechtigungen nicht zugewiesen sind, können Sie das Grant-CsSetupPermission-Cmdlet ausführen, um Mitgliedern der RTCUniversalServerAdmins-Gruppe das Recht zu geben, Skype for Business Server zu installieren und zu aktivieren.

## <a name="running-the-test"></a>Ausführen des Tests

Rufen Sie das Cmdlet Test-CsSetupPermission auf, um zu ermitteln, ob Setup Berechtigungen für einen Active Directory-Container zugewiesen sind. Geben Sie den Distinguished Name des Containers an, der überprüft werden soll. Dieser Befehl überprüft beispielsweise die Setup Berechtigungen für den Container ou = CsServers, DC = "litwareinc, DC = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn Test-CsSetupPermission feststellt, dass die erforderlichen Berechtigungen bereits für einen Active Directory-Container festgelegt wurden, gibt das Cmdlet den Wert "true" zurück:

Wahr 

Wenn Berechtigungen nicht festgelegt werden, gibt Test-CsSetupPermission den Wert false zurück. Beachten Sie, dass dieser Wert in der Regel in viele Warnmeldungen eingeschlossen ist. Beispiel:

Warnung: Zugriffssteuerungseintrag (ACE) ATL-CS-001\RTCUniversalServerAdmins; Ermöglichen ExtendedRight; Keine Keine 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

Warnung: die Zugriffssteuerungseinträge (ACEs) für das Objekt "CN = Computers, DC =" litwareinc, DC = com "sind nicht bereit. 

Falsch 

Warnung: die Verarbeitung von "Test-CsSetupPermission" wurde mit Warnungen abgeschlossen. "2"-Warnungen wurden während dieser Ausführung aufgezeichnet. 

Warnung: detaillierte Ergebnisse finden Sie unter "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-ABE2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Es gibt zwar seltene Ausnahmen, doch wenn Test-CsSetupPermission fehlschlägt, bedeutet dies in der Regel, dass dem angegebenen Active Directory-Container keine Setup Berechtigungen zugewiesen sind. Diese Berechtigungen können mithilfe des Cmdlets Grant-CsSetupPermission zugewiesen werden. Beispielsweise gewährt dieser Befehl dem Container "Computer" im Domänen litwareinc.com Setup Berechtigungen:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .
