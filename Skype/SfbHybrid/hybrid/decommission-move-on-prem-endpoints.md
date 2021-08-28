---
title: Migrieren von Hybridanwendungsendpunkten in die Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Migrieren Sie hyridierende Anwendungsendpunkte vor der Außerbetriebnahme einer Skype for Business lokalen Umgebung.
ms.openlocfilehash: 2968cdb5ecec3bffb22fffaf43c77e97ab8004d1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583419"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>Migrieren von Hybridanwendungsendpunkten vor der Außerbetriebnahme Ihrer lokalen Umgebung

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In diesem Artikel wird beschrieben, wie Sie erforderliche Hybridanwendungsendpunkte in die Microsoft-Cloud verschieben, bevor Sie Ihre lokale Skype for Business umgebung außer Betrieb setzen. Dies ist Schritt 3 der folgenden Schritte zum Außerbetriebsetzen Ihrer lokalen Umgebung:

- Schritt 1. [Verschieben aller erforderlichen Benutzer aus der lokalen Umgebung in die Onlineumgebung](decommission-move-on-prem-users.md)

- Schritt 2. [Deaktivieren Sie Ihre Hybridkonfiguration.](cloud-consolidation-disabling-hybrid.md)

- **Schritt 3. Migrieren Sie Hybridanwendungsendpunkte von der lokalen Umgebung zur Onlinebereitstellung.** (Dieser Artikel)

- Schritt 4. [Entfernen Sie Ihre lokale Skype for Business Bereitstellung.](decommission-remove-on-prem.md)


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>Migrieren aller erforderlichen Hybridanwendungsendpunkte von der lokalen Umgebung zur Onlinebereitstellung

Bevor Sie diese Endpunkte online verschieben können, müssen Sie sicherstellen, dass Sie über aktualisierte DNS-Einträge verfügen, um auf Microsoft 365 für alle sip-Domänen zu verweisen, die von den Endpunkten verwendet werden. Beachten Sie, dass nach dem Aktualisieren von DNS auf Microsoft 365 alle vorhandenen Hybridanwendungsendpunkte nicht mehr gefunden werden können, bis Sie diesen Schritt abgeschlossen haben. Da dieser Schritt (Erstellen von Onlineressourcenkonten) nicht möglich ist, wenn DNS-Einträge auf eine lokale Bereitstellung verweisen, sollten Sie beide Schritte 2 und 3 im selben Wartungsfenster durchführen. Weitere Informationen finden Sie unter [Deaktivieren der Hybridkonfiguration.](cloud-consolidation-disabling-hybrid.md)

1. Rufen Sie lokale Endpunkteinstellungen für hybride Anwendungen ab und exportieren Sie sie, indem Sie den folgenden lokalen Skype for Business Server PowerShell-Befehl ausführen:

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Erstellen und Lizenz neuer [Ressourcenkonten](/microsoftteams/manage-resource-accounts) in Microsoft 365, um die vorhandenen lokalen Hybridanwendungsendpunkte zu ersetzen.

3. Ordnen Sie die neuen Ressourcenkonten den vorhandenen Hybridanwendungsendpunkten zu.

4. Entfernen Sie Telefonnummern, die in den lokalen Hybridanwendungsendpunkten definiert sind, indem Sie den folgenden lokalen Skype for Business Server PowerShell-Befehl ausführen:

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Da Telefonnummern für diese Konten möglicherweise nicht lokal, sondern in Microsoft 365 verwaltet wurden, führen Sie den folgenden Befehl in Teams PowerShell aus:

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

6. Weisen Sie den in Schritt 2 erstellten neuen Ressourcenkonten Telefonnummern zu. Weitere Informationen zum Zuweisen einer Telefonnummer zu einem Ressourcenkonto finden Sie im folgenden Artikel: [Zuweisen einer Servicenummer.](/microsoftteams/manage-resource-accounts)

7. Löschen Sie die lokalen Endpunkte, indem Sie den folgenden lokalen Skype for Business Server PowerShell-Befehl ausführen:

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
Sie können jetzt [Ihre lokale Skype for Business Bereitstellung entfernen.](decommission-remove-on-prem.md)

## <a name="see-also"></a>Siehe auch

- [Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung](decommission-on-prem-overview.md)

- [Verschieben aller erforderlichen Benutzer aus der lokalen Umgebung in die Onlineumgebung](decommission-move-on-prem-users.md)

- [Deaktivieren der Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md)

- [Entfernen Ihrer lokalen Skype for Business-Bereitstellung](decommission-remove-on-prem.md)




