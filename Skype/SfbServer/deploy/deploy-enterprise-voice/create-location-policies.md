---
title: Erstellen von ortungsrichtlinien in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Lesen Sie in diesem Thema erfahren, wie konfigurieren erweiterten notrufunterstützung (E9-1-1) anhand von Standortrichtlinien in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 01525af7c47869525c38056b00cd137ce1e5c1a5
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "23891939"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>Erstellen von ortungsrichtlinien in Skype für Business Server
 
Lesen Sie in diesem Thema erfahren, wie konfigurieren erweiterten notrufunterstützung (E9-1-1) anhand von Standortrichtlinien in Skype für Business Server Enterprise-VoIP. 
  
Skype für Business Server verwendet eine ortungsrichtlinie, um Skype für Business-Clients für E9-1-1 bei der Clientregistrierung aktivieren. Eine Standortrichtlinie enthält die Einstellungen für die Definition der Notrufdienstimplementierung. Weitere Informationen finden Sie unter [Planen von Standortrichtlinien für Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).
  
Sie können mithilfe der Skype für die Business-Systemsteuerung oder mithilfe des Cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Standortrichtlinien definieren.
  
> [!NOTE]
> Skype für Business Server unterstützt jetzt die Konfiguration von mehreren Notfall Zahlen für einen Client an. Wenn Sie mehrere Notfall Nummern konfigurieren möchten, müssen Sie die Informationen in [mehrere Notfall Zahlen in Skype für Business Server planen](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) und [Konfigurieren von mehreren Notfall Zahlen in Skype für Business](configure-multiple-emergency-numbers.md)befolgen. 
  
Sie können die globale Standortrichtlinie bearbeiten und bereichsspezifische Standortrichtlinien erstellen. Ein Client, der sich nicht in einem Subnetz mit zugeordneter Standortrichtlinie befindet oder dem nicht direkt eine Standortrichtlinie zugeordnet wurde, ruft eine globale Richtlinie ab. Bereichsspezifische Standortrichtlinien werden Subnetzen oder Benutzern zugewiesen.   
  
Zum Erstellen einer Standortrichtlinie müssen Sie ein Konto verwenden, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsVoiceAdministrator“ ist oder entsprechende Administratorrechte und -berechtigungen besitzt.
  
Weitere Informationen finden Sie unter [Planen von Standortrichtlinien für Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). Cmdlets in diesem Verfahren verwenden eine Standortrichtlinie, die mit den folgenden Werten definiert ist. Eine vollständige Beschreibung des Cmdlet-Parameter und Werte finden Sie unter [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).
  
|**Element**|**Wert**|
|:-----|:-----|
|EnhancedEmergencyServicesEnabled  <br/> |**True** <br/> |
|LocationRequired  <br/> |**Haftungsausschluss** <br/> |
|EnhancedEmergencyServiceDisclaimer  <br/> |Die Unternehmensrichtlinie erfordert, dass Sie einen Standort festlegen. Wenn Sie keinen Standort festlegen, können Sie im Ernstfall nicht von Notfalldiensten lokalisiert werden. Bitte legen Sie einen Standort fest.  <br/> |
|UseLocationForE911Only  <br/> |**False** <br/> |
|PstnUsage  <br/> |**EmergencyUsage** <br/> |
|EmergencyDialString  <br/> |**911** <br/> |
|EmergencyDialMask  <br/> |**112** <br/> |
|NotificationUri  <br/> |**SIP:Security@litwareinc.com** <br/> |
|ConferenceUri  <br/> |**SIP:+14255550123@litwareinc.com** <br/> |
|ConferenceMode  <br/> |**twoway** <br/> |
|LocationRefreshInterval  <br/> |**2** <br/> |
   
### <a name="to-create-location-policies"></a>So erstellen Sie Standortrichtlinien

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
    > [!NOTE]
    > Bei Ausführung von „CsLocationPolicy“ tritt ein Fehler auf, wenn sich die Einstellung für **PstnUsage** nicht bereits in der globalen Liste „PstnUsages“ befindet.
  
2. Optional können Sie auch das folgende Cmdlet ausführen, um die globale Standortrichtlinie zu bearbeiten:
    
   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. Führen Sie folgendes Cmdlet aus, um eine bereichsspezifische Standortrichtlinie zu erstellen.
    
   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. Führen Sie das folgende Cmdlet aus, um die in Schritt 3 erstellte bereichsspezifische Standortrichtlinie auf eine Benutzerrichtlinie anzuwenden.
    
   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```