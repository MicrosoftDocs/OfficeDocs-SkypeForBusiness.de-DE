---
title: Bewerten von Meine Anruf in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Zusammenfassung: Informationen Sie zum Feature Rate Meine Aufrufen in Skype für Business Server.'
ms.openlocfilehash: 61aaff26c5786cd8574b7277ed600da75c3679ce
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886303"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>Bewerten von Meine Anruf in Skype für Business Server

**Zusammenfassung:** Lernen Sie das Feature Rate Meine Aufrufen in Skype für Business Server aus.

Rate Meine aufrufen, wurde ein neues Feature in Skype für Business 2015 und 2016 Clients unter Windows, das Unternehmen eine Möglichkeit zum Abrufen von Feedback von ihren Endbenutzern bereitstellt.

Das Fenster Rate Meine aufrufen bietet einen "Stern" Bewertungssystem und vordefinierten Token für Audio-und Videoanrufe. Darüber hinaus können Administratoren ein benutzerdefiniertes Feld Ihr Feedback übermitteln können.

Erfasste Daten aus „Meinen Anruf bewerten“ sind derzeit nicht in einem vorhandenen Überwachungsbericht enthalten, es gibt jedoch einen separaten Überwachungsbericht. Daten werden in der SQL-Tabellen, die durch Ausführen von SQL-Abfragen zugegriffen werden kann.

## <a name="rate-my-call-prerequisites"></a>Voraussetzungen für „Meinen Anruf bewerten“

Bevor die Benutzer in Ihrer Skype für Business Server-Bereitstellung Rate Meine aufrufen Funktionalität zugreifen können, muss die folgende Gruppe von Komponenten bereitgestellt und konfiguriert werden:

-  Skype benötigen Sie für Business Server installiert (Version 9160 oder höher).

- Müssen Sie sich die Benutzer installieren und aktualisieren Sie auf die neueste Version von Skype für Unternehmen und auch bitten, der Skype für Business-Benutzeroberfläche verwenden.

- Benutzer müssen auf die Skype für Business Server-Front-End-Pool befinden.

- Sie benötigen einen Skype für Business Server Überwachungsdatenbank bereitgestellt und auf Ihrer Skype für Business Server-Pools verknüpft.

- Die Bereitstellung des Anrufqualitäts-Dashboards (CQD) wird empfohlen.

## <a name="configure-rate-my-call"></a>„Meinen Anruf bewerten“ konfigurieren

Das Feature Rate Meine aufrufen, ist standardmäßig in die Clientrichtlinie mit den folgenden Einstellungen aktiviert:

- Bewerten von Meine Prozentsatz der Anzeige - 10 %

- Bewerten von Meine Anruf zulassen benutzerdefinierte Benutzerfeedback - deaktiviert

Wenn Sie benutzerdefinierte Feedback möchten, müssen separat aktivieren, aber es ist keine Aktion erforderlich, um die Basis Feature jedoch aktivieren. Die folgenden Windows PowerShell-Cmdlets ist ein Beispiel des benutzerdefinierten Endbenutzer Feedback aktivieren und das Intervall von 10 % auf 80 % ändern.

```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>Zugriff auf die Daten von „Meinen Anruf bewerten“

Daten von Benutzern werden in zwei Tabellen in der Überwachungsdatenbank erfasst.

 **[QoeMetrics]. [Dbo]. [CallQualityFeedbackToken]** -Die folgende Tabelle enthält die Ergebnisse der token Abruf durch Endbenutzer.

 **[QoeMetrics]. [Dbo]. [CallQualityFeedbackTokenDef]** -Die folgende Tabelle enthält Definitionen für token.

Token-Definitionen sind folgendermaßen codiert:

|||
|:-----|:-----|
|1  <br/> |DistortedSpeech  <br/> |
|2  <br/> | ElectronicFeedback <br/> |
|3  <br/> | BackgroundNoise <br/> |
|4  <br/> |MuffledSpeech  <br/> |
|5  <br/> |Echo  <br/> |
|21  <br/> | FrozenVideo <br/> |
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

 **[QoeMetrics]. [Dbo]. [CallQualityFeedback]** Die folgende Tabelle enthält Abrufergebnisse aus "Stern" Stimmabgabe und Customer Feedback aktiviert.

Daten von Tabellen mithilfe von aufgerufen werden können ein **auswählen \* aus [Table.Name]** Abfrage oder mithilfe von Microsoft SQL Server Management Studio.

Die folgenden SQL-Abfragen können verwendet werden:

 **Audio**

```
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

```
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

## <a name="updating-token-definitions"></a>Aktualisieren von Token Definitionen

Die neuesten Skype für Business Clients melden neues Problem Token IDs (\> 100), die möglicherweise nicht in Ihrer [QoeMetrics] vorhanden sein. [Dbo]. [CallQualityFeedbackTokenDef]-Tabelle. So aktualisieren Sie die Datenbanktabelle mit den neuesten token Definitionen, die unter SQL-Befehl kann auf die Überwachungsdatenbank mit Microsoft SQL Server Management Studio ausgeführt werden. Mit diesem Befehl werden alle Einträge in der [QoeMetrics] ersetzt. [Dbo]. [CallQualityFeedbackTokenDef]-Tabelle.

```
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


