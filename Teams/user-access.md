---
title: Verwalten des Benutzerzugriffs auf Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Hier erfahren Sie, wie Sie den Zugriff auf Benutzerebene pro Benutzer aktivieren oder deaktivieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 318d9467bf1565a50987b6716f2b0a1ad86999bf
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
<a name="manage-user-access-to-microsoft-teams"></a>Verwalten des Benutzerzugriffs auf Microsoft Teams
=====================================

Auf Benutzerebene kann der Zugriff auf Microsoft Teams pro Benutzer aktiviert oder deaktiviert werden, indem die Produktlizenz für Microsoft Teams zugewiesen oder entfernt wird.

Zurzeit gibt es keine Richtlinienoptionen für das Aktivieren oder Deaktivieren von Microsoft Teams oder einer Teilmenge der Funktionen von Microsoft Teams für einzelne Benutzer außerhalb der Lizenzierung.



> [!NOTE]
>Microsoft empfiehlt, Microsoft Teams für alle Benutzer in einer Firma zu aktivieren, damit Teams organisch für Projekte und andere dynamische Aktivitäten gebildet werden können. Auch wenn Sie sich für ein Pilotprojekt entscheiden, kann es hilfreich sein, Microsoft Teams für alle Benutzer aktiviert zu lassen, während Sie die Kommunikation auf die Pilotbenutzergruppe beschränken.

Microsoft Teams-Lizenzen auf Benutzerebene werden direkt über die Benutzerverwaltungsschnittstellen im Office 365 Admin Center verwaltet. Ein Administrator kann neuen Benutzern Lizenzen zuweisen, wenn neue Benutzerkonten erstellt werden, oder Benutzern mit vorhandenen Konten Lizenzen zuweisen. Der Administrator muss über Berechtigungen eines globalen Office 365-Administrators oder eines Benutzerverwaltungsadministrators verfügen, um Microsoft Teams-Lizenzen zu verwalten.

Wenn einem Benutzer eine Lizenz-SKU wie E3 oder E5 zugewiesen wird, wird automatisch eine Microsoft Teams-Lizenz zugewiesen, und der Benutzer wird für Microsoft Teams aktiviert. Administratoren können alle Office 365-Dienste und -Lizenzen präzise steuern, und die Microsoft Teams-Lizenz für einen bestimmten Benutzer oder eine bestimmte Gruppe von Benutzern kann aktiviert oder deaktiviert werden.

![Screenshot des Abschnitts „Produktlizenzen“ im Office 365 Admin Center](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Eine Microsoft Teams-Benutzerlizenz kann jederzeit deaktiviert werden. Wenn die Lizenz deaktiviert ist, wird der Zugriff der Benutzer auf Microsoft Teams verhindert, und sie können Microsoft Teams nicht mehr im App-Startprogramm und auf der Homepage von Office 365 sehen.

![Screenshot des Abschnitts „Produktlizenzen“ im Office 365 Admin Center mit ausgewählter Option „Microsoft Teams“](media/Manage_user_access_to_Microsoft_Teams_image4.png)

Neben dem Office 365 Admin Center können Office 365-Administratoren auch Office 365 PowerShell verwenden, um Benutzerlizenzen zuzuweisen und zu entfernen. Verwenden Sie die folgende Syntax, um eine Lizenz zu einem Benutzer zuzuweisen:

```
Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"
```

Im folgenden Beispiel wird eine Lizenz aus dem Lizenzplan „litwareinc:ENTERPRISEPACK“ (Office 365 Enterprise E3) dem nicht über eine Lizenz verfügenden Benutzer „belindan@litwareinc.com“ zugewiesen.

```
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Weitere Details und Beispiele finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell](https://go.microsoft.com/fwlink/?linkid=855755).

Mit der folgenden Syntax entfernen Sie Lizenzen von einem vorhandenen Benutzerkonto:

```
Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"
```

Im folgenden Beispiel wird die Lizenz „litwareinc:ENTERPRISEPACK“ (Office 365 Enterprise E3) vom Benutzerkonto „BelindaN@litwareinc.com“ entfernt.

```
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

Weitere Details und Beispiele finden Sie unter [Entfernen von Lizenzen von Benutzerkonten mit Office 365 PowerShell](https://go.microsoft.com/fwlink/?linkid=855756).

| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Entscheidungspunkt         |<ul><li>Wie sieht der Plan Ihrer Organisation für das organisationsweite Microsoft Teams-Onboarding aus? (Pilotprojekt oder offen)</li></ul>         |
|![Symbol für „Nächste Schritte“](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Nächste Schritte         |<ul><li>Wenn Sie das Onboarding über ein geschlossenes Pilotprojekt durchführen, entscheiden Sie, ob Sie dies über die Lizenzierung oder durch zielgerichtete Kommunikation tun möchten.</li><li>Stellen Sie abhängig von der Entscheidung durch die entsprechenden Schritte sicher, dass nur Pilotbenutzer auf Microsoft Teams zugreifen dürfen (wenn dies notwendig ist).</li><li>Dokumentieren Sie die Richtlinien dafür, welche Benutzer auf Microsoft Teams zugreifen dürfen (oder nicht zugreifen dürfen).</li></ul>         |
