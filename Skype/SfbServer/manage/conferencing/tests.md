---
title: Testen von einwahlkonferenzen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Zusammenfassung: Erfahren Sie, wie einwahlkonferenzen in Skype für Business Server zu testen.'
ms.openlocfilehash: 410cbaa9319130dcf4a98c23360362211869e52f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924885"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Testen von einwahlkonferenzen in Skype für Business Server
 
**Zusammenfassung:** Erfahren Sie, wie einwahlkonferenzen in Skype für Business Server zu testen.
  
Zur endgültigen Bestätigung der Einwahlkonferenzkonfiguration können Sie nach Wähleinstellungen suchen, die eine Region für Einwahlkonferenzen aufweisen, die von keiner Zugriffsnummer verwendet wird, und nach Zugriffsnummern suchen, für die keine Region für Einwahlkonferenzen angegeben ist. Sie sollten außerdem sicherstellen, dass die Website mit Einstellungen für die Einzelwahlkonferenz und die Zugriffsnummern korrekt funktionieren.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>So ermitteln Sie Sätze mit Wähleinstellungen mit einer Region für Einwahlkonferenzen, die von keiner Zugriffsnummer verwendet wird

1. Melden Sie sich beim Computer als Mitglied der Gruppe  RTCUniversalServerAdmins  oder als Benutzer mit der Rolle  Cs-ServerAdministrator  oder  CsAdministrator  an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Dieses Cmdlet gibt alle Sätze mit Wähleinstellungen mit einer Region für Einwahlkonferenzen zurück, die von keiner Zugriffsnummer verwendet wird.
    
Weitere Informationen finden Sie unter [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="find-access-numbers-without-assigned-regions"></a>So bestimmen Sie Zugriffsnummern ohne zugewiesene Regionen

1. Melden Sie sich beim Computer als Mitglied der Gruppe  RTCUniversalServerAdmins  oder als Benutzer mit der Rolle  Cs-ServerAdministrator  oder  CsAdministrator  an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Dieses Cmdlet gibt alle Zugriffsnummern für Einwahlkonferenzen zurück, die keiner Region zugeordnet sind.
    
Weitere Informationen finden Sie unter [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="test-webpage-and-access-numbers"></a>So testen Sie Websites und Zugriffsnummern

Sie müssen die folgenden Aufgaben ausführen, um sicherzustellen, dass die Webseite mit den Einstellungen für Einwahlkonferenzen und die Zugriffsnummern für die Einwahl ordnungsgemäß funktionieren:
  
- Testen Sie die Webseite mit Einstellungen für Einwahlkonferenzen, indem Sie sich über die einfache URL anmelden.
    
- Testen Sie die Zugriffsnummern für einen bestimmten Pool, indem Sie das weiter unten in diesem Thema gezeigte Skript ausführen. Dieses Skript simuliert Anrufe bei Zugriffsnummern. Sie benötigen zur Verwendung dieses Skripts die SIP-Adresse und Anmeldeinformationen für einen Unified Communications-Client (UC), der im angegebenen Pool gehostet wird.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>So testen Sie Zugriffsnummern für einen spezifischen Pool

1. Melden Sie sich beim Computer als Mitglied der Gruppe  RTCUniversalServerAdmins  oder als Benutzer mit der Rolle  Cs-ServerAdministrator  oder  CsAdministrator  an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    In den Berichtergebnissen wird der Test entweder als erfolgreich oder mit Fehlern angezeigt, zusammen mit spezifischen Diagnoseinformationen. Die - Verbose Flag enthält weitere detaillierte Informationen über wie viele Nummern gefunden und Details.
    
Weitere Informationen finden Sie unter [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).
  

