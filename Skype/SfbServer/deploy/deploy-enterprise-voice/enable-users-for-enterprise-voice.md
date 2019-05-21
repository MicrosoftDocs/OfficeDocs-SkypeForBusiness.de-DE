---
title: Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie mit Enterprise-VoIP in Skype for Business Server Anrufe tätigen und empfangen können.'
ms.openlocfilehash: 8a94fe28cc492cdeac5eee476d6886fc8674ae13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303298"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie in Skype for Business Server mithilfe von Enterprise-VoIP Anrufe tätigen und empfangen können.
  
Nachdem Sie Enterprise-VoIP oder-Anruf über Arbeit bereitgestellt haben, können Sie die folgenden Verfahren verwenden, um einem Benutzer das tätigen von Anrufen mithilfe von Enterprise-VoIP zu ermöglichen:
  
> [!NOTE]
> Von den folgenden Verfahren kann nur die erste mithilfe der Skype for Business Server-Systemsteuerung ausgeführt werden. Für die restlichen Verfahren können Sie nur die Skype for Business Server-Verwaltungsshell verwenden. 
  
- Aktivieren Sie das Benutzerkonto für Enterprise-VoIP.
    
- (Optional) Zuweisen einer benutzerspezifischen VoIP-Richtlinie für das Benutzerkonto.
    
- (Optional) Zuweisen eines benutzerspezifischen Satzes mit Wähleinstellungen für das Benutzerkonto.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>So aktivieren Sie ein Benutzerkonto für Enterprise-VoIP

1. Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.
    
6. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.
    
7. Klicken Sie auf der Seite **Skype for Business Server-Benutzer bearbeiten** unter **Telefonie**auf **Enterprise-VoIP**.
    
8. Klicken Sie auf **Anschluss-URI** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise tel:+14255550200).
    
9. Klicken Sie auf **Commit ausführen**.
    
Um die Aktivierung eines Benutzers für Enterprise-VoIP abzuschließen, stellen Sie sicher, dass dem Benutzer eine VoIP-Richtlinie und ein Wählplan zugewiesen ist, egal ob Global (standardmäßig zugewiesen) oder benutzerspezifisch. Standardmäßig werden allen Benutzern eine globale VoIP-Richtlinie und ein Wählplan zugewiesen. Wenn auf Standortebene eine VoIP-Richtlinie für den Standort vorhanden ist, der das Benutzerkonto verwaltet, gelten diese Standortrichtlinien automatisch für alle Benutzer. Führen Sie die Cmdlets **Grant-CsVoicePolicy** und **Grant-CsDialPlan** aus, um eine benutzerspezifische VoIP-Richtlinie oder einen Wählplan für einen Benutzer anzuwenden. Ausführliche Informationen finden Sie in den folgenden Verfahren in diesem Thema.
## <a name="voice-policy-assignment"></a>Zuweisen einer VoIP-Richtlinie

VoIP-Richtlinien auf globaler und Websiteebene werden automatisch allen Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind. Sie können auch VoIP-Richtlinien erstellen, die für spezielle Benutzer oder Gruppen gelten. Diese benutzerbezogenen Richtlinien müssen den Benutzern oder Gruppen explizit zugewiesen werden. Wenn Sie die Global-oder Website-VoIP-Richtlinie für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen und weiter unten in diesem Thema den Abschnitt " [Wähl Plan Zuweisung](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) " auswählen.
  
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

    In diesem Beispiel erhält der Benutzer mit dem Anzeigenamen Bob Kelly die VoIP-Richtlinie mit dem Namen **VoicePolicyJapan**.
    
## <a name="dial-plan-assignment"></a>Zuweisen eines Wählplans
<a name="BKMK_DialPlanAssignment"> </a>

Um die Konfiguration des Benutzerkontos für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen abzuschließen, muss dem Benutzer ein Wählplan zugewiesen sein. Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Standortebene, wenn Sie nicht jedem Benutzer explizit einen vorhandenen Wählplan zuweisen. Wenn Sie den Global-oder Website Wähl Plan für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.
  
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

    In diesem Beispiel erhält der Benutzer mit dem Anzeigenamen Bob Kelly den Benutzer Wählplan mit dem Namen **DialPlanJapan**.
    

