---
title: Verschieben von Hybridanwendungsendpunkten in die Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Verschieben Von hyriden Anwendungsendpunkten vor dem Außerbetriebsetzen einer lokalen Skype for Business-Umgebung.
ms.openlocfilehash: af8b521eaaf4a1e86027936f3d4d3600ab4bfa7b
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656879"
---
# <a name="move-hyrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>Verschieben von hyriden Anwendungsendpunkten vor der Außerbetriebnahme Ihrer lokalen Umgebung

In diesem Artikel wird beschrieben, wie Sie erforderliche Hybridanwendungsendpunkte in die Microsoft-Cloud verschieben, bevor Ihre lokale Skype for Business-Umgebung außer Betrieb genommen wird. Dies ist Schritt 3 der folgenden Schritte zum Außerbetriebsetzen Ihrer lokalen Umgebung:

- Schritt 1. [Verschieben aller erforderlichen Benutzer von lokal in online](decommission-move-on-prem-users.md)

- Schritt 2. [Deaktivieren Sie Die Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md).

- **Schritt 3. Verschieben Sie Hybridanwendungsendpunkte von lokal in online.** (Dieser Artikel)

- Schritt 4. [Entfernen Sie Ihre lokale Skype for Business-Bereitstellung.](decommission-remove-on-prem.md)


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>Verschieben aller erforderlichen Hybridanwendungsendpunkte von lokal in online

Bevor Sie diese Endpunkte ins Internet verschieben können, müssen Sie sicherstellen, dass Sie die DNS-Einträge so aktualisiert haben, dass sie für alle von den Endpunkten verwendeten Sipdomänen auf Microsoft 365 verweisen. Es ist nicht möglich, Onlineressourcenkonten zu erstellen, wenn DNS-Einträge auf lokale Konten verweisen. Weitere Informationen finden Sie unter [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).

1. Rufen Sie lokale Einstellungen für den Hybridanwendungsendpunkt ab, und exportieren Sie sie, indem Sie den folgenden lokalen Skype for Business Server PowerShell-Befehl ausführen:

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Erstellen und Lizenz für [neue Ressourcenkonten](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365, um die vorhandenen lokalen Hybridanwendungsendpunkte zu ersetzen.

3. Ordnen Sie die neuen Ressourcenkonten den vorhandenen Hybridanwendungsendpunkten zu.

4. Entfernen Sie telefonnummern, die in den lokalen Hybridanwendungsendpunkten definiert sind, indem Sie den folgenden lokalen Skype for Business Server PowerShell-Befehl ausführen:

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Da es möglich ist, dass Telefonnummern für diese Konten in Microsoft 365 statt lokal verwaltet wurden, führen Sie den folgenden Befehl in Skype for Business Online PowerShell aus:

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. Weisen Sie den neuen Ressourcenkonten, die in Schritt 2 erstellt wurden, Telefonnummern zu. Weitere Informationen zum Zuweisen einer Telefonnummer zu einem Ressourcenkonto finden Sie im folgenden Artikel: [Zuweisen einer Dienstnummer](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).

7. Löschen Sie die lokalen Endpunkte, indem Sie den folgenden lokalen Skype for Business Server PowerShell-Befehl ausführen:

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
Sie können nun Ihre [lokale Skype for Business-Bereitstellung entfernen.](decommission-remove-on-prem.md)

## <a name="see-also"></a>Siehe auch

- [Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung](decommission-on-prem-overview.md)

- [Verschieben aller erforderlichen Benutzer von lokal in online](decommission-move-on-prem-users.md)

- [Deaktivieren der Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md)

- [Entfernen Ihrer lokalen Skype for Business-Bereitstellung](decommission-remove-on-prem.md)




