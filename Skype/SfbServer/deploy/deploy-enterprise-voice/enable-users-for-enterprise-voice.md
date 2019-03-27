---
title: Aktivieren von Benutzern für Enterprise-VoIP in Skype für Business Server
ms.reviewer: ''
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
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Zusammenfassung: Informationen Sie zum Aktivieren von Benutzern tätigen und Entgegennehmen von Anrufen mithilfe von Enterprise-VoIP in Skype für Business Server.'
ms.openlocfilehash: b02155f424e8b3f29881caf8c4a29db6f76cb807
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882969"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Aktivieren von Benutzern für Enterprise-VoIP in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zum Aktivieren von Benutzern tätigen und Entgegennehmen von Anrufen mithilfe von Enterprise-VoIP in Skype für Business Server.
  
Nach der Bereitstellung von Enterprise-VoIP oder über Arbeitsplatz anrufen können Sie die folgenden Verfahren zum Aktivieren eines Benutzers tätigen von Anrufen mithilfe von Enterprise-VoIP verwenden:
  
> [!NOTE]
> Die folgenden Verfahren kann nur die ersten mithilfe von Skype Business Server-Systemsteuerung ausgeführt werden. Für die restlichen Schritte können Sie nur Skype für Business Server-Verwaltungsshell verwenden. 
  
- Aktivieren des Benutzerkontos für Enterprise-VoIP.
    
- (Optional) Zuweisen einer benutzerspezifischen VoIP-Richtlinie für das Benutzerkonto.
    
- (Optional) Zuweisen eines benutzerspezifischen Satzes mit Wähleinstellungen für das Benutzerkonto.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>So aktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1. Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.
    
6. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.
    
7. Klicken Sie auf der Seite **Skype für Business Server-Benutzer bearbeiten** unter **Telefonie**auf **Enterprise-VoIP**.
    
8. Klicken Sie auf **Anschluss-URI** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise tel:+14255550200).
    
9. Klicken Sie auf **Commit ausführen**.
    
Zum Abschließen der Aktivieren eines Benutzers für Enterprise-VoIP, achten Sie darauf, dass der Benutzer eine VoIP-Richtlinie und einem Wählplan zugewiesen ist, ob globale (standardmäßig zugewiesen) oder benutzerspezifische. In der Standardeinstellung alle Benutzer werden eine globale VoIP-Richtlinie zugewiesen und Wählplan. Wenn auf Standortebene eine VoIP-Richtlinie für den Standort vorhanden ist, der das Benutzerkonto verwaltet, gelten diese Standortrichtlinien automatisch für alle Benutzer. Führen Sie die Cmdlets **Grant-CsVoicePolicy** und **Grant-CsDialPlan** aus, um eine benutzerspezifische VoIP-Richtlinie oder einen Wählplan für einen Benutzer anzuwenden. Ausführliche Informationen finden Sie in den folgenden Verfahren in diesem Thema.
## <a name="voice-policy-assignment"></a>Zuweisen einer VoIP-Richtlinie

Globale und Websiteebene VoIP-Richtlinien werden automatisch alle Benutzerkonten zugewiesen, die für Enterprise Voice aktiviert sind. Sie können auch VoIP-Richtlinien erstellen, die für spezielle Benutzer oder Gruppen gelten. Diese benutzerbezogenen Richtlinien müssen den Benutzern oder Gruppen explizit zugewiesen werden. Wenn verwenden Sie die globale oder Standortebene VoIP-Richtlinie für alle Benutzer, die für Enterprise Voice aktiviert werden soll, können Sie diesen Abschnitt überspringen und weiterhin, [Dial Plan Zuordnung](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) Abschnitt weiter unten in diesem Thema.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>So weisen Sie eine benutzerspezifische VoIP-Richtlinie zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einem Benutzer eine vorhandene VoIP-Benutzerrichtlinie zuzuweisen:
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Beispiel:
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly VoIP-Richtlinie mit dem Namen **VoicePolicyJapan**zugewiesen.
    
## <a name="dial-plan-assignment"></a>Zuweisen eines Wählplans
<a name="BKMK_DialPlanAssignment"> </a>

Um Benutzerkontokonfiguration für Benutzer von Enterprise-VoIP oder Benutzer von einwahlkonferenzen abgeschlossen haben, muss der Benutzer einen Wählplan zugewiesen werden. Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Standortebene, wenn Sie nicht jedem Benutzer explizit einen vorhandenen Wählplan zuweisen. Wenn Sie möchten die globale verwenden oder Standortebene Wählplan für alle Benutzer, die für Enterprise Voice aktiviert sind, können Sie diesen Abschnitt überspringen.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Zuweisen eines benutzerspezifischen Wählplans

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einen benutzerspezifischen Wählplan zuzuweisen:
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Beispiel:
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly der benutzerwählplan mit der Bezeichnung **DialPlanJapan**zugewiesen.
    

