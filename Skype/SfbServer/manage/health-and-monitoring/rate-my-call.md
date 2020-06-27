---
title: Meinen Anruf in Skype for Business Server bewerten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Zusammenfassung: erfahren Sie mehr über die Funktion "meine Anrufe bewerten" in Skype for Business Server.'
ms.openlocfilehash: 15f2bcbcf75690baaa350541f5f1da134fb32025
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902219"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>Meinen Anruf in Skype for Business Server bewerten

**Zusammenfassung:** Erfahren Sie mehr über die Funktion "meinen Anruf bewerten" in Skype for Business Server.

"Mein Anruf bewerten" war ein neues Feature in Skype for Business 2015-und 2016-Clients unter Windows, das Unternehmen eine Möglichkeit bietet, Feedback von Ihren Endbenutzern zu erhalten.

Das Fenster "mein Anruf bewerten" bietet ein Bewertungssystem für "Sterne" und vordefinierte Token für Audio-und Videoanrufe. Darüber hinaus können Administratoren ein benutzerdefiniertes Feld zur Bereitstellung von Feedback aktivieren.

Gesammelte Rate meine Anrufdaten sind derzeit nicht in einem vorhandenen Überwachungsbericht enthalten, es gibt jedoch einen separaten Überwachungsbericht. Daten werden in SQL-Tabellen erfasst, auf die durch die Ausführung von SQL-Abfragen zugegriffen werden kann.

## <a name="rate-my-call-prerequisites"></a>Meine Voraussetzungen für Anrufe bewerten

Bevor die Benutzer in Ihrer Skype for Business Server-Bereitstellung auf die Funktion "meine Anrufe bewerten" zugreifen können, müssen die folgenden Komponenten bereitgestellt und konfiguriert werden:

-  Sie müssen Skype for Business Server installiert haben (Version 9160 oder höher).

- Lassen Sie die Benutzer die neueste Version von Skype for Business installieren und aktualisieren, und fordern Sie Sie außerdem auf, die Skype for Business Benutzeroberfläche zu verwenden.

- Benutzer müssen im Skype for Business Server Front-End-Pool verwaltet werden.

- Sie müssen über eine Skype for Business Server Überwachungsdatenbank verfügen, die Ihren Skype for Business Server-Pools bereitgestellt und zugeordnet ist.

- Es wird empfohlen, das Anruf Qualitäts Dashboard (CQD) bereitzustellen.

## <a name="configure-rate-my-call"></a>Konfigurieren von "mein Anruf bewerten"

Das Feature Meine Anruf Rate bewerten ist in der Client Richtlinie standardmäßig mit den folgenden Einstellungen aktiviert:

- Mein Anruf anzeigen: Prozentsatz-10%

- Bewerten von "meine Anrufe erlauben"-Benutzer Feedback – deaktiviert

Es ist keine Aktion erforderlich, um das Basis Feature zu aktivieren, aber wenn Sie ein benutzerdefiniertes Feedback wünschen, müssen Sie es separat aktivieren. Das folgende Windows PowerShell-Cmdlets ist ein Beispiel für die Aktivierung benutzerdefinierter Endbenutzer Feedbacks und das Ändern des Intervalls von 10% auf 80%.

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>Zugreifen auf meine Anrufdaten bewerten

Daten von Benutzern werden in zwei Tabellen in der Überwachungsdatenbank gesammelt.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** – Diese Tabelle enthält Ergebnisse von Token Polling durch Endbenutzer.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** – Diese Tabelle enthält Token-Definitionen.

Token-Definitionen werden wie folgt codiert:

|||
|:-----|:-----|
|1   <br/> |DistortedSpeech  <br/> |
|2   <br/> | ElectronicFeedback <br/> |
|3   <br/> | BackgroundNoise <br/> |
|4   <br/> |MuffledSpeech  <br/> |
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

 **[QoeMetrics]. [dbo]. [CallQualityFeedback]** Diese Tabelle enthält Polling-Ergebnisse aus "Sterne"-Abstimmungen und Kundenfeedback, falls aktiviert.

Daten aus Tabellen können mithilfe einer **Select \* from [Table.Name]** -Abfrage oder mithilfe von Microsoft SQL Server Management Studio aufgerufen werden.

Die folgenden SQL-Abfragen können verwendet werden:

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

## <a name="updating-token-definitions"></a>Aktualisieren von Token-Definitionen

Die neuesten Skype for Business Clients melden neue Problemtoken-IDs ( \> 100), die möglicherweise nicht in Ihrem [QoeMetrics] vorhanden sind. [ dbo]. [CallQualityFeedbackTokenDef]-Tabelle. Um die Datenbanktabelle mit den neuesten Token-Definitionen zu aktualisieren, kann der folgende SQL-Befehl in der Überwachungsdatenbank mit Microsoft SQL Server Management Studio ausgeführt werden. Mit diesem Befehl werden alle Einträge im [QoeMetrics] ersetzt. [dbo]. [CallQualityFeedbackTokenDef]-Tabelle.

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


