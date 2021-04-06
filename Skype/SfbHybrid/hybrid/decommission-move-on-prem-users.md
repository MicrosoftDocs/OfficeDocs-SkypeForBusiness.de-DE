---
title: Verschieben von Benutzern und Endpunkten in die Cloud
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
description: Verschieben Sie Benutzer und Endpunkte vor dem Außerbetriebsetzen einer lokalen Skype for Business-Umgebung.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593889"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a>Verschieben erforderlicher Benutzer und Endpunkte vor der Außerbetriebnahme Ihrer lokalen Umgebung

In diesem Artikel wird beschrieben, wie Sie erforderliche Benutzer und Anwendungsendpunkte in die Microsoft-Cloud verschieben, bevor Ihre lokale Skype for Business-Umgebung außer Betrieb genommen wird. Dies ist Schritt 1 der folgenden Schritte zum Außerbetriebsetzen Ihrer lokalen Umgebung:

- **Schritt 1. Verschieben Sie alle erforderlichen Benutzer und Anwendungsendpunkte von lokal in online.** (Dieser Artikel.)

- Schritt 2. [Deaktivieren Sie Die Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md).

- Schritt 3. [Entfernen Sie Ihre lokale Skype for Business-Bereitstellung.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Verschieben aller erforderlichen Benutzer aus der lokalen Cloud in die Cloud

Alle Benutzer, die Sie nach Abschluss der Migration weiterhin verwenden, müssen zuerst von der lokalen in die Cloud verschoben werden. Sie verschieben Benutzer mithilfe der lokalen Verwaltungstools. Weitere Informationen finden Sie unter [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).

Obwohl es Benutzern mit lokalen Skype for Business Server-Konten möglich ist, Teams zu verwenden, verfügen diese Benutzer nicht über die volle Funktionalität von Teams. Diese Benutzer können nicht mit anderen Benutzern zusammenarbeiten oder einen Verbund mit anderen Benutzern führen, die Skype for Business weiterhin verwenden (online oder lokal). Diese Benutzer können auch keine PSTN-Anrufe in ihrem Teams-Client empfangen. Daher müssen Sie diese Benutzer online verschieben. Dieser Schritt stellt außerdem sicher, dass alle in Skype for Business Server erstellten Kontakte oder Besprechungen zu Teams migriert werden.

Führen Sie das folgende Cmdlet in einem Skype for Business Server PowerShell-Fenster aus, um zu überprüfen, ob in Ihrer lokalen Bereitstellung noch Benutzer vorhanden sind.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Wenn Benutzer zurückgegeben werden, überprüfen Sie die Ausgabe, um festzustellen, ob Konten in die Cloud verschoben werden müssen, und führen Sie für solche Benutzer die folgenden [Schritte aus.](move-users-between-on-premises-and-cloud.md) Führen Sie für nicht mehr benötigte Benutzerkonten das folgende Skype for Business Server PowerShell-Cmdlet aus:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> Durch Disable-CsUser werden alle Skype for Business-Attribute für alle Benutzer entfernt, die die Filterkriterien erfüllen. Vergewissern Sie sich vor dem Fortfahren, dass diese Konten in Zukunft nicht mehr benötigt werden.

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a>Verschieben von lokalen Hybridanwendungsendpunkten zu Microsoft 365

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
Sie können nun Ihre [Hybridkonfiguration deaktivieren.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>Siehe auch

- [Außerbetriebsetzen Ihrer lokalen Skype for Business-Umgebung](decommission-on-prem-overview.md)

- [Deaktivieren der Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md)

- [Entfernen Ihrer lokalen Skype for Business-Bereitstellung](decommission-remove-on-prem.md)




