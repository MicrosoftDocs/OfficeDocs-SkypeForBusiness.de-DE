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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Zusammenfassung: Erfahren Sie, wie Sie Benutzern das Tätigen und Empfangen von Anrufen mithilfe von Enterprise-VoIP in Skype for Business Server ermöglichen.'
ms.openlocfilehash: 04533245348672afedfac113f3fd64188a2efba2
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012769"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Benutzern das Tätigen und Empfangen von Anrufen mithilfe von Enterprise-VoIP in Skype for Business Server ermöglichen.
  
Nachdem Sie Enterprise-VoIP oder "Anruf über Arbeit" bereitgestellt haben, können Sie die folgenden Verfahren verwenden, um einem Benutzer das Tätigen von Anrufen mithilfe von Enterprise-VoIP zu ermöglichen:
  
> [!NOTE]
> Von den folgenden Verfahren kann nur die erste mithilfe Skype for Business Server Systemsteuerung ausgeführt werden. Für die übrigen Verfahren können Sie nur Skype for Business Server Verwaltungsshell verwenden. 
  
- Aktivieren Sie das Benutzerkonto für Enterprise-VoIP.
    
- (Optional) Weisen Sie dem Benutzerkonto eine benutzerspezifische VoIP-Richtlinie zu.
    
- (Optional) Weisen Sie dem Benutzerkonto einen benutzerspezifischen Wählplan zu.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>So aktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1. Melden Sie sich am Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Rolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** an.
    
2. Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.
    
6. Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.
    
7. Klicken Sie auf der Seite **"Skype for Business Server Benutzer bearbeiten"** unter **"Telefonie"** auf **Enterprise-VoIP.**
    
8. Klicken Sie auf den **Anschluss-URI,** und geben Sie dann eine eindeutige, normalisierte Telefonnummer ein (z. B. `tel:+14255550200` ).
    
9. Klicken Sie auf **Commit ausführen**.
    
Um die Aktivierung eines Benutzers für Enterprise-VoIP abzuschließen, stellen Sie sicher, dass dem Benutzer eine VoIP-Richtlinie und ein Wählplan zugewiesen sind, ob global (standardmäßig zugewiesen) oder benutzerspezifisch. Standardmäßig wird allen Benutzern eine globale VoIP-Richtlinie und ein Wählplan zugewiesen. Wenn auf Standortebene eine VoIP-Richtlinie oder ein Wählplan für den Standort vorhanden ist, auf dem das Benutzerkonto verwaltet wird, gelten diese Standortrichtlinien automatisch für den Benutzer. Um eine Benutzer-VoIP-Richtlinie oder einen Wählplan auf einen Benutzer anzuwenden, müssen Sie die Cmdlets **"Grant-CsVoicePolicy"** und **"Grant-CsDialPlan"** ausführen. Ausführliche Informationen finden Sie in den folgenden Verfahren in diesem Thema.
## <a name="voice-policy-assignment"></a>VoIP-Richtlinienzuweisung

Globale und VoIP-Richtlinien auf Standortebene werden automatisch allen Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind. Sie können auch VoIP-Richtlinien erstellen, die für bestimmte Benutzer oder Gruppen gelten. Diese Benutzerrichtlinien müssen den Benutzern oder Gruppen explizit zugewiesen werden. Wenn Sie die globale VoIP-Richtlinie oder standortübergreifende VoIP-Richtlinie für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen und später in diesem Thema mit dem Abschnitt ["Wählplanzuweisung"](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) fortfahren.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>So weisen Sie eine benutzerspezifische VoIP-Richtlinie zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einem Benutzer eine vorhandene VoIP-Benutzerrichtlinie zuzuweisen:
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Beispiel:
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly die VoIP-Richtlinie mit dem Namen **VoicePolicyJapan** zugewiesen.
    
## <a name="dial-plan-assignment"></a>Wählplanzuweisung
<a name="BKMK_DialPlanAssignment"> </a>

Für den Abschluss der Benutzerkontokonfiguration für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen müssen dem Benutzer Wähleinstellungen zugewiesen werden. Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Standortebene, wenn Sie keinen vorhandenen Benutzerwählplan explizit zuweisen. Wenn Sie den globalen Wählplan oder Standortwählplan für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>So weisen Sie einen benutzerspezifischen Wählplan zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um benutzerspezifische Wähleinstellungen zuzuweisen:
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Beispiel:
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly der Wählplan des Benutzers mit dem Namen **DialPlanJapan** zugewiesen.
    

