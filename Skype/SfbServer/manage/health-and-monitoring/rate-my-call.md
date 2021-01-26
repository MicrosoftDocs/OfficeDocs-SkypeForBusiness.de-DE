---
title: Meinen Anruf in Skype for Business Server bewerten
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
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Zusammenfassung: Erfahren Sie mehr über die Funktion "Meinen Anruf bewerten" in Skype for Business Server.'
ms.openlocfilehash: 597a8213576e7aa2316ace68ed91288475df2a0d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814335"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>Meinen Anruf in Skype for Business Server bewerten

**Zusammenfassung:** Erfahren Sie mehr über die Funktion "Meinen Anruf bewerten" in Skype for Business Server.

"Meinen Anruf bewerten" war eine neue Funktion in Skype for Business 2015- und 2016-Clients unter Windows, mit der Unternehmen Feedback von ihren Endbenutzern erhalten können.

Das Fenster "Meinen Anruf bewerten" bietet ein Bewertungssystem mit Stern und vordefinierte Token für Audio- und Videoanrufe. Darüber hinaus können Administratoren ein benutzerdefiniertes Feld aktivieren, um Feedback zu geben.

Gesammelte Daten zur "Meinen Anruf bewerten" sind derzeit nicht in einem vorhandenen Überwachungsbericht enthalten, es ist jedoch ein separater Überwachungsbericht vorhanden. Daten werden in SQL erfasst, auf die zugegriffen werden kann, indem SQL ausführen.

## <a name="rate-my-call-prerequisites"></a>Bewerten der Voraussetzungen für "Meinen Anruf"

Bevor die Benutzer in Ihrer Skype for Business Server-Bereitstellung auf die Funktion "Meinen Anruf bewerten" zugreifen können, müssen die folgenden Komponenten bereitgestellt und konfiguriert werden:

-  Sie müssen Skype for Business Server installiert haben (Version 9160 oder höher).

- Lassen Sie Ihre Benutzer die neueste Version von Skype for Business installieren und aktualisieren, und bitten Sie sie außerdem, die Skype for Business-Benutzeroberfläche zu verwenden.

- Die Benutzer müssen sich im Skype for Business Server-Front-End-Pool befinden.

- Sie müssen über eine Skype for Business Server-Überwachungsdatenbank verfügen, die Ihren Skype for Business Server-Pools zugeordnet ist.

- Wir empfehlen die Bereitstellung des Anrufqualitätsdashboards (CQD).

## <a name="configure-rate-my-call"></a>Konfigurieren von "Meinen Anruf bewerten"

Die Funktion "Meinen Anruf bewerten" ist standardmäßig in der Clientrichtlinie mit den folgenden Einstellungen aktiviert:

- Prozentsatz der Anzeige von "Meinen Anruf bewerten" - 10 %

- Meinen Anruf bewerten – Benutzerdefiniertes Benutzerfeedback zulassen – deaktiviert

Es ist keine Aktion erforderlich, um das Basisfeature zu aktivieren. Wenn Sie jedoch benutzerdefiniertes Feedback wünschen, müssen Sie es separat aktivieren. Das folgende Windows PowerShell ist ein Beispiel für das Aktivieren von benutzerdefiniertem Feedback von Endbenutzern und das Ändern des Intervalls von 10 % auf 80 %.

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>Zugreifen auf "Meinen Anruf bewerten"-Daten

Daten von Benutzern werden in zwei Tabellen in der Überwachungsdatenbank gesammelt.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** - Diese Tabelle enthält Ergebnisse der Tokenumfrage durch Endbenutzer.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** - Diese Tabelle enthält Tokendefinitionen.

Tokendefinitionen sind wie folgt codiert:

|||
|:-----|:-----|
|1   <br/> |DistortedSpeech  <br/> |
|2   <br/> | ElectronicFeedback <br/> |
|3   <br/> | BackgroundNoise <br/> |
|4   <br/> |DumpledSpeech  <br/> |
|5   <br/> |Echo  <br/> |
| 21  <br/> | FrozenVideo <br/> |
|22  <br/> | PixelatedVideo <br/> |
|23  <br/> | BlurryImage <br/> |
|24  <br/> | PoorColor <br/> |
|25  <br/> | DarkVideo <br/> |
|101  <br/> |Audio_SilentLocal  <br/> |
|102  <br/> |Audio_SilentRemote  <br/> |
|103  <br/> |Audio_Echo  <br/> |
|104  <br/> |Audio_BackgroundNoise  <br/> |
|105  <br/> |Audio_LowSound  <br/> |
|106  <br/> |Audio_Dropped  <br/> |
|107  <br/> |Audio_DistortedSpeech  <br/> |
|108  <br/> |Audio_Interrupted  <br/> |
|109  <br/> |Audio_Other  <br/> |
|201  <br/> |Video_NoLocalVideo  <br/> |
|202  <br/> |Video_NoRemoteVideo  <br/> |
|203  <br/> |Video_LowQuality  <br/> |
|204  <br/> |Video_FrozenVideo  <br/> |
|205  <br/> |Video_StoppedUnexpectedly  <br/> |
|206  <br/> |Video_DarkVideo  <br/> |
|207  <br/> |Video_NoAudioSync  <br/> |
|208  <br/> |Video_Other  <br/> |
|301  <br/> |Pstn_DialPad  <br/> |
|401  <br/> |SS_NoContentLocal  <br/> |
|402  <br/> |SS_NoContentRemote  <br/> |
|403  <br/> |SS_CantPresent  <br/> |
|404  <br/> |SS_LowQuality  <br/> |
|405  <br/> |SS_Freezing  <br/> |
|406  <br/> |SS_StoppedUnexpectedly  <br/> |
|407  <br/> |SS_LargeDelay  <br/> |
|408  <br/> |SS_Other  <br/> |
|501  <br/> |Reliabilty_Join  <br/> |
|502  <br/> |Reliabilty_Invite  <br/> |

 **[QoeMetrics]. [dbo]. [CallQualityFeedback]** Diese Tabelle enthält Abrufergebnisse von "Stern"-Abstimmungen und Kundenfeedback, falls aktiviert.

Daten aus Tabellen können mithilfe einer Auswahl aus **\* einer [Table.Name]-Abfrage** oder mithilfe von Microsoft SQL Server Management Studio.

Die folgenden SQL können verwendet werden:

 **Audio**

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 **Video**

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a>Aktualisieren von Tokendefinitionen

Die neuesten Skype for #A0 melden neue #A1 ( \> 100), die möglicherweise nicht in Ihrer [QoeMetrics].[ dbo]. [CallQualityFeedbackTokenDef]-Tabelle. Um die Datenbanktabelle mit den neuesten Tokendefinitionen zu aktualisieren, kann der SQL befehl für die Überwachungsdatenbank mithilfe von Microsoft SQL Server Management Studio. Dieser Befehl ersetzt alle Einträge in der [QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]-Tabelle.

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


