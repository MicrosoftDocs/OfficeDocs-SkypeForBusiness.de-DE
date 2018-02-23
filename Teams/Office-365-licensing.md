---
title: "Office 365-Lizenzierung für Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen, ninadara
description: "Hier finden Sie Informationen zu den verschiedenen Office 365-Lizenzen und darüber, welche Lizenzen für die Aktivierung von Microsoft Teams erforderlich sind und wie diese Lizenzen aktiviert bzw. deaktiviert werden."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 401788f354ad57bded48d59a54646d6c10235662
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
<a name="office-365-licensing-for-microsoft-teams"></a>Office 365-Lizenzierung für Microsoft Teams
========================================

Mit den folgenden Office 365-Abonnements können Benutzer Microsoft Teams verwenden:

|Small Business-Pläne  |Enterprise-Pläne  |Education-Pläne  |
|---------|---------|---------|
|Office 365 Business Essentials     |Office 365 Enterprise E1         |Office 365 Education         |
|Office 365 Business Premium     |Office 365 Enterprise E3         |Office 365 Education Plus         |
|     |Office 365 Enterprise E4 (veraltet)         |Office 365 Education E3 (veraltet)         |
|     |Office 365 Enterprise E5         |Office 365 Education E5   
      |Office 365 Enterprise F1 |  |

> [!NOTE]
> Microsoft Teams ist auch für gemeinnützige Organisationen verfügbar. Die Lizenzierung für den öffentlichen Dienst wird derzeit nicht unterstützt, ist aber für die Zukunft in Planung.
        


Bezogen auf die **Kernfunktionen** von Microsoft Teams gibt es keine Unterschiede zwischen den jeweiligen Office 365-Abonnements, und die Verfügbarkeit der Compliance-Funktionen richtet sich nach der jeweiligen Abonnementebene. (Weitere Informationen finden Sie unter [Lizenzierung für den Schutz von Informationen](https://support.office.com/en-us/article/Plan-for-Office-365-security-and-information-protection-capabilities-3d4ac4a1-3920-4ff9-918f-011f3ce60408).)

Alle unterstützten Abonnementpläne berechtigen zum Zugriff auf den Microsoft Teams-Webclient, die Desktopclients und die mobilen Apps.

Microsoft Teams ist nicht als eigenständiger Dienst verfügbar.

<a name="teams-license"></a>Microsoft Teams-Lizenz
-------------

Die Microsoft Teams-Lizenz ist standardmäßig für alle Benutzer mit berechtigten Office 365-Abonnements aktiviert.

![Screenshot der Einstellungen im Lizenzabschnitt im Office 365 Admin Center mit aktivierter Option „Microsoft Teams“](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image2.png)


Microsoft Teams kann für einen gesamten Lizenztyp in einer Organisation aktiviert oder deaktiviert werden und ist standardmäßig für alle Lizenztypen mit Ausnahme von Gastbenutzern aktiviert. **Es ist nicht möglich, Microsoft Teams mithilfe der Option für Microsoft Teams im Office 365 Admin Center nur für einen Teil eines Lizenztyps zu aktivieren.** Wenn Sie Microsoft Teams für einen Teil Ihrer Organisation aktivieren und für einen anderen Teil deaktivieren möchten (beispielsweise wenn Sie ein Microsoft Teams-Pilotprojekt mit einer ausgewählten Benutzergruppe planen), können Sie die Option für die Microsoft Teams-Lizenz für alle Benutzer aktivieren und sie dann für einzelne Benutzer deaktivieren.

![Screenshot der Einstellung für Microsoft Teams-Benutzer und Lizenztypen im Office 365 Admin Center mit aktivierter Option „Microsoft Teams“](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image3.png)


**Tipp:** Das Aktivieren und Deaktivieren von Microsoft Teams als Arbeitsauslastungslizenz über PowerShell funktioniert genau wie bei jeder anderen Arbeitsauslastung. Der Name des Dienstplans für Microsoft Teams lautet TEAMS1. (Weitere Informationen finden Sie unter [Deaktivieren des Zugriffs auf Dienste mit Office 365 PowerShell](https://technet.microsoft.com/en-us/library/dn771769.aspx).)

**Beispiel:** Das folgende kurze Beispiel zeigt, wie Sie Microsoft Teams für alle Benutzer mit einem bestimmten Lizenztyp deaktivieren. Sie müssen dies zuerst tun und dann den Lizenztyp für die Benutzer, die im Rahmen von Pilottests Zugriff haben sollen, einzeln aktivieren.

*Um die in Ihrer Organisation vorhandenen Abonnementtypen anzuzeigen, verwenden Sie den folgenden Befehl:*

      Get-MsolAccountSku

*Tragen Sie den Namen Ihres Plans einschließlich des Organisationsnamens und des Plans für Ihre Bildungseinrichtung ein (zum Beispiel „ContosoSchool:ENTERPRISEPACK_STUDENT“), und führen Sie dann die folgenden Befehle aus:*

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
*Um Microsoft Teams für alle Benutzer mit einer aktiven Lizenz für Ihren benannten Plan zu deaktivieren, führen Sie den folgenden Befehl aus:*

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x