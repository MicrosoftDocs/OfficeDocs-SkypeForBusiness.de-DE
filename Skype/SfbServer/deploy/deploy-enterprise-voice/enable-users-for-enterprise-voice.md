---
title: Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Zusammenfassung: Erfahren Sie, wie Sie Benutzern das Senden und Empfangen von Anrufen mithilfe Enterprise-VoIP Skype for Business Server ermöglichen.'
ms.openlocfilehash: 3c18836f1c2b03d2c6d50712f33d9e3a900b43b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830875"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Benutzern das Senden und Empfangen von Anrufen mithilfe Enterprise-VoIP Skype for Business Server ermöglichen.
  
Nachdem Sie "Enterprise-VoIP" oder "Anruf über Arbeit" bereitgestellt haben, können Sie einem Benutzer mithilfe der folgenden Verfahren ermöglichen, Anrufe mithilfe von Enterprise-VoIP:
  
> [!NOTE]
> Von den folgenden Verfahren kann nur das erste mit der Skype for Business Server-Systemsteuerung ausgeführt werden. Für die verbleibenden Verfahren können Sie nur die Skype for Business Server-Verwaltungsshell verwenden. 
  
- Aktivieren Sie das Benutzerkonto für Enterprise-VoIP.
    
- (Optional) Weisen Sie dem Benutzerkonto eine benutzerspezifische Sprachrichtlinie zu.
    
- (Optional) Weisen Sie dem Benutzerkonto einen benutzerspezifischen Wählplan zu.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>So aktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1. Melden Sie sich am Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Rolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für die Enterprise-VoIP.
    
6. Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.
    
7. Klicken Sie **auf der Seite "Skype for Business Server-Benutzer** bearbeiten" unter "Telefonie" auf **Enterprise-VoIP**. 
    
8. Klicken **Sie auf den Leitungs-URI,** und geben Sie dann eine eindeutige, normalisierte Telefonnummer ein (z. B. tel:+14255550200).
    
9. Klicken Sie auf **Commit ausführen**.
    
Um die Aktivierung eines Benutzers für Enterprise-VoIP zu beenden, stellen Sie sicher, dass dem Benutzer eine Sprachrichtlinie und ein Wählplan zugewiesen sind, unabhängig davon, ob es sich um eine globale (standardmäßig zugewiesene) oder benutzerspezifische Richtlinie handelt. Standardmäßig wird allen Benutzern eine globale Sprachrichtlinie und ein Wählplan zugewiesen. Wenn eine Sprachrichtlinie oder ein Wählplan auf Standortebene für den Standort vorhanden ist, auf dem das Benutzerkonto gespeichert ist, gelten diese Standortrichtlinien automatisch für den Benutzer. Zum Anwenden einer benutzerspezifischen Sprachrichtlinie oder eines Wählplans auf einen Benutzer müssen Sie die **Cmdlets "Grant-CsVoicePolicy"** und **"Grant-CsDialPlan"** ausführen. Weitere Informationen finden Sie in den folgenden Verfahren in diesem Thema.
## <a name="voice-policy-assignment"></a>Zuweisung von Sprachrichtlinien

Globale und Standortrichtlinien werden automatisch allen Benutzerkonten zugewiesen, die für die Enterprise-VoIP. Sie können auch Sprachrichtlinien erstellen, die für bestimmte Benutzer oder Gruppen gelten. Diese Benutzerrichtlinien müssen den Benutzern oder Gruppen explizit zugewiesen werden. Wenn Sie die globale Oder Standort-Voice-Richtlinie für alle Benutzer verwenden möchten, die für [](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen und mit dem Abschnitt "Zuweisung von Wählplanen" weiter später in diesem Thema fortfahren.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>So weisen Sie eine benutzerspezifische Sprachrichtlinie zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einem Benutzer eine vorhandene VoIP-Benutzerrichtlinie zuzuweisen:
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Beispiel:
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly die Sprachrichtlinie mit dem Namen **"VoicePolicyJapan" zugewiesen.**
    
## <a name="dial-plan-assignment"></a>Zuweisung von Wählplanen
<a name="BKMK_DialPlanAssignment"> </a>

Für den Abschluss der Benutzerkontokonfiguration für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen müssen dem Benutzer Wähleinstellungen zugewiesen werden. Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Standortebene, wenn Sie keinen vorhandenen Wählplan auf Benutzerebene explizit zuweisen. Wenn Sie den globalen Wählplan oder den Standortwählplan für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>So weisen Sie einen benutzerspezifischen Wählplan zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um benutzerspezifische Wähleinstellungen zuzuweisen:
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Beispiel:
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly der Benutzerwählplan mit dem Namen **DialPlanJapan zugewiesen.**
    

