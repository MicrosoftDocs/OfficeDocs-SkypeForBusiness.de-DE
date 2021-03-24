---
title: Testen von Einwahlkonferenzen in Skype for Business Server
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
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Einwahlkonferenzen in Skype for Business Server testen.'
ms.openlocfilehash: be1cf5bba5a5bec2076f78880343582be19eda70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096731"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Testen von Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Einwahlkonferenzen in Skype for Business Server testen.
  
Als endgültige Überprüfung Ihrer Einwahlkonferenzkonfiguration können Sie nach Wählplänen suchen, die über einen Einwahlkonferenzbereich verfügen, der von keinem Zugriffsnummer verwendet wird, und nach Zugriffsnummern, die keinen Einwahlkonferenzbereich angegeben haben. Sie sollten auch überprüfen, ob die Webseite "Einstellungen für Einwahlkonferenzen" und die Zugriffsnummern für Einwahlkonferenzen ordnungsgemäß funktionieren.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Suchen von Wählplänen mit einer Einwahlkonferenzregion, die nicht von einer Zugriffsnummer verwendet wird

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle Cs-ServerAdministrator oder CsAdministrator an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Dieses Cmdlet gibt alle Wählpläne zurück, die über einen Einwahlkonferenzbereich verfügen, der nicht von einer Zugriffsnummer verwendet wird.
    
Weitere Informationen finden Sie unter [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="find-access-numbers-without-assigned-regions"></a>Suchen von Zugriffsnummern ohne zugewiesene Regionen

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle Cs-ServerAdministrator oder CsAdministrator an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Dieses Cmdlet gibt alle Zugriffsnummern für Einwahlkonferenzen zurück, die keinem Bereich zugeordnet sind.
    
Weitere Informationen finden Sie unter [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="test-webpage-and-access-numbers"></a>Testen von Webseiten und Zugriffsnummern

Sie müssen die folgenden Aufgaben ausführen, um sicherzustellen, dass die Webseite mit den Einstellungen für Einwahlkonferenzen und die Zugriffsnummern für die Einwahl ordnungsgemäß funktionieren:
  
- Testen Sie die Webseite mit Einstellungen für Einwahlkonferenzen, indem Sie sich über die einfache URL anmelden.
    
- Testen Sie die Zugriffsnummern für einen bestimmten Pool, indem Sie das weiter unten in diesem Thema gezeigte Skript ausführen. Dieses Skript simuliert Anrufe bei Zugriffsnummern. Sie benötigen zur Verwendung dieses Skripts die SIP-Adresse und Anmeldeinformationen für einen Unified Communications-Client (UC), der im angegebenen Pool gehostet wird.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>So testen Sie Zugriffsnummern für einen spezifischen Pool

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle Cs-ServerAdministrator oder CsAdministrator an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    In den Berichtergebnissen wird der Test entweder als erfolgreich oder mit Fehlern angezeigt, zusammen mit spezifischen Diagnoseinformationen. Das Flag -Verbose enthält ausführlichere Informationen dazu, wie viele Zugriffsnummern gefunden wurden, sowie Details dazu.
    
Weitere Informationen finden Sie unter [Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps).
